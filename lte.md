# History
1G: FDMA: 传输模拟信号，业务量小、质量差、安全性差、没有加密、速度低
2G: TDMA: 数字化，保密性增加、容量增大、干扰减小，能传输低速的数据业务
3G: CDMA: 更高的频谱效率、更大的系统容量，更好的抗干扰能力; TD-SCDMA、WCDMA、CDMA2000
4G: OFDMA; Orthogonal frequency-division multiple access: 速率更快、频谱利用率更高、容量更大、更灵活
5G: 低时延、高可靠、低功耗

# LTE (Long Term Evolution)

### SAE: System Architecture Evolution
扁平化、分组域化、IP化、多制式融合化、用户面与业务面分离

> 3G的四层构架: 终端(UE)、基站(NodeB)、无线网络控制器(RNC)、核心网(CN)。RNC不只是基站控制器，而且是无线接入网络控制器

> eUTRAN(evolved UTRAN)与UTRAN相比，去掉了RNC。

扁平化网络结构的好处:

* 节点数量减少，用户平面的时延大大缩短
* 简化了控制平面从睡眠状态到激活状态的过程，减少了状态迁移的时间
* 降低了系统复杂性，减少了接口类型，系统内部的交互也变少了

多了一个X2有线接口，使得eNodeB之间互相连接(类似p2p)

> NodeB是网络与终端UE进行信息交互的设备，它做射频处理和基带处理两大类工作。射频处理: 发送、接收高频无线信号，高频信号与基带信号的互相转换。基带处理: 信道编码/解码，复用/解复用，扩频/解扩频调制

> NodeB: Antenna天线, BBU基带单元, RRU远端射频单元

### EPC: Evolved Packet Core
> CS: circuit switching

> PS: packet switching

* 没有CS
* 全网IP化
* 用户面与控制面的分离

**S1 为 EPC 和 eUTRAN(eNodeB) 之间的接口**

#### MME
MME: Mobility Management Entity

属于控制平面，负责控制面的信令传输

**S1-MME 与MME相连，是控制面接口**

主要功能: 寻呼、切换、漫游、鉴权、对NAS(Non-Access Stratum)信令的加密和完整性保护，对AS(Access Stratum)的安全性控制，空闲状态移动性控制

#### SGW and PGW
SGW: Serving Gate Way, 边界网关

主要功能： 分组数据的路由、转发、监听、计费

PGW: PDN Gate Way, 和运营商外部或者内部的分组网络连接

属于用户平面，负责用户包数据的过滤、路由和转发

**S1-U 与SGW相连，是用户面接口**

### eNodeB
主要承担的是基层用户的服务和资源管理功能

## Question and Answer

#### 从一代到四代移动通信技术有哪些标准?
第一代: AMPS、ETACS、NTACS
第二代: GSM、DAMPS、IS-95
第三代: CDMA2000、WCDMA、TD-SCDMA
第四代: TDD-LTE、FDD-LTE

> FDD = Frequency Division Duplex

> TDD = Time Division Duplex

#### LTE的全称是？
Long Term Evolution

#### 中国移动在4G中使用了哪些频段?
1880-1900MHz、2320-2370MHz、2575-2635MHz

#### SAE的全称是?
System Architecture Evolution

#### 第4代移动通信系统少了哪一层？
少了 RNC(无线网络控制器) 层

#### LTE扁平化网络结构有什么好处？
* 节点数量减少，用户平面的时延大大缩短
* 简化了控制平面从睡眠状态到激活状态的过程，减少了状态迁移的时间
* 降低了系统复杂性，减少了接口类型，系统内部的交互也变少了

#### eNodeB的主要功能有哪些?
* 射频处理
* 信道编码/解码
* 复用/解复用
* 扩频/解扩频调制
* 无线资源管理
* 移动性管理
* 承载控制
* 系统接入控制
* 路由选择
* 附着

> NodeB是网络与终端UE进行信息交互的设备，它做射频处理和基带处理两大类工作。射频处理: 发送、接收高频无线信号，高频信号与基带信号的互相转换。基带处理: 信道编码/解码，复用/解复用，扩频/解扩频调制

#### LTE和EPC主要由哪些网元构成?
* MME: Mobility Management Entity
* PGW: PDN Gate Way
* SGW: Serving Gate Way