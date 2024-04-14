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
ssh 不檢查指紋直接過去
ssh -o StrictHostKeyChecking=no <ip>

sftp = /usr/libexec/openssh/sftp-server


PermitRootLogin yes //允許使用root登入
PubkeyAuthentication yes  //表示支持公鑰認證
AuthorizedKeyFile .shh/authores_keys  //公要基於認證方式開始起後對放存放位址
PasswordAuthentication yes //支持密碼認證

/etc/ssh/sshd_config
改22 -->32222

setenforce 0
systemctl stop firewalld
syytemctl restart sshd

ssh -p 32222 -o StrictHostKeyChecking=no <ip>

PermitRootLogin no //不允許使用root登入





```
pstree 父子進程的關西
