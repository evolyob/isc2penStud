```
nmcli device status 查看網卡參數
nmcli device disconnet <> 關閉連線
通常私有雲服務器的網卡一班有4-8塊：管理網路*2 traffic網路*2 儲存網卡*2

添加網卡
nmcil con add con-name ens2266 type ethernet ifname ens226 
獲取只回從dhcp取IP

nmcil con add con-name ens226 type ethernet ifname ens226 ipv4.addresses <ip>/24 ipv4.gateway <ip> ipv4.dns <ip> ipv4.metod manual
nmcli con up ens226
ip a show ens226  // 查看內容

修改網卡配置文件， 加載緩存後再重啟
nmcli con modify ens226
nmcli con show

netstat  用root操作
netstat -tunlp
查看最多連練數的ip
netstat -ntu | grep :<port> | awk '{print $5}' | cut -d : -f1 | awk '{++ip[$1]} END {for(i in ip) print ip[i],"\t" ,1}' | sort -nr

tcp 各種狀態列表
netstat -nt | grep -e 127.0.0.1 -e 0.0.0.0 -e ::: -v | awk '/^tcp/ {++state[$NF]} END {for(i in state) print i, "\t" ,state[i]}'

ss -t -a
```

```
iptable告訴net_filter規則交互或丟棄
加22port 
iptable -A  INPUT -s 192.168.0.0/24 -p tcp --dport 22 -j ACCEPT

```
```
iptable -L -t nat
Chain PREROUTING(policy ACCEPT)
target        port opt source       destination
DNAT         tcp   ---  0.0.0.0/    0.0.0.0/0        tcp dpt:5000  192.168.0.1:5000
# 任何人訪問都會導向192.168.0.1:5000

Chain INPUT(policy ACCEPT)
target        port opt source       destination
# 流量輸入
Chain OUTPUT(policy ACCEPT)
target        port opt source       destination
# 流量輸出
Chain FORWARD(policy ACCEPT)
target        port opt source       destination
# 流量轉發

Chain POSTROUTING(policy ACCEPT)
target        port opt source       destination
MASQUERADE    all --  10.10.0.0/24   0.0.0.0/0                //ssh to wan
SNAT          all --  192.168.0.0/24 0.0.0.0/0 to:192.168.0.1 //storage to wan
# 能上網


```
pstree 父子進程的關西
