# Integrated Operational Amplifier (集成运算放大器)

In China:

The $$\infty$$ 表示理想中的无限放大

![](assets/Integrated_Operational_Amplifier.png)

In United States:

![](assets/Integrated_Operational_Amplifier2.png)

___

这里补一个概念：

> 电流为0时可以有电压

> 解释： 电压一直有但没回路、没负载，电阻无穷大，电流为0

___

Inversed_Integrated_Operational_Amplifier

![](assets/Inversed_Integrated_Operational_Amplifier.png)

$$
\begin{align*}
&\because i_+ = 0 \text{ , } \therefore u_+ = 0
\\ \\
&\because u_+ = u_- \text{ , } \therefore u_- = 0
\\ \\
&\text{ } i_1 = \frac{u_i - u_-}{R_1} = \frac{u_i}{R_1} \text{ , } i_f = \frac{u_- - u_o}{R_f} = \frac{-u_o}{R_f}
\\ \\
&\because u_- \text{ and } i_- = 0 \text{, } i_1 = i_f \text{ , } \therefore u_o = -\frac{R_f}{R_1} u_i
\end{align*}
$$
