# 一阶电路的全响应

在这里修复一些理解上的错误，同时回到实际题目（即使我们都知道，题目并不是实际，但目前不是远古时代靠单纯实验就能做事，现在做事有太多抽象的预测）

全响应，并没有彻底断电或处于从零开始的充电过程，而是对电量大小进行调整，从一个级别到另一个级别

因为我们目前仍在用线性元件，所以电路信息也遵循线性代数的基本原则，可叠加：

$$
\begin{align*}
&全响应=零输入响应+零状态响应
\\ \\
f(t) &= f(0_+) \cdot e^{- \frac{t}{\tau}} + f(\infty) \cdot (1 - e^{- \frac{t}{\tau}})
\end{align*}
$$

本节之前，我也不懂 $$f(0_+)$$ 与 $$f(\infty)$$ 有何不同

$$
\begin{align*}
\\
稳态 |_{t=0} \rightarrow f(t) \leftarrow | 稳态_{t=\infty}
\\ \\
\end{align*}
$$

$$f(0_-)$$ 或 $$f(0_+)$$ 只是指 $$f(t=0)$$ 那一瞬间前后的值 \( $$f(0_-)$$ 指之前， $$f(0_+)$$ 指之后\)

$$f(\infty)$$ 则是指随着 $$f(t)$$ 中的 $$t$$ 不断增大， $$f(t)$$ 整体的值已经达到一种稳定状态，基本不变

具体来讲， $$f(0_+)$$ 永远由 $$f(0_-)$$ 求出 \(他俩相等\)。而 $$f(0_-)$$ 永远在开关改变前的电路得到

$$f(\infty)$$ 永远在开关改变后的电路得到

如图所示电路中，已知 $$U_s=30V$$， $$R_1=100\Omega$$， $$C_1=0.2\mu F$$， $$R_2=200\Omega$$， $$C_2=0.1\mu F$$，换路前电路处于稳态。试求 $$t \geq 0$$ 时的 $$u_{C1}(t)、u_{C2}(t)、i(t)$$

![](https://github.com/yingshaoxo/university-notes/tree/cc7cb1e4698c6d680876321163907ff1e1b4ac91/electrical-engineering/response/assets/Response_FullVersion.png)

```text
    \draw (0, 0) to [V=$U_s$](0, 4)
    to [short, i=$i$](3, 4)
    (3, 4) to [C, l=$C_1$, v=$u_{C1}$](3, 2) 
    to [R, l_=$R_1$](3, 0) to(0, 0)

    (3, 4) to (6, 4)
    to [R=$R_2$](6, 2)

    (6, 2) to [opening  switch, l=$S$](3, 2)
    (6, 2) to [C, l=$C_2$, v=$u_{C2}$](6, 0)
    to (3, 0);
```

$$
\begin{align*}
\\

\text{1. } & \text{When switch on, 电流从两个电阻穿过，两个电容分别与对应的两个电阻并联}
\\ \\
& u_{C1}(0_+) = u_{C1}(0_-) = U_s \cdot \frac{R_2}{R_1 + R_2} = 30 \cdot \frac{200}{100 + 200} = 20 V
\\ \\
& u_{C2}(0_+) = u_{C2}(0_-) = U_s \cdot \frac{R_1}{R_1 + R_2} = 30 \cdot \frac{100}{100 + 200} = 10 V
\\ \\

\text{2. } & \text{When switch off, 去掉开关，两个电阻分别与对应电容串联}
\\ \\
& \text{1. 直流电下，电容断电流}
\\
& \text{2. 两个电阻上都没电流, 故没电压}
\\
& \text{3. 两条并联支路上只剩电容的电压}
\\
& \text{4. 并联电压相等，两个电容在这种情况下，其电压等于电压源}
\\ \\
& u_{C1}(\infty) = u_{C2}(\infty) = u_S = 30V
\\ \\
& \text{1. } \tau \text{ 中的 }  R \text{ 是指把其他电源“置零”后，从电容流出的电所经过的电阻值“总和”}
\\
& \text{2. “置零方法”：电压源变导线，电流源变断路}
\\
& \text{3. 别忘了，电容释放的电遇到另一个电容还是会断流}
\\ \\
& \tau_{C1} = R \cdot C = 100\Omega \cdot (0.2 \cdot 10^{-6} F) = 20 \cdot 10^{-6} F
\\ \\
& \tau_{C2} = R \cdot C = 200\Omega \cdot (0.1 \cdot 10^{-6} F) = 20 \cdot 10^{-6} F
\\ \\

\text{3. } & \text{套公式，得到关于时间 t 的关系式}
\\ \\
& u_{C1}(t) = u_{C1}(0_+) \cdot e^{- \frac{t}{\tau_{C1}}} + u_{C1}(\infty) \cdot (1 - e^{- \frac{t}{\tau_{C1}}})
\\ \\
& = 20 \cdot e^{-\frac{t}{20 \cdot 10^{-6} F}} + 30 \cdot (1 - e^{-\frac{t}{20 \cdot 10^{-6} F}})
\\ \\
& = 30 - 10 \cdot e^{-50000t}
\\ \\
& u_{C2}(t) = u_{C2}(0_+) \cdot e^{- \frac{t}{\tau_{C2}}} + u_{C2}(\infty) \cdot (1 - e^{- \frac{t}{\tau_{C2}}})
\\ \\
& = 10 \cdot e^{-\frac{t}{20 \cdot 10^{-6} F}} + 30 \cdot (1 - e^{-\frac{t}{20 \cdot 10^{-6} F}})
\\ \\
& = 30 - 20 \cdot e^{-50000t}
\\ \\

\text{4. } & \text{求电流} i(t)
\\ \\
& \text{1. 我们是求的一个过程，一个代表改变的式子}
\\
& \text{2. 电容是慢慢阻断直流电的，在达到稳态时才完全阻断}
\\
& \text{3. 所以我们在计算这个变化过程表达式时还要想象电阻上还有电流}
\\
& \text{4. 别忘了 KCL 定理}
\\ \\ 
& i(t) = \frac{U_s - u_{C1}(t)}{R_1} + \frac{U_s - u_{C2}(t)}{R_2}
\\ \\
& = \frac{30 - (30 - 10 \cdot e^{-50000t})}{100} + \frac{30 - (30 - 20 \cdot e^{-50000t})}{200}
\\ \\ 
& = \frac{10 \cdot e^{-50000t}}{100} + \frac{20 \cdot e^{-50000t}}{200}
\\ \\
& = 0.2 \cdot e^{-50000t} A

\end{align*}
$$

