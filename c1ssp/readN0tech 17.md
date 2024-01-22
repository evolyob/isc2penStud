ch.17 事件預防響應

```
以限制或遏制事件發展受影響降至最低
事件定義 CIA產生負面影響的任何事情
>安全事件：攻擊導致、用戶惡意蓄意導致、
>RFC2350：危害計算機或網路安全某方面任何不利事件
>NIST SP 800-61：違背或即將違背計算機安全策略、可接受策略或標準安全實踐規範的情況
-任何未遂網路入侵拒絕服務攻擊、對惡意軟件任何檢測、未經授權訪問、違背安全策略的行為

事件管理步驟
>>>SP 800-61 事件響應生命週期：準備、檢測分析、遏制根除和恢復、事件後的恢復
-檢測 IDS/IPS檢測潛在事件後發告警、反惡意軟件檢測彈窗告警、自動化工具掃描日誌利用定義好的事件觸發告警、當用戶報告無法訪問或更新時潛在事件
>> 需區分IT問題還是安全事件的調查判斷、調查人員或專業人員都能響應發起．
-響應  對事件響應越快越能控制在有限範圍的機會、調查過程保護能充當證據所有數據、不可關機避免ram臨時文件數據丟失
>>> CIRT/CSIRT   計算機事件響應團隊按照嚴重程度、通常在中大安全事件才啟用這個團隊、
>>>              透過教育訓練執行調查、評估損害、收集證據、報告事件、執行恢復程序、還參與補救和總結教訓
-抑制    遏制事件發展限制影響範圍避免傳播其他網路連接的隔離：：段網拔網路線
-報告    內部通報組織和外部相關部門人員、有合法報告要求(PII,PHI),
>>>PCIDSS  要求向執法部門報告某些安全事件、所有人接受相關培訓識別事件如何初步應對,如何報告
-恢復  檢查事項：訪問控制表及規則、禁用不需要的服務和協議、最新的補丁、用戶帳號、受破壞都得到修復、最安全做法是重建系統
-補救  查看事件發生原因在採取措施防止再發生、根因分析對系統改進建議
-總結教訓  響應行動需要改進的方面、增加安全控制、更改策略，管理層決定採哪哪個建議、未採納建議而存在風險負責
--->>託付用戶管理：檢查表、通過禁用或斷開把惡意軟件控制在自己的系統範圍避免闊散
實施檢測和預防措施
-預防性控制  阻止不必要或未授權發生、物理控制、生物特徵、職責分離、崗位輪替、數據分類、訪問控制、加密、回呼程序、安全策略、意識培訓、防毒、防火牆、入侵預防系統
-檢測性控制  監測控在事件發生後才能發現的活動：保安、CCTV、崗位輪替、強制休假、稽核蹤跡、蜜罐密網、入侵檢測系統、違規報告、用戶監督審查、事件跳茶

基本預防措施
-保持即時更新  定期發布補丁糾正錯誤和安全缺陷、確保系統和應用程序通過相關補丁保持攻心
-移除進用不需要服務和協議  避免潛在服務和協易遭到潛在攻擊、無法利用漏洞
-使用IDS/IPS  長事件測攻擊並發出告警
-最新版反惡意軟體  應對錯是反惡意軟件程序
-使用防火牆  網路防火牆保護整個網路、主機的防火牆保護單個系統
-執行配置和系統管理流程  確保組織安全方式部署系統始終保持安全狀態
```

