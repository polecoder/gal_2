# CLASE 9 - 07/04/2025

## Teorema de Jordan

### Subbloque de Jordan (definición)

Sea $T:V\to V$ una transformación lineal con valor propio $\lambda$. Llamamos subbloque de Jordan del valor propio $\lambda$ y tamaño $k$:

$$
SJ_k(\lambda) = \begin{pmatrix}
\lambda&0&\cdots&0\\
1&\lambda&\cdots&0\\
0&1&\cdots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&\cdots&1&\lambda
\end{pmatrix}
$$

Donde la matriz es de tamaño $k\times k$

### Bloque de Jordan (definición)

Sea $T:V\to V$ una transformación lineal con valor propio $\lambda$. Un bloque de Jordan de un valor propio $\lambda$ es una matriz cuadrada de la forma:

$$
J(\lambda) = \begin{pmatrix}
SJ_{k_1}(\lambda)&&&0\\
&SJ_{k_2}(\lambda)&&\\
&&\ddots&\\
0&&&SJ_{k_p}(\lambda)&
\end{pmatrix}
$$

Donde por convención tenemos que $k_1\leq k_2\leq\ldots\leq k_p$

### Teorema de la forma canónica de Jordan

Sea $T:V\to V$ con $dim(V) = n$, con polinomio característico $\Chi_T(\lambda) = (-1)^n(\lambda-\lambda_1)^{m_1}\ldots(\lambda-\lambda_q)^{m_q}$

Entonces existe $\mathcal{B}$ base de $V$ tal que:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = \begin{pmatrix}
J(\lambda_1)&&&0\\
&J(\lambda_2)&&\\
&&\ddots&\\
0&&&J(\lambda_q)&
\end{pmatrix}
$$

Donde:

- Los tamaños de los bloques de Jordan están dados por la multiplicidad algebraica del valor propio asociado $\lambda_i$
- La forma de $\mathcal{B}$ es única salvo el reordenamiento de los bloques
- Llamamos base de Jordan a todas las bases $\mathcal{B}$ que nos llevan a esta forma

### Análisis con matrices $2\times 2$

Sea $A\in\mathcal{M}_{2\times 2}(\mathbb{K})$ tales que las raíces de su polinomio característico están en el cuerpo $\mathbb{K}$

**CASO 1: RAÍCES DISTINTAS**

En este caso el polinomio característico se vería así al factorizarse:

$$\Chi_A(\lambda) = (\lambda - a)(\lambda - b)$$

Con $a\neq b$, como tenemos dos valores propios distintos y estamos trabajando en espacio de dimensión 2, entonces $A$ es diagonalizable, por lo que su forma de Jordan sería:

$$
J = \begin{pmatrix}
a&0\\
0&b
\end{pmatrix}
$$

**CASO 2: RAÍZ DOBLE**

En este caso el polinomio característico se vería así al factorizarse:

$$\Chi_A(\lambda) = (\lambda - a)^2$$

Acá a su vez tenemos dos casos:

- $mg(a) = ma(a) = 2$
- $mg(a) = 1$ 

En el primero $A$ es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0\\
0&a
\end{pmatrix}
$$

Mientras que en el segundo $A$ NO es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0\\
1&a
\end{pmatrix}
$$

**OBSERVACIÓN:** Veamos que la multiplicidad geométrica de un valor propio nos determina la cantidad de subbloques de Jordan que tenemos.

### Análisis con matrices $3\times 3$

Sea $A\in\mathcal{M}_{3\times 3}(\mathbb{K})$ tales que las raíces de su polinomio característico están en el cuerpo $\mathbb{K}$

**CASO 1: RAÍCES DISTINTAS**

En este caso el polinomio característico se vería así al factorizarse:

$$\Chi_A(\lambda) = (-1)(\lambda - a)(\lambda - b)(\lambda - c)$$

