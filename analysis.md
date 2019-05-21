# Analysis

##### 1. 单管共射放大电路

![](/assets/single-tube_common-emitter_amplifier_circuit.png)

$$V_{cc} = I_B R_b + U_{BE}$$

$$V_{cc} = I_C R_c + U_{CE}$$

$$I_E \approx I_C = \beta I_B$$

___

##### 2. 微变等效电路

$$r_{be} \approx  300 + \beta \frac{26 mv}{I_C}$$

___

##### 3. 动态指标

$$A_u = \frac{U_o}{U_i} = \frac{- \beta i_b \cdot (R_C // R_L)}{i_b \cdot r_{be}} = \frac{- \beta \cdot (R_C // R_L)}{r_{be}}$$

$$A_u$$ 是放大倍数，对应的还有 $$A_i$$
