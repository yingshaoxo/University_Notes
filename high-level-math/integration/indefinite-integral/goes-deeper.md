# Goes deeper

## Priciple

With goes down to those hard problems, I want to let you know a priciple that we use in general math problem:

> We always split hard problem to multiple easy problems or step by step simplify hard problem.

In computer science, we named it `Divide & Conquer` \(`D&C algorithms`\)

## Simple one

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
=& 1 \int \frac{1}{\sqrt{1-(\frac{x}{a})^2}} d(\frac{x}{a})    &\text{//divide } a \text{ in x of dx while keep equation balance}
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

$$
\begin{align*}
\\ \\ \\
&\int \frac{1}{x^2 - a^2} dx ,(a \neq 0)
\\ \\
=& \int \frac{1}{(x+a)(x-a)} dx
\\ \\
=& \frac{1}{2a} \int (\frac{1}{x-a} - \frac{1}{x+a}) dx
\\ \\
\text{//}& \frac{1}{x-a} - \frac{1}{x+a} = \frac{x+a-x+a}{(x-a)(x+a)} = \frac{2a}{(x-a)(x+a)}
\\ \\
\text{//}&\text{ Because }2a \neq 1 \text{, divide 2a, that is, times} \frac{1}{2a} \text{in the beginning}
\\ \\
=& \frac{1}{2a}(\int \frac{1}{x-a} dx - \int \frac{1}{x+a} dx)
\\ \\
=& \frac{1}{2a}(\int \frac{1}{x-a} d(x-a) - \int \frac{1}{x+a} d(x-a))    &\text{//don't forget the basic temple for solving integral eqution}
\\ \\
=& \frac{1}{2a} \ln{|\frac{x-a}{x+a}|} + C
\\ \\ \\
\end{align*}
$$

## Complex one

$$
\begin{align*}
&\int \frac{1}{1 - \sqrt{x}} dx
\\ \\
& \text{make } \sqrt{x}=t \text{ , then } x=t^2
\\ \\
=& \int \frac{1}{1-t} d(t^2)
\\ \\
=& \int \frac{2t}{1-t} d(t)
\\ \\
=& 2 \int \frac{t}{1-t} d(t)
\\ \\
=& -2 \int \frac{t}{t-1} d(t)
\\ \\
=& -2 \int \frac{t-1+1}{t-1} d(t)
\\ \\
=& -2 \int \frac{t-1}{t-1} dt -2 \int \frac{1}{t-1} dt
\\ \\
=& -2 \int 1 dt -2 \int \frac{1}{t-1} dt
\\ \\
=& -2t - 2 \ln{|t-1|} + C
\\ \\
=& -2\sqrt{x} - 2 \ln{|\sqrt{x}-1|} + C
\end{align*}
$$

## Conclusion

1. Keep equation balance
2. Best way to deal with $$\sqrt{}$$ is to replace it with a symbol
3. Molecular is a constant is more convenient for us to solve equation, especially when it is $$1$$ \(for example: extract a constant out, and put it in front of $$\int$$\)