Con $a\neq b\neq c$, como tenemos tres valores propios distintos y estamos trabajando en espacio de dimensión 3, entonces $A$ es diagonalizable, por lo que su forma de Jordan sería:

$$
J = \begin{pmatrix}
a&0&0\\
0&b&0\\
0&0&c
\end{pmatrix}
$$

**CASO 2: UNA RAÍZ DOBLE Y OTRA SIMPLE**

$$\Chi_A(\lambda) = (-1)(\lambda - a)^2(\lambda - b)$$

Acá a su vez tenemos dos casos:

- $mg(a) = ma(a) = 2$
- $mg(a) = 1$ 

En el primero $A$ es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0&0\\
0&a&0\\
0&0&b
\end{pmatrix}
$$

Mientras que en el segundo $A$ NO es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0&0\\
1&a&0\\
0&0&b
\end{pmatrix}
$$

**CASO 3: UNA RAÍZ TRIPLE**

$$\Chi_A(\lambda) = (-1)(\lambda - a)^3$$

Acá a su vez tenemos tres casos:

- $mg(a) = ma(a) = 3$
- $mg(a) = 2$
- $mg(a) = 1$

En el primero $A$ es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0&0\\
0&a&0\\
0&0&a
\end{pmatrix}
$$

En el segundo $A$ NO es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0&0\\
1&a&0\\
0&0&a
\end{pmatrix}
$$

Mientras que en el tercero $A$ NO es diagonalizable, y su forma es:

$$
J = \begin{pmatrix}
a&0&0\\
1&a&0\\
0&1&a
\end{pmatrix}
$$

### Ejemplo (cálculo de una base de Jordan)

Sea $T:\mathbb{R}^3\to\mathbb{R}^3$ dada por $T(x,y,z) = (2x+z,y-z,-y+z)$

Considerando la base canónica, tenemos que:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}
2&0&1\\
0&1&-1\\
0&-1&1
\end{pmatrix}
$$

Y el polinomio característico es:

$$
\Chi_T(\lambda) = -(\lambda-2)^2\lambda
$$

**Nota:** No vemos el detalle de todo esto ya que fue calculado en una clase anterior de teórico

Tenemos que los valores propios son:

- $\lambda_1 = 2$, con $ma(2) = 2$
- $\lambda_2 = 0$, con $ma(0) = 1$

Los subespacios propios quedan definidos por las siguientes bases:

- $\{(1,0,0)\}$ es base de $S_2$
- $\{(1,-2,-2)\}$ es base de $S_0$

Por lo que sabemos que $T$ NO es diagonalizable, pero sabemos cual es su forma de Jordan a partir del razonamiento que seguimos en la parte anterior:

$$
J = \begin{pmatrix}
0&0&0\\
0&2&0\\
0&1&2
\end{pmatrix}
$$

Para construir una base que nos lleve a esta representación matricial, tenemos que

1. Elegir la mayor cantidad de vectores propios que podemos.
2. Construir los vectores faltantes a partir de lo que ya tenemos.

Mirando la primer y tercer columna de la forma de Jordan:

- Consideramos un vector propio del subespacio asociado a $0: v_1 = (1,-2,-2)$
- Consideramos un vector propio del subespacio asociado a $2: v_3 = (1,0,0)$

Con esto, veamos que la forma de Jordan nos dice que:

$$
T(v_2) = 2v_2 + v_3
$$

O visto de otra forma:

$$
(T-2\mathbb{I})v_2 = v_3
$$

Lo que nos deja con el siguiente sistema (usando la matriz asociada que obtuvimos al principio):

$$
\left(
\begin{array}{ccc|c}
2-2&0&1&1\\
0&1-2&-1&0\\
0&-1&1-2&0
\end{array}
\right)
$$

De esto sacamos que:

- $z = 1$
- $-y= z$
- $x\in\mathbb{R}$

Por lo que consideramos el vector $v_2 = (0,-1,1)$ para completar la base de Jordan.