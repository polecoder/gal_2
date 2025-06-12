# Ejercicio 1

## Consigna

Sea $A \in M_{m \times n}(\mathbb{R})$.

1. Probar que $Im(A)^\perp = Ker(A^t)$; es decir, que si $S$ es el subespacio de $\mathbb{R}^m$ generado por las columnas de $A$, entonces:  
   $$
   S^\perp = \{ X \in \mathbb{R}^m : A^t X = \vec{0} \}
   $$
2. Dado $Y \in \mathbb{R}^m$ y $S = Im(A)$, probar que $s = P_S(Y)$ si y sólo si $s = AX_0$ con $X_0 \in \mathbb{R}^n$ y  
   $$
   (A^t A) X_0 = A^t Y
   $$
3. Dado $Y \in \mathbb{R}^m$, concluir que el vector que minimiza $\|Y - AX\|$ es la solución del sistema:  
   $$
   (A^t A) X = A^t Y
   $$

## Resolución

### Parte 1

La prueba de esta parte está hecha en la clase de teórico #15.

### Parte 2

Sean $Y\in\mathbb{R}^m$ y $S=Im(A)$, queremos probar que:

$$
s=P_S(Y)\iff s=AX_0 \quad\text{con }X_0\in\mathbb{R}^n\text{ y además}\\
(A^t A) X_0 = A^t Y
$$

#### $(\Rightarrow)$

Para que $s=P_S(Y)$ se tienen que cumplir las siguientes afirmaciones.
- Como $s\in S$, $s\in Im(A)$ pues $S=Im(A)$. Entonces $s=AX_0$ para algún $X_0\in\mathbb{R}^n$
- Por propiedades del complemento ortogonal, tenemos que dados $Y\in\mathbb{R}^n,AX_0\in Im(A)$, se cumple que $Y-AX_0\in Im(A)^{\perp}=Ker(A^t)$ (usando la propiedad 1).
- Como $Y-AX_0\in Ker(A^t)$, tenemos que $A^t(Y-AX_0)=\vec{0}$, lo que equivale a decir que:

    $$
    \begin{aligned}
    &A^tY-A^tAX_0=\vec{0}\\
    &\iff\scriptstyle{(\text{despejando})}\\
    &A^tY=A^tAX_0
    \end{aligned}
    $$

Esto prueba el implica a partir de asumir que $s=P_S(Y)$

#### $(\Leftarrow)$

En esta parte asumimos que:
- $s=AX_0$ con $X_0\in\mathbb{R}^n$
- $(A^t A) X_0 = A^t Y$

De la segunda igualdad derivamos fácilmente que $Y-AX_0\in Ker(A^t)=Im(A)^{\perp}$, entonces $s=P_S(Y)$

### Parte 3

También visto en el teórico, el concepto importante detrás de esto es que la proyección ortogonal en un conjunto $S$ dado de un vector, es lo más cercano en distancia al mismo, dentro del conjunto $S$.