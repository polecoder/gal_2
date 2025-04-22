# Ejercicio 6

## Consigna

1. En $\mathbb{C}^3$ con producto interno habitual, sean $v = (2, 1+i, i)$ y $w = (2-i, 2, 1+2i)$. Calcular:  
   - $\langle v, w \rangle$, $\|v\|^2$, $\|w\|^2$, $\|v + w\|^2$.  
   - Verificar **Cauchy-Schwarz** y **desigualdad triangular**.  

2. En $C[0, 1]$ con $\langle f, g \rangle = \int_0^1 f(t)g(t)dt$, sean $f(t) = t$ y $g(t) = e^t$. Calcular:  
   - $\langle f, g \rangle$, $\|f\|^2$, $\|g\|^2$, $\|f + g\|^2$.  
   - Verificar **Cauchy-Schwarz** y **desigualdad triangular**.  

## Resolución

### Parte 1

Considerando el producto interno habitual en $\mathbb{C}^n$:

$$
\left<v, w\right> = \sum_{i=1}^{n}v_i\overline{w_i}
$$

Calculemos lo indicado en la letra:

- $\left<v, w\right>=\left<(2,1+i,i), (2-i,2,1+2i)\right> = 2\overline{(2-i)}+(1+i)\overline{2} + i\overline{(1+2i)}= 4+2i+2+2i+i+2=8+5i$
- $\|v\|^2 = \left<v, v\right> = \left<(2,1+i,i), (2,1+i,i)\right> = 4 + (1+i)\overline{(1-i)} + 1 = 7$
- $\|w\|^2=\left<w, w\right>=\left<(2-i,2,1+2i), (2-i,2,1+2i)\right> = (2-i)\overline{(2-i)} + 4 + (1+2i)\overline{(1+2i)} = 5 + + 4 + 1 + 4 = 14$
- $\|v+w\|^2 = \left<v, v\right> + \left<v, w\right> + \overline{\left<v, w\right>} + \left<w, w\right> = 7+8+5i+8-5i+14 = 37$

Verifiquemos las dos desigualdades que nos faltan:

**Cauchy-Schwarz:**

$$
|\left<v, w\right>| \leq \|v\|\|w\|\iff\\
|\left<v, w\right>|^2 \leq \|v\|^2\|w\|^2\iff\\
|8+5i|^2\leq 7\cdot 14\iff\\
8^2+5^2\leq 98\iff\\
89\leq 98
$$

Por lo tanto esto se cumple.

**Desigualdad triangular:**

$$
\|v+w\| \leq \|v\|+\|w\|\iff\\
\sqrt{37}\leq \sqrt{7}+\sqrt{14}\iff\\
\sqrt{37}^2\leq (\sqrt{7}+\sqrt{14})^2\iff\\
37\leq 7+2\sqrt{7}\sqrt{14}+14\iff\\
16\leq 2\sqrt{98}\iff\\
8\leq \sqrt{98}\iff\\
64\leq 98
$$

Cómo lo último se cumple, verificamos que la desigualdad triangular se cumple.