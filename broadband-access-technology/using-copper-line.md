# 宽带铜线接入

## 电话线接入

DSL: Digital Subscriber Loop

上下行速率不对称: ADSL(Asymmetric DSL)、RADSL、VDSL(Very high speed DSL)
上下行速率对称: HDSL(DSL)、SDSL(Sigle line DSL)

> T1: 1.544 Mbit/s

2B+D: B is data(64kbit/s), D is sigling(16kbit/s)

> 窄带<3k传输语音，大于3k传数字信号

> VDSL速度快，但传输距离短，需和光纤FTTx结合使用

### ADSL的特点

1. 使用高于3kHz的频带传输数字信号
2. 使用高性能的`离散多音频调制(DMT)编码`技术; 正交+QAM
3. 使用`频分复用(FDM)`和`回波抵消(EC)`技术
4. 使用信号分离作用

> 回波抵消用于上、下行传输频段有重叠的通信系统
> 语音/数据分离器的作用: 过滤由电话机或其他通信设备产生的杂波，避免对数据通信产生干扰。
> 高阻分离器可以有多个(接 电话)，低阻分离器只能有一个(接 无线路由器)

### 影响ADSL速率的因素
1. 线路的长度 (太长)
2. 线的规格 (太粗，阻抗大)
3. 线的干扰

## 同轴线(电视网)接入
HFC：Hybrid Fiber Coaxial

### 频段
上行频段: 5～65MHz
下行频段: 87～1GHz

采用频分复用, 属于全业务宽带网络。

### 结构
前端(信号的接收与处理)、用户端、HFC传输端

可构成 数字电视系统、语音系统和宽带数据系统
> 其数字电视业务需要机顶盒
> 其话音业务采用IP技术

### 其他
CM: Cable Modem; 同轴电缆上的调制解调器
CMTS: Cable Modem Termination System

> 中国的HFC电视频道带宽是8MHz

## 网线(以太网)接入

### 以太网特点
1. 设备共用一个通信线路
2. 广播工作方式
3. CSMA/CD: Carrier Sense Multiple Access/Collision Detection; 补偿算法可以减少碰撞
4. 每个设备都有唯一MAC地址

> 10Base-T: 10Mbit/s : 双绞线
> FE: 100Mbps : 同轴细榄
> GE: 1000Mbps: 同轴粗榄
> 10 GE: 10000Mbps : 光纤

### 以太网设备
* 网卡: 主要技术参数为带宽、总线方式、电气接口方式
* 集线器: 用于信息分发，是共享式设备
* 交换机: 工作在链路层，有数据过滤、网络分段、广播控制等功能
* 路由器: 主要作用是为收到的报文寻找最佳路径，并转发出去
* 网桥: 用于扩展网络的距离

## 电力线接入
PLC： Power Line Communication
速率: 4~200M

### 特点
电力线的入户率高，覆盖范围大

### 缺点
当电力线上的负荷很重时，线路阻抗急剧下降，PLC的通信信号的功率会下降，网络质量也会下降