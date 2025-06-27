# Ejercicio 3

## Consigna

Sean $T, S : V \to W$ y $R : U \to V$ transformaciones lineales entre espacios vectoriales de dimensión finita con producto interno sobre $\mathbb{K}$, y $\alpha \in \mathbb{K}$. Probar las siguientes propiedades de la adjunta:

1. Si $\{e_1, \dots, e_n\}$ es base ortonormal de $V$, entonces:  
   $$
   T^*(w) = \langle w,\ T(e_1)\rangle_W \cdot e_1 + \dots + \langle w,\ T(e_n)\rangle_W \cdot e_n,\quad \forall w \in W
   $$

2. $(T + S)^* = T^* + S^*$  
3. $(\alpha T)^* = \overline{\alpha} T^*$  
4. $(T \circ R)^* = R^* \circ T^*$  
5. $(T^*)^* = T$  
6. $T$ es invertible $\Leftrightarrow$ $T^*$ es invertible. Además: $(T^*)^{-1} = (T^{-1})^*$  
7. $\lambda$ es valor propio de $T$ $\Leftrightarrow$ $\overline{\lambda}$ es valor propio de $T^*$  
8. $\ker(T^*) = (\operatorname{Im}(T))^\perp$  
9. $\operatorname{Im}(T^*) = (\ker(T))^\perp$  
10. $\ker(T^* T) = \ker(T)$  
11. $\dim(\operatorname{Im}(T^* T)) = \dim(\operatorname{Im}(T))$

## Resolución

### Parte 1

Queremos probar que si $\{e_1, \dots, e_n\}$ es base ortonormal de $V$, entonces:  
   $$
   T^*(w) = \langle w,\ T(e_1)\rangle_W \cdot e_1 + \dots + \langle w,\ T(e_n)\rangle_W \cdot e_n,\quad \forall w \in W
   $$

Para esto, consideremos las siguientes dos propiedades:

1. Dada una base ortonormal $\{e_1, \dots, e_n\}$ de $V$, $\forall v\in V: v=\left<v, e_1\right>e_1+\ldots+\left<v, e_n\right>e_n$.
2. $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$

Calculemos $T(v)$:

$$
\begin{aligned}
&v=\left<v, e_1\right>e_1+\ldots+\left<v, e_n\right>e_n\\
&\iff\scriptstyle{(\text{aplicando }T)}\\
&T(v)=\left<v, e_1\right>T(e_1)+\ldots+\left<v, e_n\right>T(e_n)\\
\end{aligned}
$$

Por lo que podemos sustituir $T(v)$ en la siguiente expresión:

$$
\begin{aligned}
&\left<w, T(v)\right>_W=\left<T^*(w), v\right>_V\\
&\iff\scriptstyle{(\text{desarrollo de }T(v))}\\
&\left<w, \sum_{i=1}^{n}\left<v, e_i\right>_VT(e_i)\right>_W=\left<T^*(w), v\right>_V\\
&\iff\scriptstyle{(\text{propiedades de producto interno})}\\
&\sum_{i=1}^{n}\left<v, e_i\right>_V\left<w, T(e_i)\right>_W=\left<T^*(w), v\right>_V\\
&\iff\scriptstyle{(\text{desarrollo de }v)}\\
&\sum_{i=1}^{n}\left<v, e_i\right>_V\left<w, T(e_i)\right>_W=\left<T^*(w), \sum_{i=1}^{n}\left<v, e_i\right>e_i\right>_V\\
&\iff\scriptstyle{(\text{propiedades del producto interno})}\\
&\sum_{i=1}^{n}\left<v, e_i\right>_V\left<w, T(e_i)\right>_W=\sum_{i=1}^{n}\left<v, e_i\right>_V\left<T^*(w), e_i\right>_V\\
&\iff\scriptstyle{(\text{simplificando})}\\
&\left<w, T(e_i)\right>_W=\left<T^*(w), e_i\right>_V\\
\end{aligned}
$$

Como consideramos $v\in V$ y $w\in W$ cualquiera, esta propiedad vale $\forall v\in V, \forall w\in W, \forall i=1,\ldots,n$.

