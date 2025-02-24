# Ejercicio 1

## Consigna

Dadas las siguientes transformaciones lineales:

1. $T: \mathbb{K}^2 \to \mathbb{K}^2$, $T(x, y) = (-2x - 7y, x + 2y)$
2. $T: \mathbb{K}^3 \to \mathbb{K}^3$, $T(x, y, z) = (x, z, y)$
3. $T: \mathbb{K}^3 \to \mathbb{K}^3$, $T(x, y, z) = (x, z, -y)$

(a) Hallar valores propios y bases de los subespacios propios de $T$, si $\mathbb{K} = \mathbb{R}$.

(b) Hallar valores propios y bases de los subespacios propios de $T$, si $\mathbb{K} = \mathbb{C}$.

## Resolución (parte 1)

Para hallar los vectores y valores propios de $T$, necesitaremos hallar una matriz asociada a dicha transformación, para la cual usaremos las bases canónicas.

Sea $\mathcal{E} = \{(1,0), (0,1)\}$, hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(1,0) = (-2,1)$
- $coord_{\mathcal{E}}(0,1) = (-7,2)$

Entonces:

$${}_{\mathcal{E}}(T)_{\mathcal{E}}=\begin{pmatrix}-2&-7\\1&2\end{pmatrix}$$

**Observación**: "Deshago" la función $coord$ porque la base es la canónica.

Con esto puedo hallar el polínomio característico:

$$
\begin{align*}
\Chi_T(\lambda) &= det({}_{\mathcal{E}}(T)_{\mathcal{E}}-\lambda\mathbb{I})\\
&= \begin{vmatrix}-2-\lambda&-7\\1&2-\lambda\end{vmatrix}
\end{align*}
$$

Entonces el polínomio característico es:

$$\Chi_T(\lambda) = (-2-\lambda)(2-\lambda) +7 = \lambda^2-4+7 = \lambda^2 + 3$$

Si quisiera hallar las raíces:

$$
\begin{align*}
&\Chi_T(\lambda) = 0\\
&\lambda^2 + 3 = 0\\
&\lambda^2 = -3\\
&\lambda = \pm \sqrt{-3}\\
&\lambda = \pm \sqrt{3}\cdot i
\end{align*}
$$

Por lo que si $\mathbb{K} = \mathbb{R}$ entonces no hay valores propios, así que trabajaremos con $\mathbb{K} = \mathbb{C}$, donde tenemos:

- $\lambda_1 = \sqrt{3}\cdot i$
- $\lambda_2 = -\sqrt{3}\cdot i$

Ahora tenemos que encontrar soluciones al sistema:

$$({}_{\mathcal{E}}(T)_{\mathcal{E}}-\lambda\mathbb{I})\cdot\begin{pmatrix}x\\y\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix}$$

Esto equivale a resolver el siguiente sistema, para $\lambda_1$ y $\lambda_2$:

$$
\left(
\begin{array}{cc|c}
-2-\lambda&-7&0\\
1&2-\lambda&0
\end{array}
\right)
$$

### Subespacio $\lambda_1 = \sqrt{3}\cdot i$

El sistema que queremos resolver en este caso es:

$$
\left(
\begin{array}{cc|c}
-2-\sqrt{3}\cdot i&-7&0\\
1&2-\sqrt{3}\cdot i&0
\end{array}
\right)\Rightarrow
\left(
\begin{array}{cc|c}
-2-\sqrt{3}\cdot i&-7&0\\
2+\sqrt{3}\cdot i&7&0
\end{array}
\right)
$$

**Observación:** Multiplicamos la fila dos por $(2+\sqrt{3}\cdot i)$, es muy importante tener en cuenta el conjugado para cuando usamos el cuerpo de los complejos.

Veamos las cuentas auxiliares que hicimos:

$$
(2+\sqrt{3}\cdot i)((2-\sqrt{3}\cdot i)) = 4 - \sqrt{3}^2\cdot i^2 = 4+3 = 7
$$

Ahora, siguiendo con el sistema, operemos sobre la primer fila (ya que la segunda es CL de la primera):

$$
\begin{align*}
&(2-\sqrt{3}\cdot i)x -7y = 0\\
&y = \frac{(2-\sqrt{3}\cdot i)x}{-7}
\end{align*}
$$

Entonces, si llamamos $v$ al vector propio que buscamos, podemos decir que: $coord_{\mathcal{E}}(v) = (x,\frac{(2-\sqrt{3}\cdot i)x}{-7})$

Pero como estamos trabajando con la base canónica, podemos decir que:

$v = (x,\frac{(2-\sqrt{3}\cdot i)x}{-7})$ para algún $x\in\mathbb{C}$

Finalizando, podemos decir que:

$$
S_{\sqrt{3}\cdot i} := \{(\alpha,\frac{(2-\sqrt{3}\cdot i)\alpha}{-7})\mid\alpha\in\mathbb{C} \}\\
$$

Y la base de dicho subespacio es:

