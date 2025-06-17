# Ejercicio 1

## Consigna

Hallar el representante de Riesz de los siguientes funcionales lineales:

1. $T : \mathbb{R}^3 \to \mathbb{R}$ dada por $T(x, y, z) = x + 2y - 3z$
2. $T : \mathbb{C}^3 \to \mathbb{C}$ dada por $T(x, y, z) = ix + (2 + 3i)y + (1 - 2i)z$
3. $T : \mathbb{R}_1[x] \to \mathbb{R}$ definida por $T(p) = p(\alpha)$, donde $\alpha \in \mathbb{R}$ fijo
4. $T : \mathbb{R}_2[x] \to \mathbb{R}$ definida por $T(p) = p(0) + p'(1)$

## Resolución

### Recordatorio (definición de representante de Riesz)

Sea $V$ un espacio vectorial con producto interno, tal que $dim(V)=n$.
Si $T:V\to\mathbb{K}$ es una funcional lineal entonces existe un único $w\in V$ tal que $T(v)=\left<v, w\right>\quad\forall v\in V$.
Llamamos a $w\in V$ el representante de Riesz de la funcional lineal $T$

### Parte 1

Consideramos $T : \mathbb{R}^3 \to \mathbb{R}$ dada por $T(x, y, z) = x + 2y - 3z$.

Queremos encontrar $w=(w_1,w_2,w_3)\in\mathbb{R}^3$ tal que para todo $v=(x,y,z)\in\mathbb{R}^3$ se cumpla que $T(v)=\left<v, w\right>$. Considerando el producto interno usual, tenemos que:

- $\left<(x,y,z), (w_1,w_2,w_3)\right>=xw_1+yw_2+zw_3$

Para cumplir la igualdad necesitamos que:

$$
x + 2y - 3z=xw_1+yw_2+zw_3
$$

De donde sacamos que: $w=(1,2,-3)$

### Parte 2

Consideramos $T : \mathbb{C}^3 \to \mathbb{C}$ dada por $T(x, y, z) = ix + (2 + 3i)y + (1 - 2i)z$.

Queremos encontrar $w=(w_1,w_2,w_3)\in\mathbb{C}^3$ tal que para todo $v=(x,y,z)\in\mathbb{C}^3$ se cumpla que $T(v)=\left<v, w\right>$. Considerando el producto interno usual, tenemos que:

- $\left<(x,y,z), (w_1,w_2,w_3)\right>=x\overline{w_1}+y\overline{w_2}+z\overline{w_3}$

Para cumplir la igualdad necesitamos que:

$$
ix + (2 + 3i)y + (1 - 2i)z=x\overline{w_1}+y\overline{w_2}+z\overline{w_3}
$$

De donde sacamos que: $w=(-i,2-3i,1+2i)$

### Parte 3

Consideramos $T : \mathbb{R}_1[x] \to \mathbb{R}$ definida por $T(p) = p(\alpha)$, donde $\alpha \in \mathbb{R}$ fijo.

Queremos encontrar $w=a x+b\in\mathbb{R}_1[x]$ tal que para todo $p\in\mathbb{R}_1[x]$ se cumpla que $T(p)=\left<p, w\right>$. Considerando el producto interno usual, tenemos que:

- $\left<p, w\right>=\int_0^1(a x+b)p(x)dx$ para todo $p\in\mathbb{R}_1[x]$

Enfrentaremos este caso de forma diferente a los casos de $\mathbb{R}^3$ y $\mathbb{C}^3$, vamos a trabajar con la base canónica de $\mathbb{R}_1[x]$ para obtener un sistema que nos permita encontrar $a$ y $b$ para construir $w\in\mathbb{R}_1[x]$:

- Considerando $p=1$:
    - $T(1)=1(\alpha)=1=\int_0^1ax+b\cdot 1dx=\frac{a}{2}+b$
- Considerando $p=x$:
    - $T(x)=x(\alpha)=\alpha=\int_0^1(ax+b)xdx=\frac{a}{3}+\frac{b}{2}$

Esto nos deja con el siguiente sistema:

$$
\left(
\begin{array}{cc|c}
\frac{1}{2}&1&1\\
\frac{1}{3}&\frac{1}{2}&\alpha\\
\end{array}
\right)\\
\sim\scriptstyle{(2F_1\text{ y }6F_2)}\\
\left(
\begin{array}{cc|c}
1&2&2\\
2&3&6\alpha\\
\end{array}
\right)\\
\sim\scriptstyle{(F_2-2F_1)}\\
\left(
\begin{array}{cc|c}
1&2&2\\
0&-1&6\alpha-4\\
\end{array}
\right)\\
$$

Sustituyendo obtenemos que:

- $b=-6\alpha+4$
- $a=2-2(-6\alpha+4)=12\alpha-6$

Entonces el representante de Riesz es $w=(12\alpha-6)x+(-6\alpha+4)$

### Parte 4

Consideramos $T : \mathbb{R}_2[x] \to \mathbb{R}$ definida por $T(p) = p(0) + p'(1)$

Queremos encontrar $w=ax^2+bx+c\in\mathbb{R}_2[x]$ tal que para todo $p\in\mathbb{R}_2[x]$ se cumpla que $T(p)=\left<p, w\right>$. Considerando el producto interno usual, tenemos que:

- $\left<p, w\right>=\int_0^1p(x)(ax^2+bx+c)dx$

Enfrentaremos este caso de forma diferente a los casos de $\mathbb{R}^3$ y $\mathbb{C}^3$, vamos a trabajar con la base canónica de $\mathbb{R}_2[x]$ para obtener un sistema que nos permita encontrar $a$ y $b$ para construir $w\in\mathbb{R}_2[x]$:

- Considerando $p=1$:
    - $T(1)=1(0)+1'(1)=1=\int_0^11\cdot(ax^2+bx+c)dx=\frac{a}{3}+\frac{b}{2}+c$
- Considerando $p=x$:
    - $T(x)=x(0)+x'(1)=1=\int_0^1x(ax^2+bx+c)dx=\frac{a}{4}+\frac{b}{3}+\frac{c}{2}$
- Considerando $p=x^2$:
    - $T(x)=x^2(0)+(x^2)'(1)=2=\int_0^1x^2(ax^2+bx+c)dx=\frac{a}{5}+\frac{b}{4}+\frac{c}{3}$

Esto nos deja con el siguiente sistema:

$$
\left(
\begin{array}{ccc|c}
\frac{1}{3}&\frac{1}{2}&1&1\\
\frac{1}{4}&\frac{1}{3}&\frac{1}{2}&1\\
\frac{1}{5}&\frac{1}{4}&\frac{1}{3}&2
\end{array}
\right)\\
\sim\scriptstyle{(6F_1,24F_2\text{ y }60F_3)}\\
\left(
\begin{array}{ccc|c}
2&3&6&6\\
6&8&12&24\\
12&15&20&120
\end{array}
\right)\\
\sim\scriptstyle{(F_2-3F_1\text{ y }F_3-6F_1)}\\
\left(
\begin{array}{ccc|c}
2&3&6&6\\
0&-1&-6&6\\
0&-3&-16&84
\end{array}
\right)\\
\sim\scriptstyle{(F_3-3F_2)}\\
\left(
\begin{array}{ccc|c}
2&3&6&6\\
0&-1&-6&6\\
0&0&2&66
\end{array}
\right)\\
$$

Sustituyendo obtenemos que:

- $c=33$
- $b=-6-6(33)=-204$
- $a=\frac{6-6(33)-3(-204)}{2}=210$

Por lo tanto, tenemos que $w=210x^2-204x+33$