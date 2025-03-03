# Ejercicio 9

## Consigna

Dadas las bases $\mathcal{A}=\{(1,1,0),(1,0,1),(0,1,1)\}$ y $\mathcal{B}=\{(1,0,1),(0,1,0),(-1,0,0)\}$ de $\mathbb{R}^3$.

1. Hallar $coord_{\mathcal{A}}(v)$ y $coord_{\mathcal{B}}(v)$ $\forall v\in\mathbb{R}^3$.
2. Dada $Id:\mathbb{R}^3\to\mathbb{R}^3$ la transformación identidad, hallar ${}_{\mathcal{A}}(Id)_{\mathcal{B}}$ y ${}_{\mathcal{B}}(Id)_{\mathcal{A}}$.
3. Verificar que: $coord_{\mathcal{A}}(v)={}_{\mathcal{A}}(Id)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v)$ y $coord_{\mathcal{B}}(v)={}_{\mathcal{B}}(Id)_{\mathcal{A}}\cdot coord_{\mathcal{A}}(v)$

## Resolución (parte 1)

Hallemos $coord_{\mathcal{A}}(v)$ y $coord_{\mathcal{B}}(v)$ $\forall v\in\mathbb{R}^3$. Para esto, llamemos $v = (x,y,z)$, entonces:

$$coord_{\mathcal{A}}(v) = (a_1,a_2,a_3)$$

Tal que $a_1,a_2,a_3$ cumplen lo siguiente:

$$(x,y,z) = a_1(1,1,0)+a_2(1,0,1)+a_3(0,1,1)$$

Esto nos deja con el siguiente sistema:

$$
\begin{array}{ccc|c}
1&1&0&x\\
1&0&1&y\\
0&1&1&z
\end{array}\rightarrow
\begin{array}{ccc|c}
1&1&0&x\\
0&-1&1&y-x\\
0&1&1&z
\end{array}\rightarrow
\begin{array}{ccc|c}
1&1&0&x\\
0&-1&1&y-x\\
0&0&2&z+y-x
\end{array}
$$

Entonces:

- $a_3 = \frac{z+y-x}{2}$
- $a_2 = -(\frac{-z-y+x}{2}+y-x) = -(\frac{-z+y-x}{2}) = \frac{z-y+x}{2}$
- $a_1 = x + \frac{-z+y-x}{2} = \frac{-z+y+x}{2}$

Concluimos que:

$$coord_{\mathcal{A}}(v) = (\frac{-z+y+x}{2},\frac{z-y+x}{2},\frac{z+y-x}{2}) = \frac{1}{2}(-z+y+x,z-y+x,z+y-x)$$

Ahora hagamos lo mismo con:

$$coord_{\mathcal{B}}(v) = (b_1,b_2,b_3)$$

Tal que $b_1,b_2,b_3$ cumplen lo siguiente:

$$
(x,y,z) = b_1(1,0,1)+b_2(0,1,0)+b_3(-1,0,0)
$$

Esto nos deja con el sistema:

$$
\begin{array}{ccc|c}
1&0&-1&x\\
0&1&0&y\\
1&0&0&z
\end{array}
$$

Se observa trivialmente que:

- $b_1 = z$
- $b_2 = y$
- $b_3 = -(x-z) = -x+z$

Entonces:

$$coord_{\mathcal{B}}(v) = (z,y,-x+z)$$

## Resolución (parte 2)

Queremos hallar ${}_{\mathcal{A}}(Id)_{\mathcal{B}}$, para esto tenemos que hallar las coordenadas de los vectores de la base de partida $\mathcal{B}$ transformados, en la base de llegada $\mathcal{A}$; es decir:

- $coord_{\mathcal{A}}(Id(1,0,1)) = \frac{1}{2}(0,2,0) = (0,1,0)$
- $coord_{\mathcal{A}}(Id(0,1,0)) = (\frac{1}{2},\frac{-1}{2},\frac{1}{2})$
- $coord_{\mathcal{A}}(Id(-1,0,0)) = (\frac{-1}{2},\frac{-1}{2},\frac{1}{2})$

**Observación:** Obviamente acá usamos la fórmula que hallamos en la parte anterior, o sea la siguiente:

$$coord_{\mathcal{A}}(v) = \frac{1}{2}(-z+y+x,z-y+x,z+y-x)$$

Entonces:

$$
{}_{\mathcal{A}}(Id)_{\mathcal{B}} =
\begin{pmatrix}
0&\frac{1}{2}&\frac{-1}{2}\\
1&\frac{-1}{2}&\frac{-1}{2}\\
0&\frac{1}{2}&\frac{1}{2}
\end{pmatrix} 
$$

Ahora hallemos ${}_{\mathcal{B}}(Id)_{\mathcal{A}}$:

- $coord_{\mathcal{B}}(Id(1,1,0)) = (0,1,-1)$
- $coord_{\mathcal{B}}(Id(1,0,1)) = (1,0,0)$
- $coord_{\mathcal{B}}(Id(0,1,1)) = (1,1,1)$

Entonces:

$$
{}_{\mathcal{B}}(Id)_{\mathcal{A}} =
\begin{pmatrix}
0&1&1\\
1&0&1\\
-1&0&1
\end{pmatrix}
$$

## Resolución (parte 3)

Verifiquemos que $coord_{\mathcal{A}}(v)={}_{\mathcal{A}}(Id)_{\mathcal{B}}\cdot coord_{\mathcal{B}}(v)$:

$$coord_{\mathcal{A}}(v) = \frac{1}{2}(-z+y+x,z-y+x,z+y-x)$$

$$coord_{\mathcal{B}}(v) = (z,y,-x+z)$$

$$
\frac{1}{2}(-z+y+x,z-y+x,z+y-x) =
\begin{pmatrix}
0&\frac{1}{2}&\frac{-1}{2}\\
1&\frac{-1}{2}&\frac{-1}{2}\\
0&\frac{1}{2}&\frac{1}{2}
\end{pmatrix}\cdot
\begin{pmatrix}
z\\
y\\
-x+z
\end{pmatrix}
$$

Esto se verifica, chequear mentalmente. Ahora lo mismo para:

$$
(z,y,-x+z) =
\begin{pmatrix}
0&1&1\\
1&0&1\\
-1&0&1
\end{pmatrix}\cdot
\begin{pmatrix}
\frac{-z+y+x}{2}\\
\frac{z-y+x}{2}\\
\frac{z+y-x}{2}
\end{pmatrix}
$$

También se verifica, en caso de duda siempre verificarlo haciendo la cuenta. Mentalmente es más fácil para evitar la cantidad de cuentas