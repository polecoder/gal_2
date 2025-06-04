# Ejercicio 4

## Consigna

Sea $S = \left[ (3, 5, 1) \right] \cup \{ (0, 1, 1) \}$ un subconjunto de $\mathbb{R}^3$.  
Se considera el producto interno:  
$$
\langle (x, y, z), (x', y', z') \rangle = xx' + 2yy' + 3zz'
$$
Calcular $S^\perp$.

## Resolución

Definimos los conjuntos $S$ y $S^{\perp}$ como los siguientes:

- $S=\{(3\alpha,5\alpha,\alpha):\alpha\in\mathbb{R}\}\cup\{(0,1,1)\}$
- $S^{\perp}=\{v\in \mathbb{R}^3: \left<v, s\right>=0\quad\forall s\in S\}$

Primero, necesitamos que el siguiente razonamiento sea válido para $v\in\mathbb{R}$:

$$
\begin{aligned}
&\left<v, s\right>=0\\
&\iff\scriptstyle{(\text{ampliando los vectores})}\\
&\left<(x,y,z), (3\alpha,5\alpha,\alpha)\right>=0\\
&\iff\scriptstyle{(\text{cálculo del producto interno})}\\
&x3\alpha+2y5\alpha+z3\alpha=0\\
&\iff\scriptstyle{(\text{simplificando})}\\
&\alpha(3x+10y+3z)=0
\end{aligned}
$$

Esto último es cierto para todo $\alpha\in\mathbb{R}$ solo si:

- $z= -\frac{10}{3}y-x$
- $y\in\mathbb{R}$
- $x\in\mathbb{R}$

En segundo lugar, necesitamos que el siguiente razonamiento también sea válido para $v\in\mathbb{R}$:

$$
\begin{aligned}
&\left<v, (0,1,1)\right>=0\\
&\iff\scriptstyle{(\text{ampliando los vectores})}\\
&\left<(x,y,z), (0,1,1)\right>=0\\
&\iff\scriptstyle{(\text{cálculo del producto interno})}\\
&2y+3z=0\\
&\iff\scriptstyle{(\text{simplificando})}\\
&2y+3z=0
\end{aligned}
$$

Esto último es cierto para todo $\alpha\in\mathbb{R}$ solo si:

- $z=-\frac{2}{3}y$
- $x\in\mathbb{R}$
- $z\in\mathbb{R}$

Juntando ambas partes, tenemos que:

$$
\begin{aligned}
&z=z\\
&\iff\scriptstyle{(\text{resultados obtenidos})}\\
&-\frac{10}{3}y-x=-\frac{2}{3}y\\
&\iff\scriptstyle{(\text{simplificando})}\\
&x=-\frac{8}{3}y
\end{aligned}
$$

Recapitulando, necesitamos que se cumplan las siguientes igualdades:

- $x=-\frac{8}{3}y$
- $y\in\mathbb{R}$
- $z=-\frac{2}{3}y$

Entonces, tenemos que:

$$
S^{\perp}=\{(-8\alpha,3\alpha,-2\alpha)\mid\alpha\in\mathbb{R}\}\\
\mathcal{B}^{S^{\perp}}= \{(-8,3,-2)\}
$$