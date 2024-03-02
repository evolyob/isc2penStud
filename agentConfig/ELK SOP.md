```php
yum -y install telnet vim net-tools
yum -y update
#rockylinux 不支援 sha1 signed package，暫時開啟信任
update-crypto-policies --set DEFAULT:SHA1
#關閉 sha1-signed package 信任
update-crypto-policies --set DEFAULT

#Install opensearch
sudo curl -SL https://artifacts.opensearch.org/releases/bundle/opensearch/2.x/opensearch-2.x.repo -o /etc/yum.repos.d/opensearch-2.x.repo
yum clean all
yum repolist
yum -y list opensearch --showduplicates
yum -y install 'opensearch-2.8.0'
systemctl start opensearch
systemctl enable opensearch
systemctl status opensearch

向連接埠 9200 發送請求
curl -X GET https://localhost:9200 -u 'admin:admin' --insecure
查詢外掛端點
curl -X GET https://localhost:9200/_cat/plugins?v -u 'admin:admin' --insecure
```
```php
以下是opensearch single-node設定參數
vim /etc/opensearch/opensearch.yml
# Bind OpenSearch to the correct network interface. Use 0.0.0.0
# to include all available interfaces or specify an IP address
# assigned to a specific interface.
network.host: 0.0.0.0

# Unless you have already configured a cluster, you should set
# discovery.type to single-node, or the bootstrap checks will
# fail when you try to start the service.
discovery.type: single-node

# If you previously disabled the Security plugin in opensearch.yml,
# be sure to re-enable it. Otherwise you can skip this setting.
plugins.security.disabled: false

#如果主機有 8 GB 內存，那麼您可能需要將初始堆大小和最大堆大小設為 4 GB
vim /etc/opensearch/jvm.options
-Xms4g
-Xmx4g

systemctl restart opensearch
```
```php
#Install opensearch-dashboards
sudo curl -SL https://artifacts.opensearch.org/releases/bundle/opensearch-dashboards/2.x/opensearch-dashboards-2.x.repo -o /etc/yum.repos.d/opensearch-dashboards-2.x.repo
yum repolist
yum clean all
yum -y list opensearch-dashboards --showduplicates
yum -y install 'opensearch-dashboards-2.8.0'
systemctl start opensearch-dashboards
systemctl enable opensearch-dashboards
systemctl status opensearch-dashboards

vim /etc/opensearch-dashboards/opensearch_dashboards.yml
server.host: "0.0.0.0"

產出密碼
sudo cd /usr/share/opensearch/plugins/opensearch-security/tools
sudo OPENSEARCH_JAVA_HOME=/usr/share/opensearch/jdk ./hash.sh


產出設定檔
mkdir current-config
OPENSEARCH_JAVA_HOME=/usr/share/opensearch/jdk /usr/share/opensearch/plugins/opensearch-security/tools/securityadmin.sh \
  -cacert /etc/opensearch/root-ca.pem \
  -cert /etc/opensearch/kirk.pem \
  -key /etc/opensearch/kirk-key.pem \
  -r  \
  -cd current-config

修改使用者設定檔
cd current-config
vim internal_users_2023-Nov-17_10-29-07.yml

上傳使用者設定檔
OPENSEARCH_JAVA_HOME=/usr/share/opensearch/jdk /usr/share/opensearch/plugins/opensearch-security/tools/securityadmin.sh \
  -t internalusers \
  -f current-config/internal_users_2023-Nov-17_10-29-07.yml \
  -cacert /etc/opensearch/root-ca.pem \
  -cert /etc/opensearch/kirk.pem \
  -key /etc/opensearch/kirk-key.pem

測試admin密碼
curl --insecure -u admin:admin -X GET "https://localhost:9200/_plugins/_security/api/account"
```
```php
#使用WEB介面
#Dev Tools
#建立預設 index 樣板
PUT _index_template/laravel_log
{
	"index_patterns": [
		"laravel-logs-*"
	],
	"template": {
		"aliases": {
			"my_logs": {}
	},
	"settings": {
		"number_of_shards": 1,
		"number_of_replicas": 1
	},
	"mappings": {
		"properties": {
			"i.time": {
				"type": "date_nanos",
				"format": "yyyy-MM-dd HH:mm:ss.SSSSSS"
				}
			}
		}
	}
}

#使用WEB介面
#Dev Tools
# 建立帳號 logstash
PUT _plugins/_security/api/roles/logstash_write
{
	"index_permissions": [{
		"index_patterns": [
			"laravel-logs-*"
	],
	"dls": "",
	"fls": [],
	"masked_fields": [],
	"allowed_actions": [
		"crud", "create_index", "read",
		"indices:data/write/index*",
		"indices:data/write/update*",
		"indices:admin/mapping/put",
		"indices:data/write/bulk*",
		"indices:data/write/bulk",
		"indices:data/write/index"
		]
	}]
}
PUT _plugins/_security/api/internalusers/logstash_internal
{
	"password": "ZV7dKBbkdRg6FgREkxFXfMBFtkPnKMZH",
	"backend_roles": ["logstash_write", "logstash", "admin"]
}

#Install logstash
vim /etc/yum.repos.d/logstash.repo
[logstash-8.x]
name=Elastic repository for 8.x packages
baseurl=https://artifacts.elastic.co/packages/8.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
```
```php
yum -y install logstash
cd /usr/share/logstash/
bin/logstash-plugin install logstash-output-opensearch
vim /etc/logstash/conf.d/default.conf
input {
	redis {
		data_type => "list"
		key => "filebeat"
		host => "localhost"
		port => 6379
		password => "setpassword"
		threads => 5
	}
}

filter {
	grok {
		match => {
			"message" => "%{GREEDYDATA}"
		}
	}
	json {
		source => "message"
		target => "i"
	}
	if [i][context] {
		mutate {
			add_field => {
				"load" => "%{[i][context]}"
			}
		}
}

# sql
if [i][context][sql][span] and [i][context][sql][tag] {
	mutate {
		add_field => { "[sql][tag]" => "%{[i][context][sql][tag]}" }
		add_field => { "[sql][span]" => "%{[i][context][sql][span]}" }
	}
	mutate {
		convert => {"[sql][span]" => "float" }
	}
}

# controller
if [i][context][con][span] and [i][context][con][code]{
	mutate {
		add_field => { "[con][span]" => "%{[i][context][con][span]}" }
		add_field => { "[con][code]" => "%{[i][context][con][code]}" }
	}
	mutate {
		convert => {"[con][span]" => "float" }
	}
}

# job
## End
if [i][context][job][span] and [i][context][job][name] {
	mutate {
		add_field => { "[job][span]" => "%{[i][context][job][span]}" }
		add_field => { "[job][name]" => "%{[i][context][job][name]}" }
		add_field => { "[job][queue]" => "%{[i][context][job][queue]}" }
	}
	mutate {
		convert => {"[job][span]" => "float" }
	}

## Start
} else if [i][context][job][delay] and [i][context][job][name] {
	mutate {
		add_field => { "[job][delay]" => "%{[i][context][job][delay]}" }
		add_field => { "[job][name]" => "%{[i][context][job][name]}" }
		add_field => { "[job][queue]" => "%{[i][context][job][queue]}" }
	}
	mutate {
		convert => {"[job][delay]" => "float" }
	}

## Pub
} else if [i][context][job][name] and [i][context][job][queue]{
	mutate {
		add_field => { "[job][name]" => "%{[i][context][job][name]}" }
		add_field => { "[job][queue]" => "%{[i][context][job][queue]}" }
	}
}

# command
if [i][context][cmd][start] {
	mutate {
		add_field => { "[cmd][state]" => "%{[i][context][cmd][state]}" }
		add_field => { "[cmd][name]" => "%{[i][context][cmd][name]}" }
		add_field => { "[cmd][start]" => "%{[i][context][cmd][start]}" }
	}
} else if [i][context][cmd][end] {
	mutate {
		add_field => { "[cmd][state]" => "%{[i][context][cmd][state]}" }
		add_field => { "[cmd][name]" => "%{[i][context][cmd][name]}" }
		add_field => { "[cmd][end]" => "%{[i][context][cmd][end]}" }
		add_field => { "[cmd][span]" => "%{[i][context][cmd][span]}" }
	}
	mutate {
		convert => {"[cmd][span]" => "float" }
	}
}

# curl
if [i][context][curl][url] and [i][context][curl][method] and [i][context][curl][code] and [i][context][curl][span]{
	mutate {
		add_field => { "[curl][url]" => "%{[i][context][curl][url]}" }
		add_field => { "[curl][method]" => "%{[i][context][curl][method]}" }
		add_field => { "[curl][code]" => "%{[i][context][curl][code]}" }
		add_field => { "[curl][span]" => "%{[i][context][curl][span]}" }
	}
	mutate {
		convert => {"[curl][span]" => "float" }
	}
} else if [i][context][curl][url] and [i][context][curl][method]{
	mutate {
		add_field => { "[curl][url]" => "%{[i][context][curl][url]}" }
		add_field => { "[curl][method]" => "%{[i][context][curl][method]}" }
	}
}

# 由於context部分log會有很深的json結構，故拋棄
ruby {
	code => "
	i = event.get('i')
	i['context'] = {}
	event.set('i', i)
"
}

# Remove empty lines
if [message] =~ /^\s*$/ or "_jsonparsefailure" in [tags] {
	drop {}
}
	mutate {
		remove_field => [
			"[event]",
			"[agent]",
			"[ecs]",
			"[input]",
			"[log][offset]",
			"[host][hostname]",
			"[host][name]",
			"[host][id]",
			"[host][mac]",
			"[host][architecture]",
			"[host][containerized]",
			"[host][os]",
			"[message]"
		]
	}
}

output {
	opensearch {
		hosts => ["https://localhost:9200"]
		auth_type => {
			type => 'basic'
			user => 'logstash_internal'
			password => 'ZV7dKBbkdRg6FgREkxFXfMBFtkPnKMZH'
		}
		ssl => true
		ssl_certificate_verification => true
		cacert => "/etc/opensearch/root-ca.pem"
		index => "laravel-logs-%{+YYYY.MM.dd}"
	}
}


#Install redis
yum -y install redis
vim /etc/redis/redis.conf
bind 0.0.0.0
protected-mode yes
supervised systemd
requirepass setpassword

#上傳Log主機 Install filebeat
vim /etc/yum.repos.d/filebeats.repo
[elastic-8.x]
name=Elastic repository for 8.x packages
baseurl=https://artifacts.elastic.co/packages/8.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md

yum -y install filebeat
vim /etc/filebeat/filebeat.yml
filebeat.inputs:
  - type: filestream
    id: laravel-log-id
    enabled: true
    ignore_older: 5m
    paths:
      - /var/log/*/*.log

output.redis:
  hosts: ["192.168.31.151:6379"]
  password: "setpassword"
  key: "filebeat"
  db: 0
  timeout: 5
  
#log等級改一下，OSSCE比較不會一直跳告警
logging.level: warning

```

