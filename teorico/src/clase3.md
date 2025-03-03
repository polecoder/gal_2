# CLASE 3 - 20/2/2025

## Vectores y valores propios

### Proposición

Sea $T:V\to V$ un operador líneal, $\mathcal{B} = \{v_1, v_2,\ldots, v_n\}$ una base de $V$. Consideramos la matriz $A = {}_{\mathcal{B}}(T)_{\mathcal{B}}$.

Decimos que $v$ es vector propio de $T$ asociado al valor propio $\lambda$ sii:

$$coord_{\mathcal{B}}(v) = (a_1, a_2, \ldots, a_n)$$

Es solución no trivial del sistema:

$$(A-\lambda\mathbb{I})\cdot\begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix} = \begin{pmatrix}0\\0\\\vdots\\0\end{pmatrix}$$

#### Demostración

##### $(\Rightarrow)$

Consideramos $v\in V, v\neq\vec{0}$, tal que $v$ es vector propio de $T$.

Por las hipótesis, se cumple que:

1. $coord_{\mathcal{B}}(v)\neq (0,0,\ldots,0)$
2. $coord_{\mathcal{B}}(T(v)) = coord_{\mathcal{B}}(\lambda v) = \lambda\cdot coord_{\mathcal{B}}(v)$

A su vez:

$$coord_{\mathcal{B}}(T(v)) = {}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v)$$

Entonces, si sustituimos en el punto (2):

$$
\begin{aligned}
&{}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v) = \lambda\cdot coord_{\mathcal{B}}(v)\iff\\
&{}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v) - \lambda\cdot coord_{\mathcal{B}}(v) = (0,0,\ldots,0)\iff\\
&({}_{\mathcal{B}}(T)_{\mathcal{B}} - \lambda\mathbb{I})\cdot coord_{\mathcal{B}}(v) = (0,0,\ldots,0)\iff\\
&(A - \lambda\mathbb{I})\cdot coord_{\mathcal{B}}(v) = (0,0,\ldots,0)
\end{aligned}
$$

Que es lo que queríamos hallar. Esto prueba $(\Rightarrow)$

##### $(\Leftarrow)$

Si $coord_{\mathcal{B}}(v) = (a_1, a_2, \ldots, a_n)$ es solución no trivial del sistema:

$$(A-\lambda\mathbb{I})\cdot\begin{pmatrix}a_1\\a_2\\\vdots\\a_n\end{pmatrix} = \begin{pmatrix}0\\0\\\vdots\\0\end{pmatrix}$$

Entonces:

$$
A\cdot\begin{pmatrix}a_1\\a_2\\\vdots\\a_n\end{pmatrix} = \lambda \cdot\begin{pmatrix}a_1\\a_2\\\vdots\\a_n\end{pmatrix}
$$

Esto equivale a:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v) = \lambda\cdot coord_{\mathcal{B}}(v)
$$

Pero sabiendo que ${}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v) = coord_{\mathcal{B}}(T(v))$, entonces:

$$
coord_{\mathcal{B}}(T(v)) = coord_{\mathcal{B}}(\lambda v)
$$

Por lo tanto: $T(v) = \lambda v$, lo que significa que $v$ es vector propio asociado a $\lambda$ de $T$

### Corolario

Sea $V$ un espacio vectorial sobre $\mathbb{K}$, una transformación $T:V\to V$ un operador lineal, $\mathcal{B}$ es base de V, y $A={}_{\mathcal{B}}(T)_{\mathcal{B}}$

Se cumple que:

$\lambda$ es valor propio de $T$ sii:

1. $\lambda\in\mathbb{K}$
2. $det(A-\lambda\mathbb{I}) = 0$

#### Demostración

Por la proposición anterior, sabemos que:

$\lambda$ es valor propio sii existe $v\in V$ tal que $coord_{\mathcal{B}}(v)$ es solución no trivial del sistema:

$$(A-\lambda\mathbb{I})\cdot\begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix} = \begin{pmatrix}0\\0\\\vdots\\0\end{pmatrix}$$

Esto pasa solo si el sistema es compatible indeterminado (más de una solución aparte de la trivial). Esto a su vez solo pasa si $(A-\lambda\mathbb{I})$ es invertible, que es equivalente a decir que solo pasa si $det(A-\lambda\mathbb{I}) = 0$

