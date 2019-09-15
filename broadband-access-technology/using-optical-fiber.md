# 光纤接入

## 基本概念
OAN: Optical Access Network, 光纤接入网

### 功能模块
#### OLT (Optical Line Terminal)
光线路终端: 真实网络 与 用户配线网络 之间 的设备; OLT 下面可以接多个 ODN
61, 图303
#### ODN (Optical Distribution Network)
光配线网络: 在OLT与ONU中间提供光传输，完成光信号的功率分配

包括 光纤、光衰减器、光连接器、光分路器(OBD, Optical Branching Device)

属于无源器件(不需要电)
#### ONU (Optical Network Unit)
光网络单元: 用户配线网络 与 用户 之间 的设备; OLT 下面可以接多个 ONU

### 光纤接入网分类

#### 有源 (Active Optical Network, AON)
#### 无源 (Passive Optical Network, PON)
PON用WDM技术，实现单纤双向传输。下行用`广播技术`(使用`LLID`区分下行用户)，上行用`TDMA`(测距，`延时`速率高、距离近的用户，`不延时`速率低、距离远的用户)。

> 上行: 1310nm

## 以太网无源光网络(EPON)
EPON: Ethernet Passive Optical Network

核心技术: MPCP (多点控制协议)

## 吉比特无源光网络(GPON)
GPON: Gigabit-Capable PON

特点: 高带宽、高效率、大覆盖范围

### T-Cont (Transmission Container)
带宽分配的最小单位

### GEM (GPON Encapsulation Method)
数据流的最小单位

## EPON 与 GPON 的区别
![](/assets/The difference between EPON and GPON.jpg)

![](/assets/The difference between EPON and GPON.png)

## 接入网网管综述
...