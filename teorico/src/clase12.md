# CLASE 12 - 15/04/2025

## Método de Ortonormalización de Gram-Schmidt

Sea $V$ un espacio vectorial con producto interno, $dim(V)=n$. Dada una base $\mathcal{B} = \{v_1,\ldots,v_n\}$ de $V$, existe una base **ortonormal** $\mathcal{B}' = \{y_1,\ldots,y_n\}$ de $V$, que además cumple:

- $[v_1,\ldots,v_k] = [y_1,\ldots,y_k]\quad\forall k\in\{1,\ldots,n\}$

### Demostración

Primero debemos hallar una base ortogonal $\{w_1,\ldots,w_n\}$ que cumpla:

- $[w_1,\ldots,w_k] = [y_1,\ldots,y_k]\quad\forall k\in\{1,\ldots,n\}$

Luego bastará con normalizar dicha base.

Veamos como elegir vectores de forma apropiada para cumplir con lo que necesitamos.

1. Para seleccionar $w_1$ tenemos la forma trivial que sería seleccionar $w_1=v_1$, de esta forma cumplimos con que $[w_1]=[v_1]$. Por ahora no necesitamos más que cumplir con esa condición.

2. Selecciono $w_2$ como combinación lineal de $v_1,v_2$ de la siguiente forma:

    $$
    w_2 = v_2 - \frac{\left<v_2, w_1\right>}{\left<w_1, w_1\right>}w_1
    $$

    1. En primer lugar, tenemos que $[w_1,w_2]=[v_1,v_2]$, esto porque estamos eligiendo $w_2$ específicamente para que esto se cumpla.
    2. $w_2\neq 0$, pues es la combinación lineal de dos vectores que son LI.
    3. Nos restaría probar que $w_2 \perp w_1$. Verifiquemos:

        $$
        \begin{aligned}
        &\left<w_2, w_1\right>\\
        &= \scriptstyle{(\text{definición de producto interno (linealidad)})}\\
        &\left<v_2, w_1\right>-\frac{\left<v_2, w_1\right>}{\left<w_1, w_1\right>}\left<w_1, w_1\right>\\
        &= \scriptstyle{(\text{operatoria})}\\
        &0
        \end{aligned} 
        $$

    Con esto seleccionamos $w_2$ que cumple con todo lo que buscabamos.

3. Selecciono $w_3$ como combinación lineal de $v_1,v_2,v_3$ de la siguiente forma:

    $$
    w_3 = v_3 - \frac{\left<v_3, w_2\right>}{\left<w_2, w_2\right>}w_2 - \frac{\left<v_3, w_1\right>}{\left<w_1, w_1\right>}w_1
    $$

    1. En primer lugar, tenemos que $[w_1,w_2,w_3]=[v_1,v_2,v_3]$, esto porque estamos eligiendo $w_3$ específicamente para que esto se cumpla.
    2. $w_3\neq 0$, pues es la combinación lineal de tres vectores que son LI.
    3. Nos restaría probar que $w_3 \perp w_2$ y $w_3 \perp w_1$. Verifiquemos:

        $$
        \begin{aligned}
        &\left<w_3, w_2\right>\\
        &= \scriptstyle{(\text{definición de producto interno (linealidad)})}\\
        &\left<v_3, w_2\right>-\frac{\left<v_3, w_2\right>}{\left<w_2, w_2\right>}\left<w_2, w_2\right>-\frac{\left<v_3, w_1\right>}{\left<w_1, w_1\right>}\left<w_1, w_2\right>\\
        &= \scriptstyle{(\text{operatoria: }\left<w_1, w_2\right>=0)}\\
        &0
        \end{aligned} 
        $$

        De la misma forma veamos $w_3\perp w_1$:

        $$
        \begin{aligned}
        &\left<w_3, w_1\right>\\
        &= \scriptstyle{(\text{definición de producto interno (linealidad)})}\\
        &\left<v_3, w_1\right>-\frac{\left<v_3, w_2\right>}{\left<w_2, w_2\right>}\left<w_2, w_1\right>-\frac{\left<v_3, w_1\right>}{\left<w_1, w_1\right>}\left<w_1, w_1\right>\\
        &= \scriptstyle{(\text{operatoria: }\left<w_2, w_1\right>=0)}\\
        &0
        \end{aligned} 
        $$

