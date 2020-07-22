# Mobility Management

Mobility management is one of the major functions of a GSM or a UMTS network that allows mobile phones to work. The aim of mobility management is to track where the subscribers are, allowing calls, SMS and other mobile phone services to be delivered to them.

## 位置更新\(Location update\)

> LAI: Location area identity
>
> HLR: Home location register
>
> TMSI: Temporary Mobile Subscriber Identity

MS从`一个位置区(LAI)`移动到`另一个位置区`，需要登记。\(一旦MS`发现存储器中的LAI`与`从BCCCH接收到的LAI`不同时，就需要登记\)

* 不同 MSC/VLR \(跨越不同铁路局\): 更新HLR中的内容，分配TMSI，更新VLR里的LAI
* 同一 MSC/VLR \(同一铁路局\): 不更新HLR中的内容，不分配TMSI，更新VLR里的LAI

## 切换\(Handover\)

将`正在通话状态下的MS`切换到`新信道(TCH)`的过程。\(是否切换这个决定，由`MSC or BSC`决定\)

### 情况1， 为了负载平衡而切换

### 情况2， 从`一个位置区`切换到`另一个位置区`

> BTS ∈ BSC ∈ MSC

#### 1. 同一BSC，不同小区 \(BSC负责切换\)

MS向BSC报告`原BTS与周围BTS的信号强度`，`原BSC` `分配TCH`并发出“切换命令”

#### 2. 同一MSC/VLR，不同BSC \(MSC负责切换\)

* `MS`向`原BSC`发送“测量报告”
* `原BSC`向`原MSC`发送“切换请求”
* `原MSC`向`新BSC`发送“切换指令\(准备TCH\)”
* `新BSC`向`原MSC`发送“切换指令已收到”
* `原MSC`向`原BSC`、`MS`发送“切换命令”
* 切换完成后，`原MSC`向`原BSC`发送“清除原信道请求”，释放原来被占用的信道

#### 3. 不同MSC/VLR

* `MS`向`原BSC`发送“测量报告”
* `原BSC`向`原MSC`发送“切换请求”
* `原MSC`向`新MSC`发送“切换请求”
* `新MSC`通知`新VLR`分配TMSI
* `新MSC`通知`新BSC`分配TCH
* `新MSC`通知`原MSC`“切换TMSI”
* `原MSC`在`两个MSC之间`建立地面有线链路
* `两个MSC`同时向`各自的BSC`发送切换命令
* `MS`换频率、时隙，切换成功
* `MS`通知`上层系统`，上层释放原来被占用的信道
* 若是通话刚结束，还要做`位置登记`

