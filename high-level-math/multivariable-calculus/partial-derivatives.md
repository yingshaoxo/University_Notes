# Partial derivatives

Partial derivatives

> a derivative of `a function of two or more variables` with respect to one variable, the other\(s\) being treated as constant.

$$
\begin{align*}

z &= \arctan{\frac{y}{x}}
\\ \\ \\
\frac{\partial z}{\partial x} &= \frac{1}{1 + {\frac{y}{x}}^2} \cdot [y \cdot (-1 \cdot x^{-2})] = - \frac{y}{x \left(x + y^{2}\right)}
\\ \\

\frac{\partial z}{\partial y} &= \frac{1}{1 + {\frac{y}{x}}^2} \cdot [\frac{1}{x} \cdot 1] = \frac{1}{x + y^2}
\\ \\ \\

\frac{\partial^2 z}{\partial x^2} &= \frac{y}{x \left(x + y^{2}\right)^{2}} + \frac{y}{x^{2} \left(x + y^{2}\right)}
\\ \\
\frac{\partial^2 z}{\partial y^2} &= - \frac{2 y}{\left(x + y^{2}\right)^{2}}
\\ \\
\frac{\partial^2 z}{\partial y \partial x} &= \frac{\partial^2 z}{\partial x \partial y} = - \frac{1}{\left(x + y^{2}\right)^{2}}

\end{align*}
$$

So, I really wanna say, all those things is about who you should treat as `variable`, who you should treat as `constant`

For example:

$$\frac{\partial z}{\partial x}$$, you should see $$x$$ as `variable`, $$y$$ as `constant`

$$\frac{\partial z}{\partial y}$$, you should see $$y$$ as `variable`, $$x$$ as `constant`

And for $$\frac{\partial^2 z}{\partial x \partial y}$$, first see $$x$$ as `variable`, do calculation, then see $$y$$ as `variable`, get result

