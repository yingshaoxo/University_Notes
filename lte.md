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

## Question and Answer

#### SAE的全称是?
System Architecture Evolution

#### 第四代移动通信技术少了哪一层？
RNC

#### LTE扁平化网络结构有什么好处？
* 节点数量减少，用户平面的时延大大缩短
* 简化了控制平面从睡眠状态到激活状态的过程，减少了状态迁移的时间
* 降低了系统复杂性，减少了接口类型，系统内部的交互也变少了

#### eNodeB的主要功能有哪些？
* 无线资源管理
* 用户数据流的IP报头压缩和加密
* UE附着状态时MME的选择
* 实现SGW用户面数据的路由选择
* 执行由MME发起的寻呼信息和广播信息的调度和传输
* 完成有关移动性配置和调度的测量和测量报告

#### LTE和EPC主要由哪些网元构成？
* MME: Mobility Management Entity
* PGW: PDN Gate Way
* SGW: Serving Gate Way

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

## Question and Answer

#### 请写出MIMO的两种工作模式和区别
发射**分集**: 多路信道传输同样的信息

空间**复用**: 多路信道同时传输不同信息

#### 请写出OFDM的优缺点
优点: 
1. 通过循环前缀，有效克服无线环境的多径干扰
2. 实现用户间完全正交的频率复用，保证频谱效率
3. OFDM容易和MIMO技术结合
4. 支持频率纬度的链路自适应和多用户调度

缺点:
1. 对相位噪声和载波频偏十分敏感
2. 峰均比过大
3. 所需线性范围宽
4. PAPR比SC-FDMA更高

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

## Question and Answer

#### 哪些情况会发生随机接入? 什么类型的？

1. RRC_IDLE状态下的初始接入
2. RRC连接重建
3. 切换
4. RRC_CONNECTED状态下有下行数据到达，但上行处于失步状态
5. RRC_CONNECTED状态下有上行数据到达，但上行处于失步状态，或没有用于SR的PUCCH资源
6.  RRC_CONNECTED状态下的UE辅助定位

竞争性随机接入: 1 to 5

非竞争性随机接入: 2, 3, 6

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

____

# LTE系统无线资源管理

## Question and Answer

#### 资源分配的方式有哪些？
* 集中式资源分配
* 分散式资源分配

#### 负载均衡的意义是什么？
* 使各个小区间的负荷更加均衡
* 使系统间的负荷更加均衡
* 使系统的容量得到提升
* 减少`人工参与网络管理与优化`
* 保证用户的QoS，减少拥塞造成的性能恶化

___

# All for The Exam

## Level 1

#### 简述FDD-LTE工作原理。
上下行收发在相同时间的不同频点上（全双工系统）    

#### 简述TD-LTE工作原理。
上下行收发在相同频点的的不同时间段上（半双工系统）

#### 请简述TD-LTE帧结构。
1. TDD帧结构引入了特殊子帧的概念
2. 特殊子帧中包括DwPTS（Downlink Pilot Time Slot, 下行导频时隙）、GP（Guard Period, 保护周期）和UpPTS（Uplink Pilot Time Slot, 上行导频时隙）
3. 特殊子帧各部分的长度可以配置，但总时长固定为1ms

#### LTE有哪些关键技术，请列举简要说明。
OFDM正交频分复用技术
* OFDM技术原理
* OFDM多址接入

MIMO多天线技术
* AMC链路自适应技术
* HARQ混合自动重传

#### 描述MIMO技术的三种应用模式。
发射**分集**: 多路信道传输同样的信息

空间**复用**: 多路信道同时传输不同信息

波束赋形: 多路天线阵列赋形成单路信号传输

#### 简述OFDM的基本原理，有哪些优势和劣势？
基本原理：OFDM是一种正交频分复用技术，是由多载波技术MCM发展而来的; OFDM既属于调制技术，也属于复用技术。

优势：

1. 通过循环前缀，有效克服无线环境的多径干扰
2. 实现用户间完全正交的频率复用，保证频谱效率
3. OFDM容易和MIMO技术结合
4. 支持频率纬度的链路自适应和多用户调度

劣势:

1. 对相位噪声和载波频偏十分敏感
2. 峰均比过大
3. 所需线性范围宽

#### LTE上行为什么要采用SC-FDMA技术？
1. 相对于OFDMA，具有更低的PAPR，便于UE功放的设计
2. 相对于传统的单载波频率复用，能实现用户间完全正交的频率复用，同时保证频谱效率
3. 用户复用可以通过DFT交换，正交子载波映射等过程方便地实现
4. 支持频率维度的链路自适应和多用户调度

