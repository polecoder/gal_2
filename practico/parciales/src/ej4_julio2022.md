# Ejercicio 4 - Parcial Julio 2022

## Consigna

Se considera el subespacio $S = \{(x, y, z) \in \mathbb{R}^3 : 2x + y - z = 0\}$  
y $T : \mathbb{R}^3 \to \mathbb{R}^3$ una transformación lineal tal que:

1. $T|_S = Id$
2. $(2,\ 1,\ -1) \in \ker(T)$

Indicar la opción correcta:

**A.** Si $P_S : V \to V$ es la proyección ortogonal sobre $S$, entonces $T(v) = P_S(v)$ para todo $v \in V$

**B.** La matriz asociada a $T$ en la base canónica ${}_{\mathcal{C}}(T)_{\mathcal{C}}$ es:
$$
\frac{1}{3}
\begin{pmatrix}
1 & -1 & 1 \\
-1 & 5 & 2 \\
1 & 1 & 2
\end{pmatrix}
$$

**C.** Si $P_{S^\perp} : V \to V$ es la proyección ortogonal sobre $S^\perp$, entonces $T(v) = P_{S^\perp}(v)$ para todo $v \in V$

**D.** La matriz asociada a $T$ en la base canónica ${}_{\mathcal{C}}(T)_{\mathcal{C}}$ es:
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{pmatrix}
$$

## Resolución

La estrategia de este ejercicio es nuevamente definir bien que es lo que nos aporta cada dato.

**Dato #1**:

- $T|_S = Id$

Este dato puede resultar engañoso, pero lo que nos está diciendo es que:

- $\forall s\in S: T(s)= s$

Que es lo mismo que decir que 1 es valor propio de $T$. Observemos que entonces cualquier vector en $S$, es un vector asociado al valor propio 1. Entonces podemos decir que:

- $S\subseteq S_1$

Veamos además que se puede decir sobre la definición de $S$

- $S = \{(x, y, z) \in \mathbb{R}^3 : 2x + y - z = 0\}$

De donde obtenemos que:

- $z=y+2x$
- $x,y\in\mathbb{R}$

Entonces una definición alternativa de $S$ podría ser:

- $S=\{(\alpha,\beta,\beta+2\alpha):\alpha,\beta\in\mathbb{R}\}$ o
- $S=[(1,0,2),(0,1,1)]$

**Dato #2**

- $(2,\ 1,\ -1) \in \ker(T)$

Este dato es más directo, nos dice que $ker(T)\neq\emptyset$, por lo que entonces 0 es valor propio de $T$.

Esto nos dice que $S=S_1$, pues $dim(S)=dim(S_1)=2$ y por tanto tenemos una base de $S$ formada por vectores propios.

Teniendo en cuenta que $S_0=S_2^{\perp}$, podemos hallar una definición del conjunto para hallar la forma de los vectores propios asociados a 0.
Considerando $v=(x,y,z)\in S_0$, entonces:

- $\left<(x,y,z), (1,0,2)\right>=0\to x=-2z$
- $\left<(x,y,z), (0,1,1)\right>=0\to y=-z$

Por lo que:

- $S_0=\{(-2\alpha,-\alpha,\alpha):\alpha\in\mathbb{R}\}$ o
- $S_0=[(2,1,-1)]$

**Observación:** Creo que todo este razonamiento era innecesario, pero ante la duda no está mal confirmar quién es $S_0$.

Para rematar el problema la clave está en que $S_0=S_2^{\perp}=S^{\perp}$.

Consideremos la opción **A**.

Por el dato 1, sabemos que:

- $\forall s\in S: P_S(s)=T(s)=s$, entonces para todos los vectores $s\in S$ sabemos que la afirmación es verdadera.

Por otra parte, podemos caracterizar $T$ para los vectores que están en $S^{\perp}$, usando el dato 2:

- Nos restaría probar que $\forall v\in S^{\perp}$: $T(v)=P_S(v)=0$

Pero observemos que esto último se cumple, pues si $v\in S^{\perp}$, entonces todos los productos internos $\left<v, s_i\right>$ con $s_i$ vectores de la base de $S$ es 0.