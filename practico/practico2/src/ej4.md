# Ejercicio 4

## Consigna

Sea $T: V \to V$ una transformación lineal. Probar que:

1. $T$ es invertible $\iff$ $0$ no es valor propio de $T$.
2. Si $T$ es invertible y $\lambda$ es valor propio de $T$, entonces $\lambda^{-1}$ es valor propio de $T^{-1}$.
3. Si $\lambda$ es valor propio de $T$, entonces $\lambda^n$ es valor propio de $T^n$ para todo $n \in \mathbb{N}$.
4. Si $T$ es invertible y $\lambda$ es valor propio de $T$, entonces $\lambda^{-n}$ es valor propio de $T^{-n}$ para todo $n \in \mathbb{N}$.

**Nota:** Existen resultados análogos para matrices cuadradas.


## Resolución

Veamos cada afirmación de forma separada

### Afirmación #1

$T$ es invertible $\iff$ $0$ no es valor propio de $T$.

#### ($\Rightarrow$)

$T$ es invertible, esto nos dice que $T$ es biyectiva, y además nos dice que $Ker(T) = \{0\}$, es decir, el único vector que mapea a $0$ es el $0$ (todo esto es teórico).

Sabiendo esto, supongamos que $0$ es valor propio de $T$, entonces existe un vector propio $v \neq 0$ tal que $T(v) = 0 \cdot v = 0$, pero esto contradice que $Ker(T) = \{0\}$, ya que dicho vector pertenecería al nucleo de $T$, por lo que $0$ no puede ser valor propio de $T$.

#### ($\Leftarrow$)

$0$ NO es valor propio de $T$, esto implica que $\not\exists v\in V$ tal que $T(v) = 0 \cdot v = 0$, es decir, que el único vector que mapea a $0$ es el $0$. Esto implica que $Ker(T) = \{0\}$, por lo que $T$ es inyectiva (teórico). Además como estamos trabajando en un espacio finito, si $T$ es inyectiva, entonces también es sobreyectiva. Por lo que $T$ es biyectiva, y por lo tanto invertible.

### Afirmación #2

Si $T$ es invertible y $\lambda$ es valor propio de $T$, entonces $\lambda^{-1}$ es valor propio de $T^{-1}$.

Sabemos que $\lambda$ es valor propio de $T$, por lo que existe un vector $v \neq 0$ tal que $T(v) = \lambda v$. Si aplicamos $T^{-1}$ a ambos lados de la ecuación, obtenemos:

$$
T^{-1}(T(v)) = T^{-1}(\lambda v) \Rightarrow v = \lambda T^{-1}(v)
$$

Ahora aplicando $\lambda^{-1}$ a ambos lados de la ecuación, obtenemos:

$$
\lambda^{-1} v = T^{-1}(v)
$$

Por lo que $\lambda^{-1}$ es valor propio de $T^{-1}$.

### Afirmación #3

Si $\lambda$ es valor propio de $T$, entonces $\lambda^n$ es valor propio de $T^n$ para todo $n \in \mathbb{N}$.

Sabemos que $\lambda$ es valor propio de $T$, por lo que existe un vector $v \neq 0$ tal que $T(v) = \lambda v$. Probemos esto por inducción:

**Caso base:** $n = 2$

$$
T^2(v) = T(T(v)) = T(\lambda v) = \lambda T(v) = \lambda\cdot\lambda v = \lambda^2 v
$$

**Paso inductivo:** Supongamos que $\lambda^n$ es valor propio de $T^n$, probemos que $\lambda^{n+1}$ es valor propio de $T^{n+1}$

$$
T^{n+1}(v) = T(T^n(v)) = T(\lambda^n v) = \lambda^n T(v) = \lambda^n \lambda v = \lambda^{n+1} v
$$

Por lo que $\lambda^{n+1}$ es valor propio de $T^{n+1}$, lo que prueba la afirmación.

### Afirmación #4

Si $T$ es invertible y $\lambda$ es valor propio de $T$, entonces $\lambda^{-n}$ es valor propio de $T^{-n}$ para todo $n \in \mathbb{N}$.

Sabemos que $\lambda$ es valor propio de $T$, por lo que $\lambda^{-1}$ es valor propio de $T^{-1}$, y por la afirmación 3, $\lambda^{n}$ es valor propio de $T^{n}$ para todo $n \in \mathbb{N}$.

Entonces, tomando $T = T^{-1}$ y usando la afirmación 3:

$$
\begin{aligned}
&T^{-1} = \lambda^{-1}v\\
&(T^{-1})^n = (\lambda^{-1})^nv\\
&T^{-n} = \lambda^{-n}v
\end{aligned}
$$