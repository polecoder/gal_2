# CLASE 8 - 07/04/2025

## Forma canónica de Jordan

### Vectores propios generalizados

Sea $T:V\to V$ con $dim(V)=n$ y un valor propio $\lambda_0$.

Podemos decir que:

$$S_{\lambda_0}^{(1)} = \{v\in V\mid(T-\lambda_0\mathbb{I})v = \vec{0}\}$$

Es el subespacio propio de $\lambda_0$, donde sus vectores son los que conocemos como vectores propios.

Consideremos los siguientes subespacios:

$$S_{\lambda_0}^{(2)} = \{v\in V\mid(T-\lambda_0\mathbb{I})^2v = \vec{0}\}$$

$$S_{\lambda_0}^{(3)} = \{v\in V\mid(T-\lambda_0\mathbb{I})^3v = \vec{0}\}$$

Y así sucesivamente. Observemos que el cada uno de ellos está contenido en el siguiente. Todos los vectores que pertenezcan a alguno de los que tiene grado mayor a 1 se llaman vectores propios generalizados.

Se puede probar que eventualmente llegaremos a un subespacio $S_{\lambda_0}^{(m_0)}$ tal que dejaremos de aumentar "el tamaño" y todos los subespacios siguientes serán iguales a este último. Para este valor se cumple lo siguiente:

- $m_0\leq ma(\lambda_0)$
- $dim(S_{\lambda_0}^{(m_0)}) = ma(\lambda_0)$
- Si $v\in S_{\lambda_0}^{(k)}$ entonces $(T-\lambda_0\mathbb{I})\in S_{\lambda_0}^{(k-1)}$
- Si $v\in S_{\lambda_0}^{(k)}-S_{\lambda_0}^{(k-1)}$ entonces $(T-\lambda_0\mathbb{I})\in S_{\lambda_0}^{(k-1)}-S_{\lambda_0}^{(k-2)}$

Veamos un ejemplo para entender la intuición de lo que vamos a hacer con las formas de Jordan.

### Ejemplo

Supongamos que tenemos los siguientes subespacios que cumplen las siguientes propiedades para $\lambda_0$.

- $dim(S_{\lambda_0}^{(1)}) = 3$
- $dim(S_{\lambda_0}^{(2)}) = 5$
- $dim(S_{\lambda_0}^{(3)}) = 6 = ma(\lambda_0)$

Como $dim(S_{\lambda_0}^{(3)}) = dim(S_{\lambda_0}^{(2)}) + 1$ elijo $v_1\in S_{\lambda_0}^{(3)}-S_{\lambda_0}^{(2)}$

A partir de $v_1$, podemos elegir $v_2$ de la siguiente forma:

- $(T-\lambda_0\mathbb{I})v_1 = v_2$

Observemos que $v_2\in S_{\lambda_0}^{(2)}-S_{\lambda_0}^{(1)}$, con el mismo razonamiento elegimos $v_3$.

- $(T-\lambda_0\mathbb{I})v_2 = v_3\in S_{\lambda_0}^{(1)}$

Es decir que $v_3$ es valor propio asociado a $\lambda_0$.

Ahora, como $dim(S_{\lambda_0}^{(2)}) = dim(S_{\lambda_0}^{(1)}) + 2$ elijo $v_4\in S_{\lambda_0}^{(1)}-S_{\lambda_0}^{(1)}$. Con esto puedo elegir $v_5$ usando el mismo razonamiento anterior:

- $(T-\lambda_0\mathbb{I})v_4 = v_5\in S_{\lambda_0}^{(1)}$

Es decir que $v_5$ es valor propio asociado a $\lambda_0$.

Y nos restaría elegir un vector, el cual podemos elegir en $S_{\lambda_0}^{(1)}$, lo llamamos $v_6$.

**IDEA:** Queremos elegir la máxima cantidad de vectores por cada subespacio, y lo hacemos partiendo el más grande, y usando las propiedades descritas anteriormente para construirnos vectores en los subespacios más pequeños.

