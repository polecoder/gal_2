# Ejercicio 9

## Consigna

Dadas las matrices:

$$
A = \begin{pmatrix} a & 1 & -1 \\ 2 & a & 2 \\ 1 & 1 & a \end{pmatrix}, \quad
B = \begin{pmatrix} 1 & -2 & -2 - a \\ 0 & 1 & a \\ 0 & 0 & 1 \end{pmatrix}, \quad
C = \begin{pmatrix} 0 & 0 & 1 \\ 0 & b & 0 \\ a & 0 & 0 \end{pmatrix}
$$

Hallar los valores reales de $a$ y $b$ para que la matriz sea diagonalizable.

## Resolución

### Matriz $A$

$$A = \begin{pmatrix} a & 1 & -1 \\ 2 & a & 2 \\ 1 & 1 & a \end{pmatrix}$$

Hallamos el polinomio característico:

$$
\Chi_A(\lambda) = det
\begin{pmatrix}
a-\lambda & 1 & -1 \\
2 & a-\lambda & 2 \\
1 & 1 & a-\lambda
\end{pmatrix}
$$

Desarrollando el determinante por el método de Sarrus:

$$
\begin{aligned}
\Chi_T(\lambda) &= ((a-\lambda)^3-2+2) - (-(a-\lambda)+2(a-\lambda)+2(a-\lambda))\\
&= (a-\lambda)^3 - 3(a-\lambda)\\
&= (a-\lambda)((a-\lambda)^2 - 3)\\
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = a$ (primer polinomio)
- $\lambda_2 = a + \sqrt{3}$ (segundo polinomio)
- $\lambda_3 = a - \sqrt{3}$ (segundo polinomio)

Como estamos trabajando en un espacio de dimensión 3, y tenemos tres valores propios distintos, sabemos que $T$ es diagonalizable $\forall a\in\mathbb{R}$, porque se cumplirá para todo $\lambda$ valor propio de $A$ que:

$$1 = mg(\lambda) = ma(\lambda)$$

### Matriz $B$

$$B = \begin{pmatrix} 1 & -2 & -2 - a \\ 0 & 1 & a \\ 0 & 0 & 1 \end{pmatrix}$$

Hallamos el polinomio característico:

$$
\Chi_A(\lambda) = det
\begin{pmatrix}
1-\lambda&-2&-2-a \\
0 & 1-\lambda & a \\
0 & 0 & 1-\lambda
\end{pmatrix}
$$

Desarrollemos por la primer columna:

$$
\Chi_A(\lambda) = (1-\lambda)((1-\lambda)^2 - 0) = (1-\lambda)^3
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 1$ que es raíz triple $\rightarrow ma(\lambda) = 3$

#### Subespacio $S_1$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(B-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0&-2&-2-a&0 \\
0 & 0 & a&0 \\
0 & 0 & 0&0
\end{array}
\right)
$$

Observemos que estamos buscando que la matriz tenga todas las filas con ceros, que sería la única forma de que $B$ sea diagonalizable ya que $ma(1) = 3$.

Pero esto es imposible, ya que la primera no podría ser una fila solo de ceros para cualquier valor de $a\in\mathbb{R}$

Esto nos da que como mucho, para $a=0$, $mg(1)=2$ que no es suficiente para volver a $B$ diagonalizable.

Concluyendo, $B$ no es diagonalizable $\forall a\in\mathbb{R}$

### Matriz $C$

$$C = \begin{pmatrix} 0 & 0 & 1 \\ 0 & b & 0 \\ a & 0 & 0 \end{pmatrix}$$

Hallamos el polinomio característico:

$$
\Chi_C(\lambda) = det
\begin{pmatrix}
-\lambda & 0 & 1 \\
0 & b-\lambda & 0 \\
a & 0 & -\lambda
\end{pmatrix}
$$

Desarrollemos por la segunda fila:

$$
\Chi_C(\lambda) = (b-\lambda)(\lambda^2-a)
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = b$
- $\lambda_2 = \sqrt{a}$
- $\lambda_3 = -\sqrt{a}$

En este punto, tenemos varios factores que considerar. Primero:

- $0\leq a$ porque estamos trabajando en un espacio de cuerpo $\mathbb{R}$
- ¿Qué pasa si $b=\sqrt{a}$ o $b=-\sqrt{a}$?
- ¿Qué pasa si $a=0$?

Esto es muy importante, porque a priori no tenemos 3 valores propios diferentes en todos los casos.

#### Caso $b=\sqrt{a}$ o $b=-\sqrt{a}$

Estudiaremos este caso con $a\neq 0$, consideraremos ese problema en la siguiente sección.

##### Subcaso $b=\sqrt{a}$

En este caso tenemos que $ma(\sqrt{a}) = 2$, veamos que podemos decir sobre su subespacio propio $S_{\sqrt{a}}$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(C-\sqrt{a}\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-\sqrt{a} & 0 & 1 & 0 \\
0 & b-\sqrt{a} & 0 & 0 \\
a & 0 & -\sqrt{a} & 0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
-\sqrt{a} & 0 & 1 & 0 \\
0 & b-\sqrt{a} & 0 & 0 \\
0 & 0 & 0 & 0
\end{array}
\right)
$$

Las operaciones realizadas en orden son:

- $F_3 = F_3 + \sqrt{a}F_1$

De esto podemos sacar que:

- $z = \sqrt{a}x$

Y nada más, usando que $b = \sqrt{a}$ entonces la entrada $2,2$ de la matriz es 0

Por lo tanto, el subespacio propio asociado a $\lambda = \sqrt{a}$ es:

$$
S_{\sqrt{a}} = \{(\alpha,\beta,\sqrt{a}\alpha)\mid \alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,0,\sqrt{a}),(0,1,0)\}
$$

Entonces $mg(\sqrt{a}) = ma(\sqrt{a}) = 2$, por lo que en este caso $C$ es diagonalizable

Observemos que el caso $b=-\sqrt{a}$ es completamente análogo. Por lo que estos casos no imponen ninguna limitación sobre $a,b$

#### Caso $a=0$

Si $a=0$, tenemos que como mínimo $ma(0) = 2$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(C)v = 0$:

$$
\left(
\begin{array}{ccc|c}
0 & 0 & 1 & 0 \\
0 & b & 0 & 0 \\
0 & 0 & 0 & 0
\end{array}
\right)
$$

Se observa fácilmente que a priori esto tiene $mg(0) = 1 (y=0, z=0)$, a menos que $b=0$ pero si ocurre esto, entonces $ma(0) = 3$, pero la multiplicidad geométrica sería dos como máximo.

Entonces si $a=0$, $C$ NO es diagonalizable.

#### Conclusión

Concluimos que $C$ es diagonalizable sii:

- $b\in\mathbb{R}$ y,
- $0<a\mid a\in\mathbb{R}$