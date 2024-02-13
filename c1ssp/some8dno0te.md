

```
風險處置或任何解決方案，都要考慮成本/效益並且注意變更管理。 
以CISO主管的高度，考量組織、業務、技術的整體方向，心存業務思維知道如何 善用技術來解決業務問題，以創造價值。
將題目所提及的條件或限制納入思考，選擇資安控制措施，妥適的解決問題。
具體的技術解決方案通常只能解決特定或個問題，

範圍和計畫 ：組織分析、選擇團隊、資源人關需求人力、軟應體、測試、法律和法規要求
BIA：資源優先級、識別風險、可能性評估、影響評估
實現批准：高層批准計劃、計畫實現、教育訓練、文件化
恢復團隊：負責啟動和運行備用設備、首先回覆最關鍵服務、恢復到原始或永久性設施

風險胃納(Risk Appetite):經營高層可以接受的風險程度(或水平)
固有風險(Inherent Risk):未經處置的風險
聯級風險(Cascading Risk):風險併發的其他風險
殘餘風險(Residual Risk):風險處置後剩餘的風險
衍生/次級風險(Secondary Risk):風險處置後產生的其他風險

NIST RMF(Risk Management Framework):
0. 準備(Prepare):如果RMF未識別到的風險要在此階段自行識別
1. 分類系統(Categorize System):盤點資料有多重要(看CIA)(高、中、低)
2. 選擇控制(Select Controls):等級選擇
a. 定範圍(Scoping):適用性聲明
b. 量身訂作(Tailoring):定範圍後再根據系統及組織個別的安全需要初步的控制措施
3. 實施控制(Implement Controls):執行安全控制措施
4. 評鑑控制(Assess Controls):評鑑(查驗Examination、訪談Interviewing、測試Testing)
5. 授權系統(Authorize System):主管授權非永久授權，會定期評鑑
6. 監控控制(Monitor Controls):上線後監控

FISMA  資訊安全根本大法。保護美國政府，避免遭受網路安全攻擊和 自然災害，致使敏感資料遭遇風險，
SOX法案 或《沙賓法案》目的是監督內線交易，企業必須以文件(至少保存5年)記錄對公司經營高層做法律的問責。
《執法通信協助法案》(CALEA) 適當法院命令的執法人員提供竊聽
數字千年版權法案 (DMCA) 保護作品設置的版權保護機制。
《兒童在線隱私保護法》(COPPA) 必須獲得 13 歲以下兒童的父母的同意。

HIPAA, 醫療健康產業善加利用新科技，並為醫療資訊的安全和隱私建立屏障
HITECH,醫療健康產業善加利用新科技，並為醫療資訊的安全和隱私建立屏障
經濟合作與發展組織(OECD)法規  組織及個資合理的取得、利用及保護
GLBA, 金融服務法現代化法案、集團內的客戶個資做規範。解決保護使用者隱私權的問題。
GDPR, 對歐盟成員的個資保護要求、屬人原則+屬地原則


GDPR適用的範圍
• 在歐盟境內設立據點的企業
• 對歐盟境內人民提供產品、服務或監測歐盟境內人民網路行為的境外企業
• 在個資跨境傳輸的部分
• 歐盟是採「原則禁止、例外允許」符合例外 情形下個資才能跨境傳輸

例外獲得許可的情形
• 由企業採行符合規範的適當保護措施
• 擬定具約束性企業規則，並報請歐 盟個資主管機關許可
• 取得特定認證
• 取得個資當事人明確同意等方式。
• 若第三國家個資保護水平達到GDPR標準的認可，即可自由與歐盟間進行個資跨境傳輸
       
跨境傳輸保護措施
• 匿名化:去除可識別唯性
• 擬名化:仍可使用對照表，還原可識別唯性


(ISC)2分類以時間軸來看 
Before
• Directive 指示(影響行為) 
• Deterrent 威懾(打消動機) 
• Preventive 預防(提高門檻) 
During
•  Detective 偵測(儘早發現)
•  Corrective 糾正(立即改善)
After
• Recovery 復原 (傷害恢復): 
Others
• Compensating 補償


COBIT 框架可以幫助各種規模的組織:
•有效利用 IT 實現業務目標
•提高和保持高水平的信息質量以支持業務決策
•使用技術促進卓越運營
•確保 IT 風險得到有效管理
•確保 IT 服務和技術費用的投資回報
•遵守法律、法規和合同協議
•協助解決整個企業利益相關者的需求

CSA 的安全、信任和保證註冊計劃 (CSA STAR(安全控制項在CCM))
• CSA STAR 1 級:自我評估
• CSA STAR 2 級:第三方認證
• CSA STAR 3 級:持續監控全雲保障和透明度
```
|L7|應用程式|FTP明文傳輸|DNS cache毒|流氓DHCP|
|:--|:--|:--|:--|:--|
|L6|編碼,壓縮,加解密|暴力破解|中間人|生日彩虹表|
|L5|全雙工,半雙工,單攻|中間人|XXS跨站||
|L4|TCP,UDP|UDP:fraggle,icmp|TCP:syn flood,Xmas||
|L3|addressing,routing|smurf,ping flood|DDoS|death ping|
|L2|MAC,LLC|MAC spoofing|ARP|Flooding|
|L1||訊號衰減|干擾|竊聽破壞|
```
• TeardropAttack淚珠攻擊:利用IP封包重組的漏洞進行攻擊。導致網路服務主機誤判封包大小，造成系統當機現象。
• Smurfattack藍色小精靈:偽造來源，Ping各方。
• LANDAttack:攻擊者利用IP偽裝的技術修改即
• TCPSYN(SYNflood): 受攻擊的系統會將尚未收到ACK回應的SYN，直到收到對方的ACK回應或超過逾期時間才移除。
• Ping of Death:經由發送過大的 ping 請求以造成緩衝區溢位 (Overflow)，繼而導致無法正常運作或當機。

transport end to end
tunnel gw to gw

SPF (Sender Policy Framework) 寄件者政策框架  電子郵件是否來自被允許的發信機位址
DKIM (DomainKeys Identified Mail)，網域驗證郵件，用來防止郵件內容遭到竄改
-->對這封郵件做簽章解碼，如果 公鑰與私鑰能配對成功，代表郵件確實為原始發信機所發出。
DMARC 是用來輔助 SPF 與 DKIM 的不足
-->用來讓發信端網域通知收件端郵件服務器，當遇到 SPF 與 DKIM 的設定檢查不過時，進行的處理方式。

SAML 斷言
• 斷言方是個系統實體，它發出帶有身份驗證、屬性和授權語句的 SAML斷言。依賴方是使用它收到的斷言的系統實體。
 SAML安全
• TLS 提供消息機密性和完整性， 可以防止竊聽。
-->SAML沒有安全模式，需要時依靠TLS 和數字簽名來確保安全。
```

