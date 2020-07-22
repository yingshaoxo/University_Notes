# Inductor

## Unit

The unit of inductance $$L$$ is the henry \(symbol: $$H$$\), but it is too large for normal usage. So a more common unit is `millihenrys`, abbreviated as $$mH$$ \($$1mH == 10^{-3}H$$\)

## Inductor i-v equation

$$v = L\frac{di}{dt}$$

## Feature

1. If a constant current flows in an inductor, then $$\frac{dt}{di} = 0$$ \(a constant's derivative is 0\), so in that case, there is zero voltage across the inductor.（Zero voltage means an inductor with constant current looks like a short circuit, the same as a plain wire.）
2. The current in an inductor does not \(will not\) change instantaneously.

$$
\begin{align*}
i &= \sqrt{2} I \sin(wt + \psi_i)
\\ \\ \\
u =  L\frac{di}{dt} = L \cdot i^\prime &= \sqrt{2} wLI \cos(wt + \psi_i) = \sqrt{2}wLI \sin(wt + \psi_i + \frac{\pi}{2})
\\ \\
u &= \sqrt{2} U \sin(wt + \psi_i + \frac{\pi}{2}) = \sqrt{2} U \sin(wt + \psi_u)
\end{align*}
$$

So here we can see:

$$
\begin{align*}
U &= wLI
\\ \\
\psi_u &= \psi_i + \frac{\pi}{2}
\end{align*}
$$

在电感元件中，电压的相位 $$\psi_u$$ 超前电流的相位 $$\psi_i$$ $${90}^\circ$$

Actually, $$wL$$ is just like a resistor value $$R$$ in $$U = RI$$

So we call $$wL$$ `inductive reactance (感抗)`. $$\Omega$$ is the unit of him.

