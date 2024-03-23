---
tags:
  - AM2
---
Toda la info se sacó de [Acá](https://www.youtube.com/watch?v=X2pYXeSdFIQ&list=PLM7ZBJfsXV3RhmUZUf2AJj3rOX5YlfmKZ&index=19&ab_channel=MartinMaulhardt)

Agarramos una curva, y la dividimos en puntos, luego, unimos todos esos puntos con líneas rectas, lógicamente, mientras más puntos agreguemos, mas nos acercamos al valor real de la longitud de la curva.

![[Pasted image 20231107175437.png]]

Suponiendo la curva **$C$** de ecuación $\overline{X} = \overline{g}(t)$ es suave entonces es recrificable y su longitud se calcula como:

$$\LARGE Long(C) = \int_{a}^{b} ||g’(t)|| dt$$

##### Ejemplo
![[Pasted image 20231107181711.png]]


### Integral de Línea de Campos Escalares

Sea $f: D \subset R^{n} \to R$ una función continua en $H$. Sea $C$ un arco de curva suave a trozos de ecuación $\overline{X} = \overline{g}(t)$ con $a \le t \le b$ y supongamos que $C \subset H$. Se llama integral de línea de $f$ a lo largo de $C$

$$\LARGE  \int_{C} f ds = \int_{a}^{b}f(\overline{g}(t)) \space||\overline{g’}(t)|| dt$$  
Lógicamente, en el caso en el que $f(\overline{X}) = 1$ ,
$$\Large Long(C) \ = \int_{C}\ ds = \int_{a}^{b} \  ||\overline{g’}(t)|| \ dt$$

A su vez, si $f$ es la densidad longitudinal de masa (también denotada $\large \delta$ ) en cada punto,
$$\Large Masa(C) \ = \int_{C}\ f \ ds $$

También, si $f$ es el costo por unidad de longitud en cada punto,
$$\Large Costo(C) \ = \int_{C}\ f \ ds $$
##### Valor Medio
El valor medio del campo escalar $f$ en $C$ es:
$$\LARGE f_{med} = \frac{1}{Long(C)} \ \int_{C}f\ ds$$

##### Ejemplo
![[Pasted image 20231107193736.png]]