```
Zero Trust 就是存取控制2.0
• 以資料為中心(虛擬邊界),SDN 虛擬定義網路, 微區隔 VxLan
• 更細緻  802.1x 不斷驗證,不止帳號還包含屬性(ABAC)
• 更動態  動態敲門技術(需要時才開)
• 更透明  持續監控
三. 大核心理念:
• 裝置不再有信賴與不信賴的邊界
• 不再有信賴與不信賴的網路
• 不再有信賴與不信賴的使用
四. 大核心元件:
• 網路分區閘:正確分割網路資源
• 創建平行且安全的網路分區:微核心邊界，想保護的資料都個別套起來
• 網路後臺集中管理:增加操作上的便利性
• 建立數據蒐集網路以掌控網路整體狀況，加速數據取得以便日後故障修繕

```
|model|key|solution|e.g.||
|:--|:--|:--|:--|:--|
|DAC|所有者可以授予或拒絕|使用客體ACL,能力表|windows檔案夾權限|take grant|
|MAC|主客體標籤|依賴分類標籤、應需而知|軍方等級,可存取專案|BLP.Biba|
|RBAC|角色或群|消除特權潛變、最小權限|windowsOS帳戶權限|wordpress站台|
|ABAC|包含多屬性規則比RBAC靈活|屬性可以是用戶、裝置的任何特徵|SD-WAN||
|ruleBAC|限制、過濾器||防火牆||
|riskBAC|風險基於ABAC的風險分數制|時間地點給分看風險|NAC內網准入管理||
```
國際通用標準測試過程四個術語:
• 評估目標(ToE):要測試的系統或產品
• 安全目標(ST):描述ToE和任何安全要求的文檔
• 保護配置文件(PP):針對要測試的產品類型的㇐組安全要求和對象
• 評估保證級別(EAL):產品經過測試後分配給產品的評級級別


Type of evidence:
真實證據 (Real Evidence) 亦被稱之為客觀證據
• 文檔證據 (Documentary Evidence)
1. 最佳證據規則:能夠呈現在法庭用於證實的書面內容，必須能附帶原始文檔，若提供原始文檔的副本，則稱之為次要證據，不被法庭接受
2. 口頭證據規則:當雙方的協議以書面形式記載下來時，若書面文檔被假設包含所有協議條款，並且以口頭方式協議，則不可修改書面協議

• 言辭證據 (Testimonial Evidence):證人的證詞
1. 可以是法庭上的口頭正詞
2. 也可以是紀錄下來的書面證詞

證據標籤包含的內容:
• 證據的㇐般性描述
• 證據收集的時間和日期
• 證據收集來源的確切位置
• 證據收集人員的姓名
• 證據收集的相關環境

```

