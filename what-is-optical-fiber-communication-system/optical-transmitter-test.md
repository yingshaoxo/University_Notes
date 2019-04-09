## 光发送机测试

#### 一、光纤系统传输的码型

##### 1. 对于`电接口`

###### 对于 PCM

**Ｅ1**: 2 Ｍbit/s, HDB3
**Ｅ2**: 8 Mbit/s, HDB3
**Ｅ3**: 34 Mbit/s, HDB3
**Ｅ4**: 139 Mbit/s, CMI

> E1指`一次集群`， 以此类推

###### 对于 Ethernet

**Eth(Ethernet)**: 10 Mbit/s，曼彻斯特编码(Manchester Encoding)
**FE(Fast_Ethernet)**: 100 Mbit/s，曼彻斯特编码(Manchester Encoding)
**GE(Gigabit_Ethernet)**: 1000 Mbit/s，曼彻斯特编码(Manchester Encoding)

##### 2. 对于`光接口`

###### For SDH(Synchronous optical networking)

**STM-1**： 155 Ｍb/s, NRZ encoding
**STM-4**： 622 Ｍb/s, NRZ encoding
**STM-16**： 2488 Ｍb/s, NRZ encoding
**STM-64**： 9953 Ｍb/s, NRZ encoding

> STM: Synchronous Transport Module

###### For Ethernet

**Eth(Ethernet)**: 10 Mbit/s，mBnB
**FE(Fast_Ethernet)**: 100 Mbit/s，mBnB
**GE(Gigabit_Ethernet)**: 1000 Mbit/s，mBnB

> mBnB take m bits of the original data and encode them into n bits