### Ejemplo (hallar valores y vectores propios de una transformación)

Sea $V$ un $\mathbb{R}$-espacio vectorial con cierta base $\mathcal{B} = \{v_1,v_2,v_3\}$ y $T:V\to V$. Supongamos que: 
$$A= {}_{\mathcal{B}}(T)_{\mathcal{B}} = \begin{pmatrix}2&0&0\\0&1&-1\\0&-1&1\end{pmatrix}$$

Tenemos que calcular $det(A-\lambda\mathbb{I})$ para encontrar los valores propios de $T$:

$$
det(A-\lambda\mathbb{I}) = \begin{vmatrix}2-\lambda&0&0\\0&1-\lambda&-1\\0&-1&1-\lambda\end{vmatrix}
$$

Por lo tanto:

$$
det(A-\lambda\mathbb{I}) = (2-\lambda)((1-\lambda)^2-1) = (2-\lambda)(\lambda^2-2\lambda)
$$

Obtenemos que:

- $\lambda_1 = 0$ es solución, por lo tanto valor propio de $T$
- $\lambda_2 = 2$ es solución, por lo tanto valor propio de $T$

Ahora que tenemos los valores propios de $T$, hallemos los subespacios propios asociados a los $\lambda$ que hallamos. Para esto tenemos que resolver el sistema de ecuaciones utilizando $\lambda_1,\lambda_2$:

#### Subespacio $S_0$

$det(A-0\mathbb{I})\cdot\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}0\\0\\0\end{pmatrix}$

Esto es:

$$
\begin{pmatrix}2&0&0\\0&1&-1\\0&-1&1\end{pmatrix}\cdot\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}0\\0\\0\end{pmatrix}
$$

Que equivale al sistema

$$
\begin{array}{ccc|c}
2&0&0&0\\
0&1&-1&0\\
0&-1&1&0
\end{array}
$$

De donde obtengo que:

- $x = 0$
- $y = z$
- $z\in\mathbb{R}$

Entonces $coord_{\mathcal{B}}(v) = (0,\alpha,\alpha)\mid \alpha\in\mathbb{R}$. Con esto podemos definir el subespacio propio:

$$S_0 = \{v\in V\mid v= \alpha(v_2+v_3)\quad \alpha\in\mathbb{R}\}$$

Observemos que $dim(S_0) = 1$

#### Subespacio $S_2$

Reducimos algunos pasos para este caso, ya que siempre es el mismo procedimiento.

$$
\begin{array}{ccc|c}
0&0&0&0\\
0&-1&-1&0\\
0&-1&-1&0
\end{array}
$$

Podemos ver que nos queda:

- $y = -z$

Entonces $coord_{\mathcal{B}}(v) = (\alpha,-\beta,\beta)\mid \alpha,\beta\in\mathbb{R}$. Con esto podemos definir el subespacio propio:

$$S_2 = \{v\in V\mid v= \alpha v_1+\beta(v_3-v_2)\quad \alpha,\beta\in\mathbb{R}\}$$

Observemos que $dim(S_2) = 2$

### Extensión de vaps y veps a Matrices

La definición de vectores y valores propios se puede extender a matrices en caso de que trabajemos con ellas:

Sea $A\in\mathcal{M}_{n\times n}(\mathbb{K})$. Decimos que un vector propio de $A$ asociado a un valor propio $\lambda$ es un vector no nulo $(x_1,x_2,\ldots,x_n)\in\mathbb{K}^n$ tal que:

$$
A\cdot\begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix} = \lambda\cdot\begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix}
$$

Entonces los valores propios son soluciones (en $\mathbb{K}$) de $det(A-\lambda\mathbb{I}) = 0$

### Notación

- Polínomio característico de $T$: $\Chi_T(\lambda) := det(A-\lambda\mathbb{I})$

- Ecuación característica de $T$: $\Chi_T(\lambda) = 0$

Las soluciones de la ecuación característica, son llamadas **raíces características** de $T$. Entonces si dichas raíces pertenecen al cuerpo de $T$, son los valores propios de $T$