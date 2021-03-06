# Structure of GSM-R

## GSM-R 的网络结构

电路交换部分\(打电话部分\):

![](../.gitbook/assets/the_structure_of_GSM_R.jpg)

组成: 移动台\(Mobile station, MS\)，Base station subsystem\(BSS\)，Network switching subsystem\(NSS\)，Operation Support Subsystem\(OSS\)

> 这里的移动台分为: 1. OPH\(Operational Purpose Handheld\)\(手持机\)\(比传统手机多两个键: PTT\(push to talk\)、紧急呼叫键\)； 2.机载台\(CIR\)\(Cab Integrated Radio\)

### BSS\(Base subsystem\)

#### BTS\(Base transceiver station\):

由 天线、耦合系统\(连接天线与收发信机的部分\)、收发信机\(TRX\)、公共功能单元\(BCF, base station control function\) 构成

> A BTS is controlled by a parent BSC via the "base station control function" \(BCF\). The BCF is implemented as a discrete unit or even incorporated in a TRX in compact base stations.

一个 TRX 管理一个 TDMA 帧 = 1个频点 = 8个时隙 = 8个用户

一个`基站小区`有一个 TRX

一个`铁路位置区`至少有4个`基站小区` = 4个频点 = 4个TRX

> 按照概念的从大到小: 服务区 -&gt; PLMN -&gt; 若干MSC区 -&gt; 若干位置区 -&gt; 若干基站区

#### BSC\(Base station controler\):

由 处理单元、交换机矩阵单元、中继控制单元 组成

#### TRAU\(Transcoder and Rate Adaptation Unit， 转码器 和 速率适配单元\)

由 编\(译\)码器、控制器、外部PCM接口 组成

把`RPE-LTP编码`转为`PCM编码`

把`13kbit/s`转为`64kbit/s`

把BSC过来的`1线120个用户`转为`4线，毎线30个用户`，送给GMSC/VLR

### NSS\(Network subsystem\)

#### MSC\(mobile switching center\)

每个路局放一个，共19个

#### HLR\(home location register\)

#### VLR\(visitor location register\)

放置上，靠近MSC

#### AuC\(authentication center\)

#### EIR\(Equipment Identity Register\)

存储 IMEI\(International Mobile Equipment Identity\)

#### GCR\(Group Call Register\)

存储`移动用户组的ID`、`要呼叫的小区`信息 ...

放置上，也靠近MSC

#### IWF\(inter-working function，互连功能\)

MSC上的模块，可以让`GSM-R系统`与其他网络连接

#### SmS-SC\(短消息服务中心\)

在铁路上，并不被使用

### OSS\(Operate subsystem\)

OMC-R: 管理BSS, R is for radio

OMC-S: 管理NSS, S is for switch

OMC-F: 管理FAS, F is for FAS

## Question and Answer

### 简述 TRAU 的组成与功能

**组成**: 编\(译\)码器、控制器、外部PCM接口

**功能**:

把`RPE-LTP编码`转为`PCM编码`

把`13kbit/s`转为`64kbit/s`

把`1线120个用户`转为`4线，毎线30个用户`

