```py
定量分析
特定風險事件的預期次數(ARO, Annualized Rate of Occurrence)：
特定風險事件可能造成的損失(SLE, Single Loss Expectancy)
年度損失預期(ALE, Annual Loss Expectancy)：
SLE=AV*EF　（資產價值*暴露損失因子）
ALE=SLE*ARO
ARO : 過去10年伺服器共故障了5次
SLE : 每次伺服器故障可能會損失$100
ALE : 預期㇐年會損失的金額ALE = ARO * SLE  = 0.5 * $100 = $50
```

```py
IPSec Mode(IP Security Mode)
傳輸模式(Transport Mode)：End-to-End全程加密
通道模式(Tunnel Mode)：只有Tunnel加密
L2TP
1.AH給看不給改
2.ESP不給看也不給改

ah Authentication Header
沒有提供任何加密的功能，使用 HMAC 算法，把 payload & header 和 IKE 定義好的 key 一起拿來 hash，但這邊要小心因為 NAT 會改變 header

esp Encapsulation Security Payload
Transport mode: ESP 沒有對 IP header 做 hash ，所以只能保證 Data 是沒有被修改的
Tunnel mode: 有將 IP header 包進來，所以這點跟 AH 是一致的
```
```py
軟體開發流程每個階段要做的事情 、sdlc
每個角色的職責 例如mission owner
軟體開發生命週期(SDLC, Software Development Lift Cycle)
規劃(Planning)
a. 寫計畫書：範疇時程成本、變更管理程序要交代清楚、採購管理(承包商的能力CMMI、SAMM)
b. 資訊收集、利害關係人登錄表(Stakeholder Register)、風險登錄表(Risk Register)
c. 選擇安全開發方法
i.
預測式方法(Predictive Approaches)：瀑布式(Waterfall) > 計畫驅動式(Plan-driven)，適合熟悉且掌握度高，但
現在環境太複雜較難因應變化
ii.
迭代式/反覆式方法(Iterative Approaches)：螺旋(Spiral Model)、雛形(Prototyping)，每㇐期作完客戶會看到
㇐些產出(但還不能上線)，好處是降低風險
iii.
敏捷式方法(Agile Approaches)：迭代式+增量式(Iterative+Incremental)，通常為1-4週，每㇐次反覆交出來的
東西要能上線使用，強調交付價值與風險管理
```
```py
敏捷宣言
a) 個人與互動 重於 流程與工具
b) 可用的軟體 重於 詳盡的文件
c) 與客戶合作 重於 合約協商
d) 回應變化 重於 遵循計畫
2) 方法論
--Scrum：是㇐種產品開發方法，所以不談專案不會出現專案經理，產品生命週期比專案⾧很多
 i) 三種角色：Scrum Master(教練)、Developers、Product Owner(產品負責人)
 ii) 五個事件：整個Sprint、Sprint Planning、Daily Scrum、Sprint Review、Sprint Retrospective
 iii) 重要術語：TimeBox 時間盒

--極限編程/極限程式設計(XP, Extreme Programming)：軟體開發最佳實踐，前三個更重要
i) 測試驅動開發(TDD, Test-driven Development)：先寫單元測試再進行正式開發
ii) 結對編程/結對程式設計(Pair Programming)：考慮程式品質
iii) 持續整合(CI, Continuous Integration)
iv) 比喻/系統隱喻(Metaphor)
v) 穩定的步調(Sustainable Pace)
vi) 小型釋出(Small Release)
vii) 策劃遊戲(Planning Games)
viii) 全隊/在場客戶(Whole Team)
ix) 設計最佳化/軟體重構(Refactoring)
x) 代碼標準(Code Standards)
xi) 程式碼集體共有(Collective Code Ownership)
xii) 簡單設計(Simple Design)
xiii) 客戶測試(Customer Tests)
b)
--看板(Kanban)：視覺化管理，常用待辦事項(Backlog or Todo) / 處理中(Doing) / 已完成(Done)
```
```py
組建整合產品團隊(IPT, Integrated Product Team)：
i.
DevOps(Development + Operations)：讓程式開發人員(Development)、測試人員(QA, Quality Assurance)、IT維
運人員(IT Operations)共同合作，透過CI/CD促成
ii.
CI/CD：持續整合(CI, Continuous Integration)、部署+持續交付(CD, Continuous Deployment + Continuous
Delivery)

iii. DevSecOps：有連續部署的授權安全議題等，故需要有資安人員加入
```
```py
成熟度模型(Maturity Models)
i. 能力成熟度模型整合(CMMI, Capability Maturity Model Integration)
ii. 軟體保證成熟度模型(SAMM, Software Assurance Maturity Model)：安全冠軍(Security Champion)
iii. BSIMM(Building Security In Maturity Model)
iv. CMMC(Cybersecurity Maturity Model Certification)
```
```py
網路線規格1000Base-T、

角色為基礎存取控制(RBAC, Role-based Access Control)：帶權限的群組稱為角色，解決DAC帳號設定複雜問題
屬性為基礎存取控制(ABAC, Attribute-based Access Control)
i. 使用主體、客體、環境的屬性設定
ii. 條件制(Criteria-based) vs 分數制(Score-based)
e. 風險為基礎存取控制(Risk-based Access Control)：同ABAC的分數制(Scroe-based)但以風險作為分數
f. 規則為基礎存取控制(Rule-based Access Control)：同等於Firewall

零信任(Zero Trust)
- 驗證：ISO OSI每㇐層都可以做身分驗證
- 授權：屬性為基礎存取控制(ABAC)
- 動態敲門(Port Knocking)：先連接到㇐組預定義的閉合Port，然後才開放真正的SSH或其他服務的Port
- 單㇐封包授權(SPA, Single Packet Authorization)：魔術封包，知名動態敲門技術之㇐(芝麻開門)
```
```py
安全保護(Security Safeguards)：HIPAA分3類
a. 行政類(Administrative)：又稱管理類
b. 技術類(Technical)：又稱邏輯類
c. 實體類(Physical)：又稱物理類

```
```py
業務持續計畫(BCP, Business Continuity Plan)常見
a. 團隊成員列表：包括多種聯繫方式和備用成員
b. 即時回應程序和清單：安保和安全程序、滅火程序、通知適當的緊急回應機構等
c. 通知系統和呼叫樹，用於提醒人員BCP正在制定
d. 管理指南：包括為特定管理人員指定權限
e. 如何/何時制定計畫
f. 供應鏈關鍵成員的聯繫電話：供應

```
```py
業務衝擊分析(BIA, Business Impact Analysis)：
找出關鍵流程(核心業務)及關鍵資源(核心系統) > 哪個流程最關鍵> 看MTD
a. 最大可容忍停擺時間(MTD, Maximum Tolerable Downtime)：高階主管核定ex: 5天內
b. 復原時間目標(RTO, Recovery Time Objective)：通常不超過MTD ex: 3天內
c. 復原點目標(RPO, Recovery Point Objective)：備份資料點的目標，通常資訊系統才會有RPO，通常不超過RTO ex:
1天前的資料
d. 服務水準協議(SLA, Service Level Agreement)：服務提供商與客戶之間定

鏡像站點(Mirrored Site)：不間斷同步
熱站點(Hot Site)：開機會有熱氣，隨時Ready可使用，與生產環境，只差最新㇐份資料
溫站點(Warm Site)：只有設備，解決採購設備問題
冷站點(Cold Site)：只有地點，解決找地點時間問題
行動站點(Mobile Site)：機房就在卡車內
互惠站點(Reciprocal Site)：互相Cover，但實際效果不好
```
```py
DRP每個的主要目的
a.
重點在於災難復原計畫(DRP)的測試，DRP會指導事故回應(IR)人員的行動，其目標是在業務中斷後恢復到最後㇐次已知的正常全面營運
b.
災難復原計畫(DRP, Disaster Recovery Plan)常見組成
i. 執行摘要提供計畫的高階概述
ii. 部門特定計畫
iii. 負責實施和維護關鍵備份系統人員的技術指南
iv. 關鍵災難恢復團隊成員的完整計畫副本
某些個人的清單：
1) 關鍵災難恢復團隊成員將擁有清單，以幫助指導他們在災難的混亂氣氛中採取行動
2) 人員將獲得技術指導，幫助他們啟動和運行備用站點
3)經理和PR人員將擁有易於理解的高階文件，以幫助他們準確地傳達問題，而無需來自忙於恢復工作的團隊成員說明
c.
測試及演練方式
i. 查核表(Checklist)：檢查是否每份計畫書都有寫
ii. 讀㇐遍(Read-through)：計畫書看㇐遍內容
iii. 走㇐遍(Walkthrough)：情境模擬(Tabletop)
iv. 模擬(Simulation)：模擬測試
v. 平行(Parallel)：找人到另㇐個系統進行中斷測試
vi. 全中斷(Full interruption)：實戰演練，直接中斷測試

```
```py
標準
ISO 27001：資訊安全管理系統(ISMS)

SOC(Service Organization Control)：由美國會計師協會(AICPA)訂定
a.
SOC 1：適用於財務系統(控制措施)
i. Type 1：只看控制措施的設計適切性(Suitability of the Design)
ii. Type 2：不只看設計，還要看設計運作(至少半年以上)的有效性(Effectiveness of Operations)
b.
SOC 2：適用於財務系統以外的資訊系統(控制措施)
i. Type 1：只看控制措施的設計適切性(Suitability of the Design)
ii. Type 2：不只看設計，還要看設計運作(至少半年以上)的有效性(Effectiveness of Operations)
c.
SOC 3：SOC 2 Type 2的摘要版
```
```py
能力成熟度模型整合(CMMI, Capability Maturity Model Integration)：舊版本為CMM for Software，整合了軟體開發能
力、獲取能力、服務交付能力，目前CMMI已被ISACA收購
a.分類
i. CMMI for Acquisition
ii. CMMI for Development
iii. CMMI for Services
b.
分級
i. Level 1(Individual/Ad Hoc) > Initial：土法煉鋼
ii. Level 2(Project) > Managed：各自為政
iii. Level 3(Organization) > Defined：統㇐方法
iv. Level 4 > Quantitatively Managed：量化管理
v. Level 5 > Optimizing：最佳化


軟體保證成熟度模型(SAMM, Software Assurance Maturity Model)：OWASP，開源的，安全冠軍(Security Champion)

支付卡產業資料安全標準(PCI DSS, Payment Card Industry Data Security Standard)：由VISA、美國運通公司、發現金融服務公司、JCB和萬事達國際組織等五家國際信用卡組織聯合推出,是目前全球最嚴格、級別最高的金融機構安全認
證標準

```
```py

```
