# Ejercicio 2

## Consigna

Hallar los valores propios y bases de los subespacios propios de la transformación lineal $T: M_2(\mathbb{R}) \to M_2(\mathbb{R})$ tal que:

$$
T\begin{pmatrix}a&b\\c&d\end{pmatrix} = \begin{pmatrix} 
4a+b+d & 2a+3b+d \\ 
-2a+b+2c-3d & 2a-b+5d \end{pmatrix}
$$

## Resolución

Consideremos la base canónica:

$$
\mathcal{E} = \{\begin{pmatrix}1&0\\0&0\end{pmatrix}, \begin{pmatrix}0&1\\0&0\end{pmatrix}, \begin{pmatrix}0&0\\1&0\end{pmatrix}, \begin{pmatrix}0&0\\0&1\end{pmatrix}\}
$$

Hallemos los transformados de los vectores de la base $\mathcal{E}$:

- $T\begin{pmatrix}1&0\\0&0\end{pmatrix}= \begin{pmatrix}4&2\\-2&2\end{pmatrix}$
- $T\begin{pmatrix}0&1\\0&0\end{pmatrix}= \begin{pmatrix}1&3\\1&-1\end{pmatrix}$
- $T\begin{pmatrix}0&0\\1&0\end{pmatrix}= \begin{pmatrix}0&0\\2&0\end{pmatrix}$
- $T\begin{pmatrix}0&0\\0&1\end{pmatrix}= \begin{pmatrix}1&1\\-3&5\end{pmatrix}$

Ahora las coordenadas de dichos vectores transformados sería casi equivalente (porque la base es canónica):

- $coord_{\mathcal{E}}(T\begin{pmatrix}1&0\\0&0\end{pmatrix}) = (4,2-2,2)$
- $coord_{\mathcal{E}}(T\begin{pmatrix}0&1\\0&0\end{pmatrix}) = (1,3,1,-1)$
- $coord_{\mathcal{E}}(T\begin{pmatrix}0&0\\1&0\end{pmatrix}) = (0,0,2,0)$
- $coord_{\mathcal{E}}(T\begin{pmatrix}0&0\\0&1\end{pmatrix}) = (1,1,-3,5)$

**Observación:** lo que cambia es la representación, los números son los mismos, porque la base es canónica.

Entonces:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \begin{pmatrix}4&1&0&1\\2&3&0&1\\-2&1&2&-3\\2&-1&0&5\end{pmatrix}
$$

Quiero hallar el polinomio característico, para esto, veamos el siguiente recordatorio:

### Recordatorio (desarrollo de un determinante por una fila)

Sea $A\in\mathcal{M}_{n\times n}(\mathbb{R})$ una matriz $(a_{i,j})$. Podemos desarrollar el determinante de $A$ por la fila $i$ de la siguiente manera:

$$
det(A) = \sum_{j=1}^{n}(-1)^{i+j}a_{i,j}\cdot det(D_{i,j})
$$

Donde $D_{i,j}$ es la matriz obtenida de $A$ eliminando la fila $i$ y la columna $j$.

### Continuación

Utilizando el recordatorio, hallemos el polinomio característico:

$$
\begin{align*}
&\Chi_T(\lambda) = det({}_{\mathcal{E}}(T)_{\mathcal{E}}-\lambda\mathbb{I})\\
&\Chi_T(\lambda) = \begin{vmatrix}4-\lambda&1&0&1\\2&3-\lambda&0&1\\-2&1&2-\lambda&-3\\2&-1&0&5-\lambda\end{vmatrix}\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\begin{vmatrix}4-\lambda&1&1\\2&3-\lambda&1\\2&-1&5-\lambda\end{vmatrix}\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[
    \begin{align*}
    &\left((-1)^{1+1}(4-\lambda)\cdot\begin{vmatrix}3-\lambda&1\\-1&5-\lambda\end{vmatrix}\right)+\\
    &\left((-1)^{1+2}\cdot 1\cdot\begin{vmatrix}2&1\\2&5-\lambda\end{vmatrix}\right)+\\
    &\left((-1)^{1+3}\cdot 1\cdot\begin{vmatrix}2&3-\lambda\\2&-1\end{vmatrix}\right)
    \end{align*}
\right]\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[
    \begin{align*}
    &((4-\lambda)\cdot((3-\lambda)(5-\lambda)+1))+\\
    &(-1\cdot(10-2\lambda-2))+\\
    &(-2-6-2\lambda))
    \end{align*}
