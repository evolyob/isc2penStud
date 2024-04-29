```
web server
yum -y install httpd
修改設定文件

cd /var/www/html/
echo test >> index.html
systemctl restart httpd
systemctl enable httpd

curl localhost
```
```
dhcp  67 port
yum -y install dhcp-server
rpm -ql dhcp-server | grep example  //設置文件範本
cp /usr/share/doc/dhcp-server/dhcp.conf.examlp /etc/dhcp/dhcpd.conf
//複製範本
nmcli device status
ip a a 1.1.1.1/24 dev ens224
ip a show ens224

subnet 1.1.1.0 netmask 255.255.255.0 {
  range 1.1.1.100 1.1.1.200;
  option domain-name-servers 114.114.114.114;
  option routers 1.1.1.1;
  default-lease-time 600;
  max-lease-time 7200;
}

systemctl restart dhcpd
netstat -tunlp


客戶端設定
nmcli device status
nmcil con add con-name dhcp ifname ens160 type ethernet
nmcil con up dhcp
ip route show
nmcli con show
cat /var/lib/dhcpd/dhcpd.leases //查看已取號的地址

```
```
pstree 父子進程的關西
kickstart
自動安裝操作系統
anaconda-ks.cfg
yum -y install system-config-kickstart








```
