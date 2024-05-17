
ch. 7 雲運用安全

```
培訓和意識宣貫
--
--
開發和管理人員處理的問體和特性
-->多租戶
-->第三方管理
-->部署模型
-->服務模型

常見雲應用部署陷阱
>>>本地應用未必能夠遷移
>>>文件缺失
>>>兵分所有應用都適用於雲環境
>>>租戶隔離
>>>使用安全和經歷驗證API
```
```
雲軟體開發週期SDLC
--定義、設計、開發、測試
-->
-->
-->DAST SAST
>>>
>>>

```

```
ISO/IEC 27034-1應用開發安全標準
--業務環境、監管環境、技術環境、規格說明書、角色職責和資格、流程、應用安全控制
>>>
ONF  組織規範框架 Organization
ANF  應用規範框架 Application
ASMP 應用安全管理流程

身份和訪問管理 IAM

--身份管理 配置
-->
--訪問管理
-->身份驗證
-->授權
-->策略管理
-->聯合驗證
-->身份儲存庫

身份儲存庫
-->
>>>X.500, LDAP, MS_AD, Novell eDirectory,源數據複製同步
>>>

--單點登入 SSO
-->
--聯合身份管理
->>Web of Trust
->>Third-party Identifier

-->聯合驗證標準 SAML
->>WS-Federation, OAuth, 
->>OpenID(OpenID Connect) OAuth2.0

-->多因素身份驗證
-->輔助安全設備
-->
>>>WAF
>>>DAM
--API
>>>XML API

```
雲應用架構

```

--應用編程接口
--REST
-->URL XML
-->CVS,JSOM,XML
REST工作場景
-->

--SOAP
--> XML
>>>
SOAP工作場景
>>>
--租戶隔離(tenancy separation)
-->多租戶
-->
--密碼學
-->靜態數據加密 at rest
-->動態數據加密 in transit
-->使用數據加密 in use
-->傳輸層加密 crypto offloading
-->安全套接字層 SSL
-->虛擬專用網路 VPN VPN
-->全實例加密 whole instance encryption/whole disk encryption,WDE
-->卷加密

沙箱技術
>>>
>>>
應用虛擬化
--Linux  windows
>>>

```
雲應用保證與驗證

```
--
-->威脅建模 STRIDE
>>>欺騙
>>>竄改
>>>抵賴
>>>信息洩漏
>>>拒絕服務  CIA
>>>特權提升


-->注入injection SQL,LDAP,OS
-->失效身分驗證
-->跨站腳本(XSS)  僅次於注入攻擊 Web XSS
-->不安全的直接對象訪問
-->安全錯誤配置
-->敏感數據洩漏 PII
-->功能及訪問控制缺失 UI
-->跨站請求偽造CSRF  HTTP cookies
-->使用包含已知漏洞
-->為驗證重定向和轉發

>>>數據丟失
>>>數據洩漏
>>>帳戶接管或劫持
>>>不安全的API
>>>拒絕服務
>>>內部威脅
>>>濫用雲服務
>>>未盡到"應盡職責"
>>>共享技術問題


```

```
QoS 服務質量
--
軟件安全測試
-->漏洞掃描
-->EULA 最終用戶許可協議
-->白盒測試
-->黑盒測試
```
|SAST||||||
|:--|:--|:--|:--|:--|:--|
|DAST||||||
|||||||
```
>>>SAST XSS SLQ
>>>SAST DAST HTTP

-->框架核心組件
>>>識別、保護、檢測、響應、恢復
-->配置文件
-->框架實施層

已核准API
-->API API API
-->API  API
>>>
軟件供應鏈管理(API方面)
--> API API
開源軟件安全
-->敏捷
RASP運行應用自我保護 runtime application self protection
-->
代碼安全審查
>>>
>>>

```

```
OWASP 編碼缺陷

-->輸入驗證
-->源代碼設計
-->信息洩漏和不正確處理錯誤
-->直接對象引用
-->資源使用
-->API使用
-->違反最佳實踐
-->薄弱會話管理
-->使用HTTP get 查詢字串

```
