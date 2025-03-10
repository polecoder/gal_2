# CLASE 5 - 10/03/2025

## Diagonalización

### Ejemplo 1

$T: \mathbb{R}^3\to \mathbb{R}^3$ definida por: $T(x,y,z) = (2x,y-z,-y+z)$

Consideramos la base canónica $\mathcal{E}$, tenemos lo siguiente:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
2&0&0\\
0&1&-1\\
0&-1&1
\end{pmatrix}
$$

Hallemos el polínomio característico $\Chi_T(\lambda)$:

$$
\begin{aligned}
\Chi_T(\lambda) &=
\begin{vmatrix}
2-\lambda&0&0\\
0&1-\lambda&-1\\
0&-1&1-\lambda
\end{vmatrix}\\ 
&= (2-\lambda)((1-\lambda)^2-1)\\
&= (2-\lambda)(\lambda^2 - 2\lambda)\\
&= (2-\lambda)(\lambda(\lambda - 2))
\end{aligned}
$$

De esto se observa que tenemos dos raíces:

1. $\lambda_1 = 0$
2. $\lambda_2 = 2$ que aparece dos veces

Ahora veamos los subespacios propios asignados a estos valores propios:

$$S_0 = \{v\in V\mid v= \alpha(v_2+v_3)\quad \alpha\in\mathbb{R}\}$$

$$S_2 = \{v\in V\mid v= \alpha v_1+\beta(v_3-v_2)\quad \alpha,\beta\in\mathbb{R}\}$$

Vemos que $dim(S_0) = 1$ y $dim(S_2) = 2$, la clave para ver que $T$ es diagonalizable, será estudiar si la suma de las dimensiones de los subespacios propios de los valores propios da la dimensión del espacio en el que estamos trabajando.

En este caso si se da, podemos dar una base de vectores propios para confirmar que $T$ es diagonalizable:

$$
\mathcal{B} = \{(0,1,1), (0,1,-1), (1,0,0)\}
$$

Entonces concluimos que $T$ es diagonalizable, calculemos ${}_{\mathcal{B}}(T)_{\mathcal{B}}$:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
0&0&0\\
0&2&0\\
0&0&2
\end{pmatrix}
$$

### Ejemplo 2

$T: \mathbb{R}^3\to \mathbb{R}^3$ definida por: $T(x,y,z) = (2x+z,y-z,-y+z)$

Consideramos la base canónica $\mathcal{E}$, tenemos lo siguiente:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=
\begin{pmatrix}
2&0&1\\
0&1&-1\\
0&-1&1
\end{pmatrix}
$$

El polinomio característico es el mismo que antes:

$$
\Chi_T(\lambda) = (2-\lambda)(\lambda(\lambda - 2))
$$

Por lo que tenemos los mismos valores propios:

1. $\lambda_1 = 0$
2. $\lambda_2 = 2$ que aparece dos veces

Ahora hallemos los subespacios propios:

#### $S_0$

Tenemos que resolver el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
2&0&1&0\\
0&1&-1&0\\
0&-1&1&0
\end{array}
\right)
$$

De lo cual se deriva que:

- $z = y$
- $z = -2x$

Con esto podemos definir el subespacio propio:

$$S_0 = \{v\in V\mid v= \alpha(v_1-2v_2-2v_3)\quad \alpha\in\mathbb{R}\}$$

Es decir que una base de $S_0$ podría ser:

$$
S_0 = \{(1,-2,-2)\}
$$

#### $S_2$

Tenemos que resolver el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
0&0&1&0\\
0&-1&-1&0\\
0&-1&-1&0
\end{array}
\right)
$$

De lo cual se deriva que:

- $z=0$
- $y=-z$

Con esto podemos definir el subespacio propio:

$$S_2 = \{v\in V\mid v= \alpha v_1\quad \alpha\in\mathbb{R}\}$$

Es decir que una base de $S_2$ podría ser:

$$
S_2 = \{(1,0,0)\}
$$

Por lo que la dimensión del espacio $S_2$ es $1$. Con esto ya sabemos que esta transformación $T$ no es diagonalizable, porque nunca va a poder existir una base de vectores propios si la dimensión de los subespacios propios no suma la dimensión del espacio del operador.

### Condiciones necesarias y suficientes para que una transformación sea diagonalizable

Sea $T:V\to V$ con $dim(V) = n$ con valores propios $\lambda_1,\lambda_2,\ldots,\lambda_n$ de subespacios propios $S_{\lambda_1},S_{\lambda_2},\ldots,S_{\lambda_n}$

#### Lema

La suma de subespacios propios asociados a valores propios distintos es suma directa (es decir que el único elemento que tienen en común es el 0).

##### Demostración

Consideremos $S_{\lambda_1}+S_{\lambda_2}+\ldots+S_{\lambda_n}$ y $v\in S_{\lambda_1}+S_{\lambda_2}+\ldots+S_{\lambda_n}$. Queremos ver que la descomposición de $v$ es única.

Supongamos que:

- $v=v_1+v_2+\ldots+v_n$
- $v=v'_1+v'_2+\ldots+v'_n$

Con $v_i,v'_i\in S_{\lambda_i}$

Son dos formas diferentes de escribir a $v$. Entonces

$$
(v_1-v'_1)+(v_2-v'_2)+\ldots+(v_n-v'_n) = 0
$$

Donde para cada resta, puedo decir lo siguiente:

- $(v_1-v'_1)\in S_{\lambda_1}$ es $0$ o es vector propio asociado a $\lambda_1$
- $(v_2-v'_2)\in S_{\lambda_2}$ es $0$ o es vector propio asociado a $\lambda_2$
- $\ldots$
- $(v_n-v'_n)\in S_{\lambda_n}$ es $0$ o es vector propio asociado a $\lambda_n$

Pero todos estos vectores pertenecen a subespacios propios asociados a valores propios DISTINTOS, esto quiere decir que los vectores son LI.

Por lo tanto, es imposible que la suma de una cantidad finita de vectores LI sea $0$. 

Esto prueba que ambas formas de escribir $v$ son la misma. 

#### Proposición

Sea $T:V\to V$ con $dim(V) = n$ con valores propios $\lambda_1,\lambda_2,\ldots,\lambda_n$. Entonces las siguientes afirmaciones son equivalentes:

1. $T$ es diagonalizable
2. $V = S_{\lambda_1}\oplus S_{\lambda_2}\oplus\ldots\oplus S_{\lambda_n}$
3. $dim(S_{\lambda_1}) + dim(S_{\lambda_2}) +\ldots+ dim(S_{\lambda_n}) = dim(V)$

##### Demostración

Está en esta clase del teórico pero es extremadamente tediosa de escribir.