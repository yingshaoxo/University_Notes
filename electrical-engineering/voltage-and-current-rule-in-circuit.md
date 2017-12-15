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