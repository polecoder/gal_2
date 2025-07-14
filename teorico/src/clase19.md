# CLASE 19 - 14/07/2025

## Operadores autoadjuntos

### Teorema

Retomamos el teorema visto en la clase anterior, para demostrarlo en esta clase.

Sea $V$ un $\mathbb{R}$-espacio vectorial de dimensión finita con producto interno, sea $T:V\to V$. Entonces las siguientes afirmaciones son equivalentes:

1. $T$ es autoadjunto
2. $\forall\mathcal{B}\to V$ ortonormal, ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es simétrica
3. $\exists\mathcal{B}_0\to V$ ortonormal, ${}_{\mathcal{B}_0}(T)_{\mathcal{B_0}}$ es simétrica

#### Demostración

##### $1\implies 2$

Queremos probar que si $T$ es autoadjunta, entonces $\forall\mathcal{B}\to V$ ortonormal, ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es simétrica.

Entonces:

Como $T$ es autoadjunto, entonces $T=T^*$, en particular tenemos que ${}_{\mathcal{B}}(T)_{\mathcal{B}}={}_{\mathcal{B}}(T^*)_{\mathcal{B}}$.

Por la representación matricial de la transformación adjunta, tenemos que:
- ${}_{\mathcal{B}}(T^*)_{\mathcal{B}}=\overline{({}_{\mathcal{B}}(T)_{\mathcal{B}})^t}$

En particular, como estamos en un $\mathbb{R}$-espacio vectorial, tenemos que:
- ${}_{\mathcal{B}}(T^*)_{\mathcal{B}}=({}_{\mathcal{B}}(T)_{\mathcal{B}})^t$

Además, como $T$ es autoadjunta, tenemos que:

- ${}_{\mathcal{B}}(T^*)_{\mathcal{B}}={}_{\mathcal{B}}(T)_{\mathcal{B}}=({}_{\mathcal{B}}(T)_{\mathcal{B}})^t$

Que es la definición de matriz simétrica, por lo tanto queda demostrada esta implicancia.

##### $2\implies 3$

Esta demostración es trivial, pues si se cumple que $\forall\mathcal{B}\to V$ ortonormal, ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es simétrica, entonces en particular existe una base $\mathcal{B}_0$ que cumple con dicha propiedad.

##### $3\implies 1$

Queremos probar que si $\exists\mathcal{B}_0\to V$ ortonormal, ${}_{\mathcal{B}_0}(T)_{\mathcal{B_0}}$ es simétrica, entonces $T$ es autoadjunta.

Veamos lo siguiente:

$$
\begin{aligned}
&{}_{\mathcal{B}_0}(T)_{\mathcal{B}_0}\\
&=\scriptstyle{(\text{por ser simétrica})}\\
&({}_{\mathcal{B}_0}(T)_{\mathcal{B}_0})^t\\
&=\scriptstyle{(\text{como }\mathbb{K}=\mathbb{R})}\\
&\overline{({}_{\mathcal{B}_0}(T)_{\mathcal{B}_0})}^t\\
&=\scriptstyle{(\text{representación matricial de la adjunta})}\\
&{}_{\mathcal{B}_0}(T^*)_{\mathcal{B}_0}\\
\end{aligned}
$$

Entonces $T$ es autoadjunta.

Por lo tanto, queda probada esta implicancia, y en consecuencia todas las equivalencias.

#### Observación

El teorema vale también para los complejos, pero con una pequeña diferencia.

Sea $V$ un $\mathbb{K}$-espacio vectorial de dimensión finita con producto interno, sea $T:V\to V$. Entonces las siguientes afirmaciones son equivalentes:

1. $T$ es autoadjunta
2. $\forall\mathcal{B}\to V$ ortonormal, ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es hermítica
3. $\exists\mathcal{B}_0\to V$ ortonormal, ${}_{\mathcal{B}_0}(T)_{\mathcal{B_0}}$ es hermítica

**Observación:** Una matriz $A$ es hermítica sii $A=\overline{(A)}^t$

### Teorema espectral de operadores autoadjuntos

Sea $V$ un $\mathbb{K}$-espacio vectorial de dimensión finita con producto interno. Sea $T:V\to V$ un operador autoadjunto.

Entonces existe $\mathcal{B}$ una base ortonormal de vectores propios de $T$.

**Observación:** Para probar este resultado, necesitamos de algunos resultados anteriores que vamos a probar a continuación.

#### Teorema 1

Sea $T:V\to V$ un operador autoadjunto en un $\mathbb{C}$-espacio vectorial con producto interno.
Entonces si $\lambda\in\mathbb{C}$ es un valor propio $\implies \lambda\in\mathbb{R}$

##### Demostración (Teorema 1)

1. Como $\lambda\in\mathbb{C}$ es un valor propio, entonces existe $v_0\in V, v_0\neq \vec{0}$ tal que $T(v_0)=\lambda v_0$

