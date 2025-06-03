# CLASE 14 - 02/06/2025

## Complemento ortogonal

### Proposición

Sea $V$ un espacio vectorial con producto interno y $S$ un subespacio vectorial de dimensión finita.

Entonces:

$$
V = S \oplus S^{\perp}
$$

#### Demostración

Queremos probar que:

1. $V=S+S^{\perp}$
2. $S\cap S^{\perp} = \{\vec{0}\}$

Consideramos $\mathcal{B}=\{s_1,\ldots,s_k\}$ una base ortonormal de $S$.
Dado $v\in V$ definimos: $(v_s=\sum_{i=1}^{k}\left<v, s_i\right>s_i)\in S$.

Veamos que $(v-v_s)\in S^{\perp}$, para esto, verifiquemos que $\left<v-v_s, s_j\right>=0$ para $j=1,\ldots,k$.

$$
\begin{aligned}
\left<v-v_s, s_j\right>&=\left<v-\sum_{i=1}^{k}\left<v, s_i\right>s_i, s_j\right>\\
&= \left<v, s_j\right>-\sum_{i=1}^{k}\left<v, s_i\right>\left<s_i, s_j\right>\\
&=\left<v, s_j\right>-\left<v, s_j\right>\cdot 1\\
&= 0
\end{aligned}
$$

Por lo tanto probamos que $(v-v_s)\in S^{\perp}$. Entonces, podemos decir que:

$$
v= v_s + (v-v_s)
$$

Donde:
1. $v_s\in S$
2. $v-v_s\in S^{\perp}$

En conclusión $V=S+S^{\perp}$.

Ahora, queremos demostrar que $S\cap S^{\perp} = \{\vec{0}\}$, para esto, consideremos $v\in S\cap S^{\perp}$:
1. $v\in S$
2. $v\in S^{\perp}$

Entonces $\left<v, v\right>=0\Rightarrow v=\vec{0}$

Juntando ambas cosas, probamos que $V=S\oplus S^{\perp}$

#### Observación

Dado $v\in V$ existen únicos $v_s\in S$ y $v_{s^{\perp}}\in S^{\perp}$ tales que $v=v_s+v_{s^{\perp}}$.
Nosotros utilizamos una base ortonormal $\{s_1,s_2,\ldots,s_k\}$ de $S$. De donde obtuvimos $v_s=\sum_{i=1}^{k}\left<v, s_i\right>s_i$.
Si usamos otra base ortonormal diferente, el resultado que obtenemos será el mismo. Esto significa que el cálculo de $v_s$ no depende de la base ortonormal elegida

## Proyección ortogonal

### Definición

Dado $v\in V$, definimos $v_s$ como la proyección ortogonal de $v$ sobre el subespacio $S$ y se denota:

$P_S(v)=v_s=\sum_{i=1}^{k}\left<v, s_i\right>s_i$

#### Observación

1. La definición de proyección ortogonal no depende de la base ortonormal elegida para calcularla.
2. Si proyectamos sobre $S^{\perp}$:
    $$
    v=v_{s^{\perp}}+v_{(s^{\perp})^{\perp}}=v_{s^{\perp}} + v_s = P_{S^{\perp}}(v) + P_S(v)
    $$
3. $P_S:V\to V$ es un operador lineal. Esto se deriva fácilmente de las propiedades de producto interno.

#### Ejemplo 1

$V=P_2[x](\mathbb{R})$ con producto interno: $\left<p, q\right>= \int_{-1}^1p(t)q(t)dt$ y $S=[t^2]$.
Consideremos $p(t)=1+t$. Queremos calcular $P_S(p)$
Usaremos la siguiente base ortonormal de $S:\mathcal{B}=\{\sqrt{\frac{5}{2}}t^2\}$ (asumiremos que es ortonormal).

Con todo esto:

$P_S(v)=\left<p, p_1\right>p_1(t)$

Donde:

