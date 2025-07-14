# CLASE 20 - 14/07/2025

## Teorema espectral para operadores autoadjuntos

### Lema 1

Sea $V$ un $\mathbb{K}$-espacio vectorial y $T:V\to V$ operador autoadjunto. $S$ un subespacio de $V$ $T$-invariante.

Entonces $S^{\perp}$ es $T$-invariante.

#### Demostración

Dado $w\in S^{\perp}$ queremos probar que $T(w)\in S^{\perp}$.

Entonces consideramos $s\in S$, veamos lo siguiente:

$$
\begin{aligned}
&\left<T(w), s\right>\\
&=\scriptstyle{(T\text{ autoadjunto})}\\
&\left<w, T(s)\right>\\
&=\scriptstyle{(S\text{ invariante y }w\in S^{\perp})}\\
&0
\end{aligned}
$$

### Enunciado teorema espectral para operadores autoadjuntos

Sea $V$ un $\mathbb{K}$-espacio vectorial de dimensión finita con producto interno. Sea $T:V\to V$ un operador autoadjunto.

Entonces existe $\mathcal{B}$ una base ortonormal de vectores propios de $T$.

#### Demostración

Como $V$ es de dimensión finita, los valores propios son raíces de $\Chi_T$ que tendrá al menos una raíz. Ésta será real por uno de los teoremas previos que probamos.
Llamaremos $\lambda_0$ al valor propio, entonces existe $v_0\in V,v_0\neq\vec{0}$ tal que $T(v_0)=\lambda_0v_0$.
Consideramos $w_0=\frac{v_0}{\|v_0\|}$.

Continuaremos la prueba razonando por inducción sobre la dimensión del espacio vectorial $V$.

##### Paso base

Si $dim(V)=1$, entonces consideramos $\mathcal{B}=\{w_0\}$ que es una base ortonormal de $V$ formada por vectores propios de $T$.

##### Paso inductivo

Supongamos que el teorema es cierto para espacios de dimensión $n-1$ y lo probamos para espacios de dimensión $n$.

Sea $S=[w_0]\subseteq S_{\lambda_0}$, observemos que $S$ es $T$-invariante, pues $T(w_0)=\lambda_0w_0\quad\forall w_0\in S$.
Entonces por el lema anterior $S^{\perp}$ también es $T$-invariante. Consideremos $T\mid_{S^{\perp}}:S^{\perp}\to S^{\perp}$

Como tenemos que $V=S\oplus S^{\perp}$, en particular tenemos que $dim(V)=dim(S)+dim(S^{\perp})$. De donde concluimos que:

- $dim(S^{\perp})=n-1$

Entonces veamos que:

$S^{\perp}$ es un $\mathbb{K}$-espacio vectorial de dimensión $n-1$, y tenemos $T\mid_{S^{\perp}}:S^{\perp}\to S^{\perp}$ que es autoadjunto.

Luego, por hipótesis inductiva, existe una base $\mathcal{B}_1$ ortonormal de $S^{\perp}$ de vectores propios de $T\mid_{S^{\perp}}$

Concluyendo, consideramos la base $\mathcal{B}=B_1\cup\{w_0\}$ que está formada por vectores propios de $T$ y además es ortonormal.