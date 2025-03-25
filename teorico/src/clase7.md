# CLASE 7 - 25/03/2025

## Gershgorin

### Círculos de Gershgorin

Sea $A \in \mathcal{M}_{n \times n}(\mathbb{C})$ una matriz cuadrada. con la siguiente forma:

$$
A= 
\begin{pmatrix}
a_{11} & a_{12} & \cdots & a_{1i} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2i} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots & \vdots &\vdots \\
a_{i1} & a_{i2} & \cdots & a_{ii} & \cdots & a_{in} \\
\vdots & \vdots & \vdots & \vdots & \ddots &\vdots \\
a_{n1} & a_{n2} & \cdots & a_{ni} & \cdots & a_{nn} \\
\end{pmatrix}
$$

Considerando la fila $i$ de la matriz, se define el disco de Gershgorin $C_i$ como el disco centrado en $a_{ii}$ con radio $R_i$ tal que:

- $R_i$ es la suma de los módulos de todos los elementos de la fila $i$ a excepción de $a_{ii}$

### Teorema de Gershgorin

Dada una matriz $A \in \mathcal{M}_{n \times n}(\mathbb{C})$:

1. Si $\lambda$ es valor propio de $A$, entonces $\lambda\in\bigcup_{i=1}^{n} C_i$
2. Si el conjunto $M=C_{i1}\cup C_{i2}\cup\ldots\cup C_{im}$ es disjunto con respecto a los demás discos, entonces $M$ contiene exactamente $m$ valores propios de $A$

#### Demostración

1. Consideramos $\lambda_0$ un valor propio de $A$, y $(x_1,x_2,\ldots,x_n)\in\mathbb{C}^n$ un vector propio asociado a $\lambda_0$. Esto significa que:

$$
A(x_1,x_2,\ldots,x_n) = \lambda_0(x_1,x_2,\ldots,x_n)
$$

Consideramos el componente del vector propio que tiene mayor módulo, es decir el elemento que se encuentra en la posición $i_0$ tal que $|x_{i_0}|=\max\{|x_1|,|x_2|,\ldots,|x_n|\}$
Como estamos trabajando con un vector propio, sabemos que por lo menos uno de los valores será distinto de 0, por lo que $|x_{i_0}|>0$.

Consideremos la igualdad anterior ahora expandiendo la matriz $A$:

$$
\begin{pmatrix}
\vdots&\vdots&\vdots&\vdots&\vdots&\vdots\\
a_{i_01}&a_{i_02}&\ldots&a_{i_0i_0}&\ldots&a_{i_0n}\\
\vdots&\vdots&\vdots&\vdots&\vdots&\vdots\\
\end{pmatrix}\cdot
\begin{pmatrix}
x_1\\
\vdots\\
x_n
\end{pmatrix}=
\begin{pmatrix}
\vdots\\
a_{i_01}x_1+a_{i_02}x_2+\ldots+a_{i_0i_0}x_{i_0}+\ldots+a_{i_0n}x_n\\
\vdots\\
\end{pmatrix}
$$

Y como $\lambda_0$ es valor propio tenemos que:

$$
\begin{pmatrix}
\vdots\\
a_{i_01}x_1+a_{i_02}x_2+\ldots+a_{i_0i_0}x_{i_0}+\ldots+a_{i_0n}x_n\\
\vdots\\
\end{pmatrix}=
\begin{pmatrix}
\vdots\\
\lambda_0x_{i_0}\\
\vdots\\
\end{pmatrix}
$$

Entonces podemos decir que:

$$
\begin{aligned}
&a_{i_01}x_1+a_{i_02}x_2+\ldots+a_{i_0i_0}x_{i_0}+\ldots+a_{i_0n}x_n = \lambda_0x_{i_0}\\
&a_{i_01}x_1+a_{i_02}x_2+\ldots+a_{i_0n}x_n = \lambda_0x_{i_0} - a_{i_0i_0}x_{i_0}\\
&\sum_{j=1;j\neq i_0}^{n}a_{i_0j}x_j = x_{i_0}(\lambda_0 - a_{i_0i_0})\\
&|\sum_{j=1;j\neq i_0}^{n}a_{i_0j}x_j| = |x_{i_0}(\lambda_0 - a_{i_0i_0})|\\
&|x_{i_0}(\lambda_0 - a_{i_0i_0})| = |\sum_{j=1;j\neq i_0}^{n}a_{i_0j}x_j|\leq\sum_{j=1;j\neq i_0}^{n}|a_{i_0j}x_j| = \sum_{j=1;j\neq i_0}^{n}|a_{i_0j}||x_j|\\
&|x_{i_0}(\lambda_0 - a_{i_0i_0})| = |\sum_{j=1;j\neq i_0}^{n}a_{i_0j}x_j|\leq\sum_{j=1;j\neq i_0}^{n}|a_{i_0j}x_j| = \sum_{j=1;j\neq i_0}^{n}|a_{i_0j}||x_{i_0}|\\
&|x_{i_0}(\lambda_0 - a_{i_0i_0})| \leq \sum_{j=1;j\neq i_0}^{n}|a_{i_0j}||x_{i_0}|\\
&|\lambda_0 - a_{i_0i_0}| \leq \sum_{j=1;j\neq i_0}^{n}|a_{i_0j}|\\
\end{aligned}
$$

Donde se observa que el lado derecho de la desigualdad es el radio del disco de Gershgorin $C_{i_0}$, por lo que $\lambda_0\in C_{i_0}$, por consecuencia $\lambda_0\in\bigcup_{i=1}^{n} C_i$

2. Se prueba en el libro rojo, pero no se da en la clase con detalle.