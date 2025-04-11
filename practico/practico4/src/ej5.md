# Ejercicio 5

## Consigna

Hallar la forma y una base de Jordan de los siguientes operadores:

1. $T: \mathbb{R}^3 \to \mathbb{R}^3$ tal que $T(x, y, z) = (-y - 2z, x + 3y + z, x + 3z)$ 
2. $T: \mathbb{R}^3 \to \mathbb{R}^3$ tal que $T(x, y, z) = (3x + 2y - 2z, 4y - z, y + 2z)$

## Resolución

### Transformación 1

Considerando la base canónica de $\mathbb{R}^3$, calculemos la matriz asociada ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $T(1,0,0) = (0,1,1)$
- $T(0,1,0) = (-1,3,0)$
- $T(0,0,1) = (-2,1,3)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}
0&-1&-2\\
1&3&1\\
1&0&3
\end{pmatrix}
$$

Ahora calculemos el polinomio característico $\Chi_T(\lambda)$:

$$
\begin{aligned}
\Chi_T(\lambda) &= \begin{vmatrix}
-\lambda&-1&-2\\
1&3-\lambda&1\\
1&0&3-\lambda
\end{vmatrix}\\
&= (-\lambda)(3-\lambda)^2+0-1-(-2(3-\lambda)+0-1(3-\lambda))\\
&= (-\lambda)(3-\lambda)^2 - 1 + 3(3-\lambda)\\
&= (3-\lambda)(-\lambda(3-\lambda)+3)-1\\
&= (3-\lambda)(\lambda^2-3\lambda+3)-1\\
&= -\lambda^3 + 6\lambda^2 -12\lambda +8
\end{aligned}
$$

#### Recordatorio (teorema de raíces racionales)

Si un polinomio tiene raíces racionales, estas son de la forma $\frac{p}{q}$, donde $p$ es un divisor del término independiente y $q$ es un divisor del coeficiente del término de mayor grado.

#### Continuación

Ahora que conocemos la forma de las raíces, podemos concluir que las raíces del polinomio de tercer grado anterior están incluidas en la lista: $\{\pm 1,\pm 2,\pm 4,\pm 8\}$

Probemos con 2:

$$
\begin{aligned}
-(2)^3 + 6\cdot2^2 - 12\cdot 2 + 8 &= -8 + 24 - 24 + 8\\
&= 0
\end{aligned}
$$

Como sabemos que $1$ es raíz, podemos factorizar el polinomio con Ruffini:

$$
\begin{array}{r|rrrr}
& \lambda^3 & \lambda^2 &\lambda^1 &1\\
\hline
& -1 & 6 & -12 & 8\\
\hline
2 & \downarrow & -2 & 8 & -8\\
\hline
& -1 & 4 & -4 & 0
\end{array}
$$

Por lo tanto, puedo expresar el polinomio de tercer grado como:

$$
-\lambda^3 + 6\lambda^2 -12\lambda +8 = (\lambda - 2)(-\lambda^2+4\lambda-4)
$$

Entonces tenemos $\lambda_1 = 2$, y ahora usando Bhaskara puedo obtener todas las demás raíces:

$$
\begin{aligned}
\lambda &= \frac{-4\pm\sqrt{16-16}}{-2}\\
&= \frac{-4\pm0}{-2}
\end{aligned}
$$

De donde obtenemos:

- $\lambda = 2$, con $ma(2) = 3$

**$S_2$**

Tenemos que resolver el sistema $(T-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-2&-1&-2&0\\
1&1&1&0\\
1&0&1&0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
-2&-1&-2&0\\
0&\frac{1}{2}&0&0\\
0&-\frac{1}{2}&0&0
\end{array}
\right)
$$

De donde sacamos que:

- $y=0$
- $x=-z$
- $z\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_2 = \{(-\alpha,0,\alpha)\in\mathbb{R}^3: \alpha\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(-1,0,1)\}
$$

Por lo que $mg(2) = 1$, esto implica que $T$ NO es diagonalizable, la forma de Jordan sería:

$$
J_T = \begin{pmatrix}
2&0&0\\
1&2&0\\
0&1&2
\end{pmatrix} 
$$

**BASE DE JORDAN**

Por ahora entonces la base de Jordan que tenemos es $\mathcal{B} = \{v_1,v_2,(-1,0,1)\}$.

Para hallar $v_2$, tenemos que:

$$
T(v_2) = 2v_2 + v_3\\
(T-2\mathbb{I})v_2 = v_3
$$