- $\left<p, p_1\right>=\int_{-1}^1(1+t)\sqrt{\frac{5}{2}}t^2dt=\int_{-1}^1\sqrt{\frac{5}{2}}t^2+\sqrt{\frac{5}{2}}t^3dt = \sqrt{\frac{5}{2}}\int_{-1}^1t^2+t^3dt=\sqrt{\frac{5}{2}}((\frac{1}{3}+\frac{1}{4}) - (\frac{-1}{3}+\frac{1}{4}))=\sqrt{\frac{5}{2}}\cdot\frac{2}{3}=\frac{2\sqrt{5}}{3\sqrt{2}}$

Entonces:

$P_S(v)=\frac{2\sqrt{5}}{3\sqrt{2}}\cdot\frac{\sqrt{5}}{\sqrt{2}}t^2=\frac{10}{6}t^2=\frac{5}{3}t^2$

#### Ejemplo 2

$V=\mathbb{R}^3$ producto interno habitual. $S=\{(x,y,z)\in\mathbb{R}^3: x+y+z=0\}$. 
Consideremos $v=(1,0,0)$, queremos calcular $P_S(v)$.
Consideramos la siguiente base ortonormal de $S$ (no verificaremos nuevamente): $\mathcal{B}=\{\frac{1}{\sqrt{2}}(1,-1,0),\sqrt{\frac{2}{3}}(\frac{1}{2},\frac{1}{2},-1)\}$.

Con esto, podemos calcular:

$$
\begin{aligned}
P_S(1,0,0)&=\left<(1,0,0), \frac{1}{\sqrt{2}}(1,-1,0)\right>\frac{1}{\sqrt{2}}(1,-1,0) + \left<(1,0,0), \sqrt{\frac{2}{3}}\left(\frac{1}{2},\frac{1}{2},-1\right)\right>\sqrt{\frac{2}{3}}\left(\frac{1}{2},\frac{1}{2},-1\right)\\
&= \frac{1}{2}(1,-1,0)+\frac{1}{3}\left(\frac{1}{2},\frac{1}{2},-1\right)\\
&= \frac{1}{6}\left(\frac{3}{2},\frac{-1}{2},-1\right)
\end{aligned}
$$

### Teorema

Sea $V$ un espacio vectorial con producto interno y $S$ un subespacio vectorial. Entonces:

$$
\|v-P_s(v)\| \leq \|v-s\|\quad\forall s\in S
$$

Este resultado es muy geométrico, no es fácil entender lo que es mirando la expresión. La idea es que la proyección ortogonal del vector $v$ es la que resulta teniendo la menor distancia al vector $v$ en si, con respecto a todos los demás vectores de $S$.

#### Demostración

Tomemos un vector cualquiera $s\in S$, entonces:

$$
\begin{aligned}
&\|v-s\|^2\\
&=\scriptstyle{(\text{norma inducida})}\\
&\left<v-s, v-s\right>\\
&=\scriptstyle{(\text{proposición anterior})}\\
&\left<P_S(v)+P_{S^{\perp}}(v)-s, P_S(v)+P_{S^{\perp}}(v)-s\right>\\
&=\scriptstyle{(\text{propiedades del producto interno})}\\
&\left<P_S(v)-s,P_S(v)-s \right>+\left<P_S(v)-s, P_{S^{\perp}}(v)\right>+\left<P_{S^{\perp}}(v),P_S(v)-s\right>+\left<P_{S^{\perp}}(v), P_{S^{\perp}}(v)\right>\\
&=\scriptstyle{(\left<P_S(v)-s, P_{S^{\perp}}(v)\right>=0\text{ y }\left<P_{S^{\perp}}(v),P_S(v)-s\right>=0)}\\
&\left<P_S(v)-s,P_S(v)-s \right>+\left<P_{S^{\perp}}(v), P_{S^{\perp}}(v)\right>\\
&=\scriptstyle{(\text{norma inducida})}\\
&\|P_S(v)-s\|^2+\|P_{S^{\perp}}(v)\|^2
\end{aligned}
$$

Por lo encontrado en el último paso, si consideramos $\|v-s\|^2$ como una función, ésta alcanza su valor mínimo cuando $\|P_S(v)-s\|^2=0$ que es cuando $s=P_S(v)$. Podemos decir que:

$$
\|v-s\|^2 \geq \|v-P_S(v)\|^2
$$

Como tomamos $s\in S$ cualquiera, este razonamiento es válido para todo $s$. Lo que concluye la prueba