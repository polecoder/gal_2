# Ejercicio 5

## Consigna

Sean $T:\mathbb{R}^3\to\mathbb{R}^3$, la matriz $A=\begin{pmatrix}1&4&1\\2&1&1\\2&1&1\end{pmatrix}$ y las bases:
- $\mathcal{B}=\{(1,-1,1),(1,1,1),(1,0,0)\}$ y
- $\mathcal{A}=\{(1,2,0),(2,1,0),(1,1,1)\}$.

1. ¿Queda $T$ únicamente determinada por $A={}_{\mathcal{A}}(T)_{\mathcal{B}}$? Justifique su respuesta.
2. En caso afirmativo, hallar $T(x,y,z)$.

## Resolución

$T$ queda únicamente determinada por una justificación teórica que no logré encontrar.

Podemos usar una propiedad de la matriz asociada que es la siguiente:

$$coord_{\mathcal{A}}(T(v)) = {}_{\mathcal{A}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v)$$

Con esto, tenemos como hallar las coordenadas del transformado de un vector en la base de llegada; en base a la matriz asociada (que tenemos) y las coordenadas en la base de partida de ese mismo vector.

Hallemos $coord_{\mathcal{B}}(x,y,z)$, para poder usar la propiedad:

$$
(x,y,z) = c_1(1,-1,1)+c_2(1,1,1)+c_3(1,0,0)
$$

$$
\begin{array}{ccc|c}
1 & 1 & 1 & x\\
-1 & 1 & 0 & y\\
1 & 1 & 0 & z\\
\end{array}\rightarrow
\begin{array}{ccc|c}
1 & 1 & 1 & x\\
0 & 2 & 1 & y+x\\
0 & 0 & -1 & z-x\\
\end{array}
$$

Usando $F3-F1$ y $F2+F1$. Obtengo que:

- $c_3 = x-z$
- $c_2 = \frac{z-x+y+x}{2} = \frac{z+y}{2}$
- $c_1 = x+z-x+\frac{-z-y}{2} = \frac{z-y}{2}$

Ahora puedo plantear la propiedad:

$$
coord_{\mathcal{A}}(T(x,y,z)) = \\
\begin{pmatrix}
1&4&1\\
2&1&1\\
2&1&1
\end{pmatrix}\cdot
\begin{pmatrix}
\frac{z-y}{2} \\
\frac{z+y}{2} \\
x-z
\end{pmatrix}
$$

Para separar las cuentas, llamemos $(a,b,c) = coord_{\mathcal{A}}(T(x,y,z))$

- $a = \frac{z-y}{2}+2z+2y+x-z = \frac{3z+3y+2x}{2}$
- $b = z-y+\frac{z+y}{2}+x-z = \frac{z-y+2x}{2}$
- $c = z-y+\frac{z+y}{2}+x-z = \frac{z-y+2x}{2}$

Entonces:

$$coord_{\mathcal{A}}(T(x,y,z)) =
\begin{pmatrix}
\frac{3z+3y+2x}{2}\\
\frac{z-y+2x}{2}\\
\frac{z-y+2x}{2}
\end{pmatrix}
$$

Ahora, me queda "eliminar" las coordenadas, es decir:

$$
\begin{aligned}
T(x,y,z)&=\frac{3z+3y+2x}{2}\cdot(1,2,0)+\frac{z-y+2x}{2}\cdot((2,1,0)+(1,1,1))\\
&= \left(\frac{3z+3y+2x}{2}, 3z+3y+2x, 0\right)+\frac{z-y+2x}{2}\cdot(3,2,1)\\
&= \left(\frac{3z+3y+2x}{2}, 3z+3y+2x, 0\right) + \left(\frac{3z-3y+6x}{2}, z-y+2x, \frac{z-y+2x}{2}\right)\\
&= \left(3z+4x, 4z+2y+4x, \frac{z-y+2x}{2} \right)
\end{aligned}
$$

Entonces $T(x,y,z)$ está dada por:

$$
T(x,y,z) = \left(3z+4x, 4z+2y+4x, \frac{z-y+2x}{2} \right)
$$