Lo que nos deja con el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
-2&-1&-2&-1\\
1&1&1&0\\
1&0&1&1
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
-2&-1&-2&-1\\
0&\frac{1}{2}&0&-\frac{1}{2}\\
0&-\frac{1}{2}&0&\frac{1}{2}
\end{array}
\right)\\\sim
\left(
\begin{array}{ccc|c}
-2&-1&-2&-1\\
0&1&0&-1\\
0&-1&0&1
\end{array}
\right)
$$

De donde sacamos que:

- $y = -1$
- $x = \frac{-2+2z}{-2} = 1-z$
- $z\in\mathbb{R}$

Con esto podemos elegir un vector, por ejemplo:

$$
v_2 = (1,-1,0)
$$

Ahora tenemos que repetir el proceso para hallar $v_1$, tenemos que:

$$
T(v_1) = 2v_1 + v_2\\
(T-2\mathbb{I})v_1 = v_2
$$

Lo que nos deja con el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
-2&-1&-2&1\\
1&1&1&-1\\
1&0&1&0
\end{array}
\right)\sim
\left(
\begin{array}{ccc|c}
-2&-1&-2&1\\
0&\frac{1}{2}&0&-\frac{1}{2}\\
0&-\frac{1}{2}&0&\frac{1}{2}
\end{array}
\right)\\\sim
\left(
\begin{array}{ccc|c}
-2&-1&-2&1\\
0&1&0&-1\\
0&-1&0&1
\end{array}
\right)
$$

De donde sacamos que:

- $y = -1$
- $x = -z$
- $z\in\mathbb{R}$

Con esto podemos elegir un vector, por ejemplo:

$$
v_1 = (0,-1,0)
$$

Solo habría que verificar que los vectores son LI, por lo tanto, verifiquemos que el siguiente determinante sea diferente a 0:

$$
\begin{vmatrix}
0&1&-1\\
-1&-1&0\\
0&0&1
\end{vmatrix} = 1\dot(0+1) = 1
$$

Con esto confirmamos que $\mathcal{B}= \{(0,-1,0),(1,-1,0),(-1,0,1)\}$ es una base, y además es base de Jordan.

**VERIFICACIÓN:**

Para estar seguros que esto es correcto, verifiquemos que se cumple lo siguiente:

- $T(0,-1,0) = 2v_1 + v_2$
- $T(1,-1,0) = 2v_2 + v_3$
- $T(-1,0,1) = 2v_3$

Con la definición de la transformación tenemos:

$T: \mathbb{R}^3 \to \mathbb{R}^3$ tal que $T(x, y, z) = (-y - 2z, x + 3y + z, x + 3z)$ 

- $T(0,-1,0) = (1,-3,0)$
- $T(1,-1,0) = (1,-2,1)$
- $T(-1,0,1) = (-2,0,2)$

Igualamos con los puntos de arriba:

- $T(0,-1,0) = (1,-3,0) = 2(0,-1,0) + (1,-1,0)\quad\blacksquare$
- $T(1,-1,0) = (1,-2,1) = 2(1,-1,0) + (-1,0,1)\quad\blacksquare$
- $T(-1,0,1) = (-2,0,2) = 2(-1,0,1)\quad\blacksquare$

Por lo tanto, $\mathcal{B}$ es efectivamente una base de Jordan

### Transformación 2

Considerando la base canónica de $\mathbb{R}^3$, calculemos la matriz asociada ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $T(1,0,0) = (3,0,0)$
- $T(0,1,0) = (2,4,1)$
- $T(0,0,1) = (-2,-1,2)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}
3&2&-2\\
0&4&-1\\
0&1&2
\end{pmatrix}
$$

Ahora calculemos el polinomio característico $\Chi_T(\lambda)$:

$$
\begin{aligned}
\Chi_T(\lambda) &= \begin{vmatrix}
3-\lambda&2&-2\\
0&4-\lambda&-1\\
0&1&2-\lambda
\end{vmatrix}\\
&= (3-\lambda)((4-\lambda)(2-\lambda) + 1)\\
&= (3-\lambda)(\lambda^2-6\lambda+9)\\
&= -\lambda^3+9\lambda^2-27\lambda+27
\end{aligned}
$$

#### Recordatorio (teorema de raíces racionales)

Si un polinomio tiene raíces racionales, estas son de la forma $\frac{p}{q}$, donde $p$ es un divisor del término independiente y $q$ es un divisor del coeficiente del término de mayor grado.

#### Continuación

Ahora que conocemos la forma de las raíces, podemos concluir que las raíces del polinomio de tercer grado anterior están incluidas en la lista: $\{\pm 1,\pm 3,\pm 9,\pm 27\}$

Probemos con 3:

$$
\begin{aligned}
-(3)^3+9\cdot(3)^2-27\cdot 3 + 27 &= -27+ 81 - 81 + 27 \\
&= 0
\end{aligned}
$$

