# Ejercicio 4

## Consigna

Probar que $T$ es autoadjunto, hallar su forma diagonal y una base ortonormal de vectores propios:  

1. $T : \mathbb{R}^3 \to \mathbb{R}^3$ tal que:  
$$T(x,y,z) = \left(\frac{3}{2}x + \frac{1}{2}z, 2y, \frac{1}{2}x + \frac{3}{2}z\right)$$  

2. $T : \mathbb{R}^3 \to \mathbb{R}^3$ tal que:  
$$T(x,y,z) = \left(\frac{3}{2}x - \frac{1}{2}z, -y, -\frac{1}{2}x + \frac{3}{2}z\right)$$  

## Resolución

### Parte 1

Hallemos la matriz asociada ${}_{\mathcal{E}}(T)_{\mathcal{E}}$ considerando $\mathcal{E}$ como la base canónica de $\mathbb{R}^3$

- $T(1,0,0)=(\frac{3}{2},0,\frac{1}{2})$
- $T(0,1,0)=(0,2,0)$
- $T(0,0,1)=(\frac{1}{2},0,\frac{3}{2})$

Por lo tanto la matriz asociada es la siguiente:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}\frac{3}{2}&0&\frac{1}{2}\\0&2&0\\\frac{1}{2}&0&\frac{3}{2}\end{pmatrix}
$$

Como la matriz asociada en una base ortonormal es simétrica, entonces $T$ es autoadjunto.

Ahora hallemos los valores propios (para un tema de cuentas, tengamos presente que si $T$ autoadjunto entonces las raíces son reales).

$$
\begin{aligned}
\Chi_T(\lambda)&=\begin{vmatrix}\frac{3}{2}-\lambda&0&\frac{1}{2}\\0&2-\lambda&0\\\frac{1}{2}&0&\frac{3}{2}-\lambda\end{vmatrix}\\
&=(2-\lambda)\left(\left(\frac{3}{2}-\lambda\right)^2-\frac{1}{4}\right)\\
&=(2-\lambda)\left(\lambda^2-3\lambda+\frac{9}{4}-\frac{1}{4}\right)\\
&=(2-\lambda)(\lambda^2-3\lambda+2)\\
\end{aligned}
$$

De donde obtenemos que:

- $\lambda_1=2$

Mediante Bháskara obtenemos las raíces que faltan:

$$
\begin{aligned}
\lambda&=\frac{3\pm\sqrt{9-8}}{2}\\
&=\frac{3\pm 1}{2}
\end{aligned}
$$

De donde obtenemos:

- $\lambda_1=2$
- $\lambda_2=1$

Por lo que tenemos las siguientes multiplicidades algebraicas:

- $ma(2)=2$
- $ma(1)=1$

Ahora hallemos los subespacios propios:

**Subespacio $S_2$**

Para hallar el subespacio tenemos que resolver el siguiente sistema:

- $(T-2Id)v=0$

Que corresponde a lo siguiente:

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
-\frac{1}{2}&0&\frac{1}{2}&0\\
0&0&0&0\\
\frac{1}{2}&0&-\frac{1}{2}&0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=z$
- $y\in\mathbb{R}$

Podemos definir el subespacio como:

- $S_2=\{(\alpha,\beta,\alpha):\alpha,\beta\in\mathbb{R}\}$ o
- $[(1,0,1),(0,1,0)]$

Observemos que $(1,0,1)\perp(0,1,0)$, por lo que podemos simplemente normalizar para obtener una base ortonormal del espacio:

- $[\frac{1}{\sqrt{2}}(1,0,1),(0,1,0)]$

Ahora hagamos el mismo razonamiento para $S_1$.

**Subespacio $S_2$**

Para hallar el subespacio tenemos que resolver el siguiente sistema:

- $(T-Id)v=0$

Que corresponde a lo siguiente:

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
\frac{1}{2}&0&\frac{1}{2}&0\\
0&1&0&0\\
\frac{1}{2}&0&\frac{1}{2}&0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=-z$
- $y=0$

Podemos definir el subespacio como:

- $S_1=\{(\alpha,0,-\alpha):\alpha\in\mathbb{R}\}$ o
- $[(1,0,-1)]$

Normalizamos para obtener una base ortonormal:

- $[\frac{1}{\sqrt{2}}(1,0,-1)]$

Entonces ahora podemos unir todo para obtener una base ortonormal de vectores propios de $T$:

- $\mathcal{B}=\{\frac{1}{\sqrt{2}}(1,0,-1),\frac{1}{\sqrt{2}}(1,0,1),(0,1,0)\}$

**Observación:** En este punto siempre conviene revisar que efectivamente los vectores sean ortogonales.

