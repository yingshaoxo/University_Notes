## SDH的帧结构

![](/assets/STM-1帧结构.png)


> 这个图你得会画

> STM-4，N=4

STM-1 速率: $$9 \times 270 \times 1 \times 8(bit/s) \times 8000(frame/s) = 155 Mbit/s$$

STM-4 速率: $$9 \times 270 \times 4 \times 8(bit/s) \times 8000(frame/s) = 622 Mbit/s$$

...

它们的帧周期都是 $$125\mu s$$

___

传输方式: 从左到右，从上到下

OH(overhead): 开销，overhead cost or expense.

RSOH(Regeneration Section Overhead): 再生段开销

AU4P(AU-4 Pointers)(Administrative Unit Group of level 4 Pointers): 管理单元指针

MSOH(Multiplex Section Overhead): 复用段开销

> 你可以试着理解一下，但维基百科上都没写清楚，似乎不需要你理解

#### THE SDH `MULTIPLEX SECTION`( MS n ) TRANSPORT LAYER
The MSn layer, where n denotes the multiplex level 1, 4, 16, 64 or 256.

The `multiplex section` specific OverHead (MS-OH) is used to transfer OAM information.

> OAM(Operations, administration and management)

#### THE SDH `REGENERATOR SECTION`( RS n ) LAYER
It has dedicated `Regenerator Section OverHead (RS-OH)` to provide the capability to check the connectivity, monitor the performance, and communicate with the regenerators located between two network elements.

`Forward Error Correction (FEC)` can be used to correct bit errors that occur due to the extended range of the optical signals.

___

![](/assets/STM-1的段开销字节.png)

`STM-N`有 $$3 \times N$$个`A1`，`A1`连续排列

`STM-N`有 $$N$$个`E1`，`E1`连续排列

#### 定帧字节: A1 和 A2
> A1 and A2 for frame alignment

用来判定`STM-*`，以及识别一帧的起始位置。

如果连续5帧都搜不到A1、A2，将产生`ROOF(报警)`，持续3ms后，又会产生`LOF(loss of frame 报警)`，此时它会向`下游设备`发送全”1“信号。`下游设备`如果接收到全`1`，会产生`AIS(报警)`

#### 再生段追踪字节: J0 
> J0 for identification

...

#### 数据通信通路(Data Communication Channel)字节: D1~D12
> D1 ... D3 and D4 ... D12 provide data communication channels

传输网管信息(OAM, Operations, administration and management)

#### 公务联络字节: E1、E2
> E1 and E2 are engineer order wires

提供 1 个 64kb/s 的数字电话通路

#### 使用者通路字节: F1
> F1 is a user channel

...

#### 奇偶效验字节: B1、B2
> B1 and B2 for performance monitoring

B1 监测`再生段`

B2 监测`复用段` 

#### 自动保护倒换(APS, Auto protection switching)字节: K1、K2
> K1 and K2 for `protection switching control` and `remote defect indication`

也称`自愈环技术`(`后路`不通，自动走`前路`)

切换时间 < 50 ms

> 这里的`multiplex section remote defect indication` = `复用段远端接收缺陷指示` = MS-RDI

#### 同步状态字节: S1
> S1 for synchronization status

#### 复用段远端误码块指示字节: M1
> M1 for remote error indication

> 这里的`multiplex section remote error indication` = MS-REI

___

#### 通道开销 分为

* 高阶通道开销(HP-POH)
* 低阶通道开销(LP-POH)

> 开销 = additional bytes    
___

Reference:

https://en.wikipedia.org/wiki/STM-1

<The ComSoc Guide to Next Generation Optical Transport SDH, SONET, OTN>