\right]\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[
    \begin{align*}
    &((4-\lambda)\cdot(\lambda^2-8\lambda+16)+\\
    &(2\lambda-8)+\\
    &(2\lambda-8)
    \end{align*}
\right]\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[ ((4-\lambda)\cdot(\lambda^2-8\lambda+16))+4\lambda-16\right]\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[ (4\lambda^2-32\lambda+64 -\lambda^3+8\lambda^2-16\lambda)+4\lambda-16\right]\\
&\Chi_T(\lambda) = (2-\lambda)\cdot\left[-\lambda^3+12\lambda^2-44\lambda+48\right]
\end{align*}
$$

Ahora, debemos factorizar el polinomio de grado 3 para encontrar sus raíces, para esto usamos el siguiente recordatorio:

### Recordatorio (teorema de raíces racionales)

Si un polinomio tiene raíces racionales, estas son de la forma $\frac{p}{q}$, donde $p$ es un divisor del término independiente y $q$ es un divisor del coeficiente del término de mayor grado.

### Continuación

Ahora que conocemos la forma de las raíces, podemos concluir que las raíces del polinomio de tercer grado anterior están incluidas en la lista: $\{\pm 1,\pm 2,\pm 4,\pm 6,\pm 8,\pm 12,\pm 16, \pm 24, \pm 48\}$

Probemos con $2$:

$$
-2^3+12\cdot 2^2-44\cdot 2+48 = -8+48-88+48 = 0
$$

Entonces $2$ es raíz de dicho polinomio, por lo que lo puedo factorizar usando Ruffini:

$$
\begin{array}{r|rrrr}
& \lambda^3 & \lambda^2 &\lambda^1 &1\\
\hline
& -1 & 12 & -44 & 48\\
\hline
2 & \downarrow & -2 & 20 & -48\\
\hline
& -1 & 10 & -24 & 0
\end{array}
$$

Por lo tanto, puedo expresar el polinomio de tercer grado como:

$$
-\lambda^3+12\lambda^2-44\lambda+48 = (\lambda - 2)(-\lambda^2+10\lambda-24)
$$

Entonces ahora hallemos las raíces del polinomio de segundo grado usando Bhaskara:

$$
\begin{align*}
&\lambda = \frac{-10\pm\sqrt{10^2-4\cdot(-1)\cdot(-24)}}{2}\\
&\lambda = \frac{-10\pm\sqrt{100-96}}{-2}\\
&\lambda = \frac{-10\pm\sqrt{4}}{-2}\\
&\lambda = \frac{-10\pm 2}{-2}\\
&\lambda_1 = \frac{-8}{-2};\quad \lambda_2 = \frac{-12}{-2}\\
&\lambda_2 = 4;\quad \lambda_3 = 6
\end{align*}
$$

Por lo tanto, las raíces del polinomio característico son $\lambda_1 = 2$, $\lambda_2 = 4$, $\lambda_3 = 6$.

**Observación:** En este caso hallamos el $2$ de dos formas diferentes, $2$ es raíz doble del polinomio característico.

Ahora hallemos los subespacios propios asociados a cada valor propio, para lo que debemos resolver el siguiente sistema:

$$
\left(
\begin{array}{cccc|c}
4-\lambda&1&0&1&0\\
2&3-\lambda&0&1&0\\
-2&1&2-\lambda&-3&0\\
2&-1&0&5-\lambda&0
\end{array}
\right)
$$

### Subespacio $\lambda_1 = 2$

El sistema que queremos resolver en este caso es:

$$
\left(
\begin{array}{cccc|c}
2&1&0&1&0\\
2&1&0&1&0\\
-2&1&0&-3&0\\
2&-1&0&3&0
\end{array}
\right)
$$

Observemos que la primera es CL de la segunda, y la tercera es CL de la cuarta, por lo que podemos decir que:

- $z=-y-2x$
- $y= 2x+3z\Rightarrow y=2x-3y-6x\Rightarrow 4y=-4x\Rightarrow y=-x$

Y con esto puedo decir que:

- $z= -y-2x = x-2x = -x$
- $y=-x$

Por lo tanto:

$$
S_2 = \{\begin{pmatrix}\alpha&-\alpha\\\beta&-\alpha\end{pmatrix}\mid\alpha,\beta\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{\begin{pmatrix}1&-1\\0&-1\end{pmatrix}, \begin{pmatrix}0&0\\1&0\end{pmatrix}\}
$$

### Subespacio $\lambda_2 = 4$

El sistema que queremos resolver en este caso es:

$$
\left(
\begin{array}{cccc|c}
0&1&0&1&0\\
2&-1&0&1&0\\
-2&1&-2&-3&0\\
2&-1&0&1&0
\end{array}
\right)
$$

Observemos que la segunda es CL de la cuarta, por lo que podemos decir que:

- $y=-z$
- $z=-2x+y\Rightarrow z=-2x-z \Rightarrow 2z=-2x\Rightarrow z=-x$
- $-2x+y-2w-3z=0\Rightarrow -2x+(-z)-2w-3(-x)=0\Rightarrow -2x+x-2w+3x=0\Rightarrow 2x-2w=0\Rightarrow x=w$

Y con esto puedo decir que:

- $y=-z\Rightarrow y=x\Rightarrow y=w$
- $z=-x\Rightarrow z=-w$
- $x=w$

Por lo tanto:

$$
S_4 = \{\begin{pmatrix}\alpha&\alpha\\\alpha&-\alpha\end{pmatrix}\mid\alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{\begin{pmatrix}1&1\\1&-1\end{pmatrix}\}
$$

### Subespacio $\lambda_3 = 6$

El sistema que queremos resolver en este caso es:

$$
\left(
\begin{array}{cccc|c}
-2&1&0&1&0\\
2&-3&0&1&0\\
-2&1&-4&-3&0\\
2&-1&0&-1&0
\end{array}
\right)
$$

Observemos que la primera es CL de la cuarta, por lo que podemos decir que:

- $z=-y+2x$
- $x=\frac{3y-z}{2}\Rightarrow x=\frac{4y-2x}{2}\Rightarrow x=2y-x\Rightarrow x=y$
- $y=2x+4w+3z$

Y con esto puedo decir que:
- $z=-y+2x\Rightarrow z=-y+2y\Rightarrow z=y$
- $x=y$
- $y=2x+4w+3z\Rightarrow y=2y+4w+3y\Rightarrow -4y=4w\Rightarrow y=-w$

Poniendo todo en función de $w$:

- $z=-w$
- $x=-w$
- $y=-w$

Por lo tanto:

$$
S_6 = \{\begin{pmatrix}-\alpha&-\alpha\\\alpha&-\alpha\end{pmatrix}\mid\alpha\in\mathbb{R}\}
$$

La base de este subespacio podría ser:

$$
\{\begin{pmatrix}-1&-1\\1&-1\end{pmatrix}\}
$$
