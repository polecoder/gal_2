# Ejercicio 1

## Consigna

Sea $V$ un espacio vectorial de dimensión finita con producto interno.

1. Sean $A$ y $B$ subconjuntos de $V$. Probar que:  
   1. Si $A \subset B \Rightarrow B^{\perp} \subset A^{\perp}$  
   2. $A^{\perp} = [A]^{\perp}$  
   3. $A \subset (A^{\perp})^{\perp}$

2. Sean $S$ y $W$ subespacios de $V$. Probar que:  
   1. $S = (S^{\perp})^{\perp}$  
   2. $(S + W)^{\perp} = S^{\perp} \cap W^{\perp}$  
   3. $(S \cap W)^{\perp} = S^{\perp} + W^{\perp}$

## Resolución

### Parte 1

#### Subparte 1

Queremos probar que si $A \subset B \Rightarrow B^{\perp} \subset A^{\perp}$.

Empezando por la hipótesis, esta nos dice que si $a\in A$, entonces $a\in B$.
Ahora, consideremos $v\in B^{\perp}$, por definición de complemento ortogonal sabemos que:

$$
\left<v, b\right>=0\quad\forall b\in B
$$

Y como $A\subset B$, tenemos que esta afirmación es cierta también para todos los vectores $a\in A$:

$$
\left<v, a\right>=0\quad\forall a\in A
$$

Por lo tanto $v\in A^{\perp}$, y como consideramos un $v$ genérico dentro de $B^{\perp}$, esto es válido para todos los $v\in B^{\perp}$.
Con esto concluimos que si $A \subset B \Rightarrow B^{\perp} \subset A^{\perp}$. $\blacksquare$

#### Subparte 2

Queremos probar que $A^{\perp} = [A]^{\perp}$.

Para esta parte probaremos que:
1. $[A]^{\perp}\subset A^{\perp}$ y
2. $A^{\perp}\subset [A]^{\perp}$

Empecemos por la primer parte.

Consideremos $v\in[A]^{\perp}$, esto implica que $\left<v, w\right>=0\quad\forall w\in [A]$.
Como $A\subset[A]$ (pues $a\in A$ es combinación lineal de vectores de $[A]$), entonces podemos decir que en particular:

- $\left<v, a\right>\quad\forall a\in A$

Por lo tanto $v\in A^{\perp}$.

Ahora vamos con la segunda parte:

Consideremos $v\in A^{\perp}$, esto implica que $\left<v, a\right>=0\quad\forall a\in A$. Ahora, considerando que cualquier vector $w\in [A]$ se puede escribir como una combinación lineal de vectores de $A$, tenemos que:

$$
\left<v, w\right>=\left<v, \sum_{i=1}^{r}\alpha_ia_i\right>=\sum_{i=1}^{r}\alpha_i\left<v, a_i\right>=0
$$

Donde la última igualdad es verdadera pues $\forall a\in A \left<v, a\right>=0$.

Esto prueba la segunda afirmación y por lo tanto concluimos que: $A^{\perp}=[A]^{\perp}$.

#### Subparte 3

Queremos probar que $A \subset (A^{\perp})^{\perp}$.

Consideremos $a\in A$, queremos probar que $\forall v\in A^{\perp} \left<a, v\right>=0$, es decir que $a\in (A^{\perp})^{\perp}$.
Observemos que esto es cierto $\forall a\in A$ pues, considerando un $v\in A^{\perp}$:

$$
\left<a, v\right>=\overline{\left<v, a\right>}=\left<v, a\right>=0\quad\forall a\in A
$$

Donde en este último paso usamos la definición de $A^{\perp}$. $\blacksquare$

### Parte 2

#### Subparte 1

Queremos probar que $S = (S^{\perp})^{\perp}$

Para esto vamos a probar:
1. $S\subset (S^{\perp})^{\perp}$
2. $(S^{\perp})^{\perp}\subset S$

Para la primera parte, la prueba es idéntica a la 1.3.

