identify
```
1.
2.
3.
4.
5.
6.
7.
8.
9.

10.
11.
12.
13.
14.
15.
16.
17.
18.
19.



```
protect
```
AC
1. 唯一帳號密碼，離職即禁用
2. 系統登入前法規聲明通知
3. 可攜式設備政策、身份識別、使用範圍的最小權限
4. 管理功能僅特權帳號使用
5. 登入失敗嚐試次數
// AD GPO限制, 底層設定
6. 閒置Session locks, 條件終止或Session timeout
// keepalive_time = 1800
7. 可使用角色、登入前授權、允許設備需經授權、行動設備批准、監控、紀錄
// intranet,wifi,intrasystem,VPN(ipsec),extranet
8. 職權分離、開發測試隔離、日誌記錄非特權使用管理狀況
9. wireless access 身份驗證、WAP2等級(AES)以上、
// mac綁定

10. 敏感資料專區、需身份驗證、定期檢查更新存取清單批准、監控、紀錄
// ad group, sudoers , time_status
11. FW,Proxy for IPDS UTM

sys communication
1. 禁止設備遠端啟用鏡頭、麥克風
// Microsoft Defender  SOFTWARE\Policies\Microsoft\AppHVSI
2. SSH 協定管理網路設備
// disable weak cipher , enable ssh2
3. 採用資安架構設計、軟體安全開發技術和系統安全工程原理
// Config hardening, develop Document, ver. chk 
4. 共享系統資源進行未經授權傳輸,驗證設置正確。
5. 定期查看FW policy chk確保沒有授權的更改
6. 禁止分割通道
7. 採加密方式傳輸受管制的資料TLS ,PKI policy
8. Mobile Code必須是受信任的來源，並且進行數位簽章認證
9. VoIP使用限制和實施指南

10. MFA,TLS,VPN configration,Session的清除機制
11. 保護靜態資料的機密性
//  encryt key、簽核流程、單獨安全區域(異地異機)
12. 定義高價值網路架構跟伺服器系統、隔離措施
// vlan, DMZ, HA, 單獨通道管理
13. FW, SW, WebProxy 信任邊界
// 進出封包側錄保存三個月、未知封包阻擋
14.實施域名系統（DNS）過濾服務
// DoH, FW設定, Web Proxy

系統和資訊完整性
1. 禁止在公開網站上發布受管制資料的政策
2. 專人執行資安情資收集IoC、公開TTP威脅情資
3. 新版本發佈時，自動更新到最新版本更新惡意程式保護機制
4. 部署端點偵測和回應方案 (EDR)到組織端點設備
5. 垃圾郵件出入站防護機制 SPAM過濾規則定期查看
6. 電子郵件偽造保護 DKIM、SPF 和 DMARC





```
detect
```
1.
2.
3.
4.
5.
6.
7.
8.
9.




```
respond
```
1.
2.
3.
4.
5.
6.
7.
8.
9.


```
recover
```
1.
2.
3.
4.
5.
6.
7.
8.
9.



```