Como sabemos que $3$ es raíz, podemos factorizar el polinomio con Ruffini:

$$
\begin{array}{r|rrrr}
& \lambda^3 & \lambda^2 &\lambda^1 &1\\
\hline
& -1 & 9 & -27 & 27\\
\hline
3 & \downarrow & -3 & 18 & -27\\
\hline
& -1 & 6 & -9 & 0
\end{array}
$$

Por lo tanto, puedo expresar el polinomio de tercer grado como:

$$
-\lambda^3+9\lambda^2-27\lambda+27 = (\lambda - 3)(-\lambda^2+6\lambda-9)
$$

Entonces tenemos $\lambda_1 = 3$, y ahora usando Bhaskara puedo obtener todas las demás raíces:

$$
\begin{aligned}
\lambda &= \frac{-6\pm\sqrt{36-36}}{-2}\\
&= \frac{-6\pm0}{-2}
\end{aligned}
$$

De donde obtenemos:

- $\lambda = 3$, con $ma(3) = 3$

**$S_3$**

Tenemos que resolver el sistema $(T-3\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
0&2&-2&0\\
0&1&-1&0\\
0&1&-1&0
\end{array}
\right)
$$

De donde sacamos que:

- $z=y$
- $x\in\mathbb{R}$
- $z\in\mathbb{R}$

El subespacio asociado sería el definido por:

$$
S_3 = \{(\alpha,\beta,\beta)\in\mathbb{R}^3: \alpha,\beta\in\mathbb{R}\}
$$

Entonces una base de este subespacio podría ser:

$$
\{(1,0,0),(0,1,1)\}
$$

Por lo que $mg(2) = 2$, esto implica que $T$ NO es diagonalizable, la forma de Jordan sería:

$$
J_T = \begin{pmatrix}
3&0&0\\
0&3&0\\
0&1&3
\end{pmatrix} 
$$

**BASE DE JORDAN**

Por ahora entonces la base de Jordan que tenemos es $\mathcal{B} = \{(1,0,0),v_2,(0,1,1)\}$.

Para hallar $v_2$, tenemos que:

$$
T(v_2) = 3v_2 + v_3\\
(T-3\mathbb{I})v_2 = v_3
$$

Lo que nos deja con el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
0&2&-2&0\\
0&1&-1&1\\
0&1&-1&1
\end{array}
\right)
$$

Ojo, tenemos que el sistema es incompatible, por lo que tenemos que elegir un vector $v_3\in S_3$ que permita que este sistema sea compatible para encontrar la base, por ejemplo: $v_3 = (2,1,1)\in S_3$. Entonces el sistema nos queda:

$$
\left(
\begin{array}{ccc|c}
0&2&-2&2\\
0&1&-1&1\\
0&1&-1&1
\end{array}
\right)
$$

De donde sacamos:

- $y = 1+z$
- $z\in\mathbb{R}$
- $x\in\mathbb{R}$

Con esto podemos elegir un vector, por ejemplo:

$$
v_2 = (0,1,0)
$$

Solo habría que verificar que los vectores de la base $\mathcal{B} = \{(1,0,0),(0,1,0),(2,1,1)\}$ son LI, por lo tanto, verifiquemos que el siguiente determinante sea diferente a 0:

$$
\begin{vmatrix}
1&0&2\\
0&1&1\\
0&0&1
\end{vmatrix} = 1\dot(1-0) = 1
$$

Con esto confirmamos que $\mathcal{B}$ es una base, y además es base de Jordan.

**VERIFICACIÓN:**

Para estar seguros que esto es correcto, verifiquemos que se cumple lo siguiente:

- $T(1,0,0) = 3v_1$
- $T(0,1,0) = 3v_2 + v_3$
- $T(2,1,1) = 3v_3$

Con la definición de la transformación tenemos:

$T: \mathbb{R}^3 \to \mathbb{R}^3$ tal que $T(x, y, z) = (3x + 2y - 2z, 4y - z, y + 2z)$

- $T(1,0,0) = (3,0,0)$
- $T(0,1,0) = (2,4,1)$
- $T(2,1,1) = (6,3,3)$

Igualamos con los puntos de arriba:

- $T(1,0,0) = (3,0,0) = 3(1,0,0)\quad\blacksquare$
- $T(0,1,0) = (2,4,1) = 3(0,1,0) + (2,1,1)\quad\blacksquare$
- $T(2,1,1) = (6,3,3) = 3(2,1,1)\quad\blacksquare$

Por lo tanto, $\mathcal{B}$ es efectivamente una base de Jordan