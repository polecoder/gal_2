# Ejercicio 2

## Consigna

Sea $V$ un espacio vectorial de dimensión finita con producto interno, $T : V \to \mathbb{K}$ un funcional lineal no nulo, y $v_0$ el representante de Riesz de $T$.

1. Probar que $v_0 \in (Ker(T))^\perp$
2. Probar que $\|v_0\| = \sqrt{T(v_0)}$
3. Probar que $\dim((Ker(T))^\perp) = 1$
4. Si $\{e\}$ es una base ortonormal de $(Ker(T))^\perp$, probar que $v_0 = T(e)\cdot e$
5. Sea $T : \mathbb{R}^3 \to \mathbb{R}$ definida por:

   $$
   T(1, 0, 0) = 2,\quad T(0, 1, 0) = 1,\quad T(0, 0, 1) = -1
   $$

    Hallar una base de $(Ker(T))^\perp$ y utilizarla para determinar el representante de Riesz de $T$.

## Resolución

### Parte 1

Expandamos las definiciones de las cosas con las que estamos trabajando:

- $v_0$ es el representante de Riesz de $T$
    - Entonces $\forall v\in V: T(v)=\left<v, v_0\right>$
- $v_0\in(Ker(T))^{\perp}$
    - Si y solo si: $\forall s\in Ker(T):\left<s, v_0\right>=0$

Veamos que esto último lo podemos expresar de otra forma:

$$
\begin{aligned}
&v_0\in(Ker(T))^{\perp}\\
&\iff\scriptstyle{(\text{definición de complemento ortogonal})}\\
&\forall s\in Ker(T):\left<s, v_0\right>=0\\
&\iff\scriptstyle{(\text{definición del representante de Riesz: }T(s)=\left<s, v_0\right>)}\\
&\forall s\in Ker(T): T(s)=0
\end{aligned}
$$

Donde esto último se cumple pues todos los vectores en $Ker(T)$ cumplen esa propiedad por pertenecer al núcleo de $T$

### Parte 2

Queremos probar que $\|v_0\| = \sqrt{T(v_0)}$.

Expandamos a ver a que podemos llegar:

$$
\begin{aligned}
&\|v_0\|\\
&=\scriptstyle{(\text{norma inducida por el producto interno})}\\
&\sqrt{\left<v_0, v_0\right>}\\
&=\scriptstyle{(\text{definición del representante de Riesz: }T(v_0)=\left<v_0, v_0\right>)}\\
&\sqrt{T(v_0)}\\
\end{aligned}
$$

Esto prueba la propiedad.

### Parte 3

Queremos probar que $\dim((Ker(T))^\perp) = 1$.

Consideremos la siguiente propiedad del complemento ortogonal:

- $V=Ker(T)\oplus(Ker(T))^{\perp}$

De esta podemos deducir que:

- $dim(V)=dim(Ker(T))+dim((Ker(T))^{\perp})\quad(i)$

Por otra parte, usando el teorema de las dimensiones, tenemos que:

- $dim(V)=dim(Im(T))+dim(Ker(T))$
- También tenemos que $dim(Im(T))=1$ pues $T$ es no nula y es una funcional lineal (por hipótesis)

Entonces podemos concluir que:

$$
\begin{aligned}
&dim(V)=dim(Im(T))+dim(Ker(T))\\
&\iff\\
&3=1+dim(Ker(T))\\
&\iff\\
&dim(Ker(T))=2
\end{aligned}
$$

Volviendo a $(i)$, tenemos lo siguiente:

$$
\begin{aligned}
&dim(V)=dim(Ker(T))+dim((Ker(T))^{\perp})\\
&\iff\\
&3=2+dim((Ker(T))^{\perp})\\
&\iff\\
&dim((Ker(T))^{\perp})=1
\end{aligned}
$$

Esto prueba la propiedad.

### Parte 4

Queremos probar que si $\{e\}$ es una base ortonormal de $(Ker(T))^\perp$, probar que $v_0 = T(e)\cdot e$.

Por la propiedad 1, sabemos que $v_0\in (Ker(T))^{\perp}$, por lo tanto si $\{e\}$ es base de $(Ker(T))^\perp$, tenemos que:

- $v_0=\alpha e$ con $\alpha\in\mathbb{K}$

Ahora observemos lo siguiente:

$$
\begin{aligned}
&T(e)\\
&=\scriptstyle{(\text{definición del representante de Riesz})}\\
&\left<e, v_0\right>\\
&=\scriptstyle{(\text{expandiendo }v_0)}\\
&\left<e, \alpha e\right>\\
&=\scriptstyle{(\text{propiedades del producto interno})}\\
&\alpha\left<e, e\right>\\
&=\scriptstyle{(\|e\|=1)}\\
&\alpha
\end{aligned}
$$

Por lo tanto $\alpha=T(e)$, entonces $v_0=T(e)\cdot e$. Esto prueba la propiedad.

### Parte 5

Para esta parte primero hallemos $T(x,y,z)\quad\forall(x,y,z)\in\mathbb{R}^3$.

Tenemos que:

- $T(1, 0, 0) = 2$
- $T(0, 1, 0) = 1$
- $T(0, 0, 1) = -1$

Considerando la base canónica de $\mathbb{R^3}$, podemos decir que:

$$
\begin{aligned}
&(x,y,z)=x(1,0,0)+y(0,1,0)+z(0,0,1)\\
&\iff\scriptstyle{(\text{aplicando }T)}\\
&T(x,y,z)=xT(1,0,0)+yT(0,1,0)+zT(0,0,1)\\
&\iff\scriptstyle{(\text{sustituyendo por los valores conocidos de }T)}\\
&T(x,y,z)=2x+y-z\\
\end{aligned}
$$

Y esto vale para todo $v=(x,y,z)\in\mathbb{R}^3$.

Se ve claramente que $v_0=(2,1,-1)$. Por lo que realizar el otro procedimiento no tiene sentido.
