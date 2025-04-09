# Ejercicio 3

## Consigna

Dada la matriz asociada a $T$ en la base canónica de $\mathbb{R}^3$:

$$
\begin{pmatrix}
\cos\theta & -\sin\theta & 0 \\
\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{pmatrix}
$$  

Hallar:  
1. Los subespacios invariantes de $T$.  
2. Sus valores propios.  
3. Discutir según $\theta$ cuándo $T$ es diagonalizable.

## Resolución

Para empezar, primero hallemos los valores propios de esta matriz, para esto calculamos el polínomio característico:

$$
\begin{aligned}
\Chi_A(\lambda) &= \begin{vmatrix}
\cos\theta-\lambda & -\sin\theta & 0 \\
\sin\theta & \cos\theta-\lambda & 0 \\
0 & 0 & 1-\lambda
\end{vmatrix}\\
&= (1-\lambda)((\cos\theta-\lambda)^2 + \sin^2\theta)\\
&= (1-\lambda)(\lambda^2 - 2\cos\theta\lambda + \cos^2\theta + \sin^2\theta)\\
&= (1-\lambda)(\lambda^2 - 2\cos\theta\lambda + 1)\\
\end{aligned}
$$

Sabemos que a priori $\lambda_1 = 1$ es raíz del polinomio, ahora apliquemos Bháskara para hallar las raíces del segundo polinomio:

$$
\begin{aligned}
\lambda &= \frac{2\cos\theta\pm\sqrt{4\cos^2\theta-4}}{2}\\
&= \frac{2\cos\theta\pm\sqrt{4(\cos^2\theta - 1)}}{2}\\
&= \cos\theta\pm\sqrt{\cos^2\theta - 1}\\
&= \cos\theta\pm\sqrt{-\sin^2\theta}\\
&= \cos\theta\pm i\sin\theta
\end{aligned}
$$

Entonces la única forma de que estos sean valores propios es que pertenezcan a $\mathbb{R}^3$, por lo tanto tenemos que $\sin\theta = 0$, lo que implica que $\theta = k\pi\quad\forall k\in\mathbb{Z}$.

En ese caso tendríamos raíz doble en $\lambda_2=\cos(k\pi)$, a su vez para esto tenemos dos casos según k:

- Si $k$ es par, entonces $\lambda_2 = 1$, habría raíz triple en 1, es decir: $ma(1) = 3$
- Si $k$ es impar, entonces $\lambda_2 = -1$, habría raíz doble en -1, es decir: $ma(-1) = 2$

Analicemos los subespacios según el caso.

**CASO 1: $k$ es par**

Si $k$ es par, tenemos un solo valor propio $\lambda = 1$ con $ma(1) = 3$, veamos de resolver el sistema $(A-1\mathbb{I})v = 0$ para hallar $mg(1)$. La representación del sistema es la siguiente:

$$
\left(
\begin{array}{ccc|c}
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{array}
\right)
$$

De esto sacamos que $mg(1) = 3$, por lo que en este caso, $T$ es diagonalizable.

En cuanto a los subespacios invariantes para este caso, podemos observar que cualquier subespacio de $\mathbb{R}^3$ sería $T$-invariante, porque tendríamos una representación matricial igual a la identidad, por lo que cualquier vector $v\in\mathbb{R}^3$ cumpliría que $T(v) = v$

**CASO 2: $k$ es impar**

En este caso ya tenemos que $ma(1) = mg(1) = 1$, solo habría que verificar el subespacio asociado a $\lambda_2 = -1$, que podemos verlo con el sistema $(A+1\mathbb{I})v = 0$. La representación del sistema es la siguiente:

$$
\left(
\begin{array}{ccc|c}
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0\\
0 & 0 & 1 & 0
\end{array}
\right)
$$

De esto sacamos que $mg(1) = 2$, por lo que en este caso también, $T$ es diagonalizable.

En este caso tendríamos que los subespacios propios serían los únicos subespacios invariantes además de los subespacios triviales.