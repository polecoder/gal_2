# Ejercicio 4

## Consigna

Hallar la forma y una base de Jordan para las siguientes matrices:
  
$$
A = \begin{pmatrix}
4 & -6 \\
2 & -4
\end{pmatrix}, \quad
B = \begin{pmatrix}
0 & 2 \\
-2 & 4
\end{pmatrix}, \quad
C = \begin{pmatrix}
6 & -2 & 1 \\
6 & -1 & 1 \\
0 & 0 & 1
\end{pmatrix}, \\
D = \begin{pmatrix}
1 & 0 & 0 \\
1 & 0 & -1 \\
1 & -1 & 0
\end{pmatrix}, \quad
E = \begin{pmatrix}
2 & 1 & -1 \\
0 & 2 & -1 \\
-3 & -2 & 3
\end{pmatrix}.
$$

## Resolución (parte a)

Hallemos los valores propios de $A$:

$$
\begin{aligned}
\Chi_A(\lambda) &= \begin{vmatrix}
4 -\lambda & -6 \\
2 & -4 -\lambda
\end{vmatrix} \\
&= (4-\lambda)(-4-\lambda)+12 \\
&= \lambda^2 - 16 + 12 \\
&= \lambda^2 - 4
\end{aligned}
$$

De donde sacamos que:

- $\lambda_1 = 2$
- $\lambda_2 = -2$

Entonces la forma de Jordan es:

$$
J_A = \begin{pmatrix}
2&0\\
0&-2
\end{pmatrix} 
$$

Para hallar la base tenemos que hallar los subespacios propios:

**$S_2$**