```
STRIDE Risk Identification
偽造(S) Spoofing || 認證 ||冒充人或物
篡改(T) Tampering||完整性 ||修改資料或代碼
抵賴否認(R) Repudiation||稽核||不承認做過某行為
資訊洩露(I) Information Disclosure||保密性||資訊被洩露或竊取
阻斷服務(D) Denial of Service||可用性||消耗資源、服務可不用
提權(E) Elevation of Privilege||授權||未經授權獲取、提升許可權

DREAD Risk Analyst
✽傷害性 Damage : 若遭受攻擊的情況有多糟糕?
✽重現性 Reproducibility : 如何重現這攻擊情境?
✽可利用性 Exploitability : 發起這攻擊需要哪些條件?
✽受影響的用戶 Affected Users : 若攻擊有多少人被影響?
✽可發現性 Discoverability : 若發現這威脅的難易度為何?


選擇安全開發方法
i. 預測式方法(PredictiveApproaches):
瀑布式(Waterfall)>計畫驅動式(Plan-driven)，適合熟悉且掌握度高，但 現在環境太複雜較難因應變化

瀑布式(Waterfall)
• 計畫式, 弄好細節按表操課, 嚴謹, 適合很熟悉的東西、掌握度高 
• 較難因應變化

ii. 迭代式/反覆式方法(IterativeApproaches):
螺旋(SpiralModel)、雛形(Prototyping)，每㇐期作完客戶會看到 ㇐些產出(但還不能上線)，好處是降低風險
螺旋式(Sprial)
• 反覆/迭代 Iteration (生命週期), 強調風險管理
• 每期作完客戶會看到些產出(但還不能上線)
• 反覆可以做出東西 但還不能用
• 反覆 "生命週期"會做出東西但結果不能實際使用 • 好處降低風險


iii. 敏捷式方法(AgileApproaches):迭代式+增量式(Iterative+Incremental)，
通常為1-4週，每㇐次反覆交出來的 東西要能上線使用，強調交付價值與風險管理
敏捷(Agile) (是觀念、方法) • 反覆+價值漸增就是敏捷
(Iteration + Increment)
• 每次的反覆交出來的東西要能上線、要能用
• 旦能用就有產生價值 -->Increment (漸增的東西)
• 強調產出、強調風險管理期在Scrum 稱為 Sprint

2) 物件導向程式設計(OOP,ObjectOrientedProgramming)
a) 類別與物件(ClassandObject):類別會包Data&Code，是封裝的機制
i) 屬性(Properties):Data，學術名稱Attributes，用名詞命名
ii) 方法(Methods):Code，學術名稱Operations，用動詞命名 b) OOPFeatures
i) 封裝(Encapsulation):包Data及處理它的Code ii) 繼承(Inheritance)
iii) 多型(Polymorphism) c) Principles
i) 高聚合(HighCohesion):不能亂包，相關的才包在㇐起
ii) 低耦合(LowCoupling):盡量不要用別人的程式，但如果還是要用到


訊息驗證代碼(MAC,MessageAuthenticationCode):Hash2.0，文件先加密碼再取MAC
i. HMAC:使用雜湊計算MAC
ii. CBC-MAC:使用Cipher計算MAC
```

