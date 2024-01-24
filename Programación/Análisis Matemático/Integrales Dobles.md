### Teorema de Fubini

Sea $f : H = [a, b] \space x \space [c, d] \subset R^{2} \to R$  una funcion acotada, entonces: $$\LARGE \iint_{H}f(x, y )\space dx \space dy \space = \space \int_a^b (\int_{c}^{d} f(x,y)\ dy)dx$$
Es decir, una Integral tiple es simplemente la integrar una y luego otra. El orden es importante, por lo que $$\LARGE \int_a^b (\int_{c}^{d} f(x,y)\ dy)dx = \space \int_c^d (\int_{a}^{b} f(x,y)\ dx)dy$$

##### Ejemplo
 
Calcule $\iint_H (xy+2y)\ dxdy$  con $H\ = \ \{(xy) \in R^{2}\ :\ 3 \le x \le 4 \ \& \ 0 \le y \le 2 \}$  

![[Pasted image 20240123205322.png]]


### Nociones de Aplicaciones

- Si $f(x,y) = 1$ entonces: $$\LARGE Área(D) = \iint_{D}dxdy$$
- Si $\delta (x,y) =$ "densidad superficial de masa" entonces: $$Masa(D) \ = \ \iint_{D}\delta(x,y) dxdy$$
