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

IEEE802.1X 基於端口訪問控制，定義封裝EAP的使用，支持LAN連接廣泛身分認證，認證前無法通信
>企業無線客戶端專用遠程身分認證系統或AAA(RADIUS,TACACS+)充當身分認證代理
>是一種認證技術不是無線技術，用於WAP、FW、SW、Router、proxy、VPN gateway、NAS, RAS(遠程訪問服務器)
>容易被中間人MITM和劫持攻擊，鎖已建立連接不是所有的802.1X,EAP是安全，需要期間再認證和會話加密

端口安全  未使用不需要的插孔或port應斷開線路、監控何時連接或斷開或被無效設備替換、需被身分認證(NAC)
服務質量   通信效率和性能監督和管理，可調整、限制、重塑網絡流量，備用傳輸路徑、移除沒關鍵數據傳輸。。 可用性

語音通信安全   PSTN公共交換電話網、專用交換機PBX、移動蜂窩服務、VoIP
-PSTN公共交換電話網 易受攔截、竊聽、破解攻擊 應使用加密通信
-VoIP 網路電話支持再TCP/IP 提供安全實時傳輸協議(SRTP)的加密
>使用相同的ISP可能不提供任何形式加密，只兼容設備到供應商之間的加密、
>
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