```php

服務啟動
systemctl start opensearch
systemctl start opensearch-dashboards
systemctl start logstash
systemctl start redis
systemctl start filebeat

開機啟動
systemctl enable opensearch
systemctl enable opensearch-dashboards
systemctl enable logstash
systemctl enable redis
systemctl enable filebeat

服務狀態
systemctl status opensearch
systemctl status opensearch-dashboards
systemctl status logstash
systemctl status redis
systemctl status filebeat

```
```php
#opensearch cluster(若要設定cluster建議以下參數設定好再啟動opensearch服務)
vim /etc/opensearch/opensearch.yml

node1
cluster.name: epay-opensearch
node.name: opensearch-master-node1
network.host: 0.0.0.0
cluster.initial_master_nodes: ["192.168.31.151"]
node.roles: [ cluster_manager, data, ingest ]
network.publish_host: 192.168.31.151
discovery.seed_hosts: ["192.168.31.151", "192.168.31.152", "192.168.31.153"]

node2
cluster.name: epay-opensearch
node.name: opensearch-data-node2
node.roles: [ data, ingest ]
network.host: 0.0.0.0
network.publish_host: 192.168.31.152
discovery.seed_hosts: ["192.168.31.151", "192.168.31.152", "192.168.31.153"]

node3
cluster.name: epay-opensearch
node.name: opensearch-data-node3
node.roles: [ data, ingest ]
network.host: 0.0.0.0
network.publish_host: 192.168.31.153
discovery.seed_hosts: ["192.168.31.151", "192.168.31.152", "192.168.31.153"]
```
```php
#檢查cluster指令
curl -XGET https://192.168.31.151:9200/_cat/nodes?v -u 'admin:admin' --insecure

#使用WEB介面檢查cluster
#Dev Tools
GET _cat/nodes?v

#使用WEB介面檢查account
GET _plugins/_security/api/account
```


