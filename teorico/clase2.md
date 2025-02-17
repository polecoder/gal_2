# CLASE 2 - 17/02/2025

## Matrices semejantes

### Aplicaciones

1. La definición de matriz semejante es muy útil a la hora de calcular potencias; sean $A,B$ dos matrices semejantes, entonces:
    - $B^2 = (P^{-1}AP)(P^{-1}AP) = P^{-1}A^2P$

    En general:
    - $B^n = P^{-1}A^nP\quad\forall n\geq1$

    Esto puede ser útil cuando tenemos que alguna de las dos matrices $A,B$ tiene una forma más sencilla de elevar (por ejemplo que alguna sea diagonal)

### Teorema

Sea $A,B\in\mathcal{M}_{n\times n}$; decimos que $A,B$ son semejantes sii:

$\exists T:V\to V$; con $dim(V) = n$ y bases $\mathcal{C}, \mathcal{C'}$ tales que:

$$A= {}_{\mathcal{C}}(T)_{\mathcal{C}}\quad B={}_{\mathcal{C'}}(T)_{\mathcal{C'}}$$

#### Demostración

En el libro rojo

### Teorema

Si $A,B\in\mathcal{M}_{n\times n}$ son matrices semejantes. Entonces:

1. $rg(A) = rg(B)$
2. $tr(A) = tr(B)$
3. $det(A) = det(B)$

#### Demostración

##### PARTE 1

Por el anterior teorema, como $A,B$ son semejantes, entonces: $\exists T:V\to V$ y bases $C,C'$ tal que: $A = {}_{\mathcal{C}}(T)_{\mathcal{C}}$ y $B = {}_{\mathcal{C'}}(T)_{\mathcal{C'}}$

Entonces:

- $rg(A) = rg\left({}_{\mathcal{C}}(T)_{\mathcal{C}}\right) = dim(Im(T))$
- $rg(B) = rg\left({}_{\mathcal{C'}}(T)_{\mathcal{C'}}\right) = dim(Im(T))$

Por lo tanto:

$\Rightarrow rg(A) = rg(B)$

##### PARTE 2

**Recordatorio**: 
1. La traza es la suma de los elementos de la diagonal de la matriz
2. $tr(AB) = tr(BA)$

Veamos que:

$$
tr(B) = tr(P^{-1}AP) = tr(AP^{-1}P) = tr(A)
$$

##### PARTE 3:

**Recordatorio**:
$det(AB) = det(A)\cdot det(B)$

Entonces:

$$
det(B)=det(P^{-1}AP) = det(P^{-1})\cdot det(A)\cdot det(P) = det(A)
$$

#### Observación

El reciproco NO es cierto, veamos un ejemplo:

$A = \begin{pmatrix}1&0\\0&1\end{pmatrix}$ y $B = \begin{pmatrix}1&0\\1&1\end{pmatrix}$

Veamos que:

- $rg(A) = rg(B)$
- $tr(A) = tr(B)$
- $det(A) = det(B)$

Supongamos que SI son semejantes, es decir que: $\exists P$ tal que:

$$
B = P^{-1}AP = (I)
$$

Pero $B\neq (I)$, entonces esto es absurdo.

