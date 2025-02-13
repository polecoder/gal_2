# Ejercicio 6

## Consigna

Sean $\mathcal{A}=\{1,t+1,(t+1)^2\}$ y $\mathcal{B}=\{(1,1,0),(1,2,3),(3,2,1)\}$ bases de $\mathbb{R}_2[t]$ y $\mathbb{R}^3$ respectivamente. Consideramos $T:\mathbb{R}_2[t]\to\mathbb{R}^3$ lineal tal que: 

$${}_{\mathcal{B}}(T)_{\mathcal{A}}=\begin{pmatrix}2&1&1\\2&3&2\\1&1&2\end{pmatrix}$$
 
Dado $q_0(t)=t^2+t-1$, $\forall t\in\mathbb{R}$, hallar $T(q_0)$.

## Resolución

La idea es exactamente la misma que el ejercicio 5, primero quiero hallar las coordenadas en la base de partida de $q_0$:

$$
\begin{align*}
coord_{\mathcal{A}}(t^2+t-1) &= c_1(1) + c_2(t+1) + c_3(t+1)^2\\
&= c_1(1) + c_2(t+1) + c_3(t^2+2t+1)
\end{align*}
$$

Esto plantea el siguiente sistema:

$$
\begin{array}{ccc|c}
1&1&1&-1\\
0&1&2&1\\
0&0&1&1\\
\end{array}
$$

Entonces:

- $c_3=1$
- $c_2=1-2c_3=-1$
- $c_1=-1$

$$coord_{\mathcal{A}}(t^2+t-1) = (-1,-1,1)$$

Utilicemos la propiedad:

$$
coord_{\mathcal{B}}(T(t^2+t-1)) =
\begin{pmatrix}
2&1&1\\
2&3&2\\
1&1&2
\end{pmatrix}\cdot
\begin{pmatrix}
-1\\
-1\\
1
\end{pmatrix}
$$

Entonces:

$$
coord_{\mathcal{B}}(T(t^2+t-1)) = (-2,-3,0)
$$

Entonces resta "eliminar" las coordenadas, es decir:

$$
T(t^2+t-1) = -2\cdot(1,1,0)-3\cdot(1,2,3) = (-5,-8,-9)
$$

Entonces la respuesta es:

$$T(t^2+t-1) = (-5,-8,-9)$$