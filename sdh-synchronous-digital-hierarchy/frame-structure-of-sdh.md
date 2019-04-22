## SDH的帧结构

![](/assets/STM-1帧结构.png)

> 这个图你得会画

> STM-4，N=4

STM-1 速率: $$9 \times 270 \times 1 \times 8(bit/s) \times 8000(frame/s) = 155 Mbit/s$$

STM-4 速率: $$9 \times 270 \times 4 \times 8(bit/s) \times 8000(frame/s) = 622 Mbit/s$$

...

它们的帧周期都是 $$125\mu s$$

传输方式: 从左到右，从上到下

OH(overhead): 开销，overhead cost or expense.

RSOH(Regeneration Section Overhead): 再生段开销

AU4P(AU-4 Pointers): 管理单元指针

MSOH(Multiplex Section Overhead): 复用段开销

> 你可以试着理解一下，但维基百科上都没写清楚，似乎不需要你理解

___

![](/assets/STM-1的段开销字节.png)

`STM-N`有 $$3 \times N$$个`A1`，`A1`连续排列

`STM-N`有 $$N$$个`E1`，`E1`连续排列

* 定帧字节: A1 和 A2。用来判定STM-*，以及识别一帧的起始位置。如果连续5帧都搜不到A1、A2，将产生`ROOF(报警)`，持续3ms后，又会产生`LOF(loss of frame 报警)`，此时它会向`下游设备`发送全”1“信号。`下游设备`如果接收到全`1`，会产生`AIS(报警)`

* 再生段追踪字节: J0

* 数据通信通路(Data Communication Channel): D1~D12

___

Reference:

https://en.wikipedia.org/wiki/STM-1