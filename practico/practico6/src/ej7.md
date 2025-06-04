# Ejercicio 7

## Consigna

Sea $M_2(\mathbb{R})$ con el producto interno $\langle A, B \rangle = \operatorname{tr}(AB^t)$.

1. Hallar una base ortonormal de $M_2(\mathbb{R})$.  
2. Sea $D$ el subespacio de las matrices diagonales. Hallar $D^\perp$ 
3. Sea $S$ el subespacio de las matrices simétricas. Hallar $S^\perp$

## Resolución

### Parte 1

Consideremos la base canónica de $M_2(\mathbb{R})$:

$$
\mathcal{B}=\left\{\begin{pmatrix}1&0\\0&0\end{pmatrix},\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\1&0\end{pmatrix},\begin{pmatrix}0&0\\0&1\end{pmatrix}\right\}
$$

Veamos si la misma es una base ortonormal, para esto tenemos que calcular los siguientes productos internos:

- $\left<\begin{pmatrix}1&0\\0&0\end{pmatrix},\begin{pmatrix}0&1\\0&0\end{pmatrix} \right> = tr\left(\begin{pmatrix}1&0\\0&0\end{pmatrix}\cdot\begin{pmatrix}0&0\\1&0\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&0\\0&0\end{pmatrix}\right)=0$
- $\left<\begin{pmatrix}1&0\\0&0\end{pmatrix},\begin{pmatrix}0&0\\1&0\end{pmatrix} \right> = tr\left(\begin{pmatrix}1&0\\0&0\end{pmatrix}\cdot\begin{pmatrix}0&1\\0&0\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&1\\0&0\end{pmatrix}\right)=0$
- $\left<\begin{pmatrix}1&0\\0&0\end{pmatrix},\begin{pmatrix}0&0\\0&1\end{pmatrix} \right> = tr\left(\begin{pmatrix}1&0\\0&0\end{pmatrix}\cdot\begin{pmatrix}0&0\\0&1\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&0\\0&0\end{pmatrix}\right)=0$
- $\left<\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\1&0\end{pmatrix} \right> = tr\left(\begin{pmatrix}0&1\\0&0\end{pmatrix}\cdot\begin{pmatrix}0&1\\0&0\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&0\\0&0\end{pmatrix}\right)=0$
- $\left<\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\0&1\end{pmatrix} \right> = tr\left(\begin{pmatrix}0&1\\0&0\end{pmatrix}\cdot\begin{pmatrix}0&0\\0&1\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&1\\0&0\end{pmatrix}\right)=0$
- $\left<\begin{pmatrix}0&0\\1&0\end{pmatrix},\begin{pmatrix}0&0\\0&1\end{pmatrix} \right> = tr\left(\begin{pmatrix}0&0\\1&0\end{pmatrix}\cdot\begin{pmatrix}0&0\\0&1\end{pmatrix}\right)=tr\left(\begin{pmatrix}0&0\\0&0\end{pmatrix}\right)=0$

Con esto comprobamos que la base es ortogonal, sumando que todas las normas de los vectores son 1, concluimos que la base es ortonormal.

### Parte 2

Consideremos $\mathcal{D}$, el subespacio de las matrices diagonales, lo definimos de la siguiente forma, junto a $\mathcal{D}^{\perp}$:

- $\mathcal{D}=\left\{\begin{pmatrix}\alpha&0\\0&\beta\end{pmatrix}:\alpha,\beta\in\mathbb{R}\right\}$
- $\mathcal{D}^{\perp}=\{A\in M_2(\mathbb{R}): \left<A, D\right>=0\quad\forall D\in \mathcal{D}\}$

Por lo tanto, veamos el siguiente razonamiento:

$$
\begin{aligned}
&\left<A, D\right>=0\\
&\iff\scriptstyle{(\text{cálculo de producto interno})}\\
&tr\left(\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix}\cdot\begin{pmatrix}\alpha&0\\0&\beta\end{pmatrix}\right)=0\\
&\iff\scriptstyle{(\text{desarrollo})}\\
&tr\begin{pmatrix}\alpha a_{11}&\beta a_{12}\\\alpha a_{21}&\beta a_{22}\end{pmatrix}=0\\
&\iff\scriptstyle{(\text{cálculo de la traza})}\\
&\alpha a_{11}+\beta a_{22}=0\\
&\iff\scriptstyle{(\text{desarrollo})}\\
&\alpha a_{11}=-\beta a_{22}\\
\end{aligned}
$$

Necesitamos que esto último se cumpla para todo $\alpha,\beta\in\mathbb{R}$, por lo tanto de esto derivamos que:

- $a_{11}=0$
- $a_{22}=0$

Como no tenemos requisitos para los demás elementos de la matriz, podemos definir el conjunto $\mathcal{D}^{\perp}$:

$$
\mathcal{D}^{\perp}=\left\{\begin{pmatrix}0&\alpha\\\beta&0\end{pmatrix}:\alpha,\beta\in\mathbb{R}\right\}\\
D^{\perp}=\left\{\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\1&0\end{pmatrix}\right\}
$$

### Parte 3

Consideremos $\mathcal{S}$, el subespacio de las matrices diagonales, lo definimos de la siguiente forma, junto a $\mathcal{S}^{\perp}$:

- $\mathcal{S}=\left\{\begin{pmatrix}\alpha&\gamma\\\gamma&\beta\end{pmatrix}:\alpha,\beta,\gamma\in\mathbb{R}\right\}$
- $\mathcal{S}^{\perp}=\{A\in M_2(\mathbb{R}): \left<A, S\right>=0\quad\forall S\in \mathcal{S}\}$

Por lo tanto, veamos el siguiente razonamiento:

$$
\begin{aligned}
&\left<A, S\right>=0\\
&\iff\scriptstyle{(\text{cálculo de producto interno})}\\
&tr\left(\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix}\cdot\begin{pmatrix}\alpha&\gamma\\\gamma&\beta\end{pmatrix}\right)=0\\
&\iff\scriptstyle{(\text{desarrollo})}\\
&tr\begin{pmatrix}\alpha a_{11}+\gamma a_{12}&\gamma a_{11}+\beta a_{12}\\\alpha a_{21}+\gamma a_{22}&\gamma a_{21}+\beta a_{22}\end{pmatrix}=0\\
&\iff\scriptstyle{(\text{cálculo de la traza})}\\
&\alpha a_{11}+\gamma a_{12}+\gamma a_{21}+\beta a_{22}=0\\
&\iff\scriptstyle{(\text{desarrollo})}\\
&\alpha a_{11}+\beta a_{22}+\gamma(a_{12}+a_{21})=0\\
\end{aligned}
$$

Necesitamos que esto último se cumpla para todo $\alpha,\beta,\gamma\in\mathbb{R}$, por lo tanto de esto derivamos que:

- $a_{11}=0$
- $a_{22}=0$
- $a_{12}=-a_{21}$

Como no tenemos requisitos para los demás elementos de la matriz, podemos definir el conjunto $\mathcal{S}^{\perp}$:

$$
\mathcal{S}^{\perp}=\left\{\begin{pmatrix}0&\alpha\\-\alpha&0\end{pmatrix}:\alpha,\beta\in\mathbb{R}\right\}\\
\mathcal{S}^{\perp}=\left\{\begin{pmatrix}0&1\\0&0\end{pmatrix},\begin{pmatrix}0&0\\-1&0\end{pmatrix}\right\}
$$