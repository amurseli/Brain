### Teorema de Fubini

Sea $f : H = [a, b] \space x \space [c, d] \subset R^{2} \to R$  una funcion acotada, entonces: $$\LARGE \iint_{H}f(x, y )\space dx \space dy \space = \space \int_a^b (\int_{c}^{d} f(x,y)\ dy)dx$$
Es decir, una Integral tiple es simplemente la integrar una y luego otra. El orden es importante, por lo que $$\LARGE \int_a^b (\int_{c}^{d} f(x,y)\ dy)dx = \space \int_c^d (\int_{a}^{b} f(x,y)\ dx)dy$$

##### Ejemplo
 
Calcule $\iint_H (xy+2y)\ dxdy$  con $H\ = \ \{(xy) \in R^{2}\ :\ 3 \le x \le 4 \ \& \ 0 \le y \le 2 \}$  

![[Pasted image 20240123205322.png]]


### Nociones de Aplicaciones

- Si $f(x,y) = 1$ entonces: $$\LARGE Área(D) = \iint_{D}dxdy$$
- Si $\delta (x,y) =$ "densidad superficial de masa" entonces: $$Masa(D) \ = \ \iint_{D}\delta(x,y) dxdy$$

# Cambio de Variables con Integrales Dobles y Triples

## Coordenadas Polares y Cilíndricas

Es usar radio r y angulo $\theta$ para definir cada punto de la función. Entonces, se cambia así: $$\begin{cases} x = r\cos{\theta} \\ y = r\sin{\theta} \end{cases}$$  Por último, es imprescindible agregar el jacobiano a la expresión con las variables cambiadas. $$\LARGE \iint_{D}\ f(x,y) \ dxdy \ = \ \iint_{D^{*}} \ f(x(r,\theta), y(r,\theta)) \ |J|\ drd\theta$$
Siendo $D{^*}$ El dominio delimitado por las nuevas variables, y $J$ el jacobiano, calculado como: $$\LARGE \left| \begin{array}{ccc} \frac{df_1}{dx_{1}} & \frac{df_1}{dx_{2}} \\ \frac{df_2}{dy_{1}} & \frac{df_2}{dy_{2}}  \end{array}   \right|$$
Es decir, con el cambio de variable a coordenadas polares, quedaría así
$$\LARGE \left| \begin{array}{ccc} \cos(\theta) & -r\sin(\theta) \\ \sin(\theta) & r\cos(\theta)  \end{array}   \right|$$ y su determinate sería, en este caso, solamente $r$.

Este cambio de variables es relevante cuando es necesario integrar un dominio como un cono, ahí este cambio es casi necesario.

Las coordenadas cilíndricas son lo mismo, pero para una integral triple. La única diferencia es que la nueva coordenada $z$ se mantiene igual sin importar el cambio de $x$ e $y$. El jacobiano permanece igual, minetras que usemos la forma simple, sin mover el dominio de ninguna forma.