Veamos como generalizar este procedimiento:

Dado $\{w_1,w_2,\ldots,w_{k-1}\}$ un conjunto ortogonal, definimos:

$$
w_k=v_k-\frac{\left<v_k, w_{k-1}\right>}{\left<w_{k-1}, w_{k-1}\right>}w_{k-1}-\frac{\left<v_k, w_{k-2}\right>}{\left<w_{k-2}, w_{k-2}\right>}w_{k-2} - \ldots -\frac{\left<v_k, w_1\right>}{\left<w_1, w_1\right>}w_1
$$

Con esto, estudiemos los 3 requerimientos que tenemos que cumplir:

1. En primer lugar, tenemos que $[w_1,w_2,\ldots,w_k]=[v_1,v_2,\ldots,v_k]$, esto porque estamos eligiendo $w_k$ específicamente para que esto se cumpla. La idea es que $w_k$ es combinación lineal de $\{v_1,v_2,\ldots,v_k\}$
2. $w_k\neq 0$, pues es la combinación lineal de $k$ vectores que son LI.
3. Nos restaría probar que es ortogonal a todos los vectores anteriores.

Probemos esto último:

Se cumple, para $j=1,2,\ldots,k-1$

$$
\begin{aligned}
&\left<w_k, w_j\right>\\
&= \scriptstyle{(\text{desarrollo de }w_k)}\\
&\left<v_k - \sum_{i=1}^{k-1}\frac{\left<v_k, w_i\right>}{\left<w_i, w_i\right>}w_i,w_j\right>\\
&= \scriptstyle{(\text{definición de producto interno})}\\
&\left<v_k, w_j\right>-\sum_{i=1}^{k-1}\frac{\left<v_k, w_i\right>}{\left<w_i, w_i\right>}\cdot\left<w_i, w_j\right>\\
&= \scriptstyle{(\text{ortogonalidad cuando }i\neq j)}\\
&\left<v_k, w_j\right>-\frac{\left<v_k, w_j\right>}{\left<w_j, w_j\right>}\cdot\left<w_j, w_j\right>\\
&= \scriptstyle{(\text{operatoria})}\\
&0
\end{aligned}
$$

Entonces $w_k\perp w_j\quad\forall j\in\{1,\ldots,k-1\}$, lo que prueba que $\{w_1,w_2,\ldots,w_k\}$ es un conjunto ortogonal.

Para obtener un conjunto ortonormal, basta con normalizar los vectores, es decir, tomamos:

$$
y_j = \left\{\frac{w_j}{\|w_j\|}: j\in\{1,\ldots,n\}\right\}
$$

Dicho conjunto es base ortonormal de $V$.

### Matriz de cambio de base con una base ortonormal

Veamos la matriz cambio de base que resulta del método de ortonormalización de Gram-Schmidt.

- $\mathcal{B}=\{v_1,\ldots,v_n\}$
- $\mathcal{B}'=\{y_1,\ldots,y_n\}$

**Notación:**

$C_{ki} = \frac{\left<v_k, w_i\right>}{\left<w_i, w_i\right>}$ con $i\in\{1,\ldots,n\}$

Los elementos de $\{w_1,\ldots,w_n\}$ los habíamos definido de la siguiente forma:

- $w_k=v_k - \sum_{i=0}^{k-1}c_{ki}w_i$ con $k\in\{1,\ldots,n\}$

Y a partir de esto dijimos que:

- $y_j=\frac{w_j}{\|w_j\|}$ para $j\in\{1,\ldots,n\}$

Con esto, podemos obtener $v_k$ como combinación lineal de $y_j$ de la siguiente forma:

- $v_1 = w_1 = \|w_1\|y_1$
- $v_2 = w_2 + C_{21}w_1 = \|w_2\|y_2 + C_{21}\|w_1\|y_1$
- $\vdots$
- $v_k = w_k + \sum_{i=1}^{k-1}C_{ki}w_i = \|w_k\|y_k + \sum_{i=1}^{k-1}C_{ki}\|w_i\|y_i$

Con esto tenemos que la matriz cambio de base queda de la siguiente forma:

$$
{}_{\mathcal{B'}}(\mathbb{I})_{\mathcal{B}}=\begin{pmatrix}
\|w_1\|&C_{21}\|w_1\|&\cdots&C_{k1}\|w_1\|&\cdots&C_{n1}\|w_1\|\\
0&\|w_2\|&\cdots&C_{k2}\|w_2\|&\cdots&C_{n2}\|w_2\|\\
\vdots&0&\ddots&\vdots&&\vdots\\
\vdots&\vdots&&\|w_k\|&&\vdots\\
\vdots&\vdots&&\vdots&\ddots&\vdots\\
0&0&\cdots&0&\cdots&\|w_n\|
\end{pmatrix}
$$

Observemos que es una matriz triangular superior, esto tendrá sus aplicaciones en posteriores clases.

### Propiedades de bases ortogonales

Sea $V$ un espacio vectorial con producto interno y una base ortonormal $\mathcal{B} = \{v_1,\ldots,v_n\}$

1. Si $v=\sum_{i=1}^n\alpha_iv_i$ y $w=\sum_{i=1}^n\beta_iv_i$ entonces $\left<v, w\right> = \sum_{i=1}^n\alpha_i\overline{\beta_i}$
2. $\forall v\in V:v=\left<v, v_1\right>v_1+\left<v, v_2\right>v_2+\ldots+\left<v, v_n\right>v_n$
3. $\forall v\in V: \|v\|^2 = \sum_{i=1}^n |\left<v, v_i\right>|^2$

#### Demostración

1. Veamoslo con lo siguiente:

$$
\begin{aligned}
&\left<v, w\right>\\
&= \scriptstyle{(\text{por hipótesis})} \\
&\left<\sum_{i=1}^n\alpha_iv_i, \sum_{j=1}^n\beta_jv_j\right>\\
&= \scriptstyle{(\text{definición de producto interno})} \\
&\sum_{i=1}^{n}\sum_{j=1}^{n}\alpha_i\overline{\beta_j}\left<v_i, v_j\right>\\
&= \scriptstyle{(\text{por ortogonalidad: }i\neq j\iff\left<v_i, v_j\right> = 0)} \\
&\sum_{j=1}^{n}\alpha_j\overline{\beta_j}\|v_j\|^2 \\
&= \scriptstyle{(\text{por ortonormalidad: }\|v_i\|=1)} \\
&\sum_{j=1}^{n}\alpha_j\overline{\beta_j}\\
\end{aligned}
$$

2. Sea $v\in V$ con coordenadas $v=\sum_{i=1}^{n}a_iv_i$, entonces para cualquier $j\in\{1,\ldots,n\}$ tenemos que:

$$
\begin{aligned}
&\left<v,v_j\right>\\
&= \scriptstyle{(\text{operatoria})} \\
&\left<\sum_{i=1}^{n}a_iv_i, v_j\right>\\
&= \scriptstyle{(\text{definición de producto interno})} \\
&\sum_{i=1}^{n}a_i\left<v_i, v_j\right>\\
&= \scriptstyle{(\text{por ortogonalidad: }i\neq j\iff\left<v_i, v_j\right> = 0)}\\
&a_j\left<v_j,v_j\right> \\
&= \scriptstyle{(\text{por ortonormalidad: }\|v_i\|=1)} \\
&a_j
\end{aligned}
$$

3. Sea $v=a_1v_1+a_2v_2+\ldots+a_nv_n$, sabemos que estos vectores son ortogonales entre si. Entonces:

$$
\begin{aligned}
&\|v\|^2 = \|\sum_{i=1}^{n}a_iv_i\|^2 \\
&= \scriptstyle{(\text{por Pitágoras})} \\
&\sum_{i=1}^{n}\|a_iv_i\|^2 \\
&= \scriptstyle{(\text{definición de norma})} \\
&\sum_{i=1}^{n}|a_i|^2\|v_i\|^2 \\
&= \scriptstyle{(\text{por ortonormalidad: }\|v_i\|=1)} \\
&\sum_{i=1}^{n}|a_i|^2 \\
&= \scriptstyle{(\text{por la propiedad anterior})} \\
&\sum_{i=1}^{n}|\left<v, v_i\right>|^2
\end{aligned}
$$