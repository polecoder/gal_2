# Ejercicio 1

## Consigna

Probar que $\langle \cdot, \cdot \rangle: V \times V \rightarrow \mathbb{K}$ es un producto interno en $V$ para los siguientes casos:  

1. **Espacio euclidiano**:  
   $V = \mathbb{R}^3$, $\mathbb{K} = \mathbb{R}$,  
   $\langle (x, y, z), (x', y', z') \rangle = xx' + 2yy' + 3zz'$.

2. **Matrices reales**:  
   $V = \mathcal{M}_n(\mathbb{R})$, $\mathbb{K} = \mathbb{R}$,  
   $\langle A, B \rangle = \text{tr}(AB^t)$.  
   ¿Cómo ajustar este producto interno para matrices complejas?

3. **Espacio complejo**:  
   $V = \mathbb{C}^2$, $\mathbb{K} = \mathbb{C}$,  
   $\langle X, Y \rangle = X^t A \overline{Y}$ con $A = \begin{pmatrix} 1 & i \\ -i & 2 \end{pmatrix}$.

## Resolución

Para probar que una función es un producto interno, necesitamos que cumpla con lo siguiente:

1. $\left<u+v, w\right> = \left<u,w\right> + \left<v,w\right>\quad\forall u,v,w\in V$
2. $\left<\alpha u, v\right> = \alpha\left<u, v\right>\quad \forall u,v\in V, \forall\alpha\in\mathbb{K}$
3. $\left< u,v \right> = \overline{\left<v,u\right>}\quad\forall u,v\in V$
4. $\left< v,v\right>\in\mathbb{R}$ y $\left<v,v\right> \geq 0 \quad\forall v\in V$ y además $\left<v,v\right> = 0 \iff v = \vec{0}$

Basaremos la prueba en verificar estos pasos.

### Parte 1

$V = \mathbb{R}^3$, $\mathbb{K} = \mathbb{R}$,  
$\langle (x, y, z), (x', y', z') \rangle = xx' + 2yy' + 3zz'$.  

Consideremos 3 vectores genéricos de $V$:
- $v_1=(x_1,y_1,z_1)$
- $v_2=(x_2,y_2,z_2)$
- $v_3=(x_3,y_3,z_3)$

1. Queremos probar que $\left<v_1+v_2, v_3\right> = \left<v_1, v_3\right> + \left<v_2, v_3\right>$

    Por un lado $(i)$:

    $$
    \begin{aligned}
    &\left<v_1+v_2, v_3\right> = \left<(x_1+x_2,y_1+y_2,z_1+z_2), (x_3,y_3,z_3)\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    &(x_1+x_2)x_3 + 2(y_1+y_2)y_3 + 3(z_1+z_2)z_3
    \end{aligned}
    $$

    Por otra parte $(ii)$:

    $$
    \begin{aligned}
    &\left<v_1, v_3\right> + \left<v_2, v_3\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    &(x_1x_3 + 2y_1y_3 +3z_1z_3)+(x_2x_3 + 2y_2y_3 + 3z_2z_3)\\
    &=\scriptstyle{(\text{operatoria})} \\
    &x_3(x_1+x_2) + y_3(2y_1+2y_2)+ z_3(3z_1+3z_2)\\
    &=\scriptstyle{(\text{operatoria})} \\
    &(x_1+x_2)x_3 + 2(y_1+y_2)y_3 + 3(z_1+z_2)z_3
    \end{aligned}
    $$

    Como $(i)$ y $(ii)$ son iguales, probamos esta parte.

2. Queremos probar que $\left<\alpha v_1, v_2\right> = \alpha \left<v_1, v_2\right>$:

    $$
    \begin{aligned}
    &\left<\alpha v_1, v_2\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    &\alpha x_1x_2 + 2\alpha y_1y_2 + 3\alpha z_1z_2\\
    &= \scriptstyle{(\text{operatoria})} \\
    &\alpha (x_1x_2+2y_1y_2+3z_1z_2)\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    &\alpha \left<v_1, v_2\right>
    \end{aligned}
    $$

3. Queremos probar $\left< v_1,v_2 \right> = \overline{\left<v_2,v_1\right>}$:

    $$
    \begin{aligned}
    &\left<v_1, v_2\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    &\ x_1x_2 + 2y_1y_2 + 3z_1z_2\\
    &= \scriptstyle{(\text{operatoria, recordar que trabajamos en espacio Real})} \\
    &\overline{\left<v_2,v_1\right>}
    \end{aligned}
    $$

4. Queremos probar que $\left< v,v\right>\in\mathbb{R}$ y $\left<v,v\right> \geq 0 \quad\forall v\in V$ y además $\left<v,v\right> = 0 \iff v = \vec{0}$

    $$
    \begin{aligned}
    &\left<v, v\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})} \\
    & x^2 + 2y^2 + 3z^2\\
    &\geq \scriptstyle{(\text{operatoria})} \\
    &0
    \end{aligned}
    $$

    También se observa que la única forma para que sea 0 es que $v=\vec{0}$

