Here we talk about response.

Generally, you must give something first, then you can get a response.

In this way, in electrical circuit, every time I change that circuit, I'll get different response or result.

In English courses, I've learned `natural response` and `step response`, but if you ask me what are those things, for my poor understanding, I can't tell you.

___

But I can tell you what my Chinese teacher said: 
> **See that changes as two stage, `before`($$0_-$$) and `after`($$0_+$$)**.
> In the two stage, **inductor's current and capacitor's voltage won't change**.

___

在图示电路中，试确定开关 $$S$$ 刚断开后的电压 $$u_c$$ 和 电流 $$i_c$$、$$i_1$$、$$i_2$$ 的初始值（$$s$$ 断开前电路已处于稳态）

![](/assets/dianlu_StateChange0.png)

(1)
$$t=0$$ , capacitor 变成开路，$$I_C(0_\_) = 0$$

此时`Capacitor`相当于与最右边的电阻器并联，此时它们俩的电压相等

现在假设左边的电阻器为 $$R_1$$ ， 右边的电阻器为 $$R_2$$， 最左边的电压源为 $$U_S$$

According to `CVL`, $$U_C(0_\_) = U_S \cdot \frac{R_{R_2}}{R_{R_1} + R_{R_2}} = 6 \cdot \frac{4}{6} = 4 V$$

(2)
Above question ask for the circuit information after switch has been opened.

Based on previous theory, we know capacitor's voltage won't change after circuit has been changed.

So $$U_C(0_+) = U_C(0_-) = 4V$$

(3)
After the switch opened, line $$R_2$$ has no current flow in, so $$i_2 = 0 A$$

By that time, only a loop of $$U_S$$, $$R_1$$, and $$Capacitor$$ has been left.

根据`KVL`， 电压在一个 loop 里升降平衡， $$U_S$$ 升 $$6V$$， $$Capacitor$$ 降 $$4V$$， $$R_1$$ 只能是降 $$2V$$.

$$U_S - U_{R_1} - U_C = 6 - U_{R_1} - 4 = 0$$ ， $$U_{R_1} = 2 $$ 

So $$i_1 = \frac{U_{R_1}}{R_{R1}} = \frac{2}{2} = 1 A$$