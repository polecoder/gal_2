# Ejercicio 2 - Examen Julio 2024

## Consigna

### Ejercicio 2  
Se considera la matriz  

$$
A = 
\begin{pmatrix}
5 & 0 & 0 \\
0 & -1 & \beta \\
3 & 0 & \alpha
\end{pmatrix} \in M_{3 \times 3}(\mathbb{R})
$$  

donde $\alpha, \beta \in \mathbb{R}$.  

Indicar la opción correcta:  

**A.** Existe un único valor de $\alpha$ y un único valor de $\beta$ para los cuales la matriz $A$ **NO** es diagonalizable.  
**B.** Existe un único valor de $\alpha$ pero infinitos valores de $\beta$ para los cuales la matriz $A$ **NO** es diagonalizable.  
**C.** Existen exactamente dos valores de $\alpha$ para los cuales la matriz $A$ **NO** es diagonalizable $\forall \beta \in \mathbb{R}$.  
**D.** Existe un único valor $\alpha$ para el cual la matriz $A$ **NO** es diagonalizable $\forall \beta \in \mathbb{R}$.

## Resolución

Calculemos el polinomio característico $\Chi_A(\lambda)$:

$$
\begin{aligned}
\Chi_A(\lambda)&=\begin{vmatrix}
5-\lambda & 0 & 0 \\
0 & -1-\lambda & \beta \\
3 & 0 & \alpha-\lambda\\
\end{vmatrix}\\
&=(5-\lambda)\begin{vmatrix}
-1-\lambda&\beta\\
0&\alpha-\lambda\\
\end{vmatrix}\\
&=(5-\lambda)(1-\lambda)(\alpha-\lambda)
\end{aligned}
$$

De donde obtenemos que los valores propios son:

- $\lambda_1=5$
- $\lambda_2=-1$
- $\lambda_3=\alpha$

Si $\alpha\neq 5$ y $\alpha\neq -1$ entonces $A$ es diagonalizable porque tenemos 3 valores propios distintos dos a dos.

Analicemos los dos casos que quedan.

**CASO 1: $\alpha=-1$**

Deberíamos verificar que $ma(-1)=mg(-1)=2$, por lo que investiguemos sobre el subespacio propio.

Tenemos que resolver el siguiente sistema:

- $(A+Id)v=0$

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
6 & 0 & 0 & 0\\
0 & 0 & \beta & 0\\
3 & 0 & 0 & 0\\
\end{array}
\right)\\
\end{aligned}
$$

De esto, la única forma de que $mg(-1)=2$ es que $\beta=0$.

Por lo tanto $T$ es diagonalizable en este caso sii $\beta=0$

**CASO 2: $\alpha=5$**

Deberíamos verificar que $ma(5)=mg(5)=2$, por lo que investiguemos sobre el subespacio propio.

Tenemos que resolver el siguiente sistema:

- $(A-5Id)v=0$

$$
\begin{aligned}
&\left(
\begin{array}{ccc|c}
0 & 0 & 0 & 0\\
0 & -6 & \beta & 0\\
3 & 0 & 0 & 0\\
\end{array}
\right)\\
\end{aligned}
$$

De donde obtenemos que:

- $x=0$
- $y=\frac{\beta z}{6}$
- $z\in\mathbb{R}$

Observemos que sin importar el valor de $\beta$, $mg(5)=1$, por lo que $T$ no es diagonalizable para ningún valor de $\beta$ en este caso.

Por lo que la opción correcta es la opción **D**