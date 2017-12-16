#### 串联时，电压按电阻值比例进行分压（分配电压）

![](/assets/fenya, chuanlian.png)

$$
\begin{align*}
U_{R_2} = \frac{R_2}{R_1 + R_2} \cdot U_s
\end{align*}
$$

```
    \draw (0, 0) to [V=$V_s$](0, 2) 
    to [R=$R_1$](2, 2)
    to [R=$R_2$](4, 2)
    to (4, 0) to (0, 0);
```

#### 并联时，电流按电阻值比例进行奇怪的分流（分配电流）

![](/assets/fenliu, binglian.png)

$$
\begin{align*}
I_{R_1} = \frac{R_2}{R_1 + R_2} \cdot I_{all}
\end{align*}
$$

```
    \draw (0, 0) to [short, i=$I_{all}$](2, 0)
    (2, 0) to (2, 1)
    to [R=$R_1$](4, 1)
    (2, 0) to (2, -1)
    to [R=$R_2$](4, -1);
```
___

Just to be clear, all those things are based on ohm's law.
___

在直流情况下，

电感器相当于一条导线，电压值为0，有电流值

电容器相当于开路，电流值为0，有电压值

我们这里讲的值是相对于这个元件来讲的，是指其元件两端的电压差或经过元件的电流值
