# CLASE 18 - 14/07/2025

## Representación matricial de la adjunta

### Teorema

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

#### Lema (usado para la demostración)

Dados $V,W$ espacios vectoriales con producto interno y $T:V\to W$ y dos bases ORTONORMALES:

- $\mathcal{A}=\{v_1,\ldots,v_n\}\to V$
- $\mathcal{B}=\{w_1,\ldots,w_m\}\to W$

Entonces:

- $({}_{\mathcal{B}}(T)_{\mathcal{A}})_{ij}=\left<T(v_j), w_i\right>$

##### Demostración (del lema)

Esto se demuestra fácilmente por cómo podemos escribir las coordenadas de un vector en una base ortonormal.

#### Demostración

Para probar el teorema, vamos a buscar demostrar que:

$$
({}_{\mathcal{A}}(T^*)_{\mathcal{B}})_{ij}=(\overline{({}_{\mathcal{B}}(T)_{\mathcal{A}})^t})_{ij}\quad\forall i=1,\ldots,n\quad\forall j=1,\ldots,m
$$

Utilizando el lema, tenemos que:

- $({}_{\mathcal{A}}(T^*)_{\mathcal{B}})_{ij}=\left<T^*(w_j), v_i\right>=\left<w_j, T(v_i)\right>=\overline{\left<T(v_i), w_j\right>}$
- $(\overline{({}_{\mathcal{B}}(T)_{\mathcal{A}})^t})_{ij}=(\overline{({}_{\mathcal{B}}(T)_{\mathcal{A}})})_{ji}=\overline{\left<T(v_i), w_j\right>}$

Como llegamos a que ambos resultados son iguales, queda demostrado el teorema.

#### Ejemplo (de uso del teorema)

Sea $T:\mathbb{R}^3\to\mathbb{R}^3$, definida por:
- $T(x,y,z)=(x-y+2z,4x-3z, x+5y+z)$

Consideremos $\mathcal{E}=\{(1,0,0),(0,1,0),(0,0,1)\}$ base ortonormal de $\mathbb{R}^3$

Observemos que:

- $T(1,0,0)=(1,4,1)$
- $T(0,1,0)=(-1,0,5)$
- $T(0,0,1)=(2,-3,1)$

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}}=\begin{pmatrix}1&-1&2\\4&0&-3\\1&5&1\end{pmatrix}
$$

Utilizando el teorema que enunciamos, tenemos que:

$$
{}_{\mathcal{E}}(T^*)_{\mathcal{E}}=\overline{({}_{\mathcal{E}}(T)_{\mathcal{E}})^t}=\begin{pmatrix}1&4&1\\-1&0&5\\2&-3&1\end{pmatrix}
$$

### Definición (transformación lineal autoadjunta)

Sea $V$ un espacio vectorial con cuerpo $\mathcal{K}$ de dimensión finita con producto interno.

Consideramos $T:V\to V$ y $T^*:V\to V$. Decimos que $T$ es autoadjunta si $T=T^*$

#### Observación

$T$ autoadjunta $\iff\left<T(v), w\right>=\left<v, T(w)\right>\quad\forall v,w\in V$

#### Teorema

Sea $V$ un $\mathbb{R}$-espacio vectorial de dimensión finita con producto interno, sea $T:V\to V$. Entonces las siguientes afirmaciones son equivalentes:

1. $T$ es autoadjunta
2. $\forall\mathcal{B}\to V$ ortonormal, ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es simétrica
3. $\exists\mathcal{B}_0\to V$ ortonormal, ${}_{\mathcal{B}_0}(T)_{\mathcal{B_0}}$