Para la segunda parte, usamos que $V=S\oplus S^{\perp}$. Por lo tanto, tomamos $v\in (S^{\perp})^{\perp}$ cualquiera tal que:

- $v=v_S+v_{S^{\perp}}$ con $v_S\in S$ y $v_{S^{\perp}}\in S^{\perp}$

Como $v\in(S^{\perp})^{\perp}$, tenemos que $\forall u\in S^{\perp}: \left<v, u\right>=0$. En particular, considerando $u=v_{S^{\perp}}$ tenemos que:

$$
\left<v, v_{S^{\perp}}\right> = \left<v_S+v_{S^{\perp}}, v_{S^{\perp}}\right>=\underline{\left<v_S, v_{S^{\perp}}\right>}+ \left<v_{S^{\perp}}, v_{S^{\perp}}\right>=0
$$

Donde lo subrayado es igual a 0 pues tengo un elemento de $S$ y uno de $S^{\perp}$.
Con lo obtenido, tenemos que:

$$
\left<v_{S^{\perp}}, v_{S^{\perp}}\right>=\|v_{S^{\perp}}\|=0
$$

Lo que implica que $v_{S^{\perp}}=0$, entonces $v= v_S\in S$. Por lo que probamos lo que estabamos buscando. $\blacksquare$

#### Subparte 2

Queremos probar que $(S + W)^{\perp} = S^{\perp} \cap W^{\perp}$.

Para esto vamos a probar:
1. $(S + W)^{\perp} \subset S^{\perp} \cap W^{\perp}$
2. $S^{\perp} \cap W^{\perp}\subset (S + W)^{\perp}$

##### PRIMERO: $(S + W)^{\perp} \subset S^{\perp} \cap W^{\perp}$

Consideremos $v\in (S+W)^{\perp}$, entonces:

$$
\left<v, u\right>=0\quad\forall u\in (S+W)
$$

Desde donde se deriva que:

$$
\left<v, s+w\right>=0\quad\forall s\in S\text{ y }\forall w\in W
$$

Si tomamos $w=\vec{0}$ entonces tenemos que:

- $\left<v, s\right>=0\quad\forall s\in S$

Lo cual implica que $v\in S^{\perp}$.

De la misma manera, si tomamos $s=\vec{0}$ entonces tenemos que:

- $\left<v, w\right>=0\quad\forall w\in W$

Lo cual implica que $v\in W^{\perp}$.

Entonces, juntando las dos afirmaciones obtenemos que $v\in S^{\perp}\cap W^{\perp}$. Y como razonamos arbitrariamente, esto es válido $\forall v\in (S+W)^{\perp}$.

##### SEGUNDO: $S^{\perp} \cap W^{\perp}\subset (S + W)^{\perp}$

Consideremos $v\in S^{\perp} \cap W^{\perp}$, esto implica que:

1. $\left<v, s\right>=0\quad\forall s\in S$
2. $\left<v, w\right>=0\quad\forall w\in W$

De esto podemos derivar que:

- $\left<v, s+w\right>=\left<v, s\right>+\left<v, w\right>=0$

Lo que significa que $v\in(S+W)^{\perp}$

Juntar las dos partes concluye la prueba. $\blacksquare$

#### Subparte 3

Queremos probar que $(S \cap W)^{\perp} = S^{\perp} + W^{\perp}$.

Usemos las propiedades probadas hasta ahora para ver que podemos decir sobre la igualdad:

$$
\begin{aligned}
&(S \cap W)^{\perp} = S^{\perp} + W^{\perp}\\
&\iff\scriptstyle{(\text{complemento ortogonal a ambos lados})}\\
&((S \cap W)^{\perp})^{\perp} = (S^{\perp} + W^{\perp})^{\perp}\\
&\iff\scriptstyle{(\text{propiedad 2.1 y propiedad 2.2})}\\
&S \cap W=(S^{\perp})^{\perp}\cap (W^{\perp})^{\perp}\\
&\iff\scriptstyle{(\text{propiedad 2.1})}\\
&S \cap W=S \cap W
\end{aligned}
$$

Lo que prueba que esta propiedad es cierta.