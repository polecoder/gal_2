# CLASE 16 - 16/06/2025

## Transformaciones lineales en espacios con producto interno

### Funcionales lineales

Sea $V$ un espacio vectorial sobre $\mathbb{K}$ con producto interno. Llamamos una funcional lineal a una transformación lineal de la siguiente forma:

$$
T:V\to\mathbb{K}
$$

#### Ejemplo

Sea $w\in V$, definimos la función:

$$
f_w(v)=\left<v, w\right>
$$

Esta es una funcional lineal.

#### Lema

Sea $V$ un espacio vectorial con producto interno.

Si $\left<v, w\right>=\left<v, w'\right>\quad\forall v\in V$, entonces $w=w'$

##### Demostración

Partamos de la hipótesis:

$$
\begin{aligned}
&\left<v, w\right>=\left<v, w'\right>\quad\forall v\in V\\
&\iff\scriptstyle{(\text{despejando})}\\
&\left<v, w\right>-\left<v, w'\right>=0\quad\forall v\in V\\
&\iff\scriptstyle{(\text{propiedades del producto interno})}\\
&\left<v, w-w'\right>=0\quad\forall v\in V\\
&\iff\scriptstyle{(\text{en particular, tomando }v=w-w')}\\
&\left<w-w', w-w'\right>=0\\
&\iff\scriptstyle{(\text{propiedades del producto interno})}\\
&w-w'=0\\
&\iff\scriptstyle{(\text{despejando})}\\
&w=w'
\end{aligned}
$$

### Teorema de representación de Riesz

Sea $V$ un espacio vectorial con producto interno, tal que $dim(V)=n$. Si $T:V\to\mathbb{K}$ es una funcional lineal entonces existe un único $w\in V$ tal que $T(v)=\left<v, w\right>\quad\forall v\in V$. Llamamos a $w\in V$ el representante de Riesz de la funcional lineal $T$

#### Demostración

Primero probamos la unicidad del representante de Riesz:

Supongamos que existen dos vectores $w,w'\in V$ tales que $T(v)=\left<v, w\right>=\left<v, w'\right>\quad\forall v\in V$. Entonces, usando el lema que probamos anteriormente, $w=w'$

Ahora, tenemos que probar que efectivamente existe un vector $w\in V$ que cumple con las propiedades mencionadas.

Consideremos $\mathcal{B}=\{e_1,\ldots,e_n\}$ una base ortonormal del espacio $V$. Entonces, dado un vector $v\in V$, podemos descomponerlo de la siguiente forma:

$$
v=\left<v, e_1\right>e_1+\ldots+\left<v, e_n\right>e_n=\sum_{i=1}^{n}\left<v, e_i\right>e_i
$$

Por lo tanto:

$$
T(v)=\sum_{i=1}^{n}\left<v, e_i\right>T(e_i)=\sum_{i=1}^{n}\left<v, \overline{T(e_i)}e_i\right>=\left<v,\sum_{i=1}^{n}\overline{T(e_i)}e_i\right>
$$

Y observemos que $\sum_{i=1}^{n}\overline{T(e_i)}e_i\in V$, por lo que llamando $w=\sum_{i=1}^{n}\overline{T(e_i)}e_i$, escribimos a $T(v)$ como $\left<v, w\right>\quad\forall v\in V$ (pues consideramos $v\in V$ cualquiera).

## Adjunta de una transformación lineal

Sean $V,W$ dos espacios vectoriales sobre el mismo cuerpo $\mathbb{K}$, ambos con producto interno: $\left<\cdot, \cdot\right>_V$ y $\left<\cdot, \cdot\right>_W$. Consideramos una transformación $T:V\to W$ una transformación lineal.

Decimos que $T$ tiene adjunta si existe una función $T^*:W\to V$ tal que:

$$
\left<T(v), w\right>_W=\left<v,T^*(w)\right>_V\quad\forall v\in V\quad\forall w\in W
$$

### Teorema

Sean $V,W$ espacios vectoriales sobre el mismo cuerpo $\mathbb{K}$ de dimensión finita, $\left<\cdot, \cdot\right>_V, \left<\cdot, \cdot\right>_W$ productos internos sobre $V,W$.
Entonces toda transformación lineal $T:V\to W$ tiene una transformación lineal adjunta $T^*:W\to V$

#### Demostración

Para probar el teorema, tenemos que probar las siguientes tres partes:

1. Unicidad
2. Existencia
3. $T^*$ es una transformación lineal

##### Unicidad

Supongamos que existen $T_1^*:W\to V$ y $T_2^*:W\to V$ tales que:

1. $\left<T(v), w\right>_W=\left<v,T_1^*(w)\right>_V\quad\forall v\in V\quad\forall w\in W$
2. $\left<T(v), w\right>_W=\left<v,T_2^*(w)\right>_V\quad\forall v\in V\quad\forall w\in W$

Por lo tanto deducimos que:

$$
\left<v,T_1^*(w)\right>_V=\left<v,T_2^*(w)\right>_V\quad\forall v\in V\quad\forall w\in W
$$

Y usando el lema anterior concluimos que:

$$T_1^*(w)=T_2^*(w)\quad\forall w\in W$$

Por lo tanto $T_1^*=T_2^*$

##### Existencia

Dado $w\in W$ construimos el funcional lineal $f_w:V\to\mathbb{K}$ definido por:

$$
f_w(v)=\left<T(v), w\right>_W\quad\forall v\in V
$$

Por el teorema de Riesz, existe un único $T^*(w)\in V$ tal que:

$$
f_w(v)=\left<v, T^*(w)\right>_V
$$

Entonces, para cada $w\in W$ tenemos $T^*(w)\in V$ tal que:

$$
\left<T(v), w\right>_W=f_w(v)=\left<v, T^*(w)\right>_V\quad\forall v\in V
$$

Por lo tanto $T^*:W\to V$ es una adjunta de $T:V\to W$

##### $T^*$ es una transformación lineal

Consideremos $w_1,w_2\in W$ y $\alpha\in\mathbb{K}$. Se cumple $\forall v\in V$:

$$
\begin{aligned}
\left<v, T^*(\alpha w_1+\beta w_2)\right>_V&=\left<T(v), \alpha w_1+\beta w_2\right>_W\\
&=\overline{\alpha}\left<T(v), w_1\right>_W+\overline{\beta}\left<T(v), w_2\right>_W\\
&=\overline{\alpha}\left<v, T^*(w_1)\right>_V+\overline{\beta}\left<v, T^*(w_2)\right>_V\\
&=\left<v, \alpha T^*(w_1)+\beta T^*(w_2)\right>_V
\end{aligned}
$$

Entonces por el lema anterior:

$$
T^*(\alpha w_1+\beta w_2)=T^*(w_1)+\beta T^*(w_2)
$$