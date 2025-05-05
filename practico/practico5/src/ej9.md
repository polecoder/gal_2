# Ejercicio 9

## Consigna

1. En $\mathbb{R}^4$ con producto interno habitual, hallar una base ortonormal de:
   $S = \left[ (1, 1, 0, 0), (1, 1, 1, 1), (-1, 0, 2, 1) \right]$.

2. En $\mathbb{C}^3$ con producto interno habitual, hallar una base ortonormal de:
   $S = \left[ (1, i, 0), (1, 1, 1) \right]$.

## Resolución

La resolución de este ejercicio es utilizar el método de Ortonormalización de Gram-Schmidt.

### Parte 1

En esta parte, consideramos el producto interno habitual de $\mathbb{R}^4$, es decir, el defindo por:

$$
\left<v, w\right>=\sum_{i=1}^{4}v_iw_i
$$

Considerando los vectores que ya tenemos, los describimos como:

- $v_1 = (1,1,0,0)$
- $v_2 = (1,1,1,1)$
- $v_3 = (-1,0,2,1)$

Queremos encontrar vectores $\{w_1,w_2,w_3\}$ tal que:

- $[w_1,w_2,w_3] = [v_1,v_2,v_3]$

Empezamos tomando $w_1=v_1=(1,1,0,0)$, a partir de esto definimos $w_2$ de la siguiente forma:

$$
w_2=v_2-\frac{\left<v_2, w_1\right>}{\left<w_1, w_1\right>}w_1
$$

Sustituyendo con los valores que conocemos:

$$
w_2=(1,1,1,1)-\frac{\left<(1,1,1,1), (1,1,0,0)\right>}{\left<(1,1,0,0), (1,1,0,0)\right>}(1,1,0,0)
$$

Cálculemos los productos internos que necesitamos:

- $\left<(1,1,1,1), (1,1,0,0)\right> = 1+1+0+0=2$
- $\left<(1,1,0,0), (1,1,0,0)\right> = 1+1+0+0=2$

Entonces:

$$
\begin{aligned}
w_2&=(1,1,1,1)-(1,1,0,0)\\
&=\left(0,0,1,1\right)
\end{aligned}
$$

Ahora deberíamos hacer lo mismo para hallar $w_3$:

$$
w_3=(-1,0,2,1)-\frac{\left<(-1,0,2,1), (0,0,1,1)\right>}{\left<(0,0,1,1), (0,0,1,1)\right>}(0,0,1,1)-\frac{\left<(-1,0,2,1),(1,1,0,0) \right>}{\left<(1,1,0,0), (1,1,0,0)\right>}(1,1,0,0)
$$

Cálculemos los productos internos que necesitamos:

- $\left<(-1,0,2,1), (0,0,1,1)\right>=0+0+2+1=3$
- $\left<(0,0,1,1),(0,0,1,1) \right> = 0+0+1+1=2$
- $\left<(-1,0,2,1), (1,1,0,0)\right>=-1+0+0+0=-1$

Entonces:

$$
\begin{aligned}
w_3&=(-1,0,2,1)-\frac{3}{2}(0,0,1,1)-\frac{-1}{4}(1,1,0,0)\\
&=\left(-1,0,\frac{1}{2},-\frac{1}{2}\right)+\frac{1}{2}(1,1,0,0)\\
&=\left(-\frac{1}{2},\frac{1}{2},\frac{1}{2},-\frac{1}{2}\right)
\end{aligned}
$$

Ahora restaría normalizar los vectores, para lo que nos faltaría solo calcular la siguiente norma al cuadrado:

- $\left<\left(-\frac{1}{2},\frac{1}{2},\frac{1}{2},-\frac{1}{2}\right), \left(-\frac{1}{2},\frac{1}{2},\frac{1}{2},-\frac{1}{2}\right)\right>=\frac{1}{4}+\frac{1}{4}+\frac{1}{4}+\frac{1}{4}=1$

