# Ejercicio 4

## Consigna

1. Hallar el producto interno en $\mathbb{R}^2$ para el cual   $\left\{ \left(\frac{1}{4}, 0\right),\ (0,\ \frac{1}{2}) \right\}$ es una base ortonormal

2. Hallar el producto interno en $\mathbb{R}^3$ para el cual  
   $\left\{(1, 0, 0),\ (1, 1, 0),\ (1, 1, 1) \right\}$ es una base ortonormal

3. Sea $T : \mathbb{R}^2 \to \mathbb{R}^3$ tal que:  
   $$
   T(x, y) = (x + 3y,\ 3x + y,\ x + y)
   $$

   Hallar $T^*$ en los siguientes casos:

   - $\mathbb{R}^2$ y $\mathbb{R}^3$ con producto interno usual  
   - $\mathbb{R}^2$ con producto interno usual, $\mathbb{R}^3$ con producto interno del punto 1.b  
   - $\mathbb{R}^2$ con producto interno del punto 1.a, $\mathbb{R}^3$ con producto interno usual  
   - Ambos espacios con los productos internos hallados en 1.a y 1.b respectivamente

## Resolución

### Parte 1

Para la resolución de estas partes, vamos a suponer que el producto interno está definido por una matriz $G$ (de tamaño igual a la dimensión del espacio en el que se trabaja) simétrica y positva, de forma que el producto interno queda de la siguiente manera:

$$
\left<x, y\right>=x^TGy
$$

Ahora si, veamos que condiciones tiene que cumplir el producto interno para que la base dada sea ortonormal:

- $\left<(\frac{1}{4},0),(0, \frac{1}{2})\right> = 0$
- $\left<(\frac{1}{4},0), (\frac{1}{4},0)\right>=1$
- $\left<(0, \frac{1}{2}), (0, \frac{1}{2})\right>=1$

Entonces, planteemos los sistemas usando $G=\begin{pmatrix}a&b\\b&c\end{pmatrix}$:

- $\left<(\frac{1}{4},0),(0, \frac{1}{2})\right>=(\frac{1}{4},0)\begin{pmatrix}a&b\\b&c\end{pmatrix}\begin{pmatrix}0\\\frac{1}{2}\end{pmatrix}=\begin{pmatrix}\frac{1}{4}a&\frac{1}{4}b\end{pmatrix}(0, \frac{1}{2})=\frac{b}{8}$
- $\left<(\frac{1}{4},0), (\frac{1}{4},0)\right> = (\frac{1}{4},0)\begin{pmatrix}a&b\\b&c\end{pmatrix}\begin{pmatrix}\frac{1}{4}\\0\end{pmatrix}=\begin{pmatrix}\frac{1}{4}a&\frac{1}{4}b\end{pmatrix}\begin{pmatrix}\frac{1}{4}\\0\end{pmatrix}=\frac{a}{16}$
- $\left<(0, \frac{1}{2}), (0, \frac{1}{2})\right> = (0, \frac{1}{2})\begin{pmatrix}a&b\\b&c\end{pmatrix}\begin{pmatrix}0\\\frac{1}{2}\end{pmatrix}=\begin{pmatrix}\frac{1}{2}b&\frac{1}{2}c\end{pmatrix}\begin{pmatrix}0\\\frac{1}{2}\end{pmatrix}=\frac{c}{4}$

Lo que nos deja con:

- $\frac{b}{8}=0\iff b=0$
- $\frac{a}{16}=1\iff a=16$
- $\frac{c}{4}=1\iff c=4$

Concluyendo, podemos expresar un producto interno entre dos vectores $x,y\in\mathbb{R}^2$ de la siguiente forma:

$$
\begin{aligned}
\left<x, y\right>&=x^TGy\\
&=(x_1,x_2)\begin{pmatrix}16&0\\0&4\end{pmatrix}\begin{pmatrix}y_1\\y_2\end{pmatrix}\\
&=\begin{pmatrix}16x_1&4x_2\end{pmatrix}\begin{pmatrix}y_1\\y_2\end{pmatrix}\\
&=16x_1y_1+4x_2y_2
\end{aligned}
$$

### Parte 3

Sea $T : \mathbb{R}^2 \to \mathbb{R}^3$ tal que:  
   $$
   T(x, y) = (x + 3y,\ 3x + y,\ x + y)
   $$

### Subparte 1

- $\mathbb{R}^2$ y $\mathbb{R}^3$ con producto interno usual

Consideremos las bases canónicas de ambos espacios.

Nos basaremos en lo siguiente para completar nuestro razonamiento:

$$
T^*(x',y',z')=x'T^*(1,0,0)+y'T^*(0,1,0)+z'T^*(0,0,1)
$$

Entonces calculemos:

- $\left<(x,y), T^*(1,0,0)\right>_{\mathbb{R}^2}=\left<T(x,y), (1,0,0)\right>_{\mathbb{R}^3}=\left<(x+3y,3x+y,x+y), (1,0,0)\right>_{\mathbb{R}^3}=x+3y=\left<(x,y), (1,3)\right>_{\mathbb{R}^2}$
    - Entonces $T^*(1,0,0)=(1,3)$
- $\left<(x,y), T^*(0,1,0)\right>_{\mathbb{R}^2}=\left<T(x,y), (0,1,0)\right>_{\mathbb{R}^3}=\left<(x+3y,3x+y,x+y), (0,1,0)\right>_{\mathbb{R}^3}=3x+y=\left<(x,y), (3,1)\right>_{\mathbb{R}^2}$
    - Entonces $T^*(0,1,0)=(3,1)$
- $\left<(x,y), T^*(0,0,1)\right>_{\mathbb{R}^2}=\left<T(x,y), (0,0,1)\right>_{\mathbb{R}^3}=\left<(x+3y,3x+y,x+y), (0,0,1)\right>_{\mathbb{R}^3}=x+y=\left<(x,y), (1,1)\right>_{\mathbb{R}^2}$
    - Entonces $T^*(0,1,0)=(1,1)$

Por lo que:

$$
\begin{aligned}
T^*(x',y',z')&=x'(1,3)+y'(3,1)+z'(1,1)
&=(x'+3y'+z',3x'+y'+z')
\end{aligned}
$$

### Resto de subpartes

No se realizan por tema de tiempo, pero son todos hechos con la misma idea.