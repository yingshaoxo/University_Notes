# Common Emitter

In electronics, a common-emitter amplifier is one of three basic single-stage bipolar-junction-transistor (BJT) amplifier topologies, typically used as the voltage amplifier.

In this circuit the base terminal of the transistor serves as the input, the collector is the output, and the emitter is common to both (for example, it may be tied to ground reference or a power supply rail), hence its name.

![](/assets/NPN_common_emitter.png)

___

![](/assets/Common_emitter_configuration.png)

A change in base current $$\Delta I_B$$ produces a corresponding change in collector current, $$\Delta I_C$$, and the common emitter gain $$\beta$$ is then defined by

$$
\beta = \frac{\text{Change in collector current}} {\text{Change in base current}} = \frac{\Delta I_C}{\Delta I_B} |_{V_{CE}\text{ = CONSTANT}}
$$

___

之所以讲`共射电路`，是因为后面大多数时候我们能遇到的电路都是这个，而且后面知识的大体框架是一样的，只是细节不一样
___

#### Biasing (偏置)

##### 1. Introduction

Biasing in electronics means establishing predetermined voltages or currents at various points of an electronic circuit for the purpose of establishing proper operating conditions in electronic components.

这个时候你可能会想到叠加定理，是的，没错，只是我以前忘了做查询。这东西就是做叠加定理时会用到的手段。只不过这里要把概念扩大一下。

Many electronic devices such as transistors and vacuum tubes, whose function is processing time-varying (AC) signals also require a steady (DC) current or voltage to operate correctly — a bias.

这里讲的是。。。有些元件，比如三极管，既需要一个稳定的`直流电`给它把电路导通，又需要一点点`交流电`让它完成工作(比如把小信号放大：小交流电流控制大直流电流，最终输出大交流电流)

The AC signal applied to them is superposed(叠加) on this DC bias current or voltage. The operating point of a device, also known as bias point, quiescent(静态) point, or Q-point, is the steady-state (DC) voltage or current at a specified terminal of an active device (a transistor or vacuum tube) with no input signal applied. A bias circuit is a portion of the device's circuit which supplies this steady current or voltage.

然后它又说了，给`只分析直流时的电路状态`取一个名字，叫做`静态工作点`。这时的电路可以由原电路变化而来，具体做法我等会儿再讲。

##### 2. How to bias a `Bipolar Junction Transistor (三极管)`

1. 电流从 $$V_{cc}$$ 开始，到`地`为止
2. 遇到电容断路，后面的就不要了

实在不行问你老师，你可是交过钱的

##### 3. What we will get from this operation?

如果最后成功了，你会得到这个：

![](/assets/Fixed_bias_circuit.png)

$$V_{CC} = I_B R_B + V_{BE}$$

$$V_{CC} = I_C R_L + V_{CE}$$


