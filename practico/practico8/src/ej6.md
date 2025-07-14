# Ejercicio 6

## Consigna

Hallar ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ y ${}_{\mathcal{B}}(T^*)_{\mathcal{B}}$ en una base $\mathcal{B}$ ortonormal conveniente, para las siguientes transformaciones:

1. $T : \mathbb{C}^3 \to \mathbb{C}^3$ definida por:
   $T(x, y, z) = (2x + iy,\ y - 5iz,\ x + (1 - i)y + 3z)$

2. $T : \mathbb{R}^3 \to \mathbb{R}^2$ definida por:
   $T(x, y, z) = (2x + y - z,\ x + y + z)$

3. $T : M_2(\mathbb{R}) \to M_2(\mathbb{R})$ definida por:
   $T(A) =
   \begin{pmatrix}
   1 & 2 \\
   -1 & 3
   \end{pmatrix}
   \cdot A$

## Resolución

### Recordatorio

Para este ejercicio usaremos el siguiente teorema enunciado en la clase 18 del teórico:

Sean $V,W$ dos espacios vectoriales con producto interno.

Sea $T:V\to W$, $T^*:W\to V$ y dos bases ORTONORMALES:
- $\mathcal{A}=\{v_1,\ldots,v_n\}\to V$
- $\mathcal{B}=\{w_1,\ldots,w_m\}\to W$

Entonces:

$$
\begin{aligned}
{}_{\mathcal{A}}(T^*)_{\mathcal{B}}=\overline{({}_{\mathcal{B}}(T)_{\mathcal{A}})^t}
\end{aligned}
$$

### Parte 1

Consideremos la base canónica de $\mathbb{C^3}$:
- $\mathcal{E}=\{(1,0,0),(0,1,0),(0,0,1)\}$

Observemos que la misma es ortonormal considerando el producto interno estándar.

Entonces podemos representar $T$ de la siguiente forma:

- $T(1,0,0)=(2,0,1)$
- $T(0,1,0)=(i,1,1-i)$
- $T(0,0,1)=(0,-5i,3)$

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=\begin{pmatrix}2&i&0\\0&1&-5i\\1&1-i&3\end{pmatrix}
$$

Como estamos trabajando en una base ortonormal, entonces se cumple la propiedad enunciada en el recordatorio, entonces:

$$
{}_{\mathcal{E}}(T^*)_{\mathcal{E}}=\begin{pmatrix}2&0&1\\-i&1&1+i\\0&5i&3\end{pmatrix}
$$

### Parte 2

Recordemos la transformación lineal con la que estamos trabajando:

$T : \mathbb{R}^3 \to \mathbb{R}^2$ definida por:
   $T(x, y, z) = (2x + y - z,\ x + y + z)$

Consideremos las bases canónicas de $\mathbb{R}^3$ y $\mathbb{R}^2$ (ambas ortonormales para el PI estándar):
- $\mathcal{E}_1=\{(1,0),(0,1)\}$
- $\mathcal{E}_2=\{(1,0,0),(0,1,0),(0,0,1)\}$

Entonces:

- $T(1,0,0)=(2,1)$
- $T(0,1,0)=(1,1)$
- $T(0,0,1)=(-1,1)$

Con esto, podemos construir la matriz de la siguiente forma:

$$
\begin{aligned}
{}_{\mathcal{E_2}}(T)_{\mathcal{E_1}}=\begin{pmatrix}2&1&-1\\1&1&1\end{pmatrix}
\end{aligned}
$$

Como estamos trabajando en bases ortonormales, entonces se cumple la propiedad enunciada en el recordatorio, entonces:

$$
{}_{\mathcal{E}_1}(T^*)_{\mathcal{E}_2}=\begin{pmatrix}2&1\\1&1\\-1&1\end{pmatrix}
$$

### Parte 3

Análoga a las anteriores.