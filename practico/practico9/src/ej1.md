# Ejercicio 1

## Consigna

Sea $V$ un $\mathbb{R}$-espacio vectorial de dimensión finita con producto interno, y $T : V \to V$ el operador dado por:

$$
T(v) = \langle v,\ u_0 \rangle \cdot u_1
$$

donde $u_0$ y $u_1$ son vectores fijos y no nulos de $V$.

1. Hallar $T^*$  
2. ¿Qué condiciones deben cumplir $u_0$ y $u_1$ para que $T$ sea autoadjunto?

## Resolución

### Parte 1

Veamos el siguiente razonamiento

$$
\begin{aligned}
&\left<T(v), w\right>\\
&=\scriptstyle{(\text{definición de }T)}\\
&\left<\left<v, u_0\right>u_1, w\right>\\
&=\scriptstyle{(\text{propiedades del producto interno})}\\
&\left<v, u_0\right>\left<u_1, w\right>\\
&=\scriptstyle{(\text{propiedades del producto interno y }V\text{ es real})}\\
&\left<v, \left<u_1, w\right>u_0\right>\\
&=\scriptstyle{(\text{definición de adjunta})}\\
&\left<v, T^*(w)\right>\\
\end{aligned}
$$

Por lo que tenemos que $T^*(w)=\left<u_1, w\right>u_0$

### Parte 2

Para que $T$ sea autoadjunto, tenemos que tener que:

- $T(v)=\left<v, u_0\right>u_1=\left<u_1, w\right>u_0=T^*(w)$

Entonces, se tiene que cumplir lo siguiente:

- $\left<v, u_0\right>u_1=\left<u_1, w\right>u_0$

Lo que implica que $u_1$ y $u_2$ tienen que ser colineales. Veamos que pasa si $u_1=ku_0$ con $k\in\mathbb{R}$:

$$
\begin{aligned}
&T(w)\\
&=\scriptstyle{(\text{definición de }T^*)}\\
&\left<u_1, w\right>u_0\\
&=\scriptstyle{(u_1=ku_0)}\\
&\left<ku_0, w\right>u_0\\
&=\scriptstyle{(\text{propiedades del producto interno})}\\
&\left<u_0, w\right>ku_0\\
&=\scriptstyle{(u_1=ku_0)}\\
&\left<u_0, w\right>u_1\\
&=\scriptstyle{(\text{como }V\text{ es real})}\\
&\left<w, u_0\right>u_1\\
&=\scriptstyle{(\text{definición de }T)}\\
&T(w)
\end{aligned}
$$

Por lo que si $u_1$ y $u_2$ son colineales, entonces $T$ es autoadjunta.