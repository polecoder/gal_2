# CLASE 6 - 11/03/2025

## Diagonalización

### Definición (multiplicidad algebraica y geométrica)

Sea $T:V\to V$ con $dim(V) = n$ y $\lambda$ valor propio de $T$. Denotamos:

- la **multiplicidad algebraica de $\lambda$**: $ma(\lambda)$ como la multiplicidad de $\lambda$ como raíz del polinomio característico (la cantidad de veces que aparece la raíz)

- la **multiplicidad geométrica de $\lambda$**: $mg(\lambda)$ como la dimensión del subespacio asociado a $\lambda$

### Proposición

Si $\lambda_0$ es valor propio de $T$, entonces:

$$1\leq mg(\lambda_0)\leq ma(\lambda_0)\leq n$$

#### Demostración

- $1\leq mg(\lambda_0)$: Es obvio, la dimensión de $S_{\lambda_0}$ tiene que ser al menos 1.

- $ma(\lambda_0)\leq n$: Es obvio, el polinomio característico no puede ser de mayor grado que la dimensión del espacio.

Ahora, veamos que $mg(\lambda_0)\leq ma(\lambda_0)$.

Denotamos $m=mg(\lambda_0)=dim(S_{\lambda_0})$. Consideremos $\{v_1,\ldots,v_m\}$ base de $S_{\lambda_0}$.
Sabemos que $T(v_i) = \lambda_0 v_i\quad\forall i\in\{1,\ldots,m\}$

Ahora completemos la base de $S_{\lambda_0}$ hasta obtener una base de $V$.

$$
\mathcal{B}=\{v_1,\ldots,v_m, v_{m+1},\ldots, v_n\}
$$

Ahora, veamos la forma de la matriz asociada a esta base $\mathcal{B}$:

$$
A={}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
\lambda_0&0&0&\cdots&x&\cdots&x\\
0&\lambda_0&0&\cdots&x&\cdots&x\\
0&0&\lambda_0&\cdots&x&\cdots&x\\
\vdots&\vdots&\vdots&\ddots&y&\cdots&y\\
0&0&0&\cdots&y&\cdots&y
\end{pmatrix}
$$

Donde podemos observar 3 regiones:

- La parte diagonal donde están los valores propios, que tiene tamaño $m\times m$. La llamaremos la matriz $L$
- La parte $X$ que tiene tamaño $(m-n)\times m$
- La parte $Y$ que tiene tamaño $(m-n)\times(m-n)$

Y todo lo que está por debajo de la submatriz diagonal, son ceros.

Ahora si quisieramos hallar el polinomio característico de esta matriz, lo haríamos de la siguiente forma:

$$
det(A-\lambda\mathbb{I})=
det
\left(
\begin{array}{c|c}
L-\lambda\mathbb{I}&X\\
\hline
0&Y-\lambda\mathbb{I}_{(n-m)}
\end{array}
\right)
$$

Usando un resultado de GAL 1, podemos decir que ese determinante es igual a:

$$
\Chi_T(\lambda) = det(A-\lambda\mathbb{I}) = det(L-\lambda\mathbb{I})\cdot det(Y-\lambda\mathbb{I}_{(n-m)}) = (\lambda_0 - \lambda)^m\cdot p(\lambda)
$$

Donde $p(\lambda)$ es el polinomio característico de una matriz de tamaño $(n-m)\times(n-m)$

Observemos que $\lambda_0$ tiene como mínimo una multiplicidad algebraica $ma(\lambda_0) = m$. Pero si $\lambda_0$ es raíz del polinomio $p(\lambda)$ la multiplicidad será mayor a $m$

Con esto, podemos asegurar que:

$$
m\leq ma(\lambda_0)
$$

Pero $m=mg(\lambda_0)$, por lo que probamos la última desigualdad que nos da esta proposición. $\blacksquare$

### Corolario

Sea $T:V\to V$ con $dim(V) = n$ es diagonalizable si y sólo si:

1. toda raíz $\lambda$ de $\Chi_T(\lambda)$ está en $\mathbb{K}$ y,

2. cumple que $ma(\lambda) = mg(\lambda)$

#### Demostración

Denotamos:

1. $\lambda_1,\ldots,\lambda_r$ como los valores propios de $T$
2. $S_{\lambda_1},\ldots,S_{\lambda_r}$ como los subespacios propios asociados a dichos valores propios

Se cumple que:

$$\{\lambda_1,\ldots,\lambda_r\}\subseteq\{\lambda: \lambda\text{ es raíz de }\Chi_T(\lambda)\}$$

Entonces:

$$
\sum_{i=1}^r dim(S_{\lambda_i}) = \sum_{i=1}^r mg(\lambda_i)\leq \sum_{i=1}^r ma(\lambda_i)\leq\sum_{\lambda:\lambda\text{ raíz de }\Chi_T(\lambda)}ma(\lambda) = n
$$

Por lo tanto, para que esto suceda, todas las desigualdades necesariamente tienen que ser igualdades.

Además, como sabemos que:

$T$ es diagonalizable $\iff\sum_{i=1}^r dim(S_{\lambda_i}) = n$

Esto solo se cumple si las todas las desigualdades anteriores son igualdades, y esto a su vez solo se cumple si:

1. toda raíz $\lambda$ de $\Chi_T(\lambda)$ está en $\mathbb{K}$ porque necesitamos que: 

$$ma(\lambda_i)\leq\sum_{\lambda:\lambda\text{ raíz de }\Chi_T(\lambda)}ma(\lambda)$$

2. toda raíz $\lambda$ de $\Chi_T(\lambda)$ cumple que $ma(\lambda) = mg(\lambda)$, porque necesitamos que:

$$
\sum_{i=1}^r mg(\lambda_i)\leq \sum_{i=1}^r ma(\lambda_i)
$$

Esto prueba el resultado. $\blacksquare$