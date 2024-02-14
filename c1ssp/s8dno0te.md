domain 1  2018
```
COBIT(Control objectives for Information and related technology)
信息及相关技术控制目标，定义了用于正确管理IT并确保IT满足业务需求的 控制目标。五个原则:
1、满足利益相关者需求
2、端到端覆盖(全面覆盖所有流程和职能)
3、单一集成框架(红绿灯)
4、整体方法(把公司当一个整体来考虑，不能头痛医头)
5、把治理从管理中分离出来。

微软SDL的SD3+C:secure by Design、Default、Deployment and Communication。
暴露(exposure)􏰁述了一资产损失的种可能性，当存在脆弱性， 又存在能利用这种脆弱性的威胁，威胁事件就可能发生。

控制的类型有
威慑(deterrent，安全培训、安全标识、保安)
预防(preventive，围墙、锁、加密、IPS) block
检测(detective，工作轮换、蜜罐、IDS)
补偿(compensating，附加的或增强的安全措施，比如用传输加密增强
安全性，比如没有智能卡的时候先用令牌)
纠正(corrective，重启、删除病毒等将系统还原的方法)、纠正是还原系统的操作
恢复(recovery，备份和恢复、容错、集群)要恢复的是业务，是冗余措施的作用体现
指令(疏散路线、监督、培训、安全策略要求，强制或鼓励主体遵循安全策略)

RMF:六个步骤:
1、分类信息系统;
2、选择 安全控制;
3、实施安全控制;
4、评估安全控制;
5、授权信息系统;
6、监控安全控制;然后，如有必要，重复

如果BCP失败，连续性受到破坏，则进入灾难模式，将 采用灾难恢复计划DRP。
```
domain 2
```
商业/私营部门的分类有三种:机密/专有数据(confidential/ proprietary)、
隐私(private，偏个人)、敏感(泄漏后对公司有负面影 响)、公开。

绝密(top secret)、秘密(secret)、机密(confidential)、非机密 (unclassified)，
如果泄露分别对应grave 、critical、serious damage。所 有分类的信息都免受信息自由法案限制

Linux的 bcrypt基于Blowfish，用来加密password，bcrypt还用了128位的salt来防止 彩虹表攻击。

acceptable usage policy (AUP) ，定义了个体的责任和预期行为，以及违反的后果，个体需要定期告知他们已经了解、理解和同意

data at rest怕偷窃，data in motion(on the wire)怕窃听

```
domain 3
```
凯撒密码无非就是A换成D，替代(是一种shift cipher，也是substitution，这个属于混淆confuse)。

ECB的安全性最差，因为相同的明文分组会加密产生相同的密文。适用于很少量的数据加密。 
CBC模式，每个分组在加密前，先和前一个密文分组异或。解密后也 和前一密文再异或。CBC还有一个IV和第一个分组异或的。
IV要发给接收方，可以明文放在密文最前面，也可以用ECB保护。
CBC模式要考虑错误传播，一个分组在传输中被破坏，会影响下一个分组。 加密不可并行，解密可以并行。
CFB模式，是流密码形式的CBC，对IV或前一块密文加密后产生密钥， 直接和本块明文异或产生本块密文。

AES算法分组128位，使用128、192、256三种密钥强度(分别10轮、 12轮、14轮)
Twofish  分组密码，处理128位数据，密 钥变长:1~256位，最大256位(16轮)
贵宾犬POODLE攻击，很多机构完全放弃对SSL3.0的支持

RSA 输入值任意长度、输出值长度固 定、计算容易、单向的、不会发生冲突

SHA-2有四个变种:
SHA-224、SHA-256、处理512位的分组
SHA-384、SHA-512。处理1024位的分组。

数字签名算法都要用SHA-2散列函数，加密算法有三种:DSA(数字签名算法)、RSA算法、椭圆曲线数字签名算法ECDSA
AH 消息完整性和不可否认性。ESP 机密性和完整性。都可以 防重放。

生日攻击也被称为冲突攻击，攻击者可以在通信中篡改明文，但维持原有签名的有效性
RBAC就是MAC的一种:规则型访 问控制(Rule-Based Access Control，RBAC)在规则中说明了哪种主体可 以访问哪种客体。

Clark-Wilson  只能通过使用程序、接口或访问门户来访问客体。接口对可以 对客体做什么和不可以对客体做什么施加了特定的限制。
Brewer and Nash  任何数据项采取行动时，管理员对冲突数据的访问都会被暂时阻止。一旦任务完成后，管理员的访问将返回到完全控制。
Goguen-Meseguer  非干涉概念理论的基础
Sutherland   预防对完整性支持的干扰。

ARP缓存投毒 客户端传输的数据流将发送给非预期的其他系统。
安全技术机制:
分层法    每层都不受其他层的影响和篡改
抽象     使用正确的语法获取返回结果
数据隐藏  不同安全级别的进程是不可见的
进程隔离  不同的内存空间
硬件分隔  使用硬件来分隔

设计环境物理安全时，记住顺序:先是阻拦(Deterence，威慑)， 然后拒绝(Denail)、然后检测(Detection)，然后延缓(Delay)
```
domain 4
```
TCP通过三次握手建立一个会话。C->S: SYN S->C: SYN/ACK C->S: ACK
结束会话需要四次挥手:C->S: FIN S->C: ACK S->C:FIN C->S: ACK

如果IPv4的一个地址为 135.75.43.52(十六进制为0x874B2B34)，
它可以被转化为 0000:0000:0000:0000:0000:0000:874B:2B34或者::874B:2B34

ping of death发送大与65535字节的包
smurf通过欺骗对目标网络产生大流量
ping flood是基本的DoS攻击

DNS投毒(poisoning)更改的是DNS系统，不管是哪一级的。
DNS欺骗(spoofing)发送虚假的响应，并抑制真的响应。
DNS劫持(Hijacking)的一种方法是，发送一个自己掌握的域名，并在自己掌握的DNS域名服务器上，侦听到本地DNS服务器

桥、交换机工作在第2层
路由器工作在第3层
网关工作在第7层

UTP就是
10Base-T(3类线10M)、
100Base-T(5类100M，5e类线 1000M)、
1000Base-T(6类线1G)，7类线能到10G(短距离内)，
1 类线主要适用于语音和调制解调器的，
2类用于大型主机、
4类用于令牌环。T代表双绞线，然后距离为100米。

Bluejacking使得攻击者可以给你的设备发送类似SMS的消息。
Bluesnarfing能够在你不知情的情况下配对你的设备，访问你的联系人列表、你的数据、甚至是你的通话。
Bluebugging可以让黑客远程控制你的设备，可以打开你的麦克风进行音频监控。

飞客(Phreaker)滥用电话系统，拨入公司然后打免费的长途电话。
L2TP其实是PPTP和L2F的组合，缺乏内置的加密方案，所以经常和 IPSec结合，L2TP支持TACACS+和RADIUS

传输模式中，不对IP包头加密，AH头或ESP头在原来的IP头后面;
隧道模式中，对整个IP数据包都加密了，然后外面有个新的IP包头， 然后才是AH头或ESP头，然后是原先的IP头。


静态NAT是指特定的内部IP地址永久映射到特定的外部IP地址。
动态NAT允许多个内部客户端使用较少外部IP，动态分配。
NAT常常与代理服务器或代理防火墙结合。
```
domain 5
```
访问控制的类型:
预防(Preventive Access Control)、试图阻碍未授权活动发生。
检测 (detective)、试图检测。
纠正(corrective)、发生未授权操作后，将系统还原
威慑(deterrent)、威慑人不去做
恢复 (recovery)、违反安全策略的情况后可以修复或还原资源
指引(directive)、强制或鼓励主体遵从安全策略
补偿(compensation) 备选方案

基于时间的同步动态密码令牌(每隔60秒变一次)
基于递增计数器的异步动态密码令牌，这种是用一次变一次

联合身份系统常使用SAML(安全声明标记语言):用户登录一次后，可以访问这一联盟中 任何组织的资源。
SAML是基于XML的，主要用于联合组织之间交换认证和授权(AA) 信息的，常用于SSO的用户信息交换，配置用户、资源和服务。

MAC需要标签，但rule-BAC不需要标签
rule-BAC的一个高级实现是基于属性的ABAC, 适用于所有主体的全局规则
ABAC模型: SDN网络用 ，SD-WAN用于实现流量策略

最小特权还包括在系统上的操作权限 (right)，need to konw主要体现在业务语境下
XSS利用站点内的信任用户不攻击服务器端而攻击正 常访问网站的用户
CSRF  只要是伪造用户发起的请求

OpenID强调 认证 authentication
OAuth强调 授权 authorization
```
domain 7
```
事件响应的步骤，
检测、自动化工具告警调查确定是安全事件，就开始响应
响应、指定条件下激活的团队
缓解、限制事件的影响范围
报告、根据法律
恢复、恢复系统到正常状态
修复、真正原因和根本原因、以防再次发生
经验教训  管理层决定哪些予以实施，哪些拒绝，但拒绝后的遗留风险由管理层负责

BIA可以作为以评定 优先级任务的基础。这个任务的结果是一张简单的业务单元优先级列表。
管理层(包括公关人员)看的概览式文件;
适用于某个部门的计划;
针对IT技术人员的技术性指南;
DR团队人员要使用的检查清单(checklist)

使用完整备份和差异备份，那么只需要还原两个备份
使用完整备份和增量备份，那么就需要还原最近的完整备份以及之后的所有增量备份

DR团队必须在MTD/RTO时间内恢复全部能力
```
domain 8
```
用户的输入做验证，检测不寻常的字符。应该在服务器端作 输入验证，浏览器的代码容易受到用户的操纵

准许开发返回到先前的阶段，从而纠正在后续阶段发现的错误。这被称 为瀑布模型的反馈循环特征
PERT 被用于直接改进项目管理和软件编码，以便开发更有效的软件

静态测试:通过分析源代码不需要运行软件。通常使用自动化工具来检测bug 
动态测试:在运行时环境中评估软件的安全性，测试人员通常无法 访问基础的源代码。

数据库事务都具有 4个必需的特征，即ACID:
原子性 (atomicity)、要么全有要么全无
一致性(consistency)、规则不能破坏
隔离性(isolation)一个事务更改相同数据前
持久性 (Durability)一旦给数据库就会被存储起来

ODBC 扮演了应用程序和后端数据库驱动程序之间代理的角色，使应用程序编程人员能够自由创建解决方案，而不必考虑后端的数据库系统

专家系统通过下列 4个步骤或阶段使用模糊逻辑:模糊化、推理、 合成以及逆模糊化。
模糊逻辑(fuzzy logic):数据归类更接近于人类的思维模式。允许算法思考控制人类思维

神经网络涉及很多层次的合计每一层的合计都需要加权信息以反映在决策制定过程中的相对重要性
神经网络就能够从经验中学习知识。
决策支持系统(Decision Support System, DSS)是一种知识型应用， 它分析业务数据，并且以更容易做出业务决策的形式给用户

```