2. Como $T$ es autoadjunto, entonces tenemos que:
    - $T=T^*$
    - $\left<T(v), w\right>=\left<v, T(w)\right>\quad\forall v,w\in V$ en particular,
    - $\left<T(v), v\right>=\left<v, T(v)\right>\quad\forall v\in V$
    - Ahora consideremos el vector propio $v_0$ asociado a $\lambda$, entonces:

        $$
        \begin{aligned}
        &\left<T(v_0), v_0\right>=\left<v_0, T(v_0)\right>\\
        &\iff\scriptstyle{(\text{definición de valor propio})}\\
        &\left<\lambda v_0, v_0\right>=\left<v_0, \lambda v_0\right>\\
        &\iff\scriptstyle{(\text{propiedades de producto interno})}\\
        &\lambda\left< v_0, v_0\right>=\overline{\lambda}\left<v_0, v_0\right>\\
        &\iff\scriptstyle{(\text{como }v_0\neq\vec{0})}\\
        &\lambda=\overline{\lambda}\\
        \end{aligned}
        $$
        Donde esto último solo se cumple si $\lambda\in\mathbb{R}$

Esto prueba el teorema.

#### Corolario (del teorema 1)

Sea $V$ un $\mathbb{C}$-espacio vectorial de dimensión finita con producto interno y $T$ un operador autoadjunto.
Entonces $\Chi_T(\lambda)$ tiene todas las raíces reales.

#### Teorema 2

Sea $V$ un $\mathbb{R}$-espacio vectorial de dimensión finita con producto interno y $T:V\to V$ un operador autoadjunto.
Entonces $\Chi_T$ tiene raíces reales.

##### Demostración (Teorema 2)

Definimos $\mathcal{B}$ una base ortonormal de $V$.

Definimos $T_1:\mathbb{C}^n\to\mathbb{C}^n$, con $n=dim(V)$. Consideramos $\mathcal{B}_1$ una base ortonormal de $\mathbb{C}^n$ tal que:

$$
{}_{\mathcal{B_1}}(T_1)_{\mathcal{B_1}}={}_{\mathcal{B}}(T)_{\mathcal{B}}
$$

Observemos que como $T$ es autoadjunta y $\mathcal{B}$ es una base ortonormal, tenemos que ${}_{\mathcal{B}}(T)_{\mathcal{B}}$ es simétrica.

Ahora veamos el siguiente razonamiento:

$$
\begin{aligned}
&{}_{\mathcal{B_1}}(T_1)_{\mathcal{B_1}}\\
&=\scriptstyle{(\text{definición de }T_1)}\\
&{}_{\mathcal{B}}(T)_{\mathcal{B}}\\
&=\scriptstyle{(\text{por simetría})}\\
&({}_{\mathcal{B}}(T)_{\mathcal{B}})^t\\
&=\scriptstyle{(T\text{ es real})}\\
&\overline{({}_{\mathcal{B}}(T)_{\mathcal{B}})}^t\\
&=\scriptstyle{(T\text{definición de }T_1)}\\
&\overline{({}_{\mathcal{B_1}}(T_1)_{\mathcal{B_1}})}^t\\
\end{aligned}
$$

Por lo tanto, ${}_{\mathcal{B_1}}(T_1)_{\mathcal{B_1}}$ es hermítica, y por el teorema de inicio de clase, tenemos que $T_1$ es autoadjunta.

Con esto y el corolario anterior, $\Chi_{T_1}$ tiene raíces reales.

Como por construcción $\Chi_{T_1}=\Chi_T$, entonces $\Chi_T$ también tiene raíces reales.

Esto prueba el teorema.

#### Proposición

Sea $V$ un $\mathbb{K}$-espacio vectorial con producto interno y $T:V\to V$ un operador autoadjunto.
Consideremos dos vectores y valores propios distintos entre si:
- $v_1$ asociado a $\lambda_1$
- $v_2$ asociado a $\lambda_2$

Entonces $v_1\perp v_2$.

##### Demostración (proposición)

Consideremos el siguiente razonamiento:

$$
\begin{aligned}
&\left<T(v_1), v_2\right>=\left<v_1, T(v_2)\right>\\
&\iff\scriptstyle{(\text{definición de valor propio})}\\
&\left<\lambda_1 v_1, v_2\right>=\left<v_1,\lambda_2 v_2\right>\\
&\iff\scriptstyle{(\text{propiedades de producto interno y }\lambda_2\in\mathbb{R})}\\
&\lambda_1\left<v_1, v_2\right>=\lambda_2\left<v_1,v_2\right>\\
&\iff\scriptstyle{(\text{aritmética})}\\
&(\lambda_1-\lambda_2)\left<v_1, v_2\right>=0\\
&\iff\scriptstyle{(\lambda_1-\lambda_2\neq 0)}\\
&\left<v_1, v_2\right>=0\\
\end{aligned}
$$

Es decir que $v_1\perp v_2$