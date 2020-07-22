# Capacitor

## Unit

The unit of capacitance $$C$$ is the farad \(symbol: $$F$$\), but it is too large for normal usage. So a more common unit is `microfarad`, abbreviated as $$\mu F$$ \($$1\mu F == 10^{-6}F$$\)

$$
\begin{align*}
u &= \sqrt{2} U \sin(wt + \psi_u)
\\ \\ \\
i =  C\frac{du}{dt} = C \cdot u^\prime &= \sqrt{2} wCU \cos(wt + \psi_u) = \sqrt{2}wCU \sin(wt + \psi_u + \frac{\pi}{2})
\\ \\
i &= \sqrt{2} I \sin(wt + \psi_u + \frac{\pi}{2}) = \sqrt{2} I \sin(wt + \psi_i)
\end{align*}
$$

So here we can see:

$$
\begin{align*}
I &= wCU
\\ \\
\psi_i &= \psi_u + \frac{\pi}{2}
\end{align*}
$$

在电感元件中，电流的相位 $$\psi_i$$ 超前电压的相位 $$\psi_u$$ $${90}^\circ$$

Actually, $$\frac{1}{wC}$$ is just like a resistor value $$R$$ in $$I = \frac{U}{R}$$

So we call $$\frac{1}{wC}$$ `capacitive reactance (容抗)`. $$\Omega$$ is the unit of him.

