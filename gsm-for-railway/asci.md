> 大三角: `列车调度员`、`车站值班员`和`机车司机`

> 小三角: `车站值班员`、`机车司机`和`运转车长`

> 基站 = BTS + BSC

## Advanced Speech Call Items

#### 优先级业务 eMLPP (Enhanced Multi Level Precedence and Pre-emption)

分配优先级 + 级别高的建立呼叫时间短 + 级别高的能抢占资源

1. 优先级
2. 呼叫建立时间: 从用户按下“发送键”开始，到被叫用户能振铃为止
3. 资源抢占能力: 由优先级、呼叫建立时间决定

#### 组呼业务 VGCS (voice group call service)

一组ID + 组呼区域

> 一组ID: 标明不同的成员

组呼区域: 地理覆盖, <= 25个小区

无线信道资源分配: “一对半信道”比“一对信道”多用了一对`TCH上下行信道`，流程变复杂，提高了越区切换的能力。

建立过程:

![](/assets/移动业务用户在主控MSC发起组呼.jpg)

#### 广播业务 VBS (Voice broadcasting service)

聆听者不能变为讲话者


