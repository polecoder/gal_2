# Ejercicio 2

## Consigna

Sea $AX = b$ un sistema de ecuaciones donde:  
$$
A =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
1 & 1
\end{pmatrix},\quad
b =
\begin{pmatrix}
1 \\
1 \\
0
\end{pmatrix}
$$

1. Resolver $AX = b$  
2. Encontrar la "mejor solución" $X$ aplicando el método de mínimos cuadrados, es decir, hallar $X$ que minimice $\|AX - b\|$

## Resolución

### Parte 1

Para resolver $AX=b$ planteamos el siguiente sistema:

$$
AX=b\iff
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
1 & 1
\end{pmatrix}
\cdot
\begin{pmatrix}
x\\
y
\end{pmatrix}=
\begin{pmatrix}
1 \\
1 \\
0
\end{pmatrix}
$$

Esto nos deja con las siguientes ecuaciones:

- $x=1$
- $y=1$
- $x+y=0\iff 1+1=2\neq0$

Por lo tanto el sistema no tiene solución exacta.

### Parte 2

Ya que vimos que el sistema no tiene una solución exacta, podemos hallar la "mejor solución" $X$ en el sentido de mínimos cuadrados, tal que $X$ minimice $\|AX-b\|$.

Para esto, planteamos el sistema normal para este caso, es decir:

$$
A^tAX=A^tb
$$

Cálculemos $A^tA$ y $A^tb$

$$
A^tA=\begin{pmatrix}1&0&1\\0&1&1\end{pmatrix}\cdot\begin{pmatrix}1&0\\0&1\\1&1\end{pmatrix}=\begin{pmatrix}2&1\\1&2\end{pmatrix}\\
A^tb=\begin{pmatrix}1&0&1\\0&1&1\end{pmatrix}\cdot\begin{pmatrix}1\\1\\0\end{pmatrix}=\begin{pmatrix}1\\1\end{pmatrix}
$$

Entonces planteamos el sistema normal con las matrices obtenidas:

$$
A^tAX=A^tb\\
\begin{pmatrix}2&1\\1&2\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}1\\1\end{pmatrix}
$$

Veamos las soluciones para este sistema:

$$
\left(
\begin{array}{cc|c}
2&1&1\\
1&2&1
\end{array}
\right)
$$

- $x=1-2y$
- $2(1-2y)+y=1\iff2-4y+y=1\iff1=3y\iff y=\frac{1}{3}$

Entonces $x=\frac{1}{3}$.

Por lo tanto, el vector $X_0$ que minimiza el error es $X_0=(\frac{1}{3}, \frac{1}{3})^t$