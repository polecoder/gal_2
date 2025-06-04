# Ejercicio 6

## Consigna

Se considera el espacio $\mathbb{R}^3$ con el producto interno definido por:  
- $\langle x, y \rangle = 2x_1y_1 + x_2y_2 + x_3y_3$

donde $x = (x_1, x_2, x_3)$ e $y = (y_1, y_2, y_3)$, y el subespacio $S$ generado por el vector $(1, 1, 1)$.  
Hallar una base ortogonal de $S^\perp$.  

**Opciones**:

1. $\{(3,−4, 1), (1, 1,−2)\}$
2. $\{(1, 0, 1), (−1, 0, 1)\}$
3. $\{(0, 1,−1), (−1, 1, 1)\}$
4. $\{(2,−1,−1), (0, 1,−1)\}$
5. $\{(−1, 0, 2), (2,−5, 1)\}$

## Resolución

La mejor forma de resolver este ejercicio es comprobando que las bases cumplan las propiedades que tienen que cumplir:

### Opción 1

Queremos verificar que:

- $\left<(3,-4,1), (1,1,1)\right>=0$
- $\left<(1,1,-2), (1,1,1)\right>=0$
- $\left<(3,-4,1), (1,1,-2)\right>=0$

Si alguno de estos no se cumple, entonces no será una base ortogonal válida para $S^{\perp}$:

- $\left<(3,-4,1),(1,1,1)\right>=6-4+1=3\neq0$

Entonces, esta opción no es válida.

### Opción 2

Queremos verificar que:

- $\left<(1, 0, 1), (1,1,1)\right>=0$
- $\left<(-1, 0, 1), (1,1,1)\right>=0$
- $\left<(1, 0, 1), (−1, 0, 1)\right>=0$

Si alguno de estos no se cumple, entonces no será una base ortogonal válida para $S^{\perp}$:

- $\left<(1, 0, 1), (1,1,1)\right>=2+0+1=3\neq0$

Entonces, esta opción no es válida.

### Opción 3

Queremos verificar que:

- $\left<(0, 1,−1), (1,1,1)\right>=0$
- $\left<(-1, 1, 1), (1,1,1)\right>=0$
- $\left<(0, 1,−1), (−1, 1, 1)\right>=0$

Si alguno de estos no se cumple, entonces no será una base ortogonal válida para $S^{\perp}$:

- $\left<(0, 1,−1), (1,1,1)\right>=0+1-1=0$
- $\left<(-1, 1, 1), (1,1,1)\right>=-2+1+1=0$
- $\left<(0, 1,−1), (−1, 1, 1)\right>=0+1-1=0$

Esta opción es la correcta, pues ambos sus vectores son ortogonales a todos los vectores de $S$, además la base es ortogonal pues los vectores que la componen son ortogonales entre si.
A pesar de esto seguimos validando las demás opciones como práctica.

### Opción 4

Queremos verificar que:

- $\left<(2,−1,−1), (1,1,1)\right>=0$
- $\left<(0, 1,−1), (1,1,1)\right>=0$
- $\left<(2,−1,−1), (0, 1,−1)\right>=0$

Si alguno de estos no se cumple, entonces no será una base ortogonal válida para $S^{\perp}$:

- $\left<(2,−1,−1), (1,1,1)\right>=4-1-1=2\neq0$

Entonces, esta opción no es válida.

### Opción 5

Queremos verificar que:

- $\left<(−1, 0, 2), (1,1,1)\right>=0$
- $\left<(2,−5, 1), (1,1,1)\right>=0$
- $\left<(−1, 0, 2), (2,−5, 1)\right>=0$

Si alguno de estos no se cumple, entonces no será una base ortogonal válida para $S^{\perp}$:

- $\left<(−1, 0, 2), (1,1,1)\right>=-2+0+2=0$
- $\left<(2,−5, 1), (1,1,1)\right>=4-5+1=0$
- $\left<(−1, 0, 2), (2,−5, 1)\right>=-4+0+2=-2\neq0$

Entonces, esta opción no es válida.