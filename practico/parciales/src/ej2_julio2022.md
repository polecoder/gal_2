# Ejercicio 2 - Parcial Julio 2022

## Consigna

Sea $T : \mathbb{C}^3 \to \mathbb{C}^3$ el operador lineal que satisface:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
1 & -3i & 0 \\
3 & 4 & -i \\
1 & 2 & 0
\end{pmatrix}
$$

donde $B = \{(1,0,0),\ (0,1,0),\ (1,1,1)\}$ es una base de $\mathbb{C}^3$.  
Entonces, la matriz ${}_{\mathcal{B}}(T^*)_{\mathcal{B}}$ es igual a:

**A.**
$$
\begin{pmatrix}
2 & 4 & 1 \\
2 + 3i & 6 & 2 \\
-4 - 3i & -10 + i & -3
\end{pmatrix}
$$

**B.**
$$
\begin{pmatrix}
1 & 3 & 1 \\
3i & 4 & 2 \\
0 & i & 0
\end{pmatrix}
$$

**C.**
$$
\begin{pmatrix}
6 + 3i & 14 - i & 24 + 2i \\
6 + 6i & 16 - i & 27 + 5i \\
-4 - 3i & -10 + i & -17 - 2i
\end{pmatrix}
$$

**D.**
$$
\begin{pmatrix}
6 - 3i & 14 + i & 24 - 2i \\
6 - 6i & 16 + i & 27 - 5i \\
-4 + 3i & -10 - i & -17 + 2i
\end{pmatrix}
$$

## Resolución

Consideremos $\mathcal{E}=\{(1,0,0),(0,1,0),(0,0,1)\}$ la base canónica de $\mathbb{C}^3$
Observemos que la matriz dada ya nos da:

- $T(1,0,0)=1(1,0,0)+3(0,1,0)+1(1,1,1)=(2,4,1)$
- $T(0,1,0)=-3i(1,0,0)+4(0,1,0)+2(1,1,1)=(2-3i,6,2)$

Solo nos faltaría obtener $T(0,0,1)$ para completar ${}_{\mathcal{E}}(T)_{\mathcal{E}}$.

Observemos que:

$$
\begin{aligned}
&T(1,1,1)=T(1,0,0)+T(0,1,0)+T(0,0,1)\\
&\iff\scriptstyle{(\text{matriz asociada }{}_{\mathcal{B}}(T)_{\mathcal{B}})}\\
&0(1,0,0)-i(0,1,0)+0(1,1,1)=T(1,0,0)+T(0,1,0)+T(0,0,1)\\
&\iff\scriptstyle{(\text{sustituyendo valores conocidos})}\\
&(0,-i,0)-(2,4,1)-(2-3i,6,2)=T(0,0,1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&(-4+3i,-10-i,-3)=T(0,0,1)\\
\end{aligned}
$$

Por lo que entonces, la matriz asociada con la base canónica es:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} =
\begin{pmatrix}
2 & 2-3i & -4+3i \\
4 & 6 & -10-i \\
1 & 2 & -3
\end{pmatrix}
$$

Entonces como $\mathcal{E}$ es canónica, podemos llegar a la adjunta de la siguiente forma:

$$
{}_{\mathcal{E}}(T^*)_{\mathcal{E}}=
(\overline{{}_{\mathcal{E}}(T)_{\mathcal{E}}})^t =
\begin{pmatrix}
2 & 4 & 1 \\
2+3i & 6 & 2 \\
-4-3i & -10+i & -3
\end{pmatrix}
$$

Por lo que la opción correcta es la opción **A**.