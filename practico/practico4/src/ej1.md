# Ejercicio 1

## Consigna

Si $T: V \rightarrow V$ es una transformación lineal y $S \subset V$ es un subespacio de $V$, decimos que $S$ es un **subespacio invariante bajo $T$** (o $T$-invariante) si $T(s) \in S$ para todo vector $s \in S$.  
Probar que $V$, $\{0_V\}$, $N(T)$ (núcleo) e $Im(T)$ (imagen) son subespacios invariantes bajo $T$.

## Resolución

### $V$

Probar que $V$ es $T$-invariante es fácil porque esto está dado por la definición de $T$, sabemos que $T$ recibe un vector $v\in V$ y devuelve otro vector $T(v)\in V$ que es el espacio de llegada. 
Podemos decir que $T(V)\subseteq V$

### $\{0_V\}$

Todas las transformaciones lineales satisfacen que $T(0_V) = 0_V\in\{0_V\}$ por linealidad, por lo que entonces $\{0_V\}$ es $T$-invariante.

### $N(T)$

El núcleo de $T$ está definido por:

$$
N(T) = \{v\in V: T(v) = \vec{0}\}
$$

Veamos que en el núcleo de una transformación siempre está el $\vec{0}$ (porque su transformado será él mismo por lo visto anteriormente).
Podemos decir que $T(v) = \vec{0}\quad\forall v\in N(T)$, y como $\vec{0}\in N(T)$ concluimos que $N(T)$ es $T$-invariante.

### $Im(T)$

Si $w\in Im(T)$, entonces existe $v\in T$ tal que $w = T(v)$ (definición de imagen).

Aplicando $T$ a ambos lados obtenemos que:

- $T(w) = T(T(v))$

Pero $T(v)\in V$, entonces por definición de imagen $T(T(v))\in Im(T)$.

Entonces demostramos que $Im(T)$ es invariante ya que tomamos $w,v$ cualquiera.