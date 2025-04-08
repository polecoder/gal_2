# Ejercicio 2

## Consigna

Sea $T: V \rightarrow V$ una transformación lineal.  

1. Si $W_1$ y $W_2$ son subespacios de $V$ invariantes bajo $T$, probar que $W_1 \cap W_2$ y $W_1 + W_2$ son invariantes bajo $T$.  
2. Probar que si $\lambda$ es valor propio de $T$, entonces el subespacio propio $S_\lambda$ es invariante bajo $T$.  
3. Probar que si $\lambda$ es valor propio de $T$ y $W = [v_1, v_2]$, con $v_1 \in S_\lambda$ y $T(v_2) = v_1$, entonces $W$ es invariante bajo $T$.  
4. Si $W$ es un subespacio de $V$ invariante bajo $T$ y $\dim(W) = 1$:  
   (a) Probar que los vectores no nulos de $W$ son vectores propios de $T$.  
   (b) ¿Es $W$ un subespacio propio de $T$? Justificar.  
5. Sea $T: \mathbb{R}^3 \rightarrow \mathbb{R}^3$ tal que los siguientes subespacios son invariantes bajo $T$:  
    - $W_1 = \{(x, y, z) \in \mathbb{R}^3 : x + 2y - z = 0\}$,  
    - $W_2 = \{(x, y, z) \in \mathbb{R}^3 : x + y + z = 0\}$,  
    - $W_3 = \{(x, y, z) \in \mathbb{R}^3 : x + y - 2z = 0\}$  
        (a) Probar que $T$ es diagonalizable.  
        (b) Sabiendo que $2T - T^2 = Id$ en $W_1$ y $T = 2Id$ en $W_2 \cap W_3$, hallar los valores propios de $T$.

## Resolución

### Parte 1

**$W_1\cap W_2$**

Tomemos $v\in W_1\cap W_2$, como $W_1$ y $W_2$ son $T$-invariantes, tenemos que:

- $T(v)\in W_1$ y,
- $T(v)\in W_2$

se cumplen simultaneamente.

Por lo tanto uniendo estas dos tenemos que:

$$T(v)\in W_1\cap W_2$$

Lo que significa que $W_1\cap W_2$ es $T$-invariante porque tomamos $v$ arbitrario.

**$W_1 + W_2$**

Tomemos $v=w_1+w_2$ con $w_1\in W_1, w_2\in W_2$. Por lo que $v\in W_1 + W_2$

Aplicando $T$ de ambos lados tenemos que:

$$
T(v) = T(w_1) + T(w_2)
$$

Como $W_1$ y $W_2$ son invariantes tenemos que $T(w_1)\in W_1$ y $T(w_2)\in W_2$

Entonces $T(v) = T(w_1) + T(w_2)\in W_1+W_2$

Lo que demuestra que $W_1 + W_2$ es $T$-invariante

### Parte 2

Tomemos $v\in S_\lambda$, por definición de subespacio propio tenemos que $T(v) = \lambda v$.

Pero $\lambda v\in S_\lambda$, por lo que $S_\lambda$ es $T$-invariante.

### Parte 3

Queremos probar que dado $w\in W = [v_1,v_2]$, tenemos que $T(w)\in W$. Donde $v_1$ es valor propio de $T$, y $T(v_2) = v_1$.

Si $w = av_1 + bv_2$ entonces $T(w) = a\lambda v_1 + bv_1 = ab\lambda v_1$.

Por lo que entonces $W$ es $T$-invariante, ya que $T(w)\in W$ por lo visto anteriormente.

#### Parte 4

Sea $W$ un subespacio de $V$ $T$-invariante de $dim(W) = 1$.

Consideremos $\mathcal{B} = \{v_1\}$ base de $W$ y un vector no nulo $w\in W$.

- $w = av_1$ con $a\in\mathbb{K}, a\neq 0$

Como $W$ es invariante, tenemos que $T(w)\in W$, por lo que lo podemos escribir como

- $T(w) = bv_1$

Juntando con lo anterior tenemos que:

- $T(av_1) = bav_1$

Por lo que $av_1 = w$ es un vector propio de $T$ asociado al valor propio $b$.

Con esto probamos ambas partes, porque $W$ es un subespacio generado por $v_1$, que es un vector propio de $T$. Por lo tanto es un subespacio propio asociado a al valor propio $b$.

##### Parte 5

Para enfrentar esta parte tenemos en cuenta las propiedades vistas en la parte 1. Veamos de hallar las intersecciones entre los subespacios invariantes.

**$W_1\cap W_2$**

Queremos $v = (x,y,z)$ tal que:

$$
\begin{cases}
x+2y-z=0\\
x+y+z=0
\end{cases}
$$

Sumando las ecuaciones, obtenemos que:

- $2x+3y=0\Rightarrow x=-\frac{3}{2}y$
- $x+y+z\Rightarrow z=\frac{1}{2}y$

Por lo que una base de este subespacio podría ser:

$$
\{(-\frac{3}{2},1,\frac{1}{2})\}
$$

O, para simplificar:

$$
\{(-3,2,1)\}
$$

**$W_1\cap W_3$**

Queremos $v = (x,y,z)$ tal que:

$$
\begin{cases}
x+2y-z=0\\
x+y-2z=0
\end{cases}
$$

Restando las dos ecuaciones obtenemos que:

- $y+z=0\Rightarrow z=-y$
- $x+y+2y = 0\Rightarrow x=-3y$

Por lo que una base de este subespacio podría ser:

$$
\{(-3,1,-1)\}
$$

**$W_2\cap W_3$**

Queremos $v = (x,y,z)$ tal que:

$$
\begin{cases}
x+y+z=0\\
x+y-2z=0
\end{cases}
$$

Restando las dos ecuaciones obtenemos que:

- $3z=0\Rightarrow z=0$
- $x=-y$

Por lo que una base de este subespacio podría ser:

$$
\{(-1,1,0)\}
$$

Por la parte 4 sabemos que todos estos vectores son propios, pues $W_i\cap W_j$ son subespacios invariantes de dimensión $1$.

Si estos fueran LI, entonces tendríamos una base de $\mathbb{R}^3$ de vectores propios, lo cual implicaría que $T$ es diagonalizable.

Investiguemos si los tres vectores son LI con el método del determinante:

$$
\begin{vmatrix}
-3&-3&-1\\
2&1&1\\
1&-1&0
\end{vmatrix} = 0 + 2 - 3 - (-1 + 3 + 0) = -3
$$

La propiedad nos dice que si este determinante (con los vectores colgados como columnas) da distinto a 0, entonces los vectores son LI.

Por el razonamiento anterior, concluimos que $T$ es diagonalizable.

Evito la parte 5B porque no la termino de entender.