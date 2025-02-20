# CLASE 2 - 17/02/2025

## Matrices semejantes

### Aplicaciones

1. La definición de matriz semejante es muy útil a la hora de calcular potencias; sean $A,B$ dos matrices semejantes, entonces:
    - $B^2 = (P^{-1}AP)(P^{-1}AP) = P^{-1}A^2P$

    En general:
    - $B^n = P^{-1}A^nP\quad\forall n\geq1$

    Esto puede ser útil cuando tenemos que alguna de las dos matrices $A,B$ tiene una forma más sencilla de elevar (por ejemplo que alguna sea diagonal)

### Teorema

Sea $A,B\in\mathcal{M}_{n\times n}$; decimos que $A,B$ son semejantes sii:

$\exists T:V\to V$; con $dim(V) = n$ y bases $\mathcal{C}, \mathcal{C'}$ tales que:

$$A= {}_{\mathcal{C}}(T)_{\mathcal{C}}\quad B={}_{\mathcal{C'}}(T)_{\mathcal{C'}}$$

#### Demostración

En el libro rojo

### Teorema

Si $A,B\in\mathcal{M}_{n\times n}$ son matrices semejantes. Entonces:

1. $rg(A) = rg(B)$
2. $tr(A) = tr(B)$
3. $det(A) = det(B)$

#### Demostración

##### PARTE 1

Por el anterior teorema, como $A,B$ son semejantes, entonces: $\exists T:V\to V$ y bases $C,C'$ tal que: $A = {}_{\mathcal{C}}(T)_{\mathcal{C}}$ y $B = {}_{\mathcal{C'}}(T)_{\mathcal{C'}}$

Entonces:

- $rg(A) = rg\left({}_{\mathcal{C}}(T)_{\mathcal{C}}\right) = dim(Im(T))$
- $rg(B) = rg\left({}_{\mathcal{C'}}(T)_{\mathcal{C'}}\right) = dim(Im(T))$

Por lo tanto:

$\Rightarrow rg(A) = rg(B)$

##### PARTE 2

**Recordatorio**: 
1. La traza es la suma de los elementos de la diagonal de la matriz
2. $tr(AB) = tr(BA)$

Veamos que:

$$
tr(B) = tr(P^{-1}AP) = tr(AP^{-1}P) = tr(A)
$$

##### PARTE 3:

**Recordatorio**:
$det(AB) = det(A)\cdot det(B)$

Entonces:

$$
det(B)=det(P^{-1}AP) = det(P^{-1})\cdot det(A)\cdot det(P) = det(A)
$$

#### Observación

El reciproco NO es cierto, veamos un ejemplo:

$A = \begin{pmatrix}1&0\\0&1\end{pmatrix}$ y $B = \begin{pmatrix}1&0\\1&1\end{pmatrix}$

Veamos que:

- $rg(A) = rg(B)$
- $tr(A) = tr(B)$
- $det(A) = det(B)$

Supongamos que SI son semejantes, es decir que: $\exists P$ tal que:

$$
B = P^{-1}AP = (I)
$$

Pero $B\neq (I)$, entonces esto es absurdo.

## Valores y vectores propios

### Definición

Sea $V$ un espacio vectorial sobre $\mathbb{K}\mid(\mathbb{R}$ o $\mathbb{C})$ y una transformación lineal $T:V\to V$. Decimos que un vector $v \in V, v\neq \vec{0}$ es **vector propio** de $T$ si existe $\lambda\in\mathbb{K}$ tal que:

$$T(v) = \lambda v$$

Decimos que $v$ es un vector propio asociado al valor propio $\lambda$

#### Ejemplo

Sea $T:\mathbb{R}^2\to\mathbb{R}^2$ definida por $T(x,y) = (-2x+y, 6x-y)$. Veamos que se cumple que:

- $T(1,3) = (1,3)$
- $T(1,-2) = (-4, 8) = (-4)(1,-2)$

Entonces:

- $(1,3)$ es **vep** de $T$ asociado a $\lambda=1$
- $(1,-2)$ es **vep** de $T$ asociado a $\lambda=-4$

### Definición (subespacio propio)

Sea $T:V\to V$ un operador líneal, con $\lambda$ un valor propio de $T$. Se define el subespacio propio asociado a $\lambda$ de la siguiente forma:

$$S_\lambda = \{v\in V: T(v) = \lambda v\}$$

#### Proposición

$S_\lambda$ es un subespacio vectorial de $V$

##### Demostración

- $\vec{0}\in S_\lambda\quad(S_\lambda\neq\emptyset)$
- Si $v\in S_\lambda, \alpha\in\mathbb{K}$ entonces $T(\alpha v) = \alpha T(v) = \alpha\lambda v = \lambda(\alpha v)$. Entonces $\alpha v\in S_\lambda$
- Si $v,w\in S_\lambda$ entonces: $T(v+w) = T(v) + T(w) = \lambda v + \lambda w= \lambda(v+w)$. Entonces $(v+w)\in S_\lambda$

Entonces $S_\lambda$ es un subespacio vectorial de $V$

#### Observación

$S_\lambda = Ker(T-\lambda\mathbb{I})$

##### Demostración

Tenemos que:

$$
\begin{align*}
&v\in S_\lambda \iff\\
&T(v) = \lambda v \iff\\
&T(v)-\lambda v = 0 \iff\\
&(T-\lambda\mathbb{I})(v) = 0 \iff\\
&v\in Ker(T-\lambda\mathbb{I})
\end{align*}
$$