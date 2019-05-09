# GSM-R/GPRS Wireless Access Platform

铁路上数据交换有两种方式: 电路交换\(CSD, _Circuit Switched Data_\)、分组交换\(GPRS, General Packet Radio Services\)

> 讲真的，它们挺SB的，直接说 packaging switching 多好啊

除了列车控制信息用 `CSD`, 其他信息传输都用`GPRS`



### 组成

#### 1. GPRS接口 服务器 \(GRIS, GPRS Interface Server\)

提供GPRS`网络接入、协议转换、数据存储转发、信息安全`功能

这个服务器有自己的`IP地址`

#### 2. 归属GPRS接口 服务器 \(GROS, GPRS Home Server\)

提供`数据存储`功能: 存储全国铁路`所有的GSM-R小区信息、铁路公里标、它们的GPS信息、每个路局占用的地理范围`，能提供`每个地理位置`所对应的`GPRS接口服务器的IP地址`。

提供`数据查询与检索`功能: 废话嘛，存了不就得拿来用

#### 3. RADIUS 服务器 \(Remote Authentication Dial In User Service\)

> A RADIUS Server is a network server that other network devices contact in order to authenticate user information.

鉴权

#### 4. DNS 服务器 \(Domain Name Server\)