### Parte 2

$V = \mathcal{M}_n(\mathbb{R})$, $\mathbb{K} = \mathbb{R}$,
$\left<A, B\right> = tr(AB^t)$.

Consideremos 3 vectores genéricos de $V$:
- $A,B,C$

1. Queremos probar que $\left<A+B, C\right> = \left<A, C\right> + \left<B, C\right>$

    $$
    \begin{aligned}
    &\left<A+B, C\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &tr((A+B)C^t)\\
    &= \scriptstyle{(\text{distributividad de producto de matrices})}\\
    &tr(AC^t + BC^t)\\
    &= \scriptstyle{(\text{propiedad de la traza})}\\
    &tr(AC^t) + tr(BC^t)\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &\left<A, C\right> + \left<B, C\right>
    \end{aligned}
    $$

2. Queremos probar que $\left<\alpha A, B\right> = \alpha \left<A, B\right>$:

    $$
    \begin{aligned}
    &\left<\alpha A, B\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &tr(\alpha AB^t)\\
    &= \scriptstyle{(\text{propiedad del producto de matrices})}\\
    &tr(\alpha (AB^t))\\
    &= \scriptstyle{(\text{propiedad de la traza})}\\
    &\alpha tr(AB^t)\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &\alpha \left<A, B\right>
    \end{aligned}
    $$

3. Queremos probar $\left<A,B\right> = \overline{\left<B,A\right>}$:

    $$
    \begin{aligned}
    &\left<A,B\right>\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &tr(AB^t)\\
    &= \scriptstyle{(\text{propiedad de la traza})}\\
    &tr(B^tA)\\
    &= \scriptstyle{(\text{propiedad de la traza})}\\
    &tr((B^tA)^t)\\
    &= \scriptstyle{(\text{operatoria})}\\
    &tr(BA^t)\\
    &= \scriptstyle{(\text{definición del producto interno dado})}\\
    &\left<B, A\right>
    \end{aligned}
    $$

    Y como estamos trabajando con matrices reales: $\left<B, A\right> = \overline{\left<B, A\right>}$. Observemos que esta es la propiedad que de alguna forma nos restringe si trabajamos con matrices complejas. El producto interno que se adapta a matrices complejas es $\left<A, B\right> = tr(A\overline{B^t})$. No lo voy a demostrar porque implica algunos detalles de como definimos una matriz traspuesta y conjugada (matriz hermítica, definida con el símbolo *).

4. Queremos probar que $\left< A,A\right>\in\mathbb{R}$ y $\left<A,A\right> \geq 0 \quad\forall A\in \mathcal{M}_n(\mathbb{R})$ y además $\left<A,A\right> = 0 \iff A = \vec{0}$.

    Lo primero es que $\left<A, A\right>$ es claramente un número real, ya que es la suma de los elementos de la diagonal de una matriz de números reales.
    Lo segundo también es trivial, porque tenemos que los elementos que voy a sumar son:
    - Fila 1 $\times$ Fila 1
    - Fila 2 $\times$ Fila 2
    - Fila 3 $\times$ Fila 3
    - $\vdots$
    - Fila $n$ $\times$ Fila $n$
    Si quiero que el resultado sea 0, entonces necesitamos que todas las filas sean compuestas por ceros.