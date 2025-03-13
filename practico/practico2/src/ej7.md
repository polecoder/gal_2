# Ejercicio 7

## Consigna

Para las siguientes transformaciones lineales $T: \mathbb{R}^3 \to \mathbb{R}^3$, hallar los valores propios, bases de los subespacios propios e investigar si son diagonalizables.

1. $T(x, y, z) = (2y + z, 2x + z, x + y + z)$
2. $T(x, y, z) = (4x - 5y + 2z, 5x - 7y + 3z, 6x - 9y + 4z)$
3. $T(x, y, z) = (y, -4x + 4y, 2x + y + 2z)$
4. $T(x, y, z) = (2x, 2y, 2z)$

## Resolución

### Transformación #1

$T(x, y, z) = (2y + z, 2x + z, x + y + z)$

Consideremos la base canónica $\mathcal{E}$ y hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(T(1,0,0)) = (0,2,1)$
- $coord_{\mathcal{E}}(T(0,1,0))= (2,0,1)$
- $coord_{\mathcal{E}}(T(0,0,1))= (1,1,1)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
0&2&1\\
2&0&1\\
1&1&1
\end{pmatrix}
$$

Ahora hallemos el polinomio característico:

$$
\Chi_T(\lambda) = det
\begin{pmatrix}
-\lambda&2&1\\
2&-\lambda&1\\
1&1&1-\lambda
\end{pmatrix}
$$

Desarrollando por el método de Sarrus tenemos:

$$
\begin{aligned}
\Chi_T(\lambda) &= (\lambda^2(1-\lambda) + 2\cdot 1\cdot 1 + 1\cdot 2\cdot 1) - (1\cdot(-\lambda)\cdot 1 + 1\cdot 1\cdot(-\lambda) + (1-\lambda)\cdot 2\cdot 2)\\
&= (\lambda^2(1-\lambda)+4) - ((-\lambda)+(-\lambda)+ 4(1-\lambda))\\
&= (\lambda^2(1-\lambda)+4) - (-6\lambda +4)\\
&= -\lambda^3 + \lambda^2 + 6\lambda\\
&= \lambda(-\lambda^2+\lambda+6)
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 0$ de forma evidente
- $\lambda_2 = \frac{-1 + \sqrt{25}}{-2} = \frac{-1 + 5}{-2} = -2$
- $\lambda_3 = \frac{-1 - \sqrt{25}}{-2} = \frac{-1 - 5}{-2} = 3$

Con esto, ya podemos decir que la matriz es diagonalizable, porque tenemos 3 raíces con $ma(\lambda) = 1$, y sabemos que $1\leq mg(\lambda)\leq ma(\lambda)$ para todo $\lambda$

Por lo que $ma(\lambda) = mg(\lambda) = 1$ para todo $\lambda$, y todas las raíces están en el cuerpo en el que estamos trabajando.

Ahora para terminar, tenemos que hallar bases de los subespacios propios.

#### Subespacio $S_0$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-0\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0&2&1&0\\
2&0&1&0\\
1&1&1&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&1&0\\
0&2&1&0\\
2&0&1&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&1&0\\
0&2&1&0\\
0&-2&-1&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z = -2y$
- $x = -y+2y = y$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 0$ es:

$$
S_0 = \{(\alpha,\alpha,-2\alpha)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,1,-2)\}
$$

#### Subespacio $S_{(-2)}$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A+2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
2&2&1&0\\
2&2&1&0\\
1&1&3&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&3&0\\
2&2&1&0\\
2&2&1&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&3&0\\
0&0&-5&0\\
2&2&1&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z = 0$
- $x = -y + 0 = -y$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = -2$ es:

$$
S_{(-2)} = \{(-\alpha,\alpha,0)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(-1,1,0)\}
$$

#### Subespacio $S_3$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-3\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-3&2&1&0\\
2&-3&1&0\\
1&1&-2&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&-2&0\\
2&-3&1&0\\
-3&2&1&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
1&1&-2&0\\
0&-5&5&0\\
0&5&-5&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z=y$
- $x = -y+2y = y$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = 3$ es:

$$
S_3 = \{(\alpha,\alpha,\alpha)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,1,1)\}
$$

### Transformación #2

$T(x, y, z) = (4x - 5y + 2z, 5x - 7y + 3z, 6x - 9y + 4z)$

Consideremos la base canónica $\mathcal{E}$ y hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(T(1,0,0)) = (4,5,6)$
- $coord_{\mathcal{E}}(T(0,1,0))= (-5,-7,-9)$
- $coord_{\mathcal{E}}(T(0,0,1))= (2,3,4)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
4&-5&2\\
5&-7&3\\
6&-9&4
\end{pmatrix}
$$

Ahora hallemos el polinomio característico:

$$
\Chi_T(\lambda) = det
\begin{pmatrix}
4-\lambda&-5&2\\
5&-7-\lambda&3\\
6&-9&4-\lambda
\end{pmatrix}
$$

Desarrollando por el método de Sarrus tenemos:

$$
\begin{aligned}
\Chi_T(\lambda) &= ((4-\lambda)^2(-7-\lambda) + 5\cdot(-9)\cdot 2 + 6\cdot (-5)\cdot 3) - (2\cdot(-7-\lambda)\cdot 6 + 3\cdot(-9)\cdot(4-\lambda) + (4-\lambda)\cdot (-5)\cdot 5)\\
&= ((4-\lambda)^2(-7-\lambda) - 90 - 90) - (12(-7-\lambda)-27(4-\lambda)-25(4-\lambda))\\
&= ((\lambda^2-8\lambda+16)(-7-\lambda) - 180) - ((-84-12\lambda)-52(4-\lambda))\\
&= ((-\lambda^3+8\lambda^2-16\lambda - 7\lambda^2 + 56\lambda - 112) - 180) - (-84 - 12\lambda - 208 + 52\lambda)\\
&= (-\lambda^3+\lambda^2+40\lambda- 292) - (40\lambda - 292)\\
&= -\lambda^3+\lambda^2 = \lambda^2(-\lambda + 1)
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 0 \rightarrow ma(\lambda_1) = 2$ que es raíz doble
- $\lambda_2 = 1 \rightarrow ma(\lambda_2) = 1$

Ahora tenemos que hallar bases de los subespacios propios para poder determinar si $T$ es diagonalizable.

#### Subespacio $S_0$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-0\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
4&-5&2&0\\
5&-7&3&0\\
6&-9&4&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
4&-5&2&0\\
20&-28&12&0\\
24&-36&16&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
4&-5&2&0\\
0&-3&2&0\\
0&-6&4&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z = \frac{3}{2}y$
- $x = \frac{5y - 3y}{4} = \frac{1}{2}y$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 0$ es:

$$
S_0 = \{(\frac{\alpha}{2},\alpha,\frac{3\alpha}{2})\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,2,3)\}
$$

#### Subespacio $S_1$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
3&-5&2&0\\
5&-8&3&0\\
6&-9&3&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
3&-5&2&0\\
15&-24&9&0\\
6&-9&3&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
3&-5&2&0\\
0&1&-1&0\\
0&1&-1&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z = y$
- $x = \frac{5y-2y}{3} = y$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = 1$ es:

$$
S_1 = \{(\alpha,\alpha,\alpha)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,1,1)\}
$$

Ahora podemos concluir que $T$ no es diagonalizable, porque:

$$1 = mg(0) \neq ma(0) = 2$$

### Transformación #3

$T(x, y, z) = (y, -4x + 4y, 2x + y + 2z)$

Consideremos la base canónica $\mathcal{E}$ y hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(T(1,0,0)) = (0,-4,2)$
- $coord_{\mathcal{E}}(T(0,1,0))= (1,4,1)$
- $coord_{\mathcal{E}}(T(0,0,1))= (0,0,2)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
0&1&0\\
-4&4&0\\
2&1&2
\end{pmatrix}
$$

Ahora hallemos el polinomio característico:

$$
\Chi_T(\lambda) = det
\begin{pmatrix}
-\lambda&1&0\\
-4&4-\lambda&0\\
2&1&2-\lambda
\end{pmatrix}
$$

Desarrollando por la columna 3 obtenemos:

$$
\begin{aligned}
\Chi_T(\lambda) &= (2-\lambda)\cdot(-\lambda(4-\lambda)+4)
&= (2-\lambda)(\lambda^2-4\lambda+4)
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 2 \rightarrow ma(\lambda_1) = 3$ 1 de forma trivial y las otras dos multiplicidades son porque es raíz doble del polinomio de grado dos.

Ahora tenemos que hallar bases de los subespacios propios para poder determinar si $T$ es diagonalizable.

#### Subespacio $S_2$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-2&1&0&0\\
-4&2&0&0\\
2&1&0&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y=2x$
- $z\in\mathbb{R}$
- $x\in\mathbb{R}$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 2$ es:

$$
S_2 = \{(\alpha,2\alpha,\beta)\mid \alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,2,0),(0,0,1)\}
$$

Ahora podemos concluir que $T$ no es diagonalizable, porque:

$$2 = mg(2) \neq ma(2) = 3$$

### Transformación #4

$T(x, y, z) = (2x, 2y, 2z)$

Consideremos la base canónica $\mathcal{E}$ y hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(T(1,0,0)) = (2,0,0)$
- $coord_{\mathcal{E}}(T(0,1,0))= (0,2,0)$
- $coord_{\mathcal{E}}(T(0,0,1))= (0,0,2)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
2&0&0\\
0&2&0\\
0&0&2
\end{pmatrix}
$$

Ahora hallemos el polinomio característico:

$$
\Chi_T(\lambda) = det
\begin{pmatrix}
2-\lambda&0&0\\
0&2-\lambda&0\\
0&0&2-\lambda
\end{pmatrix}
$$

El determinante es:

$$
\begin{aligned}
\Chi_T(\lambda) &= (2-\lambda)^3
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 2 \rightarrow ma(\lambda_1) = 3$

Obviamente sabemos que $T$ es diagonalizable porque la matriz asociada a la base canónica es literalmente diagonal. Cálculemos el subespacio solo por completitud.

#### Subespacio $S_2$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0&0&0&0\\
0&0&0&0\\
0&0&0&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{R}$
- $z\in\mathbb{R}$
- $x\in\mathbb{R}$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 2$ es:

$$
S_2 = \{(\alpha,\beta,\gamma)\mid \alpha,\beta,\gamma\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,0,0),(0,1,0),(0,0,1)\}
$$

Concluyendo, en este caso, todos los vectores del espacio son vectores propios asociados a $\lambda_1 = 2$