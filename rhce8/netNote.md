```
nmcli device status 查看網卡參數
nmcli device disconnet <> 關閉連線
通常私有雲服務器的網卡一班有4-8塊：管理網路*2 traffic網路*2 儲存網卡*2

添加網卡
nmcil con add con-name ens2266 type ethernet ifname ens226 
獲取只回從dhcp取IP

nmcil con add con-name ens226 type ethernet ifname ens226 ipv4.addresses <ip>/24 ipv4.gateway <ip> ipv4.dns <ip> ipv4.metod manual
nmcli con up ens226

修改網卡配置文件， 加載緩存後再重啟
nmcli con modify ens226


```
