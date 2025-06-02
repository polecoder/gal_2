# CLASE 13 - 02/06/2025

## Descomposición QR

Sea $A\in\mathcal{M}_{n\times n}$ tal que $rg(A)=n$. Entonces existen una matriz $Q\in\mathcal{M}_{n\times n}$ que verifica $Q^tQ=\mathbb{I}$ y una matriz triangular superior $R\in\mathcal{M}_{n\times n}$ tal que:

$$A=QR$$

### Demostración

Sea $A=\begin{pmatrix}v_1&v_2&\ldots&v_n\\\vdots&\vdots&&\vdots\end{pmatrix}\in \mathcal{M}_{n\times n}$

Como $rg(A)=n$ entonces $\mathcal{B}=\{v_1,\ldots,v_n\}$ es LI, por tanto base de $\mathbb{R}^n$.

Usando el método de ortonormalización de Gram-Schmidt obtenemos una base ortonormal de $\mathbb{R}^n$, $\mathcal{B}'=\{y_1,\ldots,y_n\}$.

Llamamos $Q=\begin{pmatrix}y_1&y_2&\ldots&y_n\\\vdots&\vdots&&\vdots\end{pmatrix}\in\mathcal{M}_{n\times n}$ y $R={}_{\mathcal{B'}}(\mathbb{I})_{\mathcal{B}}$ que es triangular superior.

Ahora resta probar que $Q^tQ=\mathbb{I}$ y que $A=QR$, veamos ambas partes:

$$
Q^tQ=\begin{pmatrix}y_1&\ldots\\y_2&\ldots\\\vdots&\\y_n&\ldots\end{pmatrix}\cdot\begin{pmatrix}y_1&y_2&\ldots&y_n\\\vdots&\vdots&&\vdots\end{pmatrix}
$$

Observemos que:

$$
(Q^tQ)_{ij}=\left<y_i, y_j\right>=\begin{cases}0\quad\text{si }i\neq j\\ 1\quad\text{si }i=j\end{cases}
$$

Donde:
1. El producto interno es el usual en $\mathbb{R}^n$
2. La observación de los casos es porque la base $\mathcal{B}'$ es ortonormal.

Con esto concluimos que $Q^tQ=\mathbb{I}$.

Ahora resta probar que $A=QR$. Lo cual es bastante tedioso por lo que no lo voy a escribir, pero con las primeras columnas se ve que es verdadero.

## Complemento ortogonal

Sea $V$ espacio vectorial con producto interno, $S\subset V$.
Definimos el complemento ortogonal de $S$ como el conjunto de vectores $S^{\perp}$ tal que:

$$
S^{\perp}=\{v\in V \mid \forall s\in S: v\perp s\}=\{v\in V\mid\forall s\in S:\left<v, s\right>=0\}
$$

Es decir que $S^{\perp}$ es el conjunto de todos los vectores que son ortogonales a todos los vectores de $S$.

### Ejemplo

$V=\mathbb{R}^3$ con producto interno habitual. $S=[(1,0,1)]=\{(\alpha,0,\alpha):\alpha\in\mathbb{R}\}$

Decimos que:

$$
\begin{aligned}
v=(x,y,z)\in S^{\perp}&\iff\left<(x,y,z), (\alpha,0,\alpha)\right>=0\quad\forall\alpha\in\mathbb{R}\\
&\iff \alpha(x+z)=0\quad\forall\alpha\in\mathbb{R}\\
&\iff\begin{cases}x=-z\\y\in\mathbb{R}\end{cases}
\end{aligned}
$$

Por lo tanto:

$$
S^{\perp}=\{(x,y,-x):x,y\in\mathbb{R}\}=[(1,0,-1),(0,1,0)]
$$

### Proposición

$S^{\perp}$ es un subespacio de $V$, sin importar si $S$ no lo es.

#### Demostración

1. $0\in S^{\perp}$ pues $\left<0, s\right>=0\quad\forall s\in S$
2. $v,w\in S^{\perp}$, veamos que $\left<v+w, s\right>=\left<v, s\right>+\left<w, s\right>=0\quad\forall s\in S$. Entonces $v+w\in S^{\perp}$
3. $a\in\mathbb{K}, v\in S^{\perp}$, entonces $\left<av, s\right>=a\left<v, s\right>= 0\quad\forall s\in S$. Entonces $av\in S^{\perp}$

### Proposición

Sea $V$ espacio vectorial con producto interno. Sea $S$ subsespacio vectorial de dimensión finita, con base $\mathcal{B}=\{s_1,\ldots,s_r\}$.
Entonces $v\in S^{\perp}\iff v\perp s_i\quad\forall i=1,2,\ldots,r$

#### Demostración

$(\Rightarrow)$ Evidente por definición de $S^{\perp}$

$(\Leftarrow)$ Supongamos que $v$ cumple que: $\left<v, s_i\right>=0\quad\forall i=1,2,\ldots,r$
Consideramos $s=a_1s_1+\ldots a_rs_r\in S$. Entonces:

$$
\left<v, s\right>= \overline{a_1}\left<v, s_1\right>+\ldots+\overline{a_r}\left<v, s_r\right>=0
$$

Como no asumimos nada sobre $s\in S$, esto vale para cualquier vector $s$, lo que concluye la prueba.

#### Ejemplo

$V=\mathbb{R}^3$ con producto interno habitual.

$S=\{(x,y,z)\in\mathbb{R}^3: 2x-z=0\}=\{(x,y,2x): x,y\in\mathbb{R}\}$

Consideremos la siguiente base $\mathcal{B}$ de $S$:

$$
\mathcal{B}=\{(1,0,2),(0,1,0)\}
$$

Por lo tanto:

$S^{\perp}=\{(x,y,z)\in\mathbb{R}^3: \left<(x,y,z), (1,0,2)\right>=0\text{ y }\left<(x,y,z), (0,1,0)\right>=0\}$

De esto derivamos que:

1. $x+2z=0$
2. $y=0$

Entonces:

$$
S^{\perp}=\{(-2z,0,z):z\in\mathbb{R}\}=[(-2,0,1)]
$$
