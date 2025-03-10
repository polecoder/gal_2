# CLASE 4 - 10/03/2025

## Vectores y valores propios

### Lema

Si $A,B\in\mathcal{M}_{n\times n}$ son matrices semejantes, entonces $\Chi_A(\lambda) = \Chi_B(\lambda)$. En particular, $A,B$ tienen los mismos valores propios.

#### Demostración

Como son semejantes, $\exists P\in\mathcal{M}_{n\times n}$ tal que: $B=P^{-1}AP$, además también podemos ver que: $\lambda\mathbb{I} = P^{-1}\lambda\mathbb{I}P$

Con esto podemos decir que:

$$
\begin{aligned}
&B-\lambda\mathbb{I} = P^{-1}AP - P^{-1}\lambda\mathbb{I}P\\
&\iff\quad\text{ saco }P^{-1},P\text{ de factor común }\\
&B-\lambda\mathbb{I} = P^{-1}(A - \lambda\mathbb{I})P\\
\end{aligned}
$$

Entonces $(B-\lambda\mathbb{I})$ y $(A - \lambda\mathbb{I})$ son matrices semejantes, y como los determinantes de matrices semejantes son iguales, podemos decir que:

$$
det(A - \lambda\mathbb{I}) = det(B-\lambda\mathbb{I})\iff\\
\Chi_A(\lambda) = \Chi_B(\lambda)
$$

#### Observación

