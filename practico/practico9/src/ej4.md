# Ejercicio 4

## Consigna

Probar que $T$ es autoadjunto, hallar su forma diagonal y una base ortonormal de vectores propios:  

1. $T : \mathbb{R}^3 \to \mathbb{R}^3$ tal que:  
$$T(x,y,z) = \left(\frac{3}{2}x + \frac{1}{2}z, 2y, \frac{1}{2}x + \frac{3}{2}z\right)$$  

2. $T : \mathbb{R}^3 \to \mathbb{R}^3$ tal que:  
$$T(x,y,z) = \left(\frac{3}{2}x - \frac{1}{2}z, -y, -\frac{1}{2}x + \frac{3}{2}z\right)$$  

## Resolución

### Parte 1

Hallemos la matriz asociada ${}_{\mathcal{E}}(T)_{\mathcal{E}}$ considerando $\mathcal{E}$ como la base canónica de $\mathbb{R}^3$

- $T(1,0,0)=(\frac{3}{2},0,\frac{1}{2})$
- $T(0,1,0)=(0,2,0)$
- $T(0,0,1)=(\frac{1}{2},0,\frac{3}{2})$

Por lo tanto la matriz asociada es la siguiente:

$$
{}_{\mathcal{E}}(T)_{\mathcal{E}} = \frac{1}{2}\begin{pmatrix}3&0&1\\0&1&0\\1&0&3\end{pmatrix}
$$

Como la matriz es simétrica (estamos considerando una base ortonormal), entonces ${}_{\mathcal{E}}(T)_{\mathcal{E}}={}_{\mathcal{E}}(T^*)_{\mathcal{E}}$, lo que implica que $T=T^*$ y por lo tanto $T$ es autoadjunta.

Ahora tengo que hallar los valores propios, por lo que calculo el polinomio característico:

$$
\begin{aligned}
\Chi_T(\lambda)&=\frac{1}{2}\begin{vmatrix}3-\lambda&0&1\\0&1-\lambda&0\\1&0&3-\lambda\end{vmatrix}\\
&=(1-\lambda)((3-\lambda)^2+1)\\
&=(1-\lambda)(\lambda^2-6\lambda+10)
\end{aligned}
$$

Esto nos deja con las siguientes raíces características:

- $\lambda_1=1$
- $\lambda_2=3+i$
- $\lambda_3=3-i$

Ahora calculemos los subespacios:

#### $S_1$

Tenemos que resolver el siguiente sistema:

$(T-Id)v=0$:

$$
\left(\begin{array}{ccc|c}2&0&1&0\\0&0&0&0\\1&0&2&0\end{array}\right)\sim\left(\begin{array}{ccc|c}2&0&1&0\\2&0&4&0\\0&0&0&0\end{array}\right)\sim\left(\begin{array}{ccc|c}2&0&1&0\\0&0&3&0\\0&0&0&0\end{array}\right)
$$

De donde obtenemos que:

- $z=0$
- $x=0$
- $y\in\mathbb{R}$