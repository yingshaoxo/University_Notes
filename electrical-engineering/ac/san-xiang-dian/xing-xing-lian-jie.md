# 星形联结

把三相电源的三个负极 $$X$$、$$Y$$、$$Z$$ 接在一起，再从三个正极 $$A$$、$$B$$、$$C$$ 引出导线来，这种联结方式叫做`星型联结`。（至于为什么取这个名字，大概是因为它长得像星星吧）

![](https://github.com/yingshaoxo/university-notes/tree/cc7cb1e4698c6d680876321163907ff1e1b4ac91/electrical-engineering/ac/assets/SanXiangDianXingXingLianJie.png)

As we can see, if we assume that 三个负极所在的联结点为 $$N$$，本质上 $$\dot U_{AN} = \dot U_{A}$$、$$\dot U_{BN} = \dot U_{B}$$、$$\dot U_{CN} = \dot U_{C}$$，我们仍称 $$\dot U_{AN}$$、$$\dot U_{BN}$$、$$\dot U_{CN}$$ 为相电压

但有时，相电压提供的电压无法满足 our needs. We need a larger voltage source.

So we connect AB, BC, and CA, representing it as $$\dot U_{AB}$$、$$\dot U_{BC}$$, and $$\dot U_{CA}$$。我们称它们为线电压。

According to `Kirchhoff's Voltage Law`, `电压从一点到另一点降了多少`被称为这两点间的电压，所以有：

$$
\begin{align*}
\dot U_{AB} &= \dot U_{AN} - \dot U_{BN} = \dot U_A - \dot U_B
\\ \\
\dot U_{BC} &= \dot U_{BN} - \dot U_{CN} = \dot U_B - \dot U_C
\\ \\
\dot U_{CA} &= \dot U_{CN} - \dot U_{AN} = \dot U_C - \dot U_A
\end{align*}
$$

经过一系列的数学运算，我们发现线电压的模长\(即有效值 $$U$$\)永远是相电压的 $$\sqrt{3}$$ 倍。$$\sqrt{3} \approx 1.7$$，电压增大，满足了我们的需要。

另外，线电压在相位上永远比相电压超前 $$30^\circ$$

![](https://github.com/yingshaoxo/university-notes/tree/cc7cb1e4698c6d680876321163907ff1e1b4ac91/electrical-engineering/ac/assets/SanXiangDianXianDianYa.png)

$$
\Bigg{\Updownarrow}
$$

$$
\begin{align*}
\dot U_{AB} &= \sqrt{3} U \angle{(0^\circ + 30^\circ)}
\\ \\
\dot U_{BC} &= \sqrt{3} U \angle{(-120^\circ+ 30^\circ)}
\\ \\
\dot U_{CA} &= \sqrt{3} U \angle{(120^\circ+ 30^\circ)}
\end{align*}
$$

