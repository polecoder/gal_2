# Ejercicio 5

## Consigna

Sea $V$ un espacio con producto interno y $\|\cdot\|$ su norma inducida. Probar:

1. **Regla del paralelogramo**:  
   $\|v + w\|^2 + \|v - w\|^2 = 2\|v\|^2 + 2\|w\|^2$

2. **Polarización**:  
   $4\langle v, w \rangle = \|v + w\|^2 - \|v - w\|^2$

3. ¿Cuál de estas propiedades vale en espacios complejos?

## Resolución

### Parte 1

Queremos probar que para cualquier $v,w\in V$ se cumple que:

$$
\|v + w\|^2 + \|v - w\|^2 = 2\|v\|^2 + 2\|w\|^2
$$

Considerando la norma inducida por el producto interno. Desarrollemos:

$$
\begin{aligned}
&\|v+w\|^2 + \|v-w\|^2\\
&= \scriptstyle{(\text{definición de norma inducida})}\\
&\left<v+w, v+w\right> + \left<v-w, v-w\right>\\
&= \scriptstyle{(\text{definición de producto interno})}\\
&\left<v, v\right> + \left<v, w\right> + \left<w, v\right> + \left<w, w\right> + \\
&\left<v, v\right> - \left<v, w\right> - \left<w, v\right> + \left<w, w\right>\\
&= \scriptstyle{(\text{operatoria})}\\
&2\left<v, v\right> + 2\left<w, w\right>\\
&= \scriptstyle{(\text{definición de norma inducida})}\\
&2\|v\|^2 + 2\|w\|^2
\end{aligned}
$$

Esto prueba lo que queríamos verificar.

### Parte 2

Queremos probar que para cualquier $v,w\in V$ se cumple que:

$$
4\langle v, w \rangle = \|v + w\|^2 - \|v - w\|^2
$$

Considerando la norma inducida por el producto interno. Desarrollemos:

$$
\begin{aligned}
&\|v+w\|^2 - \|v-w\|^2\\
&= \scriptstyle{(\text{definición de norma inducida})}\\
&\left<v+w, v+w\right> - \left<v-w, v-w\right>\\
&= \scriptstyle{(\text{definición de producto interno})}\\
&\left<v, v\right> + \left<v, w\right> + \left<w, v\right> + \left<w, w\right> + \\
&- \left<v, v\right> + \left<v, w\right> + \left<w, v\right> - \left<w, w\right>\\
&= \scriptstyle{(\text{operatoria})}\\
&4\left<v, w\right>\\
\end{aligned}
$$

Esto prueba lo que queríamos verificar.

### Parte 3

Podemos observar fácilmente que la que si se cumple es la regla del paralelogramo, ya que aunque los vectores sean complejos, las partes "imaginarias" se cancelan en el desarrollo.

Sin embargo se ve que la regla de polarización no se cumplirá cuando $\left<v, w\right>$ tenga parte imaginaria.