```
了解攻擊
-殭屍網  按照一台指令多台命令和控制C&C,C2、保持休眠到具體日期時間對某件事作出響應發起大範萬的DDoS發送垃圾釣魚走件
>防止系統拉近殭屍網最好採用深度防禦戰略多層次安全保護避免感染、確保是最新的反惡意軟體程序保護
>教育訓練防止釣魚信點擊連結或下載惡意軟件或騙取用戶口令、內建的沙箱隔離web應用程序
>製造商在設計或建構這些系統應充分考慮安全因素給IoT設備易於更新

-拒絕服務攻擊DoS阻止合法訪問或請求、向服務器丟大量的數據包或已知漏洞讓系統無法癱瘓或崩潰、讓系統運行變慢、數據損毀、服務被攔截
>DoS來自單個系統或單系統為目標、利用假造源地址保持匿名很少是真實IP、DDoS多個系統協同攻擊一個、通常利用殭屍網發動DDoS、不會單獨存在
>分布式反射型拒絕服務DRDoS 不直接攻擊受害而是操縱通信流或網路服務、從其他來源反射回受害者 DNS中毒,smurf,fraggle

-SYNflood洪水攻擊  常見的DoS攻擊形式、中斷TCP發起通信交握、發送多個SYN(不同源地址)不回ACK完成連接等到他超時耗盡資源或消耗內存和處理能力
>達到一個極限也會把合法用戶請求攔截、阻止這種攻擊是縮段等待ACK時間可以半數會話從系統內存釋出
>TCP復位是操控TCP會話被FIN結束、RST復位包結束對話、在RST包假造源IP並切斷活會話、就需要重新建立會話
>>>主要是威脅需要持久會話或其他系統交換數據、並不是透過交握來建立會話

>smurf 另一種洪水、淹沒受害者的ICMP回聲包、發送假廣播ping請求回應ICMP給所有系統並假源IP地址、把受害者淹沒、
>>通過路由器發送定向廣播後所有系統都會攻擊受害者、修改路由器默認值不在轉發定向廣播流或禁止ICMP
>fraggle UDP 7, UDP 19使用UDP數據包、利用假受害者IP地址廣播UDP數據包造成所有系統都像受害者丟UDP flood

-ping洪水 ping請求淹沒受害者、通過一個殭屍網內發起攻擊而且非常奏效、會無法響應合法請求
>對應方法：攔截ICMP回升請求包可以攔截ping通信流但不能攔截所有ICMP、入侵檢測系統可以檢測出ping洪水後改變環境參數把ICMP回升請求攔住．
>>死亡ping  使用超大ping數據包造成超出系統處理能力而崩潰或緩衝區溢出錯誤
>>淚滴：把數據被打碎、使系統收到片段難以組合原始狀態造成系統崩潰
>>land攻擊：把受害IP同時做源IP和目標IP、向受害發送假SYN包、banana 把系統發出消息重新定向回系統、從而關閉所有外部通信

-零日利用  未知漏洞攻擊、不需要服務或協議就移除停用、啟用基於網路和主機的防火牆限制潛在惡意流量跟檢測攔截攻擊、或用蜜罐觀察攻擊情況
>攻擊扯最先發現漏洞輕易利用供應商未察覺這個漏洞、因而開發或發布補丁
>供應商獲悉漏洞但未發布補丁  利用發布前的空擋攻擊因為公眾不知道這個漏洞
>供應商發布補丁系統24小時內被攻擊  利用時間差攻擊

-MITM中間人(路徑攻擊)  兩個輛端點之間建立一個位置監視之間所有通信流、應即時補丁、利用VPN規避。
>複製、嗅探::充當儲存轉發或代理機制、收集登入憑證和其他敏感數據、還能更改之間交換內容、入侵檢測系統檢測不出中間人和劫持攻擊
>在客戶端偽裝服務器、在服務器偽裝是客戶端，需要配合多重攻擊配合(竄改路由和DNS值、獲取並安裝加密證書闖入加密通道，或是偽造ARP(地址解析協議)查找)

-蓄意破壞  對組織資產有足夠了解且具充分訪問權限，被解職後訪問權限依然存在
>>應禁用所有訪問全迅速採取，監測異常或未授權活動、確保員工與管理層溝通順暢

```
入侵檢測IDS和預防IPS系統 == IDPS
```

>IPS  包含檢測功能
>IDS  自動檢查日誌和實時系統事件、檢測入侵意圖和系統故障、其他機制進行補充但不回完全取代其他安全機制
>>>識別外部連接攻擊(DDOS)及內部傳播、對入勤做出即時和準確響應方法、
>>>NIST SP800-94 通篇都用IDPS通稱

-基於知識檢測  基於簽名檢測或模式匹配檢測、對已知攻擊數據庫定義模式和特點，假陽性很低、應定期/自動更新供應商提供的簽名跟新攻擊簽名更新::低誤報
-基於行為檢測  又稱統計入侵檢測、異常檢測、啟發式檢測、累計足夠基線來確定正常活動、還能進行狀態包分析和上下文檢查::高誤報
-真陽姓:發生也被檢測、假陰性:發生未檢測出來、真陰性:沒有發生沒有檢測、假陽性:未發生但被檢測出來
-IDS響應  防火牆前後放置一個被動IDS來衡量防火牆有效性
>被動:發mail或訊息也可生成報告詳細描述事件發生之前的活動、即時通知人員知曉快速隊不良行為作出有效響應
>主動:修改ACL攔阻基於端口、協議、源地址、切斷特定線段所有通信
>>>若有配置主動響應:::截斷該IP所有的通信流、攔截所有ICMP、攔截可疑或不良用戶的訪問、環境中變化需求響應進行調整
>>>主動響應IDS有時又稱IPS、

-HIDS
>
>
>
-NIDS
>
>
>

-IPS
-

-蜜罐密網
-警示
-反惡意軟件
-黑白名單
>
>
-防火牆
>
>
-沙箱
-第三方安全服務
```
日誌紀錄監測
```
日誌紀錄技術
-常見日誌類型
>系統
>應用
>防火牆
>代理
>變更

-保護日誌數據
-監測作用
>
>
>

-監測技術
>
>安全信息和事件管理
>syslog
>抽樣
>剪切級
>其他監測工具


-日誌管理
>
>
-出口監測


```

```
自動事件響應
-SOAR
>
>
-機器學習和AI工具
-威脅情報
>
>
>
>
>
>
-
-
-
-

```