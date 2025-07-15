# Ejercicio 9

## Consigna

En $\mathbb{R}^3$ con producto interno usual, se considera la base $\mathcal{B} = \{u_1, u_2, u_3\}$ tal que:

- $\langle u_1, u_2 \rangle = \langle u_1, u_3 \rangle = 0$  
- $\langle u_2, u_3 \rangle = \frac{1}{2}$

Se definen los operadores:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 3 & 0 \\
0 & 0 & 3
\end{pmatrix},
\quad
{}_{\mathcal{B}}(S)_{\mathcal{B}} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 3 & 0 \\
0 & 0 & 5
\end{pmatrix}
$$

Estudiar si $T$ y $S$ son operadores autoadjuntos

## Resolución

Primero, consideremos $S$. Observemos que $u_1,u_2,u_3$ son todos vectores propios asociados a valores propios diferentes dos a dos.
Si $S$ fuera autoadjunto, entonces estos vectores serían ortogonales dos a dos, pero esto no sucede pues: $\left<u_2, u_3\right>=\frac{1}{2}\neq0$.
Concluyendo, $S$ no es autoadjunto.

Ahora veamos $T$, observemos que en este caso, los vectores que no son ortogonales entre si, pertenecen al mismo subespacio propio asociado a 3.
Tenemos que $S_3=[u_2,u_3]$, aplicando Gram-Schmidt, podemos obtener $[w_2,w_3]$ ortogonales entre si y normalizados.
Además, considerando $w_1=\frac{u_1}{\|u_1\|}$ tenemos una base ortonormal de $\mathbb{R}^3$: $\mathcal{B}'=\{w_1,w_2,w_3\}$, y en dicha base ortonormal, la representación de la matriz sería la siguiente:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 3 & 0 \\
0 & 0 & 3
\end{pmatrix}
$$

Por lo que $T$ es autoadjunto.