Sea $T:V\to V$ con $dim(V) = n$ y dos bases de $V$; $\mathcal{B}, \mathcal{B'}$. Entonces tenemos:

- $A = {}_{\mathcal{B}}(T)_{\mathcal{B}}$
- $A' = {}_{\mathcal{B'}}(T)_{\mathcal{B'}}$

Que son matrices semejantes, entonces por el lema anterior tenemos que:

$$
\Chi_A(\lambda) = \Chi_{A'}(\lambda)
$$

Por lo que entonces, no importa la base con la que trabajemos para determinar los valores propios de una TL.

#### Observación

El recíproco del lema, no es cierto. Es decir que si dos matrices tienen el mismo polinomio característico, no necesariamente las matrices son semejantes.

Veamos un contraejemplo:

$$
A=\begin{pmatrix}1&0\\0&1\end{pmatrix};\quad B=\begin{pmatrix}1&0\\1&1\end{pmatrix}
$$

Sabemos que no son semejantes, pero es fácil observar que el polinomio característico es el mismo.

## Diagonalización

### Definición (transformación lineal diagonalizable)

Sea $T:V\to V$, decimos que $T$ es diagonalizable si existe una base de $V: \mathcal{B}$ tal que ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es una matriz diagonal.

### Definición (matriz diagonalizable)

Decimos que una matriz $A\in\mathcal{M}_{n\times n}$ es diagonalizable si es semejante a una matriz diagonal.

### Teorema

Sea $T:V\to V$ es diagonalizable $\iff$ existe una base de $V$ formada por vectores propios de $T$ (la matriz asociada en esa base es diagonal)

#### Demostración

##### ($\Rightarrow$)

$T$ es diagonalizable $\Rightarrow \exists \mathcal{B} = \{v_1,v_2,\ldots,v_n\}$ base de $V$ tal que:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = 
\begin{pmatrix}
\lambda_1&0&\ldots&0\\
0&\lambda_2&\ldots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&0&\ldots&\lambda_n
\end{pmatrix}
$$

Donde podemos observar que:

- $coord_{\mathcal{B}}(T(v_1)) = \lambda_1\cdot v_1$
- $coord_{\mathcal{B}}(T(v_2)) = \lambda_1\cdot v_2$
- $\cdots$
- $coord_{\mathcal{B}}(T(v_n)) = \lambda_1\cdot v_n$

Esto significa que:

- $v_1$ es vector propio asociado al valor propio $\lambda_1$
- $v_2$ es vector propio asociado al valor propio $\lambda_2$
- $\cdots$
- $v_n$ es vector propio asociado al valor propio $\lambda_n$

Entonces $\mathcal{B}$ es una base de $V$ formada por vectores propios de $T$.

##### ($\Leftarrow$)

Si $\mathcal{B}$ es una base de valores propios, entonces tenemos que:

- $T(v_1) = \lambda_1\cdot v_1$
- $T(v_2) = \lambda_1\cdot v_2$
- $\cdots$
- $T(v_n) = \lambda_1\cdot v_n$

Con esto podemos hallar la matriz asociada:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = 
\begin{pmatrix}
\lambda_1&0&\ldots&0\\
0&\lambda_2&\ldots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&0&\ldots&\lambda_n
\end{pmatrix}
$$

Con lo que se concluye que $T$ es diagonalizable. $\blacksquare$

#### Observación

La forma diagonal es única, a menos del órden de los valores propios $\lambda_1,\lambda_2,\ldots,\lambda_n$

### Teorema

Sea $T:V\to V$ un operador líneal. Sean $\lambda_1,\lambda_2,\ldots,\lambda_k$ valores propios de $T$ dos a dos distintos y $v_1,v_2,\ldots,v_k$ vectores propios asociados a cada uno de los valores propios.

Entonces $\{v_1,v_2,\ldots,v_k\}$ es un conjunto LI

#### Demostración

Se hará la inducción sobre el número de valores propios $k\in\mathbb{N}$.

##### Paso base

($n=1$): $v_1$ vector propio asociado a $\lambda_1$

Se observa trivialmente que $\{v_1\}$ es un conjunto LI

##### Paso inductivo

(H) ($n=k$): $v_1,v_2,\ldots,v_k$ vectores propios asociados a $\lambda_1,\lambda_2,\ldots,\lambda_k$

Asumimos que $\{v_1,v_2,\ldots,v_k\}$ es LI

(T) ($n=k+1$): $v_1,v_2,\ldots,v_k,v_{k+1}$ vectores propios asociados a $\lambda_1,\lambda_2,\ldots,\lambda_k,\lambda_{k+1}$

Consideremos la ecuación

$$
\begin{aligned}
&\alpha_1 v_1 + \alpha_2 v_2 + \ldots + \alpha_k v_k + \alpha_{k+1} v_{k+1} = 0\quad (i)\\
&\iff\text{ aplicamos }T\text{ a ambos lados}\\
&\alpha_1 T(v_1) + \alpha_2 T(v_2) + \ldots + \alpha_k T(v_k) + \alpha_{k+1} T(v_{k+1}) = 0\\
&\iff\text{utilizando los valores propios de }T\\
& \alpha_1\lambda_1 v_1 + \alpha_2\lambda_2 v_2 + \ldots + \alpha_k\lambda_k v_k + \alpha_{k+1} \lambda_{k+1} v_{k+1} = 0\quad (ii)
\end{aligned}
$$

Ahora, múltiplicamos $(i)$ por $\lambda_{k+1}$ y lo restamos a $(ii)$. Obtenemos lo siguiente:

$$
\alpha_1(\lambda_1-\lambda_{k+1}) v_1 + \alpha_2(\lambda_2-\lambda_{k+1}) v_2 + \ldots + \alpha_k(\lambda_k-\lambda_{k+1}) v_k + 0 = 0\quad (iii)
$$

Por hipótesis inductiva, $\{v_1,v_2,\ldots,v_k\}$ es LI, lo cual implica que:

- $\alpha_1(\lambda_1-\lambda_{k+1}) = 0$
- $\alpha_2(\lambda_2-\lambda_{k+1}) = 0$
- $\cdots$
- $\alpha_k(\lambda_k-\lambda_{k+1}) = 0$

Donde todos los paréntesis no pueden ser $0$, porque todos los valores propios son distintos entre si. Esto solo deja la posibilidad de que $\alpha_1,\alpha_2,\ldots,\alpha_k = 0$

Llevando todo esto a la ecuación $(i)$, nos queda que:

$$
\alpha_{k+1} v_{k+1} = 0
$$

Como $v_{k+1}$ es vector propio, sabemos que necesariamente $v_{k+1}\neq\vec{0}$. 

Esto implica que todos los escalares $\alpha_1,\alpha_2,\ldots,\alpha_k,\alpha_{k+1} = 0$, es decir, el conjunto $\{v_1,v_2,\ldots,v_k,v_{k+1}\}$ es LI. $\blacksquare$

### Corolario

Sea $T:V\to V$ con $dim(V) = n$. Si $T$ tiene $n$ valores propios diferentes dos a dos, entonces $T$ es diagonalizable

#### Demostración

Consideramos $v_1,v_2,\ldots,v_n$ vectores propios asociados a los valores propios $\lambda_1,\lambda_2,\ldots,\lambda_n$ (todos distintos).

Por el teorema anterior sabemos que: $\{v_1,v_2,\ldots,v_n\}$ es LI. Como $dim(V)=n$, juntando con lo anterior podemos decir que:

$\{v_1,v_2,\ldots,v_n\}$ es base de V, en particular, es una base de vectores propios de $T$, por lo que $T$ es diagonalizable. $\blacksquare$