# Ejercicio 2

## Consigna

Sea la matriz
$$
A = \begin{pmatrix}
6 & 1 & 1 & -2 \\
1 & 14 & 1 & 1 \\
2 & 2 & -9 & -1 \\
1 & -1 & 1 & -20
\end{pmatrix}
$$

1. Probar que $A$ es diagonalizable.
2. Determinar el signo de los valores propios de $A$ y deducir que es invertible.

## Resolución (parte a)

Probemos que $A$ es diagonalizable, para esto podemos usar el teorema de Gershgorin, hallemos los círculos:

- $C_1:$ círculo centrado en $6$ con radio $4$.
- $C_2:$ círculo centrado en $14$ con radio $3$.
- $C_3:$ círculo centrado en $-9$ con radio $5$.
- $C_4:$ círculo centrado en $-20$ con radio $3$.

Formalmente, podemos expresarlos como:

- $C_1 = \{ z \in \mathbb{C} : |z - 6| \leq 4 \}$
- $C_2 = \{ z \in \mathbb{C} : |z - 14| \leq 3 \}$
- $C_3 = \{ z \in \mathbb{C} : |z + 9| \leq 5 \}$
- $C_4 = \{ z \in \mathbb{C} : |z + 20| \leq 3 \}$

Gráficamente se verían algo así:

![Figura 1](images/ej2fig1.png)

El teorema de Gershgorin nos dice que al ser todos disjuntos, tenemos un único valor propio por círculo, por lo que $A$ tiene $4$ valores propios distintos, por lo que es diagonalizable.
Además, podemos concluir que los valores propios son todos reales, ya que de otra manera tendríamos dos raíces conjugadas en un mismo círculo.

## Resolución (parte b)

Llamemos $\lambda_i$ al valor propio correspondiente al círculo $C_i$.
En base a los círculos, podemos decir que:

- $\lambda_1 \in C_1 \Rightarrow 2 \leq \lambda_1 \leq 10$
- $\lambda_2 \in C_2 \Rightarrow 11 \leq \lambda_2 \leq 17$
- $\lambda_3 \in C_3 \Rightarrow -14 \leq \lambda_3 \leq -4$
- $\lambda_4 \in C_4 \Rightarrow -23 \leq \lambda_4 \leq -17$

Para saber si la matriz es invertible, basta con ver que todos los valores propios son distintos de $0$, lo cual se cumple ya que todos los valores propios son distintos de $0$.

En conclusión, la matriz es invertible.