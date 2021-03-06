# Response

Here we talk about response.

Generally, you must give something first, then you can get response.

In this way, in electrical circuit, every time we change that circuit, we'll get different response or result in return.

In `Khan Academy` courses, I've learned `natural response` and `step response`, but if you ask me what those things are, for my poor understanding, I can't tell you.

But I can tell you what my Chinese teacher said:

> **See that changes as two stage,** `before`**\(**$$0_-$$**\) and** `after`**\(**$$0_+$$**\)**. In the two stage, **inductor's current and capacitor's voltage won't change**.

在图示电路中，试确定开关 $$S$$ 刚断开后的电压 $$u_c$$ 和 电流 $$i_c$$、$$i_1$$、$$i_2$$ 的初始值（$$s$$ 断开前电路已处于稳态）

![](../../.gitbook/assets/dianlu_StateChange0.png)

```text
    \draw (0, 0) to [V=$6V$](0, 4)
    to [R=$2 \Omega$, i>^=$i_1$](3, 4) 
    (3, 4) to [opening switch](6, 4)
    to [R=$4 \Omega$, i>^=$i_2$](6, 0)
    to (3, 0)
    (3, 4) to [C, l_=$C$, v^=$u_C$, i>_=$i_C$](3, 0)
    to (0, 0);
```

\(1\) $$t=0$$ , 因为 Capacitor 阻断直流电流， so $$i_C(0_\_) = 0$$

此时`Capacitor`相当于与最右边的电阻器并联，它们俩的电压相等

现在假设左边的电阻为 $$R_1$$ ， 右边的电阻为 $$R_2$$， 最左边的电压源电压为 $$u_S$$

According to `CVL`, $$uu_C(0_\_) = u_S \cdot \frac{R_2}{R_1 + R_2} = 6 \cdot \frac{4}{6} = 4 V$$

\(2\) 上面的问题问开路（开关打开）后电路各元件的信息

Based on previous theory, we know capacitor's voltage won't change after circuit changed.

So $$u_C(0_+) = u_C(0_-) = 4V$$

\(3\) After the switch opened, line of $$R_2$$ has no current flow in, so $$i_2 = 0 A$$

By that time, only **one loop** of \($$Source$$, $$R_1$$, and $$Capacitor$$\) has been left.

根据`KVL`， 电压在一个 loop 里升降平衡， $$u_S$$ 升 $$6V$$， $$u_{Capacitor}$$ 降 $$4V$$， $$u_{R_1}$$ 只能是降 $$2V$$.

$$U_S - U_{R_1} - U_C = 6 - U_{R_1} - 4 = 0$$ ， $$U_{R_1} = 2$$

So $$i_1 = \frac{U_{R_1}}{R_{R1}} = \frac{2}{2} = 1 A$$

