```
戰略制定好後，高階主管透過⽂件化發佈管理意圖(Policy 政策)，請人執⾏，讓執⾏者有依據與⾜夠授權。先有戰略才會有政策

第三方審計SSAE 18(SOC)
1. SOC 1，會計師進⾏財務系統資訊安全稽核
2. SOC 2，美國版的ISO27001資訊安全稽核
3. SOC 3：SOC2-Type2精簡（給外面客戶看）
 Type 1：只書面審查控制措施的設計適切性(Suitability of the Design)
 Type 2：不只看設計，還要看設計運作 (至少半年以上)的有效性 (Effectiveness ofOperations)

 Due Care (應盡關⼼)
1. 事中矯正注意(Do Correct)
2. 跟個人相關，應當的關注
 Due Diligence (盡職審查)
1. 事前偵測防範(Do Detect)
2. 跟企業、職掌相關的事前作為
3. 合約審查



1. 資料治理：
企業⾃有資料、個資（定義、⾓⾊、處理原則、去識別化) 、資料三態
及生命週期(資料清洗與殘留)
2-資產安全：重點是在講整個生命週期中收集、處理和保護資料
3-根據資料對組織的價值進⾏分類，所有採取的安全措施都取決於分類

 patent (專利)
保護發明者的知識產權，專利法規定了 20 年的獨占期，從向專利商標局提交專利申請之⽇起算。
 Copyright (版權 )
版權法保護原創作品的創作者，防止創作者的作品遭未經授權的複製被保護時間，第一作者去世
後的70年
 Trademark (商標)
主要目的用來識別主要企業或產品 Ex. M 麥當勞(保護10年，可以一直申請/續用)
 Trade secret (營業秘密)
保護極其重要，不讓人看的。Ex. 可⼝可樂的配方 (保護期間可以最久/經濟間諜法案 EEA)
 DRM (Digital rights management ) 數位版權管理
資料不小⼼洩漏，可以追到當事人的方法

1. Verification(驗證)和Validation(確認) (V&V) 是⼯程過程。ISO 15288 中引入的技術流程
2. Certification(中立方確認符合規定)和Accreditation(主管機關 正式認可) (C&A) 是 FIPS 200 中定義的正式保證流程。
3. C&A 的概念現在在 NIST RMF 中稱為 A&A (Assessment & Authorization) 評鑑和授權
4. 每個系統都應該經過 V&V，但並不是每個組織都需要 C&A

微隔離(Microsegmentation)是將內部網路劃分為多個⼦區域
多重要素身份驗證（MFA）、身份與存取管理（IAM）、特權存取管理（PAM）及網路分區隔離，以實現全⾯的縱深防禦。
此外，零信任也倚重於 最⼩特權原則等治理政策

以OSI模型來看，SDN處理模型中2~3層，NFV處理的是4~7層、SDP處理模型第3層

雲端七大安全威脅
不安全介面與應用程式介面、惡意內部員工、共享環境造成議題、資料遺失或外洩、帳號或服務被竊取、其他未知風險、稽核和蒐證
邊緣計算在分佈式邊緣系統上進⾏處理
霧計算對分佈式傳感器收集的數據進⾏集中處理。


霧計算是雲計算的延伸。它是邊緣和雲之間的一層。當邊緣計算機向雲端發送⼤量數據時，
霧節點會接收數據並分析重要數據。然後霧節點將重要的數據傳輸到雲端進⾏存儲，刪除不
重要的數據或⾃⾏保存以供進一步分析。通過這種方式，霧計算在雲端節省了⼤量雲端空間，並且可以快速傳輸重要數據。

OCSP (The Online Certificate Status Protocol) 證書狀態協議：即時驗證效率更高，自動更新

1.下列何種破密情境最常見?
A.只有密文（Ciphertext-Only）。

2.下列何種破密情境可破解非對稱式加密的金鑰?
D.選擇密文（Chosen-Ciphertext）。

3.下列何種破密情境是掌握有限數量的明文與密文對照?
B.已知明文（Known-Plaintext）。

4.下列何種破密情境可動態將明文加密?
C.選擇明文（Chosen-Plaintext）。

5.下列何種破密情境主要是破解加密演算法?
C.選擇明文（Chosen-Plaintext）。

 訊息驗證碼(MAC)主要使用XOR計算與對稱式加密家族的DES加密演算法。
 數位簽章則使用雜湊(Hash)及公開⾦鑰密碼系統下的RSA加密演算法對雜湊值加密。

縱深防禦或深度防禦描述了通過應用多種機制構建的安全架構，以創建一系列屏障來防止、延遲或阻⽌對⼿的攻擊。
目的是在安全控制失敗或漏洞被利用的情況下提供冗餘，這可能涵蓋系統生命週期期間的人員、程序、技術和物理安全等方⾯。
```
```
+ DHCP discover 客戶端請求地址不知道服務端位置為用廣播發送請求，得知回應是服務端
+ DHCP offer 服務器收到discover報文後，尋找適合的IP位址相應期限跟配置(gw,DNS)給客戶端可以使用
+ DHCP request 客戶段收到offer選擇一個回應廣播request通告選擇的服務器
- 客戶端成功獲取ip位置，當期限過去1/2會發個DHCP request延長若沒收到DHCP ACK在發廣播報文延長

+ DHCP ACK 服務端收到request後，根據request MAC來查找相應期限紀錄，有就則發ACK通知可以使用
+ DHCP NAK 服務端收到request後，發現沒有相應期限紀錄或其他原因無法正常分配，則發NAK通知用戶無發分配IP
+ DHCP release 當用戶不需使用分配IP就會發給服務端 release報文，不需分配並服務端會釋放期限
+ DHCP decline 客戶端收到服務端DHCP ACK通過衝突檢測或其他不能使用則發 decline通知服務端IP不可用
+ DHCP inform  客戶端要更詳細配置，則發inform向服務端請求在用DHCP ACK回應

->> DHCP 餓死攻擊：發送大量請求申請IP位址，因無法辨識CHADDR字段合法性導致耗盡無法給正常主機分配
## DHCP snooping 客戶端和服務端建立虛擬防火牆．對request CHADDR進行檢查

->> 假冒DHCP服務端攻擊：無法區分哪個是DHCP服務端，分配錯誤IP參數導致無法訪問網路
## DHCP snooping 所有交換默認端口都是非信任端口，收到非信任端口交換機都直接丟棄不轉發

->> DHCP中間人攻擊：利用ARP機制機制應設關係學習戶項豹紋都要經過“中間人” 
## DHCP snoopin的交換器會偵聽，服務端和客戶端收集用戶MAC,CHADDR的IP地址、期限存放在綁定表
## 發現與綁定表不匹配就丟棄報文 
```
```
HUB 集線器：集線器是一種物理層設備，⼯作在OSI 實體層，讓連結的裝置在同一個網段⼯作。
Repeater 轉發器：轉發器的用途是連接不同的網段，轉發是將訊號重打一次
Switch 交換器：交換器的⼯作是建立網路，是整個網路運作的基礎，屬OSI第⼆層的產品 (MAC 位址表)
Bridge 橋接器：橋接器可連接多個網段(Segment)⽽形成一個網路(Network)
Router 路由器：路由器的目的是連接不同網路(Network)，路由器決定資料封包的傳輸路徑
Gateway 閘道器：應用閘道器是作協定轉換，屬於ISO OSI第七層(應用層)的設備

個⼈版身份驗證用Pre-Shared Key (PSK),
企業版用802.1X
802.1X是由IEEE制定的關於用戶接入網絡的認證標準，全稱是「基於埠的網絡接入控制」
⽀持通過⾝份驗證訪問IEEE 802 媒體，包括以太網、令牌環和 802.11 無線 LAN。
為想要連接到LAN或WLAN的裝置提供了一種認證機制
它定義了EAP (可擴展⾝份驗證協議)的封裝。

IP Sec 提供服務  訪問控制 (Access control)、完整性（數據完整性和真實性）、保密、防重放 (Anti-replay)
```
|7|應用層|53,80/443,22,23,3389|Application Poison攻擊,DNS cache poisoning,流氓 DHCP,DDoS|FTP services|
|:--|:--|:--|:--|:--|
|6|呈現層|ASCII,UTF8,BASE64,gzip,compress,HTTPS,AES|Path Traversal攻擊,DDoS|ANSI|
|5|會話層|PAP,RPC,NetBIOS|會話挾持>偷走Token|ANSI|
|4|傳輸層|TCP,UDP|SYN Flooding,聖誕樹攻擊,,Froggle|Firewall|
|3|網路層|IP,IGP,RIP(小型)、OSPF(中⼤型),ICMP|Teardrop,DDoS ,smurf,死亡之Ping,Fingerprinting|Router|
|2|資料鏈結層|MAC,LLC|ARP Attacks,MAC Spoofing|Switch ,Bridge|
|1|實體層|UTP,STP,fiber,cable|訊號衰減、干擾、竊聽、破壞 |HUB,Repeater|
```
TPM可用於實現廣泛的基於密碼學的安全保護機制。
存儲和處理硬體⽀持或作業系統實現的本地儲存設備加密系統的加密金鑰,硬體安全模塊（HSM）的一個⽰例。

Federated Identity (聯合身分) ：使用者在每個系統都有⾃⼰的帳號，透過聯盟的關係，使用盟主的帳號即可跨系統登入
Integrated Identity (整合身分)：一個使用者只有一個帳號 AD
Scripted Access (腳本存取) ：老系統，可寫程式幫忙登入

 OIDC 和 OAuth 2.0 的組合最適合互聯網和社交媒體
 SAML +X ACML更適合企業對企業或供應鏈集成。
OAuth是一種授權協議，⽽不是⾝份驗證協議

SAML安全：
1. SAML 沒有安全模式，需要時依靠TLS 和數字簽名來確保安全
2. TLS 提供消息機密性和完整性，可以防止竊聽。當與提供完整性和⾝份驗證的數字簽名配對時，偽造的斷⾔也可以被擊

OpenID Connect 指定了一個 RESTful HTTP API，使用 JSON 作為數據格式。
OIDC=OAuth 2.0 協議之上的一個簡單⾝份層，
想要快速建立身份平台，選擇 OIDC ⽽不是 SAML，無需三思。與需要重量級
XML 處理的 SAML 相比，實施基本的 OIDC 解決方案要簡單得多。
 有一個以 API 為中心的架構，有很多移動和單頁應用程序，使用 OIDC。它將保證更高效和可互操作的體驗。
 想要實施成熟的標準，已經存在很長時間的東⻄，然後選擇 SAML。它功能豐富，可以完成⼯作，⼗多年來一直是企業網絡的主要組成部分。
 OIDC 基於 OAuth 2.0在安全性上，它包含了許多記錄在案的威脅模型和安全注意事項。
加密 JSON 也比 XML 容易得多，這再次減少了實施錯誤的機會。


RBAC 技術允許您按⾓⾊授予訪問權限。
ABAC 技術讓您可以根據用戶特徵、對象特徵、操作類型等來確定訪問權限。
```
```
從 UBA/UEBA 監控中收集的資訊可用于改進人員安全政策、程式、培訓和相關的安全監督計畫。
UEBA 中的E是將分析擴展到包括發生的實體活動，這些活動不一定與用戶的特定操作直接相關或綁定，
但仍可能與漏洞、偵察、入侵、破壞或漏洞利用發生相關。

SPF (Sender Policy Framework) 寄件者政策框架：用來規範在選定的郵件發送服務器位址驗證IP 來源

DKIM (DomainKeys Identified Mail)，網域驗證郵件，用來防止郵件內容遭到竄改
DKIM 是一種電腦數位簽章，採用公鑰與私鑰這種加密驗證法進⾏，
會透過DNS 到發信者的網域查詢 DKIM 紀錄，如果公鑰與私鑰能配對成功，代表郵件確實為原始發信機所發出。

DMARC 是用來輔助 SPF 與 DKIM 的不⾜：驗證 domain
DMARC 是標準的電子郵件驗證方法，可以協助郵件管理員抵禦假冒攻擊，防止⾃家機構與網域成為駭客和其他攻擊者的假冒目標。
是一套以SPF及DKIM為基礎的電子郵件認證機制，可以檢測及防止偽冒⾝份、對付網路釣⿂或垃圾電郵。


DREAD (帶分數 排順位)
DREAD 特點是可以在確定潛在威脅後，訂立應對先後次序。
1. Damage－攻撃帶來的破壞力評估
2. Reproducibility－攻擊是否容易複製
3. Exploitability－衡量攻擊的籌備⼯作與成本
4. Affected Users－幾多用戶受影響
5. Discoverability－威脅是否容易探測

PASTA（Attack Simulation and Threat Analysis Process）
是模擬攻擊與威脅分析過程，目的是確保技術安全要求與業務目標保持一致。
1. Define Objectives（定義目標）
2. Define Technical Scope（定義技術範圍）
3. Application decomposition（應用程序分解）
4. Threat Analysis（威脅分析）
5. Vulnerability and Weakness Analysis（漏洞和弱點分析）
6. Attack Modeling（攻擊模型）
7. Risk and Impact Analysis（風險與影響分析）

OOP將物件作為程式基本單元，將程式和資料封裝於物件中，以提高軟體的重用性、靈活性和擴充功能性
OOP有三個特⾊：封裝、繼承、多形

1. Virus (病毒)：需要幫忙、需要完整性與附件、需要使用者執⾏->Virus Jump 病毒都附加在可執⾏的檔案上
2. Trojans (木馬)： Trojans (不須幫忙、完整程式碼、⾃我複製、利用弱點-> Traffic
3. Worms (蠕蟲)：不須幫忙、完整程式碼、指定目標、隱藏-> Dropper

```
STRIDE
|1. |Spoofing|－冒充⾝份的威脅|認證|偽造|
|:--|:--|:--|:--|:--|
|2.|Tampering|－篡改數據的威脅|完整|竄改|
|3.|Repudiation|－被忽略的威脅|稽核|抵賴|
|4.|Information Disclosure|－資訊外洩威脅|保密|洩漏|
|5.|Denial of Service|－不能連線，以⾄不能提供服務|可用|阻斷|
|6. |Elevation of Privileges|因程式錯誤、設計缺陷、系統設定|授權|提權|


