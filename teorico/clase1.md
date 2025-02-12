# CLASE 1 - 12/02/2025

## Matriz asociada a una transformación lineal

Sean $V, W$ dos espacios vectoriales con bases $\mathcal{A} = \{v_1, v_2, \ldots, v_n\}\rightarrow V$ y $\mathcal{B} = \{w_1, w_2, \ldots, w_m\}\rightarrow W$. Sea una transformación lineal $T: V \to W$; construimos la matriz asociada a la transformación lineal con las bases $\mathcal{A}$ y $\mathcal{B}$ de la siguiente forma:

$$
{}_{\mathcal{B}}(T)_{\mathcal{A}} = \\
\begin{pmatrix}
coord_{\mathcal{B}}(T(v_1)) & coord_{\mathcal{B}}(T(v_2)) & \cdots & coord_{\mathcal{B}}(T(v_n))
\end{pmatrix}
$$

**Observación**:
(1) Veamos que en la notación, va primero la base de llegada, luego la base de partida
(2) Recordar que $coord_{\mathcal{B}}(v)$ significa reescribir el vector $v$ en función de la base $\mathcal{B}$
(3) Las coordenadas van "colgadas" verticalmente
(4) La matriz ${}_{\mathcal{B}}(T)_{\mathcal{A}} \in \mathcal{M}_{m\times n}$

**Aplicaciones**
(1) Una vez dada la matriz asociada a una TL, podemos hallar la misma. Esto se puede ver en algún ejercicio del práctico

### Propiedades

Sean $V, W$ dos espacios vectoriales con bases $\mathcal{A}$ y $\mathcal{B}$. Sean dos transformaciones lineales $T, S: V \to W$

1. $coord_{\mathcal{B}}(T(v)) = {}_{\mathcal{B}}(T)_{\mathcal{A}} \cdot coord_{A}(v)$
2. ${}_{\mathcal{B}}(T + S)_{\mathcal{A}} = {}_{\mathcal{B}}(T)_{\mathcal{A}} + {}_{\mathcal{B}}(S)_{\mathcal{A}}$
3. Dado $\alpha\in\mathbb{K}$: ${}_{\mathcal{B}}(\alpha T)_{\mathcal{A}} = \alpha\cdot{}_{\mathcal{B}}(T)_{\mathcal{A}}$

Sean $U, V, W$ tres espacios vectoriales con bases $\mathcal{A}$, $\mathcal{B}$ y $\mathcal{C}$. Sean dos transformaciones lineales $S: U \to V$ y $T: V \to W$. Dada la transformación lineal $T \circ S$:

4. ${}_{\mathcal{C}}(T \circ S)_{\mathcal{A}} = {}_{\mathcal{C}}(T)_{\mathcal{B}} \times {}_{\mathcal{B}}(S)_{\mathcal{A}}$

## Cambio de base

Sean dos espacios vectoriales $V,W$, cada una con dos respectivas bases: $A, A' \rightarrow V$ y $B, B' \rightarrow W$. También tenemos una transformación lineal $T:V\to W$.

Nos preguntamos que relación existe entre ${}_{\mathcal{B}}(T)_{\mathcal{A}}$ y ${}_{\mathcal{B'}}(T)_{\mathcal{A'}}$.

Consideramos las transformaciones identidad en $V$ y $W$, es decir:
- $\mathbb{I}_v: V\to V$ tal que $\mathbb{I}_v(v) = v \quad\forall v\in V$
- $\mathbb{I}_w: W\to W$ tal que $\mathbb{I}_w(v) = v \quad\forall v\in W$

Podemos observar que se cumple lo siguiente de forma bastante trivial:

$$\mathbb{I}_w\circ T \circ\mathbb{I}_v = T$$

De esto podemos concluir (usando la propiedad 4):

$$
{}_{\mathcal{B'}}(T)_{\mathcal{A'}} = {}_{\mathcal{B'}}(\mathbb{I}_w)_{\mathcal{B}} \cdot {}_{\mathcal{B}}(T)_{\mathcal{A}} \cdot {}_{\mathcal{A}}(\mathbb{I}_v)_{\mathcal{A'}}
$$

Llamamos a ${}_{\mathcal{A}}(\mathbb{I}_v)_{\mathcal{A'}}$ y ${}_{\mathcal{B'}}(\mathbb{I}_w)_{\mathcal{B}}$ matrices de cambio de base

### Observación

Dado un espacio vectorial $V$ con bases $A, A'$ y la transformación identidad $\mathbb{I}_v: V\to V$:

$$
\begin{align*}
coord_{\mathcal{A'}}(\mathbb{I}(v)) &= coord_{\mathcal{A'}}(v) \\
&= {}_{\mathcal{A'}}(\mathbb{I})_{\mathcal{A}} \cdot coord_{\mathcal{A}}(v)
\end{align*}
$$

Esto por la propiedad 1 definida anteriormente. Con esto podemos concluir que:

$$
coord_{\mathcal{A'}}(v) = {}_{\mathcal{A'}}(\mathbb{I})_{\mathcal{A}} \cdot coord_{\mathcal{A}}(v)
$$

Esto explica porque llamamos a las matrices, como matrices de cambio de base.

### Observación

Partamos viendo que $(\mathbb{I}\circ\mathbb{I}) = \mathbb{I}$. Apliquemos la propiedad 4 a este hecho:

$$
{}_{\mathcal{A}}(\mathbb{I})_{\mathcal{A'}}\cdot {}_{\mathcal{A'}}(\mathbb{I})_{\mathcal{A}} = {}_{\mathcal{A}}(\mathbb{I})_{\mathcal{A}} = (\mathbb{I})
$$

Donde $(\mathbb{I})$ es la matriz identidad. Por la definición de matriz inversa, podemos concluir que:

$$
{}_{\mathcal{A}}(\mathbb{I})_{\mathcal{A'}} = {[\,{}_{\mathcal{A'}}(\mathbb{I})_{\mathcal{A}}]\,}^{-1}
$$

## Matrices semejantes

### Definición

Dadas dos matrices $A,B \in \mathcal{M}_{n\times n}$ decimos que son semejantes sii:

$$
\exists P\in \mathcal{M}_{n\times n}\text{ invertible tal que }A = P\cdot B\cdot P^{-1}
$$

### Observación

En conjunto a lo visto con el cambio de base, si nos paramos en las hipótesis del tema (es decir, nos damos un espacio vectorial, dos bases, una transformación lineal); ahora podemos decir que ${}_{\mathcal{A'}}(T)_{\mathcal{A'}}$ y ${}_{\mathcal{A}}(T)_{\mathcal{A}}$ son semejantes, donde $P$ son es una matriz de cambio de base

### Definición (operador lineal)

Una transformación lineal $T: V\to V$ se llama operador lineal cuando el espacio de llegada es igual al espacio de partida