#### Hospital Rule (某法则求 0:0 或 ∞:∞ 极限)
When you encounter some limitation formulas after giving `approaching x` seems like $$\frac{0}{0}$$ or $$\frac{\infty}{\infty}$$, you can get its molecular and denominator's first derivative partly, then do this process again and again until you get some limitation value that not seems like $$\frac{0}{0}$$ or $$\frac{\infty}{\infty}$$

```
formula = a fractional limitation formula
molecular, denominator = split_fraction(formula)

while True:
    i = 0

    molecular_limitation_value = get_limitation_value(molecular)
    denominator_limitation_value = get_limitation_value(denominator)

    if '{m}:{d}'.format(m=molecular_limitation, d=denominator) in ['0:0', '∞:∞']:
        molecular = take_first_derivative(molecular)
        denominator = take_first_derivative(denominator)
        i += 1
    else:
        return molecular_limitation_value / denominator_limitation_value

    if i > 999:
        print("You can't use hospital rule in this formula.")
```

$$
\begin{align*}
&\lim_{x \to 0}{\frac{\sin x - e^x + 1}{1 - \sqrt{1 - x^2}}}
\\ \\
{\frac{0}{0}} \atop =& \lim_{x \to 0}{\frac{\cos x - e^x}{-\frac{1}{2}(1 - x^2)^{-\frac{1}{2}} \cdot (-2x)}}
\\ \\
{\frac{0}{0}} \atop =& \lim_{x \to 0}{\frac{- \sin x - e^x}{-\frac{1}{4} (1 - x^2)^{-\frac{2}{3}} \cdot (-2x) + [-\frac{1}{2}(1 - x^2)^{-\frac{1}{2}} \cdot (-2)]}}
\\ \\
=& \frac{0}{1} = 0
\end{align*}
$$
___

#### 耗费最小化，利益最大化
