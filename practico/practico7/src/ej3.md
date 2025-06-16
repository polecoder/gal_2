# Ejercicio 3

## Consigna

En un experimento se midió según el tiempo una cierta magnitud $y$, obteniéndose los siguientes valores:

| $t$ | $y$ |
|----|----|
| 0  |  0 |
| 1  |  1 |
| 3  |  2 |
| 4  |  5 |

1. Aplicando el método de mínimos cuadrados, hallar la mejor recta que ajuste los datos anteriores ($y = \alpha t + \beta$)
2. Aplicando el método de mínimos cuadrados, hallar la mejor parábola que ajuste los datos anteriores ($y = \alpha t^2 + \beta t + \gamma$).

## Resolución

### Parte 1

Construyamos las matrices que precisamos:

- $Y=(0,1,2,5)^t$
- $A=\begin{pmatrix}0&1\\1&1\\3&1\\4&1\end{pmatrix}$
- $X=(\alpha,\beta)^t$

Con esto, planteamos el sistema normal para este caso:

$$
A^tAX=A^tY
$$

Cálculemos $A^tA$ y $A^tY$:

$$
A^tA=\begin{pmatrix}0&1&3&4\\1&1&1&1\end{pmatrix}\begin{pmatrix}0&1\\1&1\\3&1\\4&1\end{pmatrix}=\begin{pmatrix}26&8\\8&4\end{pmatrix}\\
A^tY=\begin{pmatrix}0&1&3&4\\1&1&1&1\end{pmatrix}\cdot\begin{pmatrix}0\\1\\2\\5\end{pmatrix}=\begin{pmatrix}27\\8\end{pmatrix}
$$

Ahora, hallemos $(A^tA)^{-1}$ para calcular directamente el valor de $X$:

$$
\begin{aligned}
&\left(
\begin{array}{cc|cc}
26&8&1&0\\8&4&0&1
\end{array}
\right)\\
&\sim\scriptstyle{(\frac{1}{2}F_1\text{ y }\frac{1}{2}F_2)}\\
&\left(
\begin{array}{cc|cc}
13&4&\frac{1}{2}&0\\4&2&0&\frac{1}{2}
\end{array}
\right)\\
&\sim\scriptstyle{(\frac{1}{13}F_1)}\\
&\left(
\begin{array}{cc|cc}
1&\frac{4}{13}&\frac{1}{26}&0\\4&2&0&\frac{1}{2}
\end{array}
\right)\\
&\sim\scriptstyle{(F_2-4F_1)}\\
&\left(
\begin{array}{cc|cc}
1&\frac{4}{13}&\frac{1}{26}&0\\0&\frac{10}{13}&-\frac{2}{13}&\frac{1}{2}
\end{array}
\right)\\
&\sim\scriptstyle{(\frac{13}{10}F_2)}\\
&\left(
\begin{array}{cc|cc}
1&\frac{4}{13}&\frac{1}{26}&0\\0&1&-\frac{1}{5}&\frac{13}{20}
\end{array}
\right)\\
&\sim\scriptstyle{(F_1-\frac{4}{13}F_2)}\\
&\left(
\begin{array}{cc|cc}
1&0&\frac{1}{10}&-\frac{1}{5}\\0&1&-\frac{1}{5}&\frac{13}{20}
\end{array}
\right)\\
\end{aligned}
$$

Con esto, tenemos que:

$$
\begin{aligned}
X&=(A^tA)^{-1}A^tY\\
&=\begin{pmatrix}\frac{1}{10}&-\frac{1}{5}\\-\frac{1}{5}&\frac{13}{20}\end{pmatrix}\begin{pmatrix}27\\8\end{pmatrix}\\
&=\begin{pmatrix}\frac{11}{10}\\-\frac{1}{5}\end{pmatrix}
\end{aligned}
$$

Por lo tanto, la recta que mejor ajusta a estos datos es:

$$
y=\frac{11}{10}t-\frac{1}{5}
$$

### Parte 2

Análoga pero con muchas cuentas.