Esta construcción proporciona $m=ma(\lambda_0)$ vectores linealmente independientes que conforman una base de $S_{\lambda_0}^{(3)}$.

Considerando la base $\mathcal{B} = \{v_1,v_2,v_3,v_4,v_5,v_6\}$, tenemos que:

- $(T-\lambda_0\mathbb{I})v_1 = v_2 \Rightarrow T(v_1) = \lambda_0v_1 + v_2$
- $(T-\lambda_0\mathbb{I})v_2 = v_3 \Rightarrow T(v_2) = \lambda_0v_2 + v_3$
- $(T-\lambda_0\mathbb{I})v_3 = 0 \Rightarrow T(v_3) = \lambda_0v_3$
- $(T-\lambda_0\mathbb{I})v_4 = v_5 \Rightarrow T(v_4) = \lambda_0v_4 + v_5$
- $(T-\lambda_0\mathbb{I})v_5 = 0 \Rightarrow T(v_5) = \lambda_0v_5$
- $(T-\lambda_0\mathbb{I})v_6 = 0 \Rightarrow T(v_6) = \lambda_0v_6$

Con esto podemos restringir $T$ a este subespacio, quedandonos la siguiente matriz asociada:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = \begin{pmatrix}
\lambda_0&0&0&0&0&0\\
1&\lambda_0&0&0&0&0\\
0&1&\lambda_0&0&0&0\\
0&0&0&\lambda_0&0&0\\
0&0&0&1&\lambda_0&0\\
0&0&0&0&0&\lambda_0
\end{pmatrix}
$$

Llamamos a esta matriz el bloque de Jordan asociado a $\lambda_0$

Esto se construye con los subbloques de Jordan, que en esta matriz son los siguientes:

$$
A = \begin{pmatrix}
\lambda_0&0&0\\
1&\lambda_0&0\\
0&1&\lambda_0
\end{pmatrix}
$$

$$
B = \begin{pmatrix}
\lambda_0&0\\
1&\lambda_0\\
\end{pmatrix}
$$

$$
C = \begin{pmatrix}
\lambda_0
\end{pmatrix}
$$

Entonces estos subbloques son aquellos con el valor propio en la diagonal, y 1s por debajo de la diagonal.

### Subespacios invariantes (definición)

Sea $T:V\to V$. Decimos que un subespacio $W\subset V$ es invariante con respecto a $T$ si  $T(W)\subset W$, es decir que calculamos $T$ de cualquier vector de $W$, nos mantenemos en $W$.

#### Proposición

Sea $T:V\to V$, $dim(V) = n$, $W\subset V$ subespacio invariante. Existe una base $\mathcal{B}$ de $V$ tal que:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = \left(\begin{array}{c|c}
A&B\\
\hline
0&C
\end{array}
\right)
$$

Donde $A$ y $C$ son dos matrices cuadradas, y $0$ una matriz con todos sus elementos iguales a 0.

##### Demostración

Supongamos que $dim(W) = m$, consideramos una base de $W$ y la completamos hasta obtener una base de $V$.

$\mathcal{B}=\{v_1,\ldots,v_m,v_{m+1},\ldots,v_n\}$ base de $V$

Como $W$ es invariante, para todo vector $v_i\in \mathcal{B}$ tenemos que $T(v_i)$ es combinación lineal de los vectores de la base de $W$, entonces nos podemos construir la matriz deseada:

$$
{}_{\mathcal{B}}(T)_{\mathcal{B}} = \left(\begin{array}{c|c}
A&B\\
\hline
0&C
\end{array}
\right)
$$

Donde:

- $A\in\mathcal{M}_{m\times m}$
- $B\in\mathcal{M}_{n-m\times m}$
- $0\in\mathcal{M}_{m\times n-m}$
- $C\in\mathcal{M}_{n-m\times n-m}$
