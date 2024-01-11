ch.12   安全通信與網路攻擊
```
身份認證協議
-PPP point to point protocol 鏈路wan傳輸IP流量 數據層 ip管理、同步通信管理、
>標準化封裝、多路復用、連路配置、質量測試、功能協商、自動連接、全雙工、身份認證
>取代串行線路網間協議SLIP 不提供身份認證、沒有偵錯、需手動建立移除鏈路
PAP|密碼身份驗證協議|passwd authentication protocol
>明文傳輸帳號密碼簡單傳輸途徑、把登入證書從客戶端傳遞到身份認證服務器
CHAP|徵詢握手身份驗證協議|challenge handshake md5 不安全 被MS-CHAPv2更新算法 取代
>以建立會話期間會週期重覆驗證遠程系統、確保用戶身份持續有效
EAP|可擴產身份認證協議|extensible   支持可指定身份認證解決方案 MFA 安全通道、加密
LEAP|lightweight| 輕量級cisco WPA TKIP的替代方案，802.11i/WPA被批准之前，解決TKIP缺陷、不使用
PEAP|protected| 受保護的，在TLS隧道封裝EAP安全性、支持交叉驗證
EAP-SIM|subscriber idenntity| sim卡識別 GSM移動設備永，該卡用戶的帳戶服務級別相關
EAP-FAST|flexible authentication via secure tunneling| cisco取代LEAP、由於WAP2發展
EAP-MD5|MD5| 最早EAP的方法，但已棄用
EAP-POTP|protected OTP| MFA 令牌 、用於單向或交叉身份認證．
EAP-TLS|TLS|開放的IETF,保護身份驗證的流量TLS協議、雙方都具有數字證書的交叉身份認證
EAP-TTLS|tunneled TLS|EAP-TLS的擴展、進行端點驗證前創建類似VPN隧道，確保不用明文方式傳輸．
-
-
-
-
-
-

-
-
-
-
-
-
-
```

```

-
-

-

-
-
-
-

-
-
-
-

-
-
```

```
-
-
-
-
-
-
-
-
-
-
-

-
-
-
-
```