Ahora, como $T^*(w)\in V$, y tenemos una base ortonormal de $V$, podemos expresar $T^*(w)$ de la siguiente forma:

$$
T^*(w)=\sum_{i=1}^{n}\left<T^*(w), e_i\right>_Ve_i
$$

Pero por la igualdad que demostramos anteriormente podemos concluir que:

$$
T^*(w)=\sum_{i=1}^{n}\left<w, T(e_i)\right>_We_i
$$

Lo que concluye la prueba.

### Parte 2

Queremos probar que $(T + S)^* = T^* + S^*$.

Consideremos la siguiente propiedad básica de la adjunta:

- $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$

Veamos la siguiente cadena de igualdades:

$$
\begin{aligned}
&\left<w, (T+S)(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<w, T(v)+S(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de producto interno})}\\
&\left<w, T(v)\right>_W+\left<w, S(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de la adjunta})}\\
&\left<T^*(w), v\right>_V+\left<S^*(w), v\right>_V\\
&=\scriptstyle{(\text{propiedades de producto interno})}\\
&\left<T^*(w)+S^*(w), v\right>_V\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<(T^*+S^*)(w), v\right>_V\\
\end{aligned}
$$

Lo que concluye la prueba.

### Parte 3

Queremos probar que $(\alpha T)^* = \overline{\alpha}T^*$.

Consideremos la siguiente propiedad básica de la adjunta:

- $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$

Veamos la siguiente cadena de igualdades:

$$
\begin{aligned}
&\left<w, (\alpha T)(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<w, \alpha (T(v))\right>_W\\
&=\scriptstyle{(\text{propiedades de producto interno})}\\
&\overline{\alpha}\left<w, T(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de la adjunta})}\\
&\overline{\alpha}\left<T^*(w), v\right>_V\\
&=\scriptstyle{(\text{propiedades de producto interno})}\\
&\left<\overline{\alpha}(T^*(w)), v\right>_V\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<(\overline{\alpha}T^*)(w), v\right>_V\\
\end{aligned}
$$

Lo que concluye la prueba.

### Parte 4

Queremos probar que $(T \circ R)^* = R^* \circ T^*$.

Consideremos la siguiente propiedad básica de la adjunta:

- $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$

Veamos la siguiente cadena de igualdades:

$$
\begin{aligned}
&\left<w, (T\circ R)(v)\right>_W\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<w, T(R(v))\right>_W\\
&=\scriptstyle{(\text{propiedades de la adjunta})}\\
&\left<T^*(w), R(v)\right>_V\\
&=\scriptstyle{(\text{propiedades de la adjunta})}\\
&\left<R^*(T^*(w)), v\right>_W\\
&=\scriptstyle{(\text{propiedades de transf. lineales})}\\
&\left<(R^*\circ T^*)(w), v\right>_W\\
\end{aligned}
$$

Lo que concluye la prueba.

### Parte 5

Queremos probar que $(T^*)^* = T$.

Consideremos la siguiente propiedad básica de la adjunta:

- $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$

Veamos la siguiente cadena de igualdades:

$$
\begin{aligned}
&\left<T^*(w), v\right>_V\\
&=\scriptstyle{(\text{propiedades de la adjunta})}\\
&\left<w, T(v)\right>_W
\end{aligned}
$$

Lo que concluye la prueba.

### Parte 6

Queremos probar que si $T$ es invertible $\Leftrightarrow$ $T^*$ es invertible. Además: $(T^*)^{-1} = (T^{-1})^*$

Consideremos las siguientes propiedades:

1. $\forall v\in V,\forall w\in V: \left<w, T(v)\right>_W=\left<T^*(w), v\right>_V$
2. Sea $I$ la transformación identidad, entonces: $I^*=I$

$$
\begin{aligned}
&T\circ T^{-1} = I_V\\
&\scriptstyle{(\text{aplicando adjunta a ambos lados})}\\
&(T\circ T^{-1})^* = I^*_V\\
&\scriptstyle{(\text{propiedades de la adjunta})}\\
&(T^{-1})^*\circ T^* = I_V\\
\end{aligned}
$$

Esto demuestra que $(T^{-1})^*$ es la inversa de $T^*$, lo que concluye la prueba.

