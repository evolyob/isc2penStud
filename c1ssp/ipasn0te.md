```
機密性：專用帳號密碼登入、googleHacking、
密碼學不提供可用性

RTO是計劃中的期望值，而WRT是實際發生事件時的實際值。


RAID0：至少需要兩顆，不可壞硬碟，空間利用率為2N，實務上不使用。
RAID1：至少需要兩顆，最多可壞一硬碟，空間利用率為N/2。
RAID5：至少需要三顆，最多可壞1顆硬碟，空間利用率為N-1。
RAID6：至少需要四顆，最多可壞兩顆硬碟，空間利用率為N-2。
RAID10：至少四顆，以兩對鏡像每一對鏡像中最多可壞一顆硬碟，空間利用率為N/2。


```
|Telnet|TCP 23||SFTP/SSH|TCP22|
|:--|:--|:--|:--|:--|
|FTP|TCP 21連線控制|TCP20資料傳輸|FTPs|990|
|DNS|TransferTCP53|UDP 53|||
|HTTP|TCP 80||HTTPS|TCP 443|
|SMTP|TCP25||SMTPS|587|
|POP3|TCP 110 ||POP3S |995|
|IMAP|TCP 143 ||IMAPS |993|

|微軟網路芳鄰|UDP 137、138|TCP139、445|||
|:--|:--|:--|:--|:--|
|SNMP|UDP 161 請求|UDP 162接收|||
|DHCP|服務器端67|客戶端68|NTP|UDP 123|
|SYSLOG：|UDP 514||NFS|TCP 2049|
|SQLServer||TCP 1433|||
|PPTP||TCP 1723|||
|RADIUS|UDP 1812 1813||LDAP|TCP389|
|RDP||TCP 3389|||
```
• /etc/shadow：儲存使用者密碼的Hash值。
• /etc/passwd：用戶帳號的基本訊息，但因為必須對所有人可讀，
所以將密碼的Hash值放到只有管理員可以讀取的/etc/shadow檔案。
• /var/log/secure：檔案用於記錄與安全相關的所有事件，包含遠端連線/用戶登入紀錄。
• /var/log/wtmp：使用者的登入歷史紀錄
• ./bash_history：使用者曾經下過的指令。
• ~/.ssh/known_hosts：連線至對方主機後，會記錄對方主機的指紋。
這樣做是為了在未來的連線中能夠識別和驗證該主機。以防範中間人攻擊。

• site: - 指定要在特定網站或域中搜索的資訊。例如，site:example.com 將只顯示來自"example.com" 的結果。
• filetype: - 搜索特定文件類型。例如，filetype:pdf 將找出所有的 PDF 文件。
• intitle: - 搜索在網頁標題中出現的文字。例如，intitle:"indexof" 可以用來尋找開放目錄。
• inurl: - 搜索 URL 中包含特定文字的頁面。例如，inurl:admin 將會找出 URL 中含有"admin" 的頁面。
• intext: - 搜索網頁正文中出現的特定文字。例如，intext:confidential 可以用來查找包含"confidential" 文字的頁面。

• Smurf Attack：返回地址偽裝成目標機器的IP地址，從而使得回應的Echo回應封包洪水般地返回到目標機器上
• Land Attack：一種拒絕服務（DoS）封包的標頭中將目的地IP地址和來源IP地址設置為相同的值，從而進入一種無限循環。
• Fraggle Attack：UDP協定發送大量的封包至網路的廣播地址，並將封包的來源地址偽造為攻擊目標的IP地址。
```