### Parte 2

$T : \mathbb{R}^3 \to \mathbb{R}^3$ tal que:  
$$T(x,y,z) = \left(\frac{3}{2}x - \frac{1}{2}z, -y, -\frac{1}{2}x + \frac{3}{2}z\right)$$ 

Hallemos la matriz asociada ${}_{\mathcal{E}}(T)_{\mathcal{E}}$ considerando $\mathcal{E}$ como la base canónica de $\mathbb{R}^3$

- $T(1,0,0)=(\frac{3}{2},0,-\frac{1}{2})$
- $T(0,1,0)=(0,-1,0)$
- $T(0,0,1)=(-\frac{1}{2},0,\frac{3}{2})$

Por lo tanto la matriz asociada es la siguiente:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}\frac{3}{2}&0&-\frac{1}{2}\\0&-1&0\\-\frac{1}{2}&0&\frac{3}{2}\end{pmatrix}
$$

Como la matriz asociada en una base ortonormal es simétrica, entonces $T$ es autoadjunto.

Ahora hallemos los valores propios (para un tema de cuentas, tengamos presente que si $T$ autoadjunto entonces las raíces son reales).

$$
\begin{aligned}
\Chi_T(\lambda)&=\begin{vmatrix}\frac{3}{2}-\lambda&0&-\frac{1}{2}\\0&-1-\lambda&0\\-\frac{1}{2}&0&\frac{3}{2}-\lambda\end{vmatrix}\\
&=(-1-\lambda)\left(\left(\frac{3}{2}-\lambda\right)^2-\frac{1}{4}\right)\\
&=(-1-\lambda)\left(\lambda^2-3\lambda+\frac{9}{4}-\frac{1}{4}\right)\\
&=(-1-\lambda)(\lambda^2-3\lambda+2)\\
\end{aligned}
$$

De donde obtenemos que:

- $\lambda_1=-1$

Mediante Bháskara obtenemos las raíces que faltan:

$$
\begin{aligned}
\lambda&=\frac{3\pm\sqrt{9-8}}{2}\\
&=\frac{3\pm 1}{2}
\end{aligned}
$$

De donde obtenemos:

- $\lambda_1=2$
- $\lambda_2=1$

Por lo que tenemos las siguientes multiplicidades algebraicas:

- $ma(2)=1$
- $ma(1)=1$
- $ma(-1)=1$

Ahora hallemos los subespacios propios:

**Subespacio $S_2$**

Para hallar el subespacio tenemos que resolver el siguiente sistema:

- $(T-2Id)v=0$

Que corresponde a lo siguiente:

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
-\frac{1}{2}&0&-\frac{1}{2}&0\\
0&-3&0&0\\
-\frac{1}{2}&0&-\frac{1}{2}&0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=-z$
- $y=0$

Podemos definir el subespacio como:

- $S_2=\{(\alpha,0,-\alpha):\alpha\in\mathbb{R}\}$ o
- $[(1,0,-1)]$

Normalizamos para obtener una base ortonormal:

- $[\frac{1}{\sqrt{2}}(1,0,-1)]$

**Subespacio $S_1$**

Para hallar el subespacio tenemos que resolver el siguiente sistema:

- $(T-Id)v=0$

Que corresponde a lo siguiente:

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
\frac{1}{2}&0&-\frac{1}{2}&0\\
0&-2&0&0\\
-\frac{1}{2}&0&\frac{1}{2}&0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=z$
- $y=0$

Podemos definir el subespacio como:

- $S_1=\{(\alpha,0,-\alpha):\alpha\in\mathbb{R}\}$ o
- $[(1,0,1)]$

Normalizamos para obtener una base ortonormal.

- $[\frac{1}{\sqrt{2}}(1,0,1)]$

**Subespacio $S_{-1}$**

Para hallar el subespacio tenemos que resolver el siguiente sistema:

- $(T+Id)v=0$

Que corresponde a lo siguiente:

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
\frac{5}{2}&0&-\frac{1}{2}&0\\
0&0&0&0\\
-\frac{1}{2}&0&\frac{5}{2}&0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=z=0$
- $y\in\mathbb{R}$

Podemos definir el subespacio como:

- $S_{-1}=\{(0,\alpha,0):\alpha\in\mathbb{R}\}$ o
- $[(0,1,0)]$

Normalizamos para obtener una base ortonormal.

- $[(0,1,0)]$

Concluyendo, la base ortonormal de vectores propios de $T$ es $\mathcal{B}=\{(0,1,0),\frac{1}{\sqrt{2}}(1,0,1),\frac{1}{\sqrt{2}}(1,0,-1)\}$