# Ejercicio 2

## Consigna

Sea $T: \mathbb{R}^3 \to \mathbb{R}^2$ tal que $T(x,y,z) = (3x+2y-4z,x-5y+3z)$.
Hallar ${}_{\mathcal{A}}(T)_{\mathcal{B}}$ en los siguientes casos:

1. $\mathcal{B}$ y $\mathcal{A}$ son las bases canónicas de $\mathbb{R}^3$ y $\mathbb{R}^2$ respectivamente
2. $\mathcal{B} = \{(1,1,1),(1,1,0),(1,0,0)\}$ y $\mathcal{A}$ es la base canónica de $\mathbb{R}^2$
3. $\mathcal{B} = \{(1,1,1),(1,1,0),(1,0,0)\}$ y $\mathcal{A} = \{(1,3),(2,5)\}$

## Resolución (parte 1)

- $\mathcal{B} = \{(1,0,0),(0,1,0),(0,0,1)\}$
- $\mathcal{A} = \{(1,0),(0,1)\}$

Ahora hallemos los transformados de $\mathcal{B}$:

- $T(1,0,0) = (3,1)$
- $T(0,1,0) = (2,5)$
- $T(0,0,1) = (-4,3)$

Observemos que $coord_{\mathcal{A}}(v) = v$ para todo $v$ si $\mathcal{A}$ es canónica. Esto es observable trivialmente, por lo que en este ejemplo nos estaríamos salteando el paso de obtener las coordenadas de los transformados de $\mathcal{B}$.

En conclusión:

$$
{}_{\mathcal{A}}(T)_{\mathcal{B}} =
\begin{pmatrix}
3 & 2 & -4 \\
1 & 5 & 3
\end{pmatrix}
$$

## Resolución (parte 2)

- $\mathcal{B} = \{(1,1,1),(1,1,0),(1,0,0)\}$
- $\mathcal{A} = \{(1,0),(0,1)\}$

Ahora hallemos los transformados de $\mathcal{B}$:

- $T(1,1,1) = (1,-1)$
- $T(1,1,0) = (5,-4)$
- $T(1,0,0) = (3,1)$

Tenemos la misma situación que el ejercicio anterior, ya que la base de llegada que tenemos es canónica, entonces:

$$
{}_{\mathcal{A}}(T)_{\mathcal{B}} =
\begin{pmatrix}
1 & 5 & 3 \\
1 & -4 & 1
\end{pmatrix}
$$

## Resolución (parte 3)

- $\mathcal{B} = \{(1,1,1),(1,1,0),(1,0,0)\}$
- $\mathcal{A} = \{(1,3),(2,5)\}$

La primer parte ya la hicimos en el anterior ejercicio:

- $T(1,1,1) = (1,-1)$
- $T(1,1,0) = (5,-4)$
- $T(1,0,0) = (3,1)$

En cambio ahora si tenemos que hallar las coordenadas, porque $\mathcal{A}$ ya no es canónica:

- $coord_{\mathcal{A}}(T(1,1,1)) = coord_{\mathcal{A}}(1,-1)$

Básicamente lo que tengo que hallar es los valores de $x_1, x_2$ que cumplan lo siguiente:

$$x_1(1,3)+x_2(2,5) = (1,-1)$$

Esto está dado por el siguiente sistema:

$$
\begin{array}{cc|c}
1 & 2 & 1 \\
3 & 5 & -1
\end{array}\Rightarrow
\begin{array}{cc|c}
1 & 2 & 1 \\
0 & -1 & -4
\end{array}
$$

De esto obtengo que $x_2 = 4$, y sustituyendo en la primer ecuación obtengo que $x_1 = -7$.

Ahora tengo que hacer esto para los demás vectores transformados de $\mathcal{B}$:

- $coord_{\mathcal{A}}(T(1,1,0)) = coord_{\mathcal{A}}(5,-4) = (-33,19)$
- $coord_{\mathcal{A}}(T(1,0,0)) = coord_{\mathcal{A}}(3,1) = (-13,8)$

En conclusión:

$$
{}_{\mathcal{A}}(T)_{\mathcal{B}} =
\begin{pmatrix}
-7 & -33 & -13 \\
4 & 19 & 8
\end{pmatrix}
$$

## Observación

Siempre verificar las cuentas, preferentemente escribiendo el sistema para cada coordenada que se tiene que calcular, porque ahí nacen los errores
