ch.13 管理身份和認證
```
資產定義
-信息  可以儲存在服務器、阻止信息的未授權訪問
-系統  提供多個服務任何IT系統
-設備  設備儲存的組織數據是組織資產
-設施  擁有或租用物理場所
-應用程序  提供組織訪問數據、額外的控制權限

C 機密性  若未授權訪問導致保密性喪失
I 完整性  授權後修改、需安全控制檢測變更
A 可用性  合理時間訪問權限

-身份標示identification 主體聲明宣稱身份過程、啟用身份認證、授權、問責的唯一值
-身份認證authentication  一個或多個因素與有效身份標示數據庫比對
-主體(用戶)  活動實體、訪問被動客體、授權後可修改客體
-客體(文件)  被動實體、提供活動主體
基於知識身份驗證(KBA) 多個認知口令問題只有用戶知道答案，SP800-63B不建議使用這些靜態問題

-授權  基於管理員已驗證身分訪問信任權限
-問責  對其行為負責、記錄在"審計日志"的不可否任性、軌跡logs可驗證用戶對政策遵守程度
***問則依賴有效身分標示和認證

身分認證因素 IAM
#知道什麼  已記住的密碼、短語、靜態口令
>難記密碼抄寫下來、共用口令、明文傳輸被嗅探捕獲、暴力破解
>>定期變更密碼、複雜度三到四種字符、密碼長度、最短期限才能更換、口令歷史(防止用相同口令)、不同資料來源用不同的口令
>NIST 800-63b建議
1.必須經過哈希   永不明文行儲存或傳輸
2.不應該過期    不能增加安全性，可透猜測口令使用相同方法、口令修漏才要求更改密碼
3.不應要求使用特殊符號   記憶挑戰因此會寫下來，被攻破口令庫發現特殊符號沒達到預期效果
4.可以複製貼上口令 當禁止複製貼上，用戶通常用更簡單的口令
5.可以使用所有字符 通常會拒絕空格和特殊字符，但允許可讓用戶創建更容易記憶的長口令，有時拒絕惡意抵禦SQLi，若能進行哈希則可遮蔽這些字符
6.密碼長度建議   8~64
> PCIDSS
1.90天變更密碼
2.最少7字符

#擁有什麼  擁有可以提供身分認證的物理設備
>智能卡(電路芯片) 數字證書是非對稱加密、防竄改功能、不是有效身分標誌方法要配合密碼
>令牌(6~8碼數字)
>>同步動態 : 60秒定期更換動態生成密碼、
>>異部動態 : 根據算法或遞增生成一次性PIN碼，透過網頁將挑戰號回傳給客戶，每次都會更換
>>HOTP 基於哈希消息身分認證HMAC一次性口令建立於"異步"使用前保持有效
>>TOTP 基於時間一次性口令，"同步令牌"
NIST SP 800-63B 用簡訊有漏洞，如果訂戶身分識別模塊欺騙就可以攔截簡訊消息
-你是什麼  身體特徵基於生物辨識
>基於儲存大量人員信息數據庫來檢索匹配，常用於物理訪問
>-指紋:細節特徵(環形螺旋脊'分岔)，面部:訪問安全空間之前進行驗證，視網膜:眼睛後部血管圖像、最精準，
>-虹膜:瞳孔周圍彩色部分，第二精準(隱形眼鏡或高質量)，掌紋:紅外線測量靜脈圖案
>-聲紋: 特定短句附加身分認證，很少單獨使用  ((語音識別是提取信息內容))
>>>交叉錯誤率CER體現生物辨識的準確性、錯誤拒絕率FRR錯誤接受率的位址

-你在什麼地方  通過IP或來電顯示辨識地理位置
-不在什麼地方  地理定位識別可疑活動
-上下文感知身分認證(MDM移動設備管理)  用戶位置、時段、移動設備、允許訪問組織的網路

-FIDO 線上快速身分驗證聯盟  關於口令問題:帳戶太多、口令重復使用、是數據洩漏恩本原因、因忘記密碼放棄上網購物

設備指紋識別 使用系統、版本、瀏覽器、瀏覽器字體插件、時區、數據儲存、cookie設置和HTTP頭標屬性
-MDM使用上下文感知身分驗證通常與網路訪問控制NAC乙起檢查設備運行狀態，根據配置需求授予或限制訪問權限
-802.1X 實現設備身分驗證方法通常與無線系統一起使用、強制用戶獲得訪問權限之前使用帳戶登入，就可訪問網路
```
```
服務身分認證 基於屬性(sa,root)，需設置非交互式帳戶、防止用戶用傳統登入方式登入
>>比普通用戶更強大複雜口令、設定非交互帳戶
-配置基於證書身分認證，證書被頒發給運行服務設備並在訪問資源時提供，編程接口API串接
雙向身分認證  雙方都需要提出身分認證，防止客戶為造服務器洩漏信息(數字證書)、避免被導向偽造VPN服務器
實施身分管理  避免單點故障
-集中式  所有控制權由系統的單實體執行(AD)
-分散式  整個系統各類實體執行授權驗證，多人管理難以保持一致性

SSO單點登入 集中式訪問控制技術、單次訪問多資源不必再驗證身份、保護用戶憑證方法
-LDAP輕量級目錄訪問協議 微軟(AD DS)基於LDAP、LDAP主體多域通過驗證後定位所需系統資源的授權位置、信任可以是單向或雙向
-LDAP 公鑰基礎設施PKI使用LDAP、客戶查詢發證機構獲取證書並使用LDAP和集中式訪問控制支持SSO
**-SSO 應用於第三方服務、基於雲應用程序使用聯合身份管理系統FIM，多組織可加入一個聯盟公想身份信息只能登入一次
>>聯盟不會自動售予每個人訪問其他成員資源、每個組織自己決定共享哪些資源
1.基於雲的聯合   員工培訓時內部登入ID和聯合身份關聯起來、聯合身份系統使用戶登入ID檢索匹配聯合身份和可訪問的網頁
2.本地聯合    託管在本地和雲上結合混合系統、通過創立本地聯合身份管理系統可共享身份數據、也可訪問另外一家公司資源
3.混合聯合    雲聯合和本地聯合的組合、不會自動讓公司員工訪問培訓站點．利用本地聯合跟雲聯合解決
**4.準時制JIT   自動建立兩個實體本地之間關係以便新用戶訪問資源、不需要管理員干預、 第一次JIT與雇主交換數據並建立員工帳號、通常使用SAML來交換所需資源
-SAML為實體間各種數據提供非常大的靈活性、

憑證管理系統  用戶名稱和密碼提供儲存空間、萬維網聯盟W3C用API進行憑證管理、允許不同web使用聯合身份提供者的SSO
-用戶登入後循文是否除用戶憑證、顯示帳戶選擇允許用戶跳過表單、後續訪問自動登入即使會話已過期
-身份即服務或訪問即服務IDaaS提供身份和訪問第三方管理, IDaaS有效給雲服務做SSO、在內部客戶端訪問基於軟件即服務SaaS特別有效
-一個谷歌帳戶貫穿所有谷歌服務

憑證管理器應用程序   詢問是否保存憑證、進行加密後儲存數據庫、用戶使用強密碼解開加密數據庫
腳本訪問    登入腳本提供自動登入獨立身份認證傳輸登入憑證建立通信連接、通常明文形式訪問憑證應儲存在受保護的區域
會話管理    具防止未授權的訪問，屏幕保護程序time out 參考OWASP的速查表會話各種防護方法。
```
```
管理身分和訪問配置生命週期
-配置和入職  須通過組織安全策略程序保護該流程的適當為一值配置、配發硬件保持準確的紀錄。
>>閱讀並接受組織可接受使用策略(AUP)，安全最佳實踐、移動設備策略、PC能運行跟登入、配置口令管理器、MFA、如何訪問共享和保存。
-取消配置和離職    離職、解雇、調離 最簡單方式是刪除、若有加密數據訪問登入解密後刪除、常見是停用30天
-定義新角色及該角色所需的權限，分配權線和按組分配
-帳戶維護  訪問跟權限修改應建立類似創建使用程序，降低未授權訪問能力
-帳戶訪問審查  帳戶不存在多餘權限、符合安全策略、定期檢查非活動帳戶
>過度權限  超過所需權限，擁有過多權限、應撤銷不必要權限。
>蔓延權限  隨工作分配變化累積額外權限

物理訪問控制  物理限制訪問間接保護信息和應用程式
邏輯訪問控制  身分授權許可儲存在系統的信息、訪問設置
當員工請長假應禁用帳戶而不是口令重製、禁用不會加密任何數據或擁有的特權
```