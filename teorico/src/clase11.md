# CLASE 11 - 14/04/2025

## Norma inducida y Ortogonalidad

### Observación

Sea $V$ un $\mathbb{R}$-espacio vectorial con producto interno, dos vectores $v,w\in V$ tal que $v,w\neq \vec{0}$. Se cumple que:

$$
-1\leq\frac{\left<v, w\right>}{\|v\|\|w\|}\leq 1
$$

Por otra parte, en $\mathbb{R}^3$ y con el producto interno usual: $\left<v, w\right> = \|v\|\|w\|\cos\theta$.

Definimos el ángulo entre $v$ y $w$ como el ángulo $\theta$ que cumple lo siguiente:

$$
\cos\theta = \frac{\left<v, w\right>}{\|v\|\|w\|}
$$

### Corolario 1 (de la desigualdad de Cauchy-Schwarz)

Sea $V=\mathbb{R}^n$ con $\left<x, y\right> = \sum_{i=1}^n x_iy_i$, considerando:
- $x=\{x_1,x_2,\ldots,x_n\}$
- $y=\{y_1,y_2,\ldots,y_n\}$

Se cumple:

$$
\left(\sum_{i=1}^n x_iy_i\right)^2 \leq \left(\sum_{i=1}^n x_i^2\right) \left(\sum_{i=1}^n y_i^2\right)
$$

### Corolario 2 (de la desigualdad de Cauchy-Schwarz)

Sea $V=C[a,b]$ con $\left<f, g\right>=\int_a^b f(t)g(t)dt$. Se cumple que:

$$
\left(\int_a^b f(t)g(t)dt\right)^2 \leq \left(\int_a^b f^2(t)dt\right) \left(\int_a^b g^2(t)dt\right)
$$

### Corolario 3 (de la desigualdad de Cauchy-Schwarz)

Vamos a probar la desigualdad triangular para la norma inducida por un producto interno.

$$
\|v+w\| \leq \|v\|+\|w\|\quad\forall v,w\in V
$$

**Demostración:**

$$
\begin{aligned}
&\|v+w\|^2\\ 
&= \scriptstyle{\text{(definición de norma inducida)}}\\
&\left<v+w, v+w\right>\\
&= \scriptstyle{\text{(desarrollo)}}\\ 
&\left<v, v\right> + \left<v, w\right> + \left<w, v\right> + \left<w, w\right>\\
&= \scriptstyle{(\text{por: }z+\overline{z} = 2Re(z))}\\
&= \|v\|^2 + 2Re(\left<v, w\right>) + \|w\|^2\\
&\leq \scriptstyle{(\text{por: }Re(z)\leq|z|)}\\
&\|v\|^2 + 2|\left<v, w\right>| +\|w\|^2\\
&\leq \scriptstyle{(\text{desigualdad de Cauchy-Schwarz})}\\
&\|v\|^2 + 2\|v\|\|w\| +\|w\|^2\\
&= \scriptstyle{(\text{operatoria})}\\
&(\|v\| + \|w\|)^2\\
\end{aligned}
$$

Entonces reagrupando:

$$
\begin{aligned}
&\|v+w\|^2 \leq (\|v\| + \|w\|)^2\\
&\iff \scriptstyle{(\text{ambos lados siempre positivos})}\\
&\|v+w\| \leq \|v\| + \|w\|
\end{aligned}
$$

### Definición (ortogonalidad y ortonormalidad)

Sea $V$ un espacio vectorial sobre $\mathbb{K}$ con producto interno. Decimos que $v,w$ son ortogonales si $\left<v, w\right> = 0$.

**Notación:** $v\perp w$

- Sea $A\subset V$, decimos que $A$ es un conjunto ortogonal si $\forall v,w\in A$, con $v\neq w$ se cumple que $v\perp w$. Si además $\|v\| = 1\quad\forall v\in A$ decimos que $A$ es un conjunto ortonormal

**Observaciones:**

1. $\left<v, 0\right> = 0\quad\forall v\in V$
2. $v\perp v\iff\left<v, v\right>=0\iff v = \vec{0}$
3. Sea $A$ un conjunto ortogonal tal que $\vec{0}\notin A$. Entonces el conjunto $B=\{\frac{v}{\|v\|}: v\in A\}$ es un conjunto ortonormal

### Teorema

Sea $V$ un espacio vectorial con producto interno y $\{v_1,v_2,\ldots,v_r\}\subset V$ conjunto ortogonal tal que $v_i\neq\vec{0}\quad\forall i\in 1,\ldots,r$.

Entonces $\{v_1,v_2,\ldots,v_r\}$ es LI.

**Demostración:**

Consideremos:

$$
\alpha_1v_1+\ldots+\alpha_nv_r = 0\quad(i)
$$

Para $i=1,\ldots,r$, para un $j$ fijado, se cumple que:

$$
\begin{aligned}
&\left<\sum_{i=1}^r \alpha_i v_i, v_j\right>\\
&= \scriptstyle{(\text{el primer vector es 0})}\\
&0\\
&= \scriptstyle{(\text{definición de producto interno})}\\
&\sum_{i=1}^r \alpha_i\left<v_i, v_j\right>\\
&= \scriptstyle{(\text{por ortogonalidad cuando }i\neq j)}\\
&\alpha_j\left<v_j, v_j\right>\\
&= \scriptstyle{(\text{definición de norma inducida})}\\
&\alpha_j\|v_j\|^2\\
&= \scriptstyle{(\text{porque }v_j\neq 0)}\\
&\alpha_j
\end{aligned}
$$

Es decir, para este $j$ fijado se cumple que $\alpha_j = 0$. Podemos aplicar este razonamiento para todos los valores de $j$ y obtener que la única forma para que $(i)$ sea 0 es que todos los escalares $\alpha_i$ sean.
Con esto concluimos que: $\{v_1,v_2,\ldots,v_r\}$ es LI.

### Teorema de Pitagoras

Sea $V$ un espacio vectorial con producto interno, y $\{v_1,v_2,\ldots,v_r\}$ un conjunto ortogonal. Entonces se cumple:

$$
\|\sum_{i=1}^rv_i\|^2 = \sum_{i=1}^r\|v_i\|^2
$$

**Demostración:**

$$
\begin{aligned}
&\|\sum_{i=1}^rv_i\|^2\\
&=\scriptstyle{(\text{definición de norma inducida})}\\
&\left<\sum_{i=1}^rv_i,\sum_{j=1}^rv_j \right>\\
&=\scriptstyle{(\text{definición de producto interno})}\\
&\sum_{i=1}^r\sum_{j=1}^r\left<v_i, v_j\right>\\
&= \scriptstyle{(\text{por ortogonalidad cuando }i\neq j)}\\
&\sum_{i=1}^r\left<v_i, v_i\right>\\
&= \scriptstyle{(\text{definición de norma inducida})}\\
&\sum_{i=1}^r\|v_i\|^2\\
\end{aligned}
$$