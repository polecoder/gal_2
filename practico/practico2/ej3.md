# Ejercicio 3

## Consigna

Se considera la matriz $A = \begin{pmatrix} 0 & 2 & 0 \\ 2 & 0 & 0 \\ 0 & 0 & 2 \end{pmatrix}$ y la transformación lineal $T: \mathbb{R}^3 \to \mathbb{R}^3$ tal que ${}_{\mathcal{B}}(T)_{\mathcal{B}} = A$, donde $\mathcal{B} = \{(1, 0, 0), (1, 1, 0), (1, 1, 1)\}$.

(a) Hallar los valores propios y los subespacios propios de $A$.

(b) Hallar los valores propios y los subespacios propios de $T$.

## Resolución (parte a)

Cómo ya tenemos la matriz, debemos empezar por el calculo del polinomio característico de $A$:

$$
\begin{align*}
&\Chi_A(\lambda) = det(A-\lambda\mathbb{I})\\
&\Chi_A(\lambda) = \begin{pmatrix}-\lambda&2&0\\2&-\lambda&0\\0&0&2-\lambda\end{pmatrix}\\
&\Chi_A(\lambda) = (2-\lambda)(\lambda^2-4)\\
\end{align*}
$$

A partir de esto, obtenemos que las raíces de $\Chi_A(\lambda)$ son $\lambda_1 = 2$, $\lambda_2 = -2$, observemos que $2$ es raíz doble. Hallemos los subespacios propios:

### Subespacio propio $\lambda_1 = 2$

Para $\lambda_1 = 2$, debemos resolver el sistema $(A-2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
-2&2&0&0\\
2&-2&0&0\\
0&0&0&0
\end{array}
\right)
$$

Como la primer fila es CL de la segunda, solo podemos decir que:

- $x = y$

Por lo tanto, el subespacio propio asociado a $\lambda_1 = 2$ es:

$$
S_2 = \{(\alpha,\alpha,\beta)\mid \alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,1,0), (0,0,1)\}
$$

### Subespacio propio $\lambda_2 = -2$

Para $\lambda_2 = -2$, debemos resolver el sistema $(A+2\mathbb{I})v = 0$:

$$
\left(
\begin{array}{ccc|c}
2&2&0&0\\
2&2&0&0\\
0&0&4&0
\end{array}
\right)
$$

Como la primer fila es CL de la segunda,  podemos decir que:

- $x = -y$
- $z = 0$

Por lo tanto, el subespacio propio asociado a $\lambda_2 = -2$ es:

$$
S_{-2} = \{(-\alpha,\alpha,0)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(1,-1,0)\}
$$

**Observación**: para esta parte queremos hallar los vectores $v\in\mathbb{R}$ que son propios, para este caso donde aún no necesitamos considerar bases específicas, consideramos la base canónica y nos ahorramos el paso de transformar las coordenadas.

## Resolución (parte b)

En esta parte va a cambiar un pequeño aspecto de la resolución. Ahora la matriz $A$ es la matriz de la transformación lineal $T$ en la base $\mathcal{B}$. Por lo tanto, para hallar los valores propios y subespacios propios de $T$, debemos trabajar con las coordenadas de los vectores en la base $\mathcal{B}$.

Entonces, los valores propios, serán los mismos, ya que la matriz es la misma. Lo que va a cambiar es la forma de trabajar con los subespacios propios. Veamos:

### Subespacio propio $\lambda_1 = 2$

Para $\lambda_1 = 2$, debemos resolver el sistema $({}_{\mathcal{B}}(T)_{\mathcal{B}}-2\mathbb{I})coord_{\mathcal{B}}(v) = 0$, ya lo hicimos en la parte anterior, sabemos que el sistema se cumple, si:

$coord_{\mathcal{B}}(v) = (x,x,z)$ con $x,z\in\mathbb{R}$

A partir de esto, podemos decir que:

$v = x(1,0,0) + x(1,1,0) + z(1,1,1) = (2x+z,x+z,z)$

Con esto si, podemos definir el subespacio propio para $\lambda_1 = 2$:

$$
S_2 = \{(2\alpha+\beta,\alpha+\beta,\beta)\mid \alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(2,1,0), (1,1,1)\}
$$

### Subespacio propio $\lambda_2 = -2$

Para $\lambda_2 = -2$, debemos resolver el sistema $({}_{\mathcal{B}}(T)_{\mathcal{B}}+2\mathbb{I})coord_{\mathcal{B}}(v) = 0$, ya lo hicimos en la parte anterior, sabemos que el sistema se cumple, si:

$coord_{\mathcal{B}}(v) = (-x,x,0)$ con $x\in\mathbb{R}$

A partir de esto, podemos decir que:

$v = -x(1,0,0) + x(1,1,0) = (0,x,0)$

Con esto si, podemos definir el subespacio propio para $\lambda_2 = -2$:

$$
S_{-2} = \{(0,\alpha,0)\mid \alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{(0,1,0)\}
$$

## Conclusión

Es muy importante tener en cuenta las bases en las que estamos trabajando. Si la base es canónica somos todos felices, pero cuando no tenemos la base canónica tenemos que dar ese paso extra para definir los vectores propios.