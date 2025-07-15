# Ejercicio 3

## Consigna

1. En $\mathbb{R}^3$ con producto interno habitual:

    1. Sea $T$ un operador lineal cuya matriz respecto de la base $B = \{(1,1,0),\ (0,1,0),\ (1,0,1)\}$ es:

    $$
    {}_{\mathcal{B}}(T)_{\mathcal{B}} =
    \begin{pmatrix}
    1 & 3 & 1 \\
    0 & -4 & 0 \\
    2 & -1 & 3
    \end{pmatrix}
    $$

    Probar que $T$ es autoadjunto.

    2. Sea $S$ un operador lineal con:

    $$
    {}_{\mathcal{B}}(S)_{\mathcal{B}} =
    \begin{pmatrix}
    1 & 0 & 0 \\
    0 & 2 & 1 \\
    0 & 1 & 2
    \end{pmatrix}
    $$

    ¿Es $S$ autoadjunto? 

2. En $\mathbb{C}^2$ con producto interno usual, sea $T$ tal que respecto de la base $B = \{(1,1),\ (0,1)\}$:

    $$
    {}_{\mathcal{B}}(T)_{\mathcal{B}} =
    \begin{pmatrix}
    1 + i & i \\
    -2i & 1 - i
    \end{pmatrix}
    $$

    Probar que $T$ es autoadjunto.

3. En $\mathbb{R}^3$, con producto interno habitual, se define:

    - $T(1,1,0) = (5,\ 8,\ -1)$  
    - $T(1,-1,1) = (10,\ -14,\ 10)$  
    - $T(2,1,1) = (13,\ a,\ b)$

    Hallar $a$ y $b$ para que $T$ sea autoadjunto.

## Resolución

### Parte 1

#### Subparte 1

Sea $T$ un operador lineal cuya matriz respecto de la base $B = \{(1,1,0),\ (0,1,0),\ (1,0,1)\}$ es:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
1 & 3 & 1 \\
0 & -4 & 0 \\
2 & -1 & 3
\end{pmatrix}
$$

Observemos que la base dada no es ortonormal. Consideremos $\mathcal{E}=\{(1,0,0),(0,1,0),(0,0,1)\}$ la base canónica de $\mathbb{R}^3$ que sabemos que si es ortonormal.

Planteemos entonces un cambio de base:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}={}_{\mathcal{E}}(Id)_{\mathcal{B}}\cdot{}_{\mathcal{B}}(T)_{\mathcal{B}}\cdot{}_{\mathcal{B}}(Id)_{\mathcal{E}}
$$

Donde:

- ${}_{\mathcal{E}}(Id)_{\mathcal{B}}=\begin{pmatrix}1&0&1\\1&1&0\\0&0&1\end{pmatrix}$
- ${}_{\mathcal{E}}(Id)_{\mathcal{B}}=\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}$

Entonces me queda lo siguiente:

$$
\begin{aligned}
{}_{\mathcal{E}}(T)_{\mathcal{E}}&=\begin{pmatrix}1&0&1\\1&1&0\\0&0&1\end{pmatrix}\cdot\begin{pmatrix}
1 & 3 & 1 \\
0 & -4 & 0 \\
2 & -1 & 3
\end{pmatrix}\cdot\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}\\
&=\begin{pmatrix}3&2&4\\1&-1&1\\2&-1&3\end{pmatrix}\cdot\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}\\
&=\begin{pmatrix}1&2&3\\2&-1&-1\\3&-1&0\end{pmatrix}
\end{aligned}
$$

Como la matriz es simétrica para una base ortonormal, entonces $T$ es autoadjunta.

#### Subparte 2

Sea $S$ un operador lineal con:

$$
{}_{\mathcal{B}}(S)_{\mathcal{B}} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 1 \\
0 & 1 & 2
\end{pmatrix}
$$

Observemos que la base dada no es ortonormal. Consideremos $\mathcal{E}=\{(1,0,0),(0,1,0),(0,0,1)\}$ la base canónica de $\mathbb{R}^3$ que sabemos que si es ortonormal.

Planteemos entonces un cambio de base:

$$
{}_{\mathcal{E}}(S)_{\mathcal{E}}={}_{\mathcal{E}}(Id)_{\mathcal{B}}\cdot{}_{\mathcal{B}}(S)_{\mathcal{B}}\cdot{}_{\mathcal{B}}(Id)_{\mathcal{E}}
$$

Donde:

- ${}_{\mathcal{E}}(Id)_{\mathcal{B}}=\begin{pmatrix}1&0&1\\1&1&0\\0&0&1\end{pmatrix}$
- ${}_{\mathcal{E}}(Id)_{\mathcal{B}}=\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}$

Entonces me queda lo siguiente:


$$
\begin{aligned}
{}_{\mathcal{E}}(T)_{\mathcal{E}}&=\begin{pmatrix}1&0&1\\1&1&0\\0&0&1\end{pmatrix}\cdot\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 1 \\
0 & 1 & 2
\end{pmatrix}\cdot\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}\\
&=\begin{pmatrix}1&1&2\\1&2&1\\0&1&2\end{pmatrix}\cdot\begin{pmatrix}1&0&-1\\-1&1&1\\0&0&1\end{pmatrix}\\
&=\begin{pmatrix}0&1&2\\-1&2&2\\-1&1&3\end{pmatrix}
\end{aligned}
$$

Como la matriz es simétrica NO para una base ortonormal, entonces $T$ NO es autoadjunta.

### Parte 2

Análoga a la parte 1

### Parte 3

En $\mathbb{R}^3$, con producto interno habitual, se define:

- $T(1,1,0) = (5,\ 8,\ -1)$  
- $T(1,-1,1) = (10,\ -14,\ 10)$  
- $T(2,1,1) = (13,\ a,\ b)$

Hallar $a$ y $b$ para que $T$ sea autoadjunto.

Para que $T$ sea autoadjunto, se tiene que verificar en general que $\left<T(v), w\right>=\left<v, T(w)\right>$.

En particular:

- $\left<T(1,1,0), (2,1,1)\right>=\left<(1,1,0), T(2,1,1)\right>$
- $\left<T(1,-1,1), (2,1,1)\right>=\left<(1,-1,1), T(2,1,1)\right>$

Expandamos ambos dos:

$$
\begin{aligned}
&\left<T(1,1,0), (2,1,1)\right>=\left<(1,1,0), T(2,1,1)\right>\\
&\iff\scriptstyle{(\text{definición dada de }T)}\\
&\left<(5,8,-1), (2,1,1)\right>=\left<(1,1,0), (13,a,b)\right>\\
&\iff\scriptstyle{(\text{definición de producto interno dado})}\\
&10+8-1=13+a\\
&\iff\scriptstyle{(\text{aritmética})}\\
&a=4\\
\end{aligned}
$$

Por otra parte:

$$
\begin{aligned}
&\left<T(1,-1,1), (2,1,1)\right>=\left<(1,-1,1), T(2,1,1)\right>\\
&\iff\scriptstyle{(\text{definición dada de }T)}\\
&\left<(10,-14,10), (2,1,1)\right>=\left<(1,-1,1), (13,a,b)\right>\\
&\iff\scriptstyle{(\text{definición de producto interno dado})}\\
&20-14+10=13-a+b\\
&\iff\scriptstyle{(a=4)}\\
&20-14+10=13-4+b\\
&\iff\scriptstyle{(\text{aritmética})}\\
&b=7\\
\end{aligned}
$$

Por lo tanto $T$ es autoadjunto sii $a=4$ y $b=7$