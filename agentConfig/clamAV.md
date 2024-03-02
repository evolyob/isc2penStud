```php
dnf install epel-release
dnf install clamav clamav-update clamd

vim /etc/freshclam.conf

7
# Comment or remove the line below.
#Example        這個要#掉

#DatabaseMirror clamdb.****.com.tw
#DatabaseMirror 172.16.***.***
DatabaseMirror updateserver.***.com.tw
P
116
PrivateMirror https://updateserver.***.com.tw



systemctl start clamav-freshclam
systemctl stop clamav-freshclam
systemctl status clamav-freshclam
systemctl restart clamav-freshclam

因為是走443，所以指定要改成domain，不能用IP，hosts也要指定

vim /etc/hosts
P
172.16.***.**  updateserver.***.com.tw


freshclam -v
```
```php
vim freshclam-0200.sh

#!/bin/bash

HOST=`hostname`
DATE=`date +%Y%m%d`

#echo $HOST"-"$DATE

freshclam >/var/log/Clamscan/freshclam-$HOST-$DATE.
```
```php
vim clamscan-0300.sh

#!/bin/bash

HOST=`hostname`
DATE=`date +%Y%m%d`

#echo $HOST"-"$DATE

clamscan -r /var/vhosts/* --exclude='\.(jpg|jpeg|png|gif|log)$' >/var/log/Clamscan/clamscan-$HOST-$DATE-vhost.log
clamscan -r /etc/* --exclude='\.(jpg|jpeg|png|gif|log)$' >/var/log/Clamscan/clamscan-$HOST-$DATE-etc.log

```

```php
設定排程

vim /etc/crontab

10 2 * * * root /Crontab/freshclam-0200.sh         #更新病毒碼

10 3 * * * root /Crontab/clamscan-0300.sh 2>&1     #系統掃毒
```
```php

改crontab內.sh的檔案權限
chmod 755 freshclam-0200.sh

log區 新增Clamscan資料夾
cd /var/log
mkdir Clamscan
```