$$
\{\left(1, \frac{(2-\sqrt{3}\cdot i)}{-7}\right)\}
$$

### Subespacio $\lambda_1 = -\sqrt{3}\cdot i$

El sistema que queremos resolver en este caso es:

$$
\left(
\begin{array}{cc|c}
-2+\sqrt{3}\cdot i&-7&0\\
1&2+\sqrt{3}\cdot i&0
\end{array}
\right)\Rightarrow
\left(
\begin{array}{cc|c}
-2+\sqrt{3}\cdot i&-7&0\\
2-\sqrt{3}\cdot i&7&0
\end{array}
\right)
$$

En este caso la operación es la misma que la de arriba, despejando podemos decir que:

$$
y=\frac{(-2+\sqrt{3}\cdot i)x}{-7}
$$

Trabajando con el mismo razonamiento que en el caso anterior, concluimos que:

$$
S_{-\sqrt{3}\cdot i} := \{(\alpha,\frac{(2+\sqrt{3}\cdot i)\alpha}{-7})\mid\alpha\in\mathbb{C} \}\\
$$

Y la base de dicho subespacio es:

$$
\{\left(1, \frac{(2+\sqrt{3}\cdot i)}{-7}\right)\}
$$


## Resolución (parte 2)

Sea $T: \mathbb{K}^3 \to \mathbb{K}^3$, $T(x, y, z) = (x, z, y)$, considerando la base canónica $\mathcal{E} = \{(1,0,0),(0,1,0),(0,0,1)\}$, hallemos ${}_{\mathcal{E}}(T)_{\mathcal{E}}$:

- $coord_{\mathcal{E}}(T(1,0,0)) = (1,0,0)$
- $coord_{\mathcal{E}}(T(0,1,0)) = (0,0,1)$
- $coord_{\mathcal{E}}(T(0,0,1)) = (0,1,0)$

Como estamos usando la base canónica, podemos decir que:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}1&0&0\\0&0&1\\0&1&0\end{pmatrix}
$$

Ahora hallemos el polinomio característico:

$$
\begin{align*}
&\Chi_T(\lambda) = det({}_{\mathcal{E}}(T)_{\mathcal{E}}-\lambda\mathbb{I})\\
&\Chi_T(\lambda) = \begin{vmatrix}1-\lambda&0&0\\0&-\lambda&1\\0&1&-\lambda\end{vmatrix}\\
&\Chi_T(\lambda) = (1-\lambda)(\lambda^2 -1)
\end{align*}
$$

Podemos concluir que las raíces características son:

- $\lambda_1 = 1$
- $\lambda_2 = -1$

Observemos que $\lambda_1 = 1$ aparece dos veces, una vez en $(1-\lambda)$ y la otra en $(\lambda^2-1)$.

Cómo todas las raíces del polinomio característico son reales, podemos trabajar en dicho cuerpo.

Ahora tenemos que encontrar soluciones al sistema:

$$({}_{\mathcal{E}}(T)_{\mathcal{E}}-\lambda\mathbb{I})\cdot\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}0\\0\\0\end{pmatrix}$$

Esto equivale a resolver el siguiente sistema, para $\lambda_1$ y $\lambda_2$:

$$
\left(
\begin{array}{ccc|c}
1-\lambda&0&0&0\\
0&-\lambda&1&0\\
0&1&-\lambda&0
\end{array}
\right)
$$

### Subespacio $\lambda_1 = 1$

El sistema para este valor propio es:

$$
\left(
\begin{array}{ccc|c}
0&0&0&0\\
0&-1&1&0\\
0&1&-1&0
\end{array}
\right)
$$

Se observa que las 3 filas son combinaciones lineales la una de la otra, podemos concluir que:

- $x\in\mathbb{R}$
- $z = y$

Entonces, si llamamos $v$ al vector propio que buscamos, podemos decir que: $coord_{\mathcal{E}}(v) = (x,y,y)$

Pero como estamos trabajando con la base canónica, podemos decir que:

$v = (x,y,y)$ para algunos $x,y\in\mathbb{R}$

Finalizando, podemos decir que:

$$
S_1 := \{(\alpha,\beta,\beta)\mid\alpha,\beta\in\mathbb{R} \}\\
$$

Y la base de dicho subespacio es:

$$
\{(1,0,0),(0,1,1)\}
$$

### Subespacio $\lambda_1 = -1$

El sistema para este valor propio es:

$$
\left(
\begin{array}{ccc|c}
2&0&0&0\\
0&1&1&0\\
0&1&1&0
\end{array}
\right)
$$

Obtenemos que:

- $x = 0$
- $z = -y$

Por el mismo razonamiento del caso anterior:

$$
S_{-1} := \{(0,\alpha,-\alpha)\mid\alpha\in\mathbb{R} \}\\
$$

Y la base de dicho subespacio es:

$$
\{(0,1,-1)\}
$$

## Resolución (parte 3)

Se toma como análoga a las 2 anteriores