#### 简述RSRP、RSRQ、RSSI、SINR的含义。
* RSRP(参考信号接收功率): 是终端接受到的小区公共参考信号（CRS）功率值，数值为测量带宽内单个RE功率的线性平均值，反映的是本小区有用信号的强度
* RSRQ(参考信号接收质量): 是N倍的RSRF与RSSI的比值，其中N表示RSRI的测量带宽内包含的RE数目，能反映出信号好干扰之间的相对大小
* RSSI(接收信号强度指示): 是终端接收到的所有信号（包括同频的有用和干扰、邻频干扰、热噪声等）功率的线性平均值，反映的是该资源上的负载强度
* SINR(信噪比): 是有用信号功率与干扰和噪声功率之和的比值，直接反映接收信号的质量


## Level 2

RRC两种主要的状态是       `空闲`           和        `连接`           。


特殊子帧配置中包括    `DwPTS(下行导频时隙)`           、       `GP(保护周期)`        和       `UpPTS(上行导频时隙)`           。


LTE系统中存在两种类型的CP:   `普通`     CP和    `扩展`      CP。


LTE系统的传输速率：对于大范围高速移动用户（250km/h）数据速率为2Mbit/s；对于中速移动用户（60km/h）数据速率为     `20Mbit/s`      ；对于低速移动用户（室内或步行者），数据速率为      `100Mbit/s`          。


eNodeB与UE通过      `U口`          连接。


在扩展CP情况下，一个RB包含     `84`     个RE。


无线网络接口协议栈根据用途分为      `用户平`      面协议栈和     `控制平`       面协议栈。


TTI 为物理层数据传输调度的时域基本单位，1 TTI = 1 个子帧 =     `1`     ms，1 TTI =     `12`    个OFDM符号 (普通 CP)。


LTE的网络接口中S1-MME是      `eNodeB`        连接      `MME`        的控制面接口。


LTE的网络接口中S1-U是     `e-NodeB`       连接     `SG-W`       的用户面接口。


空中接口是指     `终端`       和     `接入网`          之间的接口。


同步信号包括        `PSS`           和         `SSS`          。


物理信道中，PDCCH是        `下行控制信道`          信道，PDSCH是       `下行共享信道`          信道 。


TDD配比格式中的S的全称是        `特殊子帧`           。


OFDMA技术是基于时频二维资源的一种多址调度方式，频域上的调度资源为   `子载波`     ，时域上的最小调度单元为    `slot`       。


用户平面协议栈中层二主要由    `MAC`         ，     `RLC`       ，     `PDCP`       三个子层构成。


LTE共支持两种无线帧结构； 1个无线帧  =     `10`   ms，1个子帧 =    `1`     ms。


PRB为物理层数据传输的资源分配最小单位，时域：     `0.5`     ms，频域：    `12`     个连续子载波(Subcarrier)。


LTE标准支持两种双工模式：     `TDD`       和      `FDD`        。


TDD和FDD是不同的双工技术，它们分别用    `时间`       和     `频率`     来区分上下行


LTE系统的传输速率为：对于大范围高速移动用户（250km/h）数据速率为   `2Mbit/s`     ；对于中速移动用户（60km/h）数据速率为      `20Mbit/s`         。


核心网中控制面和用户面与基站连接时采用的接口分别为    `S1-C`      和     `S1-U`       。


LTE/SAE的组网架构变迁主要目的是      `提高峰值速率`      、     `降低系统时延`       、简化运营维护、降低系统成本。


LTE/SAE的组网架构变迁主要包括 `扁平化`  、分组域化、IP化、多制式融合化、 `用户面与业务面分离`   等。


RE (Resource Element)是物理层资源的最小粒度，时域上相当于   `1`    个OFDM符号，频域相当于      `1`     个子载波，在扩展CP情况下，一个RB包含   `72`    个RE。


LTE的网络接口中S1接口是连接       `EPC`           与      `eUTRAN`        的接口。


LTE的空口速率之所以能够获得巨大提升，主要是因为采用了         `OFDM`           技术、       `MIMO`      技术和     `高阶调制`      技术。


PGW的主要功能包括：      `分组数据过滤`        ；        `UE的IP地址分配`         ；上下行计费及限速。


LTE资源分配技术可以分成       `集中式资源分配`              、        `分布式资源分配`          ，根据传输业务类型的不同，LTE系统中的分组调度可以分为     `动态调度`       和      `半静态调度`      。


LTE 帧结构中1 个无线帧=   `10`   子帧=   `20`    时隙


UE可以通过随机接入过程实现两个基本功能：      `取得与eNodeB之间的上行同步(TA)`      ，      `申请上行资源(UL_GRANT)`         。


SGW的主要功能包括：分组数据路由及转发；   `移动性及切换支持`      ；      `合法监听`       ；   `计费`     。
