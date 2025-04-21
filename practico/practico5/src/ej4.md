# Ejercicio 4

## Consigna

Sea $\langle \cdot, \cdot \rangle$ un producto interno cualquiera en $\mathbb{R}^n$. Probar que:
$$
\langle \vec{X}, \vec{Y} \rangle = \sum_{i=1}^n\sum_{j=1}^n a_{ij}x_i y_j = \vec{X}^t A \vec{Y},
$$  
donde $A = (a_{ij})_n,\vec{X}=(x_1,x_2,\ldots,x_n),\vec{Y}=(y_1,y_2,\ldots,y_n)$.

*Qué producto interno se define si $A = I_n$?*

## Resolución

Para probar esto, consideremos la base canónica $\mathcal{E} = \{e_1,e_2,\ldots,e_n\}$ de $\mathbb{R}^n$. Con esto podemos escribir los vectores $\vec{X},\vec{Y}$ de la siguiente forma:

- $\vec{X} = x_1e_1 + x_2e_2 + \ldots + x_ne_n = \sum_{i=1}^nx_ie_i$
- $\vec{Y} = y_1e_1 + y_2e_2 + \ldots + y_ne_n = \sum_{i=1}^ny_ie_i$

Con esto podemos expresar el producto interno de la siguiente forma:

$$
\begin{aligned}
\left<X, Y\right> &= \left<\sum_{i=1}^nx_ie_i, \sum_{i=1}^ny_ie_i\right>\\
&= \sum_{i,j=1}^nx_iy_j\left<e_i, e_j\right>
\end{aligned}
$$

Por lo tanto, considerando $a_{ij} = \left<e_i, e_j\right>\quad\forall i,j\in\{1,\ldots,n\}$, probamos la primer parte de la igualdad.

Para la segunda parte de la igualdad, consideremos la matriz $A=(a_{ij})$ donde $a_{ij} = \left<e_i, e_j\right>$. Entonces tenemos que:

$$
X^tAY = (x_1,x_2,\ldots,x_n)A\begin{pmatrix}
y_1\\
y_2\\
\vdots\\
y_n
\end{pmatrix}
$$

Observemos que:

- $X^tA$ es una matriz fila, y
- $(X^tA)Y$ es el producto entre una matriz fila y una matriz columna, por lo que es una suma de números reales.

Consideremos el elemento en la posición $j$ en el producto $X^tA$:

- $(X^tA)_j = \sum_{i=0}^nx_ia_{ij}$

Con esto podemos describir la matriz fila de esta forma:

$$
X^tA = \left(\sum_{i=0}^nx_ia_{i1}, \sum_{i=0}^nx_ia_{i2},\ldots,\sum_{i=0}^nx_ia_{in}\right)
$$

Con esto podemos definir el resultado de multiplicar esta matriz fila por la matriz columna que nos queda:

$$
X^tAY = \sum_{i=0}^{n}\sum_{j=0}^{n}x_ia_{ij}y_i
$$

Que es lo que queríamos probar.

*Qué producto interno se define si $A = I_n$?*

Se observa que el producto interno definido cuando $A$ es la matriz identidad es el producto interno estándar, es decir:

$$
\left<v, w\right> = \sum_{i=1}^{n}x_iy_i
$$

Observemos que "iteramos" una sola vez ahora, porque todos los elementos que no estén multiplicados por la diagonal se van. También aquellos que se mantienen están multiplicados por 1, porque $A$ es la matriz identidad.