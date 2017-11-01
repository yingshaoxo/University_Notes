If anything goes well, it indeed has a general model for you guys getting limitation from a limit equation.

```
if equation is a fraction:
    if fraction + or - a fraction:
        reduce fractions into one fraction by setting a common denominator
    if equation has radical sign:
        get rid of it by rationalizing.
    if put giving_x into equation getting "0/0":
        do factorization, get rid of one factor which make equation looks like "0/0"
if equation is not a fraction: # combined with simple +-x/
    put giving_x in equation directly
```

#### Example
$$
\begin{align*}

& \lim_{x \to +\infty}{\sqrt{x^2 - 1} - x}
\\ \\
= & \lim_{x \to +\infty}{\frac{\sqrt{x^2 - 1} - x}{1}}
\\ \\
= & \lim_{x \to +\infty}{\frac{(\sqrt{x^2 - 1} - x) (\sqrt{x^2 - 1} + x)}{1(\sqrt{x^2 - 1} + x)}}
\\ \\
= & \lim_{x \to +\infty}{\frac{x^2 - 1 - x^2}{\sqrt{x^2 - 1} + x}}
\\ \\
= & \lim_{x \to +\infty}{\frac{-1}{\sqrt{x^2 - 1} + x}}
\\ \\
= & \lim_{x \to +\infty}{\frac{-1}{\frac{\sqrt{x^2 - 1} + x}{x}}}
\\ \\
= & \lim_{x \to +\infty}{\frac{-1}{\sqrt{\frac{x^2}{x^2} - \frac{1}{x}} + \frac{x}{x}}}
\\ \\
= & \lim_{x \to +\infty}{\frac{-1}{\sqrt{1 - \frac{1}{x}} + 1}}
\\ \\
= & \frac{-1}{\sqrt{1 - \frac{1}{+\infty}} + 1}
\\ \\
= & \frac{-1}{\sqrt{1 - 0} + 1}
\\ \\
= & -\frac{1}{2}
\end{align*}
$$
