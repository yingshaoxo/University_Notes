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

____

# LTE系统网络接口

## LTE 系统结构

### eNodeB
主要功能:
* 无线资源管理
* 用户数据流的IP报头压缩和加密
* UE附着状态时MME的选择
* 实现SGW用户面数据的路由选择
* 执行由MME发起的寻呼信息和广播信息的调度和传输
* 完成有关移动性配置和调度的测量和测量报告

### MME(Mobility Management Entity)
* NAS(Non-Access Stratum)非接入层信令的加密和完整性保护; 核心网不做处理，直接传输
* AS(Access Stratum)接入层安全性控制，空闲状态移动性控制
* EPS(Evolved Packet System)承载控制
* 支持 寻呼、切换、漫游、鉴权

### SGW
分组数据路由、转发、监听、计费

### PGW
属于用户平面，负责用户包数据的过滤、路由和转发


# 接口
23，图3-1

## Uu空中接口协议(UE 与 eNodeB)
### 控制平面协议
NAS: Non-Access Stratum
RRC: Radio Resource Control
PDCP: Packet Data Convergence Protocol
RLC: Radio Link Control
MAC: Media Access Control

> RLC(Radio Link Control)的三种传输模式: 1. TM(Transparent Mode) 2. UM(Un-acknowledgement Mode) 3. AM(Acknowledgement Mode)
### 用户平面协议
MAC、RLC、PDCP

## S1接口协议(S1-MME连接eNodeB与MME; S1-U连接eNodeB与SGW)
* EPS承载服务管理
* UE上下文管理
* 移动性管理
* 寻呼管理
* 信令传输功能
* S1接口管理
* 网络共享

### 接口用户平面
**S1-U连接eNodeB与SGW**
GTP-U: GPRS Tunneling Protocol for User Plane
### 接口控制平面
**S1-MME连接eNodeB与MME**
SCTP: Stream Control Transmission Protocol

## X2接口协议
连接eNodeB

### 接口用户平面
### 接口控制平面

_______________

# LTE 的关键技术

## OFDM(Orthogonal Frequency Division Multiplexing)

* 上行: OFDMA, Orthogonal Frequency-Division Multiple Access
* 下行: SC-FDMA, Single-Carrier Frequency-Division Multiple Access

> FFT = Fast Fourier Transformation

OFDMA的优势: 
1. 通过循环前缀，有效克服无线环境的多径干扰
2. 实现用户间完全正交的频率复用，保证频谱效率
3. OFDM容易和MIMO技术结合
4. 支持频率纬度的链路自适应和多用户调度

## SC-FDMA(Single-Carrier Frequency-Division Multiple Access)

SC-FDMA的优势:
1. 相对于OFDMA，具有更低的PAPR，便于UE功放的设计
2. 实现用户间完全正交的频率复用，保证频谱效率
3. 用户复用可以通过DFT变换、正交子载波映射等过程轻松实现
4. 支持频率纬度的链路自适应和多用户调度

## MIMO(Multiple Input Multiple Output)

利用多发射、多接收天线进行空间分集的技术

### 分集
多路信道传输相同的信息

### 复用
多路信道传输不同的信息

### 波束赋形
原理: 利用`空间信道的强相关性及波的干涉原理`产生强方向性的辐射方向图，使辐射方向图的主瓣自适应指向用户`来波方向`，从而提高信噪比，获得明显的阵列增益。

## AMC(Adaptive Modulation and Coding)
原理: 在发送功率恒定的情况下，动态地选择适当的调制和编码方式，确保链路的传输质量。

> LTE的调制方法: QPSK、16QAM、64QAM

## HARQ(Hybrid Automatic Repeat Request)

## LTE“三高、两低、一平”
三高:
* 高峰值速率
* 高频谱效率
* 高移动性

两低:
* 低时延
* 低成本

一平:
* 扁平化架构

_____

# LTE 信道

FDD: 上下行收发在相同时间的不同频点上； 全双工

TDD: 上下行收发在相同频点的不同时间段上； 半双工

> FDD 和 TDD 的帧时长都是 10ms, 一个帧分为10个子帧

> `Speicial subframe` in LTE 被用来提示`下行`切换到`上行`

## 信道分类

逻辑信道、传输信道、物理信道

### 逻辑信道

分为: 控制信道、业务信道

控制信道:
* BCCH: Broadcast Control Channel; 广播控制信道
* PCCH: Paging Control Channel; 寻呼控制信道
* CCCH: Common Control Channel; 公共控制信道
* DCCH: Dedicated Control Channel; 专用控制信道
* MCCH: MultiCast Control Channel; 多播控制信道

业务信道:
* DTCH: Dedicated Traffic Channel; 专用业务信道
* MTCH: MultiCast Traffic Channel; 多播业务信道

### 传输信道

分为: 下行信道、上行信道

下行信道:
* BCH: Broadcast Channel
* PCH: Paging Channel 
* DL-SCH: Downlink Share Channel
* MCH: MultiCast Channel

上行信道:
* RACH: Random Access Channel 
* UL-SCH: Uplink Shared Channel

### 物理信道

下行信道:
* PBCH: Physical Broadcast Channel
* PDSCH: Physical Downlink Shared Channel
* PDCCH: Physical Downlink Control Channel
* PCFICH: Physical Control Format Indicator Channel
* PHICH: Physical Hybrid ARQ Indicator Channel
* PMCH: Physical Multicast Channel

上行信道: 
* PRACH: Physical Random Access Channel
* PUSCH: Physical Uplink Shared Channel
* PUCCH: Physical Uplink Control Channel

_____

# LTE 系统物理层

PSS: Primary Synchronous Signal

SSS: Secondary Synchronous Signal

频率偏移:
* 整数倍偏移 (概念有误，应是`>1倍的频率偏移`)
* 小数倍偏移 (概念有误，应是`<1倍的频率偏移`)

随机接入:
* 竞争性随机接入
* 非竞争性随机接入
_____

# LTE 的编号

## UE

* C-RNTI: C-Radio Network Temporary Identifier
* IMEI: International Mobile Equipment Identity
* IMSI: International Mobile Subscriber Identity
* S-TMSI: Serving Temporary Mobile Subscriber Identity
* UEID: 
* GUTI: 

## Base Station
* TAI: 

## SAE

* PLMN
* MSIN: Mobile Subscriber Identification Number
* MMEGI: 
* MMEI
* eNB S1AP UE ID
* MME S1AP UE ID
* IMEI/SV
* TAC
* TAI List
* PDN ID
* EPS Bearer ID
* E-RAB ID
* DRB ID
* LBI
* TEID