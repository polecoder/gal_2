# Ejercicio 2

## Consigna

1. Se considera en $\mathbb{C}^3$ con el producto interno habitual el subespacio $S = \left[ (i, 0, 1) \right]$.  
   Hallar una base del subespacio $S^\perp$.

2. En $\mathbb{R}^3$, se considera el subespacio $S = \left[ (1, 2, 1) \right]$.  
   Calcular $S^\perp$ con:  
   1. el producto interno usual de $\mathbb{R}^3$  
   2. el producto interno definido por:  
   $$
   \langle (x_1, x_2, x_3), (y_1, y_2, y_3) \rangle = x_1y_1 + 2x_2y_2 + x_3y_3 - x_1y_2 - x_2y_1
   $$

## Resolución

### Parte 1

Definimos los conjuntos $S$ y $S^{\perp}$ como los siguientes:

- $S=\{(\alpha i,0,\alpha):\alpha\in\mathbb{C}\}$
- $S^{\perp}=\{v\in \mathbb{C}^3: \left<v, s\right>=0\quad\forall s\in S\}$

Por lo tanto, veamos el siguiente razonamiento:

$$
\begin{aligned}
&\left<v, s\right>=0\\
&\iff\scriptstyle{(\text{ampliando los vectores})}\\
&\left<(x,y,z), (\alpha i,0,\alpha)\right>=0\\
&\iff\scriptstyle{(\text{cálculo del producto interno})}\\
&x\overline{\alpha i}+0+z\overline{\alpha}=0\\
&\iff\scriptstyle{(\text{simplificando})}\\
&\alpha(-xi+z)=0
\end{aligned}
$$

Esto último es cierto para todo $\alpha\in\mathbb{C}$ solo si:

- $z= xi$
- $y\in\mathbb{C}$
- $x\in\mathbb{C}$

Entonces, tenemos que:

$$
S^{\perp}=\{(\alpha,\beta,\alpha i)\mid\alpha,\beta\in\mathbb{C}\}\\
\mathcal{B}^{S^{\perp}}= \{(1,0,i),(0,1,0)\}
$$

### Parte 2

Definimos los conjuntos $S$ y $S^{\perp}$ como los siguientes:

- $S=\{(\alpha,2\alpha,\alpha):\alpha\in\mathbb{R}\}$
- $S^{\perp}=\{v\in \mathbb{R}^3: \left<v, s\right>=0\quad\forall s\in S\}$

#### Subparte 1

Por lo tanto, veamos el siguiente razonamiento:

$$
\begin{aligned}
&\left<v, s\right>=0\\
&\iff\scriptstyle{(\text{ampliando los vectores})}\\
&\left<(x,y,z), (\alpha,2\alpha,\alpha)\right>\\
&\iff\scriptstyle{(\text{cálculo del producto interno})}\\
&\alpha(x+2y+z)=0
\end{aligned}
$$

Esto último es cierto para todo $\alpha\in\mathbb{R}$ solo si:

- $z=-x-2y$
- $y\in\mathbb{R}$
- $x\in\mathbb{R}$

Entonces tenemos que:

$$
S^{\perp}=\{(\alpha,\beta,-\alpha-2\beta)\mid\alpha,\beta\in\mathbb{R}\}\\
\mathcal{B}^{S^{\perp}}=\{(1,0,-1),(0,1,-2)\}
$$

#### Subparte 2

Para esta parte consideramos el siguiente producto interno:

$$
\langle (x_1, x_2, x_3), (y_1, y_2, y_3) \rangle = x_1y_1 + 2x_2y_2 + x_3y_3 - x_1y_2 - x_2y_1
$$

Por lo tanto, veamos el siguiente razonamiento:

$$
\begin{aligned}
&\left<v, s\right>=0\\
&\iff\scriptstyle{(\text{ampliando los vectores})}\\
&\left<(x,y,z), (\alpha,2\alpha,\alpha)\right>\\
&\iff\scriptstyle{(\text{cálculo del producto interno})}\\
&x\alpha+2y2\alpha+z\alpha-x2\alpha-y\alpha=0\\
&\iff\scriptstyle{(\text{simplificando})}\\
&\alpha(x+4y+z-2x-y)=0\\
&\iff\scriptstyle{(\text{simplificando})}\\
&\alpha(-x+3y+z)=0
\end{aligned}
$$

Esto último es cierto para todo $\alpha\in\mathbb{R}$ solo si:

- $x=3y+z$
- $y\in\mathbb{R}$
- $z\in\mathbb{R}$

Entonces tenemos que:

$$
S^{\perp}=\{(3\alpha+\beta,\alpha,\beta)\mid\alpha,\beta\in\mathbb{R}\}\\
\mathcal{B}^{S^{\perp}}=\{(3,1,0),(1,0,1)\}
$$