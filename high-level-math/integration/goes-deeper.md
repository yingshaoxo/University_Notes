#### Priciple

When we goes down to those hard problems, I want to let you know a priciple we using in general math problem:

> We always split hard problem to multiple easy problems or step by step simplify hard problem.

In computer science, we named it `Divide & Conquer` (`D&C algorithms`)

___

#### Simple one

$$
\begin{align*}
&\int \frac{1}{a^2 + x^2} dx
\\ \\ 
=& \frac{1}{a^2} \int \frac{1}{1 + (\frac{x}{a})^2} dx    &\text{//divide } a^2 \text{in denominator while keep equation balance}
\\ \\
=& \frac{1}{a} \int \frac{1}{1 + (\frac{x}{a})^2} d(\frac{x}{a})
\\ \\
=& \frac{1}{a} \cdot \arctan{\frac{x}{a}} + C    &\text{//}(\arctan{x})^\prime = \frac{1}{1 + x^2}
\end{align*}
$$

$$
\begin{align*}
\\ \\ \\
&\int \frac{1}{\sqrt{a^2 - x^2}} dx ,(a > 0)
\\ \\
=& \frac{1}{a} \int \frac{1}{\sqrt{1-(\frac{x}{a})^2}} dx
\\ \\
=& 1 \int \frac{1}{\sqrt{1-(\frac{x}{a})^2}} d(\frac{x}{a})    &\text{//divide } a \text{in x of dx while keep equation balance}
\\ \\
=& \arcsin(\frac{x}{a}) + C
\\ \\ \\
\end{align*}
$$


Let's try to analyze this equation:

$$
\frac{1}{a^2} \int \frac{1}{1 + (\frac{x}{a})^2} dx = \frac{a}{a^2} \int \frac{1}{1 + (\frac{x}{a})^2} d(\frac{x}{a})
$$

We knew that $$x$$ of $$dx$$ is the original function, so do $$\frac{1}{a^2}$$. Because two of them in a same original function, when $$x$$ becomes $$\frac{x}{a}$$, $$\frac{1}{a^2}$$ have to times $$a$$.

As for $$\int \frac{1}{1 + (\frac{x}{a})^2}$$, it must interact with $$dx$$, then it becomes original function.

You can see $$\int (...) d$$ as a whole thing. you also can extract a constant from it, we will talk about it later.