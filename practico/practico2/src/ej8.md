# Ejercicio 8

## Consigna

Dadas las matrices:

$$
A = \begin{pmatrix} 4 & 1 - i \\ 1 + i & 5 \end{pmatrix}, \quad
B = \begin{pmatrix} 0 & 0 & -2 \\ 1 & 2 & 1 \\ 1 & 0 & 3 \end{pmatrix}, \quad
C = \begin{pmatrix} 5 & 0 & 0 \\ 0 & -1 & -1 + i \\ 0 & -1 - i & 0 \end{pmatrix}
$$

1. Hallar los valores propios y las bases de los subespacios propios de cada una de ellas.
2. Deducir que cada una de ellas es diagonalizable.
3. Hallar la matriz diagonal $D$ semejante a la matriz dada y la matriz de semejanza $P$ (matriz invertible tal que $A = PDP^{-1}$).

## Resolución (matriz $A$)

$$A = \begin{pmatrix} 4 & 1 - i \\ 1 + i & 5 \end{pmatrix}$$

### PARTE 1

Hallamos el polinomio característico:

$$
\Chi_A(\lambda) = det
\begin{pmatrix}
4-\lambda&1-i\\
1+i&5-\lambda
\end{pmatrix}
$$

**RECORDATORIO:** Dados dos complejos $z=a+bi;\quad w=c+di$ cálculamos su producto mediante distributiva y reagrupando términos:

$$
\begin{aligned}
(a+bi)(c+di) &= ac + adi + bic + bdi^2\\
&= ac + (ad+bc)i - bd\\
&= (ac-bd) + (ad+bc)i
\end{aligned}
$$

Desarrollando el determinante:

$$
\begin{aligned}
\Chi_T(\lambda) &= (4-\lambda)(5-\lambda) - ((1-i)(1+i))\\
&= (20 - 4\lambda-5\lambda + \lambda^2) - (1 + i - i + 1)\\
&= \lambda^2 - 9\lambda + 20 - 2\\
&= \lambda^2 - 9\lambda + 18
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = \frac{9 + \sqrt{81 - 72}}{2} = 6$
- $\lambda_2 = \frac{9 - \sqrt{81 - 72}}{2} = 3$

Ahora tenemos que hallar bases de los subespacios propios para poder determinar si $T$ es diagonalizable.

#### Subespacio $S_3$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-3\mathbb{I})v = 0$:

$$
\left(
\begin{array}{cc|c}
1&1-i&0\\
1+i&2&0
\end{array}
\right)
\sim
\left(
\begin{array}{cc|c}
1&1-i&0\\
0&0&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $y\in\mathbb{C}$
- $x=(-1+i)y$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = 3$ es:

$$
S_3 = \{((-1+i)\alpha,\alpha)\mid \alpha\in\mathbb{C}\}
$$

La base de este subespacio podría ser:

$$
\{(-1+i,1)\}
$$

#### Subespacio $S_6$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(A-6\mathbb{I})v = 0$:

$$
\left(
\begin{array}{cc|c}
-2&1-i&0\\
1+i&-1&0
\end{array}
\right)
\sim
\left(
\begin{array}{cc|c}
-2&1-i&0\\
0&0&0
\end{array}
\right)
$$

Las operaciones realizadas fueron: $(1-i)F_2 + F_1$

**Cuentas auxiliares:**
- $-1(1-i)+1-i = -1+i+1-i=0$

De esto podemos sacar que:

- $x=\frac{1-i}{2}y\iff (1+i)x = \frac{(1-i)(1+i)}{2}y\iff (1+i)x = y$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 6$ es:

$$
S_6 = \{(\frac{1-i}{2}\alpha,\alpha)\mid \alpha\in\mathbb{C}\}
$$

Que es lo mismo que:

$$
S_6 = \{(\alpha,(1+i)\alpha)\mid \alpha\in\mathbb{C}\}
$$

La base de este subespacio podría ser:

$$
\{(1,1+i)\}
$$

### PARTE 2

Ahora tenemos que deducir que la matriz $A$ es diagonalizable, observemos que:

- $ma(3) = mg(3) = 1$
- $ma(6) = mg(6) = 1$

Entonces $A$ es diagonalizable.

### PARTE 3

Necesitamos encontrar una matriz $D$ semejante a $A$ y su matriz de semejanza $P$.

Está claro que:

$$
D=\begin{pmatrix}6&0\\0&3\end{pmatrix}
$$

Porque la matriz diagonal semejante a la matriz inicial será aquella matriz con los valores propios de la transformación, repetidos por la $mg$ de cada uno, en la diagonal.

Y la matriz $P$ es la matriz formada por los vectores de la base de vectores propios. Esa base $\mathcal{B} = \{(-1+i,1),(1,1+i)\}$ es efectivamente base del espacio porque se probó en el teórico que los subespacios propios de valores propios distintos no comparten ningún vector además del nulo.

$$
P = \begin{pmatrix}-1+i&1\\1&1+i\end{pmatrix}
$$

Ahora calculemos $P^{-1}$, con el procedimiento estándar:

$$
\begin{aligned} 
&\left(
\begin{array}{cc|cc}
-1+i&1&1&0\\
1&1+i&0&1
\end{array}
\right)\sim
\left(
\begin{array}{cc|cc}
1-i&-1&-1&0\\
1&1+i&0&1
\end{array}
\right)\sim\\
&\left(
\begin{array}{cc|cc}
1&i-2&-1&i\\
1&1+i&0&1
\end{array}
\right)\sim
\left(
\begin{array}{cc|cc}
1&i-2&-1&i\\
0&3&1&1-i
\end{array}
\right)\sim\\
&\left(
\begin{array}{cc|cc}
1&i-2&-1&i\\
0&1&\frac{1}{3}&\frac{1-i}{3}
\end{array}
\right)\sim
\left(
\begin{array}{cc|cc}
1&0&\frac{-1-i}{3}&\frac{1}{3}\\
0&1&\frac{1}{3}&\frac{1-i}{3}
\end{array}
\right)
\end{aligned}
$$

Las operaciones realizadas en órden son:

- $F_1 = -F_1$
- $F_1 = F_1 +iF_2$
- $F_2 = F_2 - F_1$
- $F_2 = \frac{1}{3}F_2$
- $F_1 = F_1 - (i-2)F_2$

**Cuentas auxiliares:** Veamos algunas de las cuentas que precisé hacer (no están en orden)

- $i(1+i) = i + i^2 = i-1$
- $-1-\frac{i-2}{3}=\frac{-3+2-i}{3} = \frac{-1-i}{3}$
- $i-\frac{(1-i)(i-2)}{3} = \frac{3i-(3i-1)}{3} = \frac{1}{3}$
- $(1-i)(i-2) = i - 2 -i^2 +2i =3i -1$

Entonces la matriz $P^{-1}$ es la siguiente:

$$
P^{-1} =
\begin{pmatrix}
\frac{-1-i}{3}&\frac{1}{3}\\
\frac{1}{3}&\frac{1-i}{3}
\end{pmatrix}
$$

## Resolución (matriz $B$)

$$B = \begin{pmatrix} 0 & 0 & -2 \\ 1 & 2 & 1 \\ 1 & 0 & 3 \end{pmatrix}$$

### PARTE 1

Hallemos el polinomio característico:

$$
\Chi_B(\lambda) = det
\begin{pmatrix}
-\lambda&0&-2\\
1&2-\lambda&1\\
1&0&3-\lambda
\end{pmatrix}
$$

Desarrollando por la segunda columna:

$$
\begin{aligned}
\Chi_B(\lambda) &= (2-\lambda)(-\lambda(3-\lambda)+ 2)\\
&= (2-\lambda)(-3\lambda+\lambda^2+2)\\
&= (2-\lambda)(\lambda^2-3\lambda+2)
\end{aligned}
$$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 2$
- $\lambda_1 = \frac{3 + \sqrt{9-8}}{2} = 2$
- $\lambda_2 = \frac{3 + \sqrt{9-8}}{2} = 1$

Entonces tenemos raíz doble en $\lambda_1 = 2$

Ahora tenemos que hallar bases de los subespacios propios para poder determinar si $T$ es diagonalizable.

#### Subespacio $S_1$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(B-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-1&0&-2&0\\
1&1&1&0\\
1&0&2&0
\end{array}
\right)
\sim
\left(
\begin{array}{ccc|c}
-1&0&-2&0\\
0&1&-1&0\\
0&0&0&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $z=y$
- $x = -2y$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = 1$ es:

$$
S_1 = \{(-2\alpha,\alpha,\alpha)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(-2,1,1)\}
$$

#### Subespacio $S_2$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(B-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-2&0&-2&0\\
1&0&1&0\\
1&0&1&0
\end{array}
\right)
$$

De esto podemos sacar que:

- $x=-z$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 2$ es:

$$
S_2 = \{(-\alpha,\beta,\alpha)\mid \alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(-1,0,1), (0,1,0)\}
$$

### PARTE 2

Ahora tenemos que deducir que la matriz $B$ es diagonalizable, observemos que:

- $ma(1) = mg(1) = 1$
- $ma(2) = mg(2) = 2$

Entonces $A$ es diagonalizable.

### PARTE 3

Necesitamos encontrar una matriz $D$ semejante a $A$ y su matriz de semejanza $P$.

Por una parte,

$$
D=\begin{pmatrix}1&0&0\\0&2&0\\0&0&2\end{pmatrix}
$$

Y la matriz $P$ es la matriz formada por los vectores de la base de vectores propios. Esa base $\mathcal{B} = \{(-1,0,1),(0,1,0),(-2,1,1)\}$ es efectivamente base del espacio porque se probó en el teórico que los subespacios propios de valores propios distintos no comparten ningún vector además del nulo.

$$
P = \begin{pmatrix}-1&0&-2\\0&1&1\\-2&0&1\end{pmatrix}
$$

Ahora calculemos $P^{-1}$, con el procedimiento estándar:

$$
\begin{aligned} 
&\left(
\begin{array}{ccc|ccc}
-1&0&-2&1&0&0\\
0&1&1&0&1&0\\
-2&0&1&0&0&1
\end{array}
\right)\sim
\left(
\begin{array}{ccc|ccc}
1&0&2&-1&0&0\\
0&1&1&0&1&0\\
-2&0&1&0&0&1
\end{array}
\right)\sim\\
&\left(
\begin{array}{ccc|ccc}
1&0&2&-1&0&0\\
0&1&1&0&1&0\\
0&0&5&-2&0&1
\end{array}
\right)\sim
\left(
\begin{array}{ccc|ccc}
1&0&2&-1&0&0\\
0&1&1&0&1&0\\
0&0&1&\frac{-2}{5}&0&\frac{1}{5}
\end{array}
\right)\sim\\
&\left(
\begin{array}{ccc|ccc}
1&0&0&\frac{-1}{5}&0&\frac{-2}{5}\\
0&1&0&\frac{2}{5}&1&\frac{-1}{5}\\
0&0&1&\frac{-2}{5}&0&\frac{1}{5}
\end{array}
\right)
\end{aligned}
$$

Las operaciones realizadas en órden son:

- $F_1 = -F_1$
- $F_3 = F_3 + 2F_1$
- $F_3 = \frac{1}{5}F_3$
- $F_1 = F_1 - 2F_3$ y $F_2 = F_2-F_1$

Entonces la matriz $P^{-1}$ es la siguiente:

$$
P^{-1} =
\begin{pmatrix}
\frac{-1}{5}&0&\frac{-2}{5}\\
\frac{2}{5}&1&\frac{-1}{5}\\
\frac{-2}{5}&0&\frac{1}{5}
\end{pmatrix}
$$

## Resolución (matriz $C$)

$$C = \begin{pmatrix} 5 & 0 & 0 \\ 0 & -1 & -1 + i \\ 0 & -1 - i & 0 \end{pmatrix}$$

### PARTE 1

Hallemos el polinomio característico:

$$
\Chi_B(\lambda) = det
\begin{pmatrix}
5-\lambda&0&0\\
0&-1-\lambda&-1+i\\
0&-1-i&-\lambda
\end{pmatrix}
$$

Desarrollando por la primer fila

$$
\begin{aligned}
\Chi_C(\lambda) &= (5-\lambda)(-\lambda(-1-\lambda)-((-1+i)(-1-i)))\\
&= (5-\lambda)(\lambda^2+\lambda-2)
\end{aligned}
$$

**Cuentas auxiliares:**
- $(-1+i)(-1-i) = 1 + i - i - i^2 = 2$

Obtenemos entonces que las raíces son:

- $\lambda_1 = 5$
- $\lambda_2 = \frac{-1 + \sqrt{1+8}}{2} = 1$
- $\lambda_3 = \frac{-1 - \sqrt{1+8}}{2} = -2$

Ahora tenemos que hallar bases de los subespacios propios para poder determinar si $T$ es diagonalizable.

#### Subespacio $S_{-2}$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(C+2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
7&0&0&0\\
0&1&-1+i&0\\
0&-1-i&2&0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
7&0&0&0\\
0&1&-1+i&0\\
0&0&0&0
\end{array}
\right)
$$

Las operaciones realizadas en órden son:
- $F_2-(-1-i)F_1$

De esto podemos sacar que:

- $x=0$
- $y = (1-i)z$

Por lo tanto, el subespacio propio asociado a $\lambda_3 = -2$ es:

$$
S_{-2} = \{(0,(1-i)\alpha,\alpha)\mid \alpha\in\mathbb{C}\}
$$

La base de este subespacio podría ser:

$$
\{(0,1-i,1)\}
$$

#### Subespacio $S_1$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(C-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
4&0&0&0\\
0&-2&-1+i&0\\
0&-1-i&-1&0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
4&0&0&0\\
0&1&\frac{1-i}{2}&0\\
0&0&0&0
\end{array}
\right)
$$

Las operaciones realizadas en órden son:
- $F_2 = \frac{-1}{2}F_2$
- $F_2-(-1-i)F_1$

De esto podemos sacar que:

- $x=0$
- $y = (\frac{-1+i}{2})z$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = 1$ es:

$$
S_1 = \{(0,(\frac{-1+i}{2})\alpha,\alpha)\mid \alpha\in\mathbb{C}\}
$$

Que es lo mismo que:

$$
S_1 = \{(0,(-1+i)\alpha,2\alpha)\mid \alpha\in\mathbb{C}\}
$$

La base de este subespacio podría ser:

$$
\{(0,-1+i,2)\}
$$

#### Subespacio $S_5$

Para hallar este subespacio tenemos que resolver el siguiente sistema de ecuaciones $(C-5\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0&0&0&0\\
0&-6&-1+i&0\\
0&-1-i&-5&0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
0&0&0&0\\
0&-1&\frac{1-i}{6}&0\\
0&-1-i&-5&0
\end{array}
\right)\sim\\
\left(
\begin{array}{ccc|c}
0&0&0&0\\
0&-1&\frac{1-i}{6}&0\\
0&0&-5-\frac{i}{3}&0
\end{array}
\right)
$$

Las operaciones realizadas en órden son:
- $F_2 = \frac{-1}{6}F_2$
- $F_2-(-1-i)F_1$

De esto podemos sacar que:

- $z=y=0$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 5$ es:

$$
S_5 = \{(\alpha,0,0)\mid \alpha\in\mathbb{C}\}
$$

La base de este subespacio podría ser:

$$
\{(1,0,0)\}
$$

### PARTE 2

Ahora tenemos que deducir que la matriz $B$ es diagonalizable, observemos que:

- $ma(-2) = mg(-2) = 1$
- $ma(1) = mg(1) = 1$
- $ma(5) = mg(5) = 1$

Entonces $A$ es diagonalizable.

### PARTE 3

Exactamente el mismo procedimiento que los anteriores, por ahora no lo voy a hacer pero es exactamente igual.

