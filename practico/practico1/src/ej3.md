# Ejercicio 3

## Consigna

Sea $T: \mathbb{R}_2[t] \to \mathbb{R}^4$ tal que $T(p) = (2a + 3b - 8c, a + b + c, 4a - 5c, 6b)$, con $p(t) = a + bt + ct^2$, $\forall t \in \mathbb{R}$. Hallar ${}_{\mathcal{A}}(T)_{\mathcal{B}}$ en los siguientes casos:

1. $\mathcal{B}$ y $\mathcal{A}$ son las bases canónicas de $\mathbb{R}_2[t]$ y $\mathbb{R}^4$ respectivamente.
2. $\mathcal{B} = \{1, t - 1, (t - 1)^2\}$ y $\mathcal{A}$ es la base canónica de $\mathbb{R}^4$.

## Resolución (parte 1)

- $\mathcal{B} = \{1, t, t^2\}$
- $\mathcal{A} = \{(1,0,0,0),(0,1,0,0),(0,0,1,0),(0,0,0,1)\}$

Antes de calcular los transformados de la base $\mathcal{B}$, busquemos los valores de $(a,b,c)$ para cada uno de ellos (aunque en este caso sea trivial).

- $1: (1,0,0)$
- $t: (0,1,0)$
- $t^2: (0,0,1)$

Entonces ahora si, hallemos los transformados de estos vectores:

- $T(1) = (2,1,4,0)$
- $T(t) = (3,1,0,6)$
- $T(t^2) = (-8,1,-5,0)$

Y como la base de llegada es canónica:

$$
{}_{\mathcal{A}}(T)_{\mathcal{B}} =
\begin{pmatrix}
2 & 3 & -8 \\
1 & 1 & 1 \\
4 & 0 & -5 \\
0 & 6 & 0
\end{pmatrix}
$$

## Resolución (parte 2)

- $\mathcal{B} = \{1, t - 1, (t - 1)^2\}$
- $\mathcal{A} = \{(1,0,0,0),(0,1,0,0),(0,0,1,0),(0,0,0,1)\}$

Calculemos $(a,b,c)$ para cada vector de la base $\mathcal{B}$:

- $1: (1,0,0)$
- $t-1: (-1, 1, 0)$
- $(t-1)^2 = t^2-2t+1: (1,-2,1)$

Ahora si, los transformados de los vectores de la base $\mathcal{B}$ son:

- $T(1) = (2,1,4,0)$
- $T(t-1) = (1,0,-4,6)$
- $T((t-1)^2) = (-12,0,-1,-12)$

$$
{}_{\mathcal{A}}(T)_{\mathcal{B}} =
\begin{pmatrix}
2 & 1 & -12 \\
1 & 0 & 0 \\
4 & -4 & -1 \\
0 & 6 & -12
\end{pmatrix}
$$