Considerando $[u_1,u_2,u_3]$ como el resultado al que queremos llegar, tenemos que:

- $u_1=\frac{w_1}{\|w_1\|}$
- $u_2=\frac{w_2}{\|w_2\|}$
- $u_3=w_3$ pues $w_3$ ya está normalizado (su norma es 1)

Usando lo obtenido hasta ahora entonces:

- $u_1=\frac{1}{\sqrt{2}}(1,1,0,0) = \left(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}},0,0\right)$
- $u_2=\frac{1}{\sqrt{2}}(0,0,1,1)=\left(0,0,\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}\right)$
- $u_3=\left(-\frac{1}{2},\frac{1}{2},\frac{1}{2},-\frac{1}{2}\right)$

Por lo que $\left[\left(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}},0,0\right),\left(0,0,\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}\right),\left(-\frac{1}{2},\frac{1}{2},\frac{1}{2},-\frac{1}{2}\right)\right]$ es el resultado que estabamos buscando.

### Parte 2

En esta parte, consideramos el producto interno habitual de $\mathbb{C}^3$, es decir, el defindo por:

$$
\left<v, w\right>=\sum_{i=1}^{3}v_i\overline{w_i}
$$

Considerando los vectores que ya tenemos, los describimos como:

- $v_1 = (1, i, 0)$
- $v_2 = (1, 1, 1)$

Queremos encontrar vectores $\{w_1,w_2\}$ tal que:

- $[w_1,w_2] = [v_1,v_2]$

Empezamos tomando $w_1=v_1=(1,i,0)$, a partir de esto definimos $w_2$ de la siguiente forma:

$$
w_2=v_2-\frac{\left<v_2, w_1\right>}{\left<w_1, w_1\right>}w_1
$$

Sustituyendo con los valores que conocemos:

$$
w_2=(1,1,1)-\frac{\left<(1,1,1), (1,i,0)\right>}{\left<(1,i,0), (1,i,0)\right>}(1,i,0)
$$

Cálculemos los productos internos que necesitamos:

- $\left<(1,1,1), (1,i,0) \right> = 1 + (-i) + 0 = 1-i$
- $\left<(1,i,0), (1,i,0)\right> = 1+ -i^2+0=2$

Entonces:

$$
\begin{aligned}
w_2&=(1,1,1)-\frac{1-i}{2}(1,i,0)\\
&=(1,1,1)-\left(\frac{1-i}{2},\frac{1+i}{2},0\right)\\
&=\left(\frac{1+i}{2},\frac{1-i}{2},1\right)
\end{aligned}
$$

Ahora restaría normalizar los vectores, para lo que nos faltaría solo calcular la siguiente norma al cuadrado:

- $\left<\left(\frac{1+i}{2},\frac{1-i}{2},1\right), \left(\frac{1+i}{2},\frac{1-i}{2},1\right)\right>=\frac{1}{2}+\frac{1}{2}+1=2$

Considerando $[u_1,u_2]$ como el resultado al que queremos llegar, tenemos que:

- $u_1=\frac{w_1}{\|w_1\|}$
- $u_2=\frac{w_2}{\|w_2\|}$

Usando lo obtenido hasta ahora entonces:

- $u_1=\frac{1}{\sqrt{2}}(1,i,0) = \left(\frac{1}{\sqrt{2}},\frac{i}{\sqrt{2}},0\right)$
- $u_2=\frac{1}{\sqrt{2}}(\frac{1+i}{2},\frac{1-i}{2},1)=(\frac{1+i}{2\sqrt{2}},\frac{1-i}{2\sqrt{2}},\frac{1}{\sqrt{2}})$

Por lo que $\left[\left(\frac{1}{\sqrt{2}},\frac{i}{\sqrt{2}},0\right),\left(\frac{1+i}{2\sqrt{2}},\frac{1-i}{2\sqrt{2}},\frac{1}{\sqrt{2}}\right)\right]$ es el resultado que estabamos buscando.