```
Kill Chain:
1. Reconnaissance (偵查):勘查目標
2. Weaponization (武器化): 針對勘查的資訊製作攻擊手法
3. Delivery (派送): 傳送至目標 ex: Email or USB
4. Exploitation (利用): 開發啟動攻擊手法的程序, 通常利用漏洞進行
5. Installation (安裝): 透過後門進行安裝, 給攻擊者使用
6. Command and Control (命令與控制): 安裝完成就提供給攻擊者控制
7. Actions on Objective (行動): 這時候就隨攻擊者想怎樣就怎樣啦!!


Buffer Overflows:緩衝區溢位(buffer overflow)，在電腦學上是指標對程式設計缺陷，向程式輸入緩衝區寫入使之 溢位的內容(通常是超過緩衝區能儲存的最巨量資料量的資料)，從而破壞程式執行、趁著中斷之際並取得程式乃至系 統的控制權。
• Pharming : 網址嫁接(Pharming)是1種重新導向(Re-dircert)的詐騙技巧，由網路釣魚(Phishing)衍生而來，藉由入侵 使用者電腦、植入木馬程式(Trojan)，或者是利用域名伺服器(Domain Name Server;DNS Server)的漏洞，將使用者 錯誤地引導到偽造的網站中，並伺機竊取重要資料。竄改 DNS 造成 DNS Poisoning。
• Session Hijacking and Man-in-the-Middle Attacks : 傳輸層安全 (TLS) 提供最有效的會話劫持防禦，因為它加密客戶 端和服務器之間的所有流量，防止攻擊者竊取會話憑據。
• Race condition:競爭危害(race hazard)又名競態條件、競爭條件(race condition)，它旨在描述㇐個系統或者 進程的輸出依賴於不受控制的事件出現順序或者出現時機。此詞源自於兩個訊號試著彼此競爭，來影響誰先輸出。
• 舉例來說，如果電腦中的兩個行程同時試圖修改㇐個共享記憶體的內容，在沒有並行控制的情況下，最後的結果依賴於 兩個行程的執行順序與時機。而且如果發生了並行存取衝突，則最後的結果是不正確的。
• TOC/TOU:檢查時間/使用時間(TOC / TOU)。這是㇐個類型的異步攻擊時出現㇐些控制信息發生變化之間的㇐次 系統的安全功能檢查內容的變量和時間變量實際操作過程中使用
• 推論(Inference):從已知信息派生新信息。推論問題是指這樣的事實，即可以在不清除用戶的級別上對導出的信息 進行分類。推斷問題是用戶從他們獲取的合法信息中推斷出未經授權的信息。
• 聚合(Aggregation):處理敏感信息時，組合或合併不同數據單元的結果。以㇐個敏感度級別聚合數據可能會導致 以較高敏感度級別指定總數據。
• 多重實例化(Polyinstantiation):多重實例化允許㇐個關係包含具有相同主鍵的多個行;多個實例通過其安全級別 進行區分。
• 側通道(side-channel)攻擊是針對硬體的攻擊, 常見的是時序分析及錯誤分析(故意製造錯誤)基於從電腦所產生的物理設 計中獲取的資訊(聲音、功率、光學等)，並使用這些資訊來反向工程電腦正在執行的操作。

XSS:惡意用戶通過使用第三方站點誘使受害者的 Web 瀏覽器執行腳本的攻擊稱為跨站點腳本 (XSS) 攻擊。跨網站指 令碼(Cross-site scripting，XSS)是㇐種網站應用程式的安全漏洞攻擊，是代碼注入的㇐種。它允許惡意使用者將程 式碼注入到網頁上，其他使用者在觀看網頁時就會受到影響。這類攻擊通常包含了HTML以及使用者端腳本語言。
• CSRF:跨站請求偽造(Cross-site request forgery, CSRF / XSRF)，也被稱為one-click attack 或者session riding， 是㇐種挾制用戶在當前已登錄的Web應用程式上執行非本意的操作的攻擊方法。跟跨網站指令碼(XSS)相比，XSS 利 用的是用戶對指定網站的信任，CSRF 利用的是網站對用戶網頁瀏覽器的信任。
• 僅知密文攻擊:在網路上聽封包得來的...㇐堆亂碼...很難成功.
• 已知明文攻擊:已經知道有部分密文, 而這密文也有對應的明文ex: 明文:Bruce 加密後密文: Veyxw，主要是來發現金鑰,
可以逆推回去, 生日攻擊這㇐類的.
• 〔選擇〕明文攻擊:A攻擊者放出㇐條OOO的明文出去, 再去偷聽OOO被B擷取的封包,傳送給C的過程 逆向篹出加密運
算
• 〔選擇〕密文攻擊:A攻擊者放出㇐條XXX的加密出去, 再去偷聽XXX被B擷取的封包,解密後再加密傳送給C的過程, 驗證
對方的演算法是否被破解
• 密碼猜測攻擊(password‐cracking attack):通關密碼破解工具很容易取得，它們大概都採用兩種方法，㇐是使用工具
在中間監看，㇐是提供密碼檔案(password file)進行字典攻擊(dictionary attack)。
• 後門攻擊(backdoorattack):後門的產生有兩種途徑，㇐種是軟體開發者原先設計的維護用後門(maintenancehook)，
 另㇐種是侵入者留下的後門以便重新進入。
• 中間人攻擊(man‐in‐the‐middle attack):中間人攻擊是指在伺服器與使用者之間放置㇐個軟體，讓雙方都無法察覺。
 這個軟體攔截㇐方的資料，備份或篡改之後若無其事地傳送給另外㇐方。




```
