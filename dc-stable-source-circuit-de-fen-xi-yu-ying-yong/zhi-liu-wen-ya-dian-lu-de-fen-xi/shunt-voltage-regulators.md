Shunt
分流

___

![](/assets/shunt voltage regulator.png)

Let me explain these symbols for you:

$$U_i$$ = $$Voltage_{\text{ } of \text{ } input}$$ 

$$I_R$$ = $$Current_{\text{ } of \text{ } Resistance}$$

$$U_R$$ = $$Voltage_{\text{ } of \text{ } Resistance}$$

$$I_Z$$ = $$Current_{\text{ } of \text{ } Zener-Diode}$$

$$D_Z$$ = $$Diode_{\text{ } of \text{ } Zener}$$

$$U_Z$$ = $$Voltage_{\text{ } of \text{ } Zener-Diode}$$

$$I_o$$ = $$Current_{\text{ } of \text{ } output}$$

$$U_o$$ = $$Voltage_{\text{ } of \text{ } output}$$

___

$$I_R = I_s = I_{source}$$

$$I_R = I_s = I_Z + I_o$$

+ Variations in Load Current
If the current in the load Iout tends to fall, the voltage across the load would tend to rise, but because it is connected in parallel with the diode the voltage will remain constant. What will change is the current ($$I_Z$$) through the diode. This will rise by an amount equal to the fall of current in the load. The total supply current $$I_s$$ being always equal to $$I_Z + I_{out}$$. An increase in load current $$I_{out}$$ will likewise cause a fall in zener current $$I_Z$$, again keeping $$U_z$$ and the output voltage steady.

+ Variations in Input Voltage
If the input voltage rises this will cause more supply current $$I_s$$ to flow into the circuit. Without the zener shunt regulator, this would have the effect of making the output voltage $$U_{out}$$ rise, but any tendency for $$U_{out}$$ to rise will simply cause the diode to conduct more heavily, absorbing the extra supply current without any increase in $$U_{Z}$$ thus keeping the output voltage constant. A fall in the input voltage would likewise cause a reduction in zener current, again keeping $$U_{out}$$ steady.