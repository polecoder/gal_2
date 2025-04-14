# CLASE 10 - 14/04/2025

## Producto interno y Norma

### Definición (producto interno)

Sea $V$ un espacio vectorial sobre $\mathbb{K}$. Una función $\left<,\right>:V\times V\to\mathbb{K}$ es un producto interno si $V$ si cumple:

1. $\left<u+v, w\right> = \left<u,w\right> + \left<v,w\right>\quad\forall u,v,w\in V$
2. $\left<\alpha u, v\right> = \alpha\left<u, v\right>\quad \forall u,v\in V, \forall\alpha\in\mathbb{K}$
3. $\left< u,v \right> = \overline{\left<v,u\right>}\quad\forall u,v\in V$
4. $\left< v,v\right>\in\mathbb{R}$ y $\left<v,v\right> \geq 0 \quad\forall v\in V$ y además $\left<v,v\right> = 0 \iff v = \vec{0}$

**Observación:**

Se cumple que:

1. $\left<u, v+w\right> = \left<u,v\right> + \left<u,w\right>\quad\forall u,v,w\in V$
2. $\left<u, \alpha v\right> = \overline{\alpha}\left<u, v\right>\quad \forall u,v\in V, \forall\alpha\in\mathbb{K}$
3. $\left<\vec{0}, v\right> = \left<v, \vec{0}\right> = 0\quad v\in V$

**Demostración:**

1. $\left<u, v+w\right> = \overline{\left<v+w, u\right>} = \overline{\left<v,u\right> + \left<w,u\right>} = \overline{\left<v,u\right>} + \overline{\left<w,u\right>} = \left<u,v\right> + \left<u,w\right>$
2. $\left<u, \alpha v\right> = \overline{\left<\alpha v, u\right>} = \overline{\alpha\left<v, u\right>} = \overline{\alpha}\overline{\left<v, u\right>} = \overline{\alpha}\left<u, v\right>$

#### Ejemplos

1. $V=\mathbb{R}^n$ y:
    - $v = \{v_1,v_2,\ldots,v_n\}$
    - $w = \{w_1,w_2,\ldots,w_n\}$

    $\left<v, w\right> = \sum_{i=1}^n v_iw_i$

2. $V=\mathbb{C}^n$ y:
    - $v = \{v_1,v_2,\ldots,v_n\}$
    - $w = \{w_1,w_2,\ldots,w_n\}$

    $\left<v, w\right> = \sum_{i=1}^n v_iw_i$

### Definición (norma)

Sea $V$ un espacio vectorial sobre $\mathbb{K}$. Decimos que una función $\|.\|: V\to \mathbb{K}$ es una norma en $V$ si cumple que:

1. $\|v\|\geq 0$ y $\|v\| = 0 \iff v=\vec{0}$
2. $\|\alpha v\| = |\alpha| \|v\|\quad\forall v\in V,\forall\alpha\in\mathbb{K}$
3. $\|v+w\| \leq \|v\| + \|w\|\quad\forall v,w\in V$ (desigualdad triangular)

#### Ejemplos

1. $V=\mathbb{R}^n, v=(v_1,v_2,\ldots,v_n)$
    1. $\|v\| = \sqrt{\sum_{i=1}^n v_i^2}$
    2. $\|v\| = \sum_{i=1}^n |v_i|$
    3. $\|v\| = (\sum_{i=1}^n |v_i|^p)^{\frac{1}{p}}$ con $p\in\mathbb{N}$

### Norma inducida

Sea $V$ un espacio vectorial con producto interno, se define la norma inducida por el producto interno como:

$$
\|v\| = \sqrt{\left<v, v\right>}\quad v\in V
$$

Veamos que $\|.\|$ es efectivamente una norma:

1. $\|v\| = \sqrt{\left<v, v\right>} \geq 0$ y $\|v\| = 0\iff\sqrt{\left<v, v\right>}= 0\iff\left<v, v\right> = 0\iff v = 0$
2. $\|\alpha v\|= \sqrt{\left<\alpha v,\alpha v \right>}=\sqrt{\alpha\overline{\alpha}\left<v, v\right>}=\sqrt{\alpha^2\left<v, v\right>}=\alpha\sqrt{\left<v, v\right>} = \alpha\|v\|$
3. La desigualdad triangular se probará en la siguiente clase, porque requiere de otros resultados que veremos posteriormente.

#### Lema

Si $\|.\|$ es una norma inducida por un producto interno, entonces se cumple:

$$
\|v+w\|^2 + \|v-w\|^2 = 2\|v\|^2 + 2\|w\|^2\quad \forall v,w\in V
$$

Esta regla se llama la regla del paralelogramo.

**Demostración:**

- $\|v+w\|^2 = \left<v+w, v+w\right> = \left<v, v\right> + \left<v, w\right> + \left<w, v\right> + \left<w, w\right>$
- $\|v-w\|^2 = \left<v-w, v-w\right> = \left<v, v\right> - \left<v, w\right> - \left<w, v\right> + \left<w, w\right>$

Al sumar, obtenemos:

$$
\|v+w\|^2 + \|v-w\|^2 = 2\|v\|^2 + 2\|w\|^2
$$

### Desigualdad de Cauchy-Schwarz

Sea $V$ un espacio vectorial con producto interno, y la norma $\|.\|$ inducida por dicho producto interno. Se cumple que:

$$
|\left<v, w\right>| \leq \|v\|\|w\|\quad\forall v,w\in V
$$

Con igualdad si y sólo si $\{v,w\}$ es LD

**Demostración:**

- Si $w=\vec{0}$ la desigualdad se cumple trivialmente como igualdad.

- Supongamos que $w\neq\vec{0}$. Para cualquier $\alpha\in\mathbb{K}$, se cumple que:

$$
0\leq\|v-\alpha w\|^2 = \left<v-\alpha w, v-\alpha w\right> = \left<v, v\right> - \overline{\alpha}\left<v,  w\right> - \alpha\left<w, v\right> + |\alpha|^2\left<w, w\right>
$$

Eligiendo un $\alpha$ particular: $\alpha = \frac{\left<v, w\right>}{\|w\|^2}$ la desigualdad queda:

$$
\begin{aligned}
&0\leq \|v\|^2-\frac{\left<w, v\right>}{\|w\|^2}\cdot\left<v, w\right> - \frac{\left<v, w\right>}{\|w\|^2}\cdot \left<w, v\right> + \frac{|\left<v, w\right>|^2}{\|w\|^4}\cdot\|w\|^2\iff\\
&0\leq \|v\|^2-\frac{|\left<v, w\right>|^2}{\|w\|^2}\iff\\
&\frac{|\left<v, w\right>|^2}{\|w\|^2}\leq\|v\|^2\iff\\
&|\left<v, w\right>|^2 \leq \|v\|^2\|w\|^2 \iff\\
&|\left<v, w\right>| \leq \|v\|\|w\|
\end{aligned}
$$

Observemos que hay igualdad si y sólo si:

$$
0 = \|v-\alpha w\|^2
$$

Y esto solo se cumple si $\{v,\alpha w\}$ son LD