Tenemos que resolver el sistema $(A-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{cc|c}
2 & -6 & 0\\
2 & -6 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $x=3y$
- $y\in\mathbb{R}$

Entonces una base de este subespacio podría ser:

$$
\{(3,1)\}
$$

**$S_{-2}$**

Tenemos que resolver el sistema $(A+2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{cc|c}
6 & -6 & 0\\
2 & -2 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $x=y$
- $y\in\mathbb{R}$

Entonces una base de este subespacio podría ser:

$$
\{(1,1)\}
$$

Juntando ambas cosas, obtenemos una base de Jordan:

$$
\mathcal{B} = \{(3,1),(1,1)\}
$$

## Resolución (parte b)

Hallemos los valores propios de $B$:

$$
\begin{aligned}
\Chi_B(\lambda) &= \begin{vmatrix}
-\lambda & 2 \\
-2 & 4-\lambda
\end{vmatrix} \\
&= (4-\lambda)(-\lambda)+4 \\
&= \lambda^2-4\lambda+4 \\
\end{aligned}
$$

Usando Bhaskara:

$$
\begin{aligned}
\lambda &= \frac{4\pm\sqrt{16-16}}{2}\\
&= 2
\end{aligned}
$$

De donde sacamos que $\lambda=2$ es raíz doble, es decir que $ma(2) = 2$.

En este caso para hallar la forma de Jordan primero debemos hallar $mg(2)$, calculemos el subespacio propio: 

**$S_2$**

Tenemos que resolver el sistema $(B-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{cc|c}
-2 & 2 & 0\\
-2 & 2 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $x=y$
- $y\in\mathbb{R}$

Entonces una base de este subespacio podría ser:

$$
\{(1,1)\}
$$

Por lo que $mg(2) = 1$, esto implica que $B$ NO es diagonalizable, la forma de Jordan sería:

$$
J_B = \begin{pmatrix}
2&0\\
1&2
\end{pmatrix} 
$$

Para hallar una base de Jordan, tenemos que elegir un vector $v_1$ tal que sea LI a $v_2=(1,1)$ que obtuvimos del subespacio propio asociado a $2$.
Para esto, veamos lo que nos dice la forma de Jordan:

$$
\begin{aligned}
B(v_1) = 2v_1 + v_2\\
(B-2\mathbb{I})v_1 = v_2
\end{aligned}
$$

Podemos plantear ese sistema para obtener quién es $v_1$.

$$
\left(
\begin{array}{cc|c}
-2 & 2 & 1\\
-2 & 2 & 1
\end{array}
\right)
$$

De donde sacamos que:

- $x=\frac{1-2y}{-2}$
- $y\in\mathbb{R}$

De aquí podemos elegir un vector que cumpla con estas condiciones, por ejemplo: $v_1=(\frac{-1}{2},0)$.

Juntando esto con lo hallado en el subespacio propio tenemos que la base de Jordan es la siguiente:

$$
\mathcal{B}=\{\left(\frac{-1}{2},0\right),(1,1)\}
$$

## Resolución (parte d)

Hallemos los valores propios de $D$:

$$
\begin{aligned}
\Chi_D(\lambda) &= \begin{vmatrix}
1-\lambda & 0 & 0 \\
1 & -\lambda & -1 \\
1 & -1 & -\lambda
\end{vmatrix} \\
&= (1-\lambda)(\lambda^2-1) \\
\end{aligned}
$$

De donde sacamos que:

- $\lambda_1=1$ con $ma(1) = 2$
- $\lambda_2=-1$ con $ma(-1) = 1$

En este caso para hallar la forma de Jordan primero debemos hallar $mg(2)$, calculemos el subespacio propio: 

**$S_1$**

Tenemos que resolver el sistema $(D-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0 & 0 & 0 & 0 \\
1 & -1 & -1 & 0 \\
1 & -1 & -1 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $x=y+z$
- $y\in\mathbb{R}$
- $z\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_1 = \{(\alpha+\beta,\alpha,\beta)\in\mathbb{R}^3: \alpha,\beta\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(1,1,0),(1,0,1)\}
$$

Por lo que $mg(2) = 2$, esto implica que $D$ es diagonalizable, la forma de Jordan sería:

$$
J_D = \begin{pmatrix}
-1&0&0\\
0&1&0\\
0&0&1
\end{pmatrix} 
$$

Ahora hallemos el subespacio asociado a $-1$ para obtener otro vector y completar la base de Jordan.

**$S_{-1}$**

Tenemos que resolver el sistema $(D+1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
1 & 0 & 0 & 0 \\
1 & 1 & -1 & 0 \\
1 & -1 & 1 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $x=0$
- $z=y$
- $y\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_{-1} = \{(0,\alpha,\alpha)\in\mathbb{R}^3: \alpha\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(0,1,1)\}
$$

Juntando lo hallado con los dos subespacios, podemos dar la siguiente base de Jordan:

$$
\mathcal{B} = \{(0,1,1),(1,1,0),(1,0,1)\}
$$

## Resolución (parte e)

Hallemos los valores propios de $E$:

$$
\begin{aligned}
\Chi_E(\lambda) &= \begin{vmatrix}
2-\lambda & 1 & -1 \\
0 & 2-\lambda & -1 \\
-3 & -2 & 3-\lambda
\end{vmatrix} \\
&= ((2-\lambda)^2(3-\lambda)+0+3-(3(2-\lambda)+2(2-\lambda)+0)) \\
&= ((2-\lambda)^2(3-\lambda)+3-5(2-\lambda))\\
&= (2-\lambda)((2-\lambda)(3-\lambda)-5)+3\\
&= (2-\lambda)(\lambda^2-5\lambda+1)+3\\
&= -\lambda^3+7\lambda^2-11\lambda+5
\end{aligned}
$$

### Recordatorio (teorema de raíces racionales)

Si un polinomio tiene raíces racionales, estas son de la forma $\frac{p}{q}$, donde $p$ es un divisor del término independiente y $q$ es un divisor del coeficiente del término de mayor grado.

### Continuación

Ahora que conocemos la forma de las raíces, podemos concluir que las raíces del polinomio de tercer grado anterior están incluidas en la lista: $\{\pm 1,\pm 5\}$

Probemos con $1$:

$$
\begin{aligned}
-(1)^3 + 7\cdot1^2 - 11\cdot 1 + 5 &= -1+7-11+5\\
&= -12+12\\
&= 0
\end{aligned}
$$

Como sabemos que $1$ es raíz, podemos factorizar el polinomio con ruffini:

$$
\begin{array}{r|rrrr}
& \lambda^3 & \lambda^2 &\lambda^1 &1\\
\hline
& -1 & 7 & -11 & 5\\
\hline
1 & \downarrow & -1 & 6 & -5\\
\hline
& -1 & 6 & -5 & 0
\end{array}
$$

Por lo tanto, puedo expresar el polinomio de tercer grado como:

$$
-\lambda^3+7\lambda^2-11\lambda+5 = (\lambda - 1)(-\lambda^2+6\lambda-5)
$$

Entonces tenemos $\lambda_1 = 1$, y ahora usando Bhaskara puedo obtener todas las demás raíces:

$$
\begin{aligned}
\lambda &= \frac{-6\pm\sqrt{36-20}}{-2}\\
&= \frac{-6\pm4}{-2}
\end{aligned}
$$

De donde obtenemos:

- $\lambda_1 = 1$
- $\lambda_2 = 5$

Entonces, recapitulando, tenemos:

- $\lambda_1 = 1$ con $ma(1) = 2$
- $\lambda_2 = 5$ con $ma(5) = 1$

En este caso para hallar la forma de Jordan primero debemos hallar $mg(1)$, calculemos el subespacio propio: 

**$S_1$**

Tenemos que resolver el sistema $(D-1\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
1 & 1 & -1 & 0 \\
0 & 1 & -1 & 0 \\
-3 & -2 & 2 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $z=y$
- $x=0$
- $y\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_1 = \{(0,\alpha,\alpha)\in\mathbb{R}^3: \alpha\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(0,1,1)\}
$$

Por lo que $mg(1) = 2$, esto implica que $E$ NO es diagonalizable, la forma de Jordan sería:

$$
J_E = \begin{pmatrix}
5&0&0\\
0&1&0\\
0&1&1
\end{pmatrix} 
$$

Ahora hallemos el subespacio asociado a $5$ para obtener otro vector para la base de Jordan.

**$S_{5}$**

Tenemos que resolver el sistema $(E-5\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-3 & 1 & -1 & 0 \\
0 & -3 & -1 & 0 \\
-3 & -2 & -2 & 0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
-3 & 1 & -1 & 0 \\
0 & -3 & -1 & 0 \\
0 & -3 & -1 & 0
\end{array}
\right)
$$

De donde sacamos que:

- $z=-3y$
- $x=\frac{4}{3}y$
- $y\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_{5} = \{(\frac{4}{3}\alpha,\alpha,-3\alpha)\in\mathbb{R}^3: \alpha\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(4,3,-12)\}
$$

Con esto, nuestra base de Jordan se ve algo así:

$$
\mathcal{B} = \{(4,3,-12),v_2,(0,1,1)\}
$$

Hallemos el vector $v_2$ en base a lo que sabemos por la forma de Jordan:

$$
E(v_2) = v_2 + v_3\\
(E-\mathbb{I})v_2 = v_3
$$

Esto nos plantea el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
1 & 1 & -1 & 0 \\
0 & 1 & -1 & 1 \\
-3 & -2 & 2 & 1
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
1 & 1 & -1 & 0 \\
0 & 1 & -1 & 1 \\
0 & 1 & -1 & 1
\end{array}
\right)
$$

De donde sacamos que:

- $z= y-1$
- $x = -1$
- $y\in\mathbb{R}$

Con esto podemos elegir un vector, por ejemplo:

$$
v_2 = (-1,1,0)
$$

Entonces la base quedaría:

$$
\mathcal{B} = \{(4,3,-12),(-1,1,0),(0,1,1)\}
$$

Solo habría que verificar que los vectores son LI, por lo tanto, verifiquemos que el siguiente determinante sea diferente a 0:

$$
\begin{vmatrix}
4&-1&0\\
3&1&1\\
-12&0&1
\end{vmatrix} = 4+0+12-(0+0-3) = 13
$$

Con esto confirmamos que $\mathcal{B}$ es una base, y además es base de Jordan.