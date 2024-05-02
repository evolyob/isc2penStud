## ch.2 設計要求
```
業務需求分析
--資產清單、每項資產價值、關鍵路徑critical path流程和資產、風險偏好的清晰理解

資產清單asset
--知道資產在哪裡能做什麼、失去對資產控制權將無法保證資產
--創建梳理資產清單的安全程序、調查、訪談、審計、自動化工具識別
資產評估 識別資產數量、區域、類型和對組織固有價值的BIA
>>>可用保險價值替換成本、data owner對數據負責業務確定數據資產價值

確定關鍵性 criticality 只資產不存在或無法運行帶來的影響跟後果程度
--真實世界場景
>>>有形資產 主要產品因無法銷售、組織業務就會停滯
>>>無形資產 知識關鍵版權被侵害就會失去存在的價值
>>>業務流程 無法完成關鍵業務流程也會造成無法正常經營
>>>數據路徑 缺貨或載貨容積不足造成無法供貨停止營業
>>>人員    關鍵人物消失也無法作業
BIA的另一個安全功能識別單點失敗，可能是來自軟硬流程人員其中一環
單點失敗SPOF處理方法
>>>增加冗余中斷就啟用替代、建立備份流程中斷就替代
>>>員工交叉培訓承擔多角色、堅持全面數據備份快捷恢復
>>>為IT資產提供負載共享或均衡
風險偏好 risk appetite *** 由高層確定、安全人員真正理解組織風險偏好才能有效履行
->>確定業務需求並完成BIA，BIA結果可用於風險評估選擇特定安全控制措施並制定BC/DR計畫
->>理解專業業務和資產價值非常重要
20.
-->風險是產生的機率、可被消滅但無法完全消除
-->可接受保持業務持續營運的風險、除影響人身安全風險可接受高於標準的風險
-->但風險必須符合行業標準或合規要求

>>>規避 avoidance    風險太高已超出風險偏好，無法通過適當控制來彌補而放棄
>>>接受 acceptance   風險偏好範圍內，繼續開產業務不需要額外關注
>>>轉移 transference 保險形式向第三方付費承擔損失，發生機率低但如果發生會很大影響後果
>>>緩解 mitigation   降低風險可能性或影響、安全人員採去控制措施實現
>>>殘餘風險residual risk  安全任務是根據組織風險偏好降至可接受風險水平
```
```
雲模型的邊界 DMZ
>>>IaaS邊界
-->客戶負責操作系統及其上的一切，但無法對供應商基礎設施做監管
-->客戶可以從軟件(操作系統)收集和查看事件日誌深入瞭解數據使用和安全性
>>>PaaS邊界
-->供應商負責操作系統的安裝維護管理、要求客戶修改安全策略付出更多確保合規性
-->客戶仍可更新維護監控審查軟件事件，客戶失去底層操作安全性控制同時也節省更多成本提高效率
>>>SaaS邊界
-->客戶不再具有軟硬件所有和管理權，只是輸入和處理系統中的數據擔負更少職權和責任
-->due diligence應盡責：供應商人員背調、持續監測其行為、嚴格物理安全措施


保護敏感數據設計原則 可用框架、模型、加強雲安全設計指南
設備加固 
>>>刪除所有訪客帳戶、關閉所有未使用端口、清除所有默認密碼
>>>強密碼策略、保護任何紀錄管理帳號
>>>禁用所有不必要服務、嚴格限制和控制物理訪問

BYOD ***
>>>使用防毒軟體或案全軟體進行保護、本地加密
>>>適時使用VPN訪問雲服務、使用DLP解決方案
>>>個人用戶設備使用容器軟件作為隔離個人數據和組織信息做法

加密技術
--雲計算數據中心加密為了
>>>長期儲存歸檔、保護近期儲存文件snapshot
>>>防止授權人對特定數據及未授權訪問(保護db的字段，DBA可管理不可修改查看)
--雲供應商和雲用戶之間通信加密為了
>>>建立安全會話、確保傳輸中數據完整性跟機密性

--同態加密技術homomorphic encryption 加密狀態處理雲端數據，而不必對雲端數據進行解密

分層防禦(供應商視角)
-- 較強人員控制措施(背景調查和持續監視)
-- 技術控制措施：加密、事件日誌、訪問控制
-- 物理控制措施：園區、基礎設施、數據中心內部處理和儲存區域、機架、特殊設備和進出園區便攜式介質
-- 建置並實施治理：強安全策略和規範、徹底審計

分層防禦(客戶視角)
--員工與雲用戶提供涵蓋安全主體的培訓計畫
--通過合同執行安全策略、BYOD使用加密和邏輯隔離機制
-- 強訪問控制：MFA
```


## ch.3 數據分級
```
數據所有權
--數據所有者
>>>
>>>
--數據託管者
>>>
>>>

雲數據生命週期
--數據分類
>>>監管合規 regulatory compliance
>>>業務功能 business function
>>>功能單元 functional unit
>>>基於項目 by project

數據分級
>>>敏感性  sensitivity
>>>司法管轄權 jurisdiction
>>>關鍵性 criticality

--分配數據標籤
>>>
>>>

數據識別方法
>>>基於標籤識別label based discovery
>>>基於元數據的識別 metadata-based discovery
>>>基於內容的識別 content based discovery pattern-matching

>>>數據分析 
-->數據挖掘 datamining
-->實時分析 real-time analytics
-->敏捷商業智能 agile business intelligence

```
司法管轄權要求
```

--美國 HIPAA, GLBA, PCI
--歐洲GDPR
--亞洲
--中南美
--澳洲

數據權限管理DRM
--知識產權保護 
>>>著作權copyright
-->合理使用 fair use
-->學術合理使用 academic fair use
-->評論 critique
-->新聞報導 news reporting
-->學術研究 scholarly research
-->諷刺文學 satire
-->圖書館保存 library preservation
-->個人備份 personal backup
-->身殘人士版本 pysical disabilities


>>>商標 trademark USPTO
-->
>>>專利 patent
-->

>>>商業秘密 trade secret

```
```
數字版權管理DRM工具特徵
--基本參考檢查 rudimentary reference chk
--在線參考檢查 online reference chk
--本地代理檢查 local agent chk
>>>許可介質保持驗證  presence of licensed media
>>>基於持續支持的許可 support based licensing

-->複製限制 replication restrictions DRM
-->司法官轄權衝突 jusisadictional confilicts
-->代理/企業衝突 agent/enterprise confilicts

-->身份和訪問管理 IAM ACL DRM IAM
-->API衝突 API conflicts
-->持久保護 persistent protection DRM
-->動態策略控制 dynamic policy control DRM ACL
-->自動失效 automatic expiration DRM
-->持續審計 Continuous auditing DRM
-->複製限制 replocation restrictions
-->遠程權限撤銷 remote rights revocation DRM
```
數據控制
```
retention disposal
數據保留 data retention
>>>保留期 retention periods
>>>適用法律法規 applocable regulation
>>>保留格式retention formats encryption engine
>>>數據分級 data classification creator,owner,curator,user
>>>歸檔和檢索程序 archiving, retrieval procedures BC/DR
>>>持續監測維護和執行 monitoring,maintenance,enforcement

數據審計 review data audit
--audit perid audit scope()()
--


>>>日誌審查和分析通常不是優先工作
>>>日誌審查是索然無味且不斷重覆
>>>日誌審查同時需要新手和富有經驗的人員
>>>審查員需要對營運具有一定理解

數據銷毀和廢棄
--介質和硬件的物理銷毀技術 physical destruction
>>>消磁 degaussing
>>>複寫 overwriting
>>>加密擦除 crypto shredding

數據廢棄策略
-->
-->
-->
data remanence

```

