*[Source](https://www.youtube.com/watch?v=G68rZeEkJUo&list=PLM7ZBJfsXV3RhmUZUf2AJj3rOX5YlfmKZ&index=20&ab_channel=MartinMaulhardt)*
##### Diferencial vectorial de longitud de arco
Recordemos que si $C$ es suave y de ecuación $\overline{X} 0 \overline{g}(t)$ definimos que:
$$\LARGE s \ = \ \int_{t0}||\overline{g’}(t)|| \ dt \Rightarrow ds = ||\overline{g’}(t) ||\ dt$$
A esto lo llamamos [[Abscisa Curvilínea]]. Consideramos a $ds$ una longitud tan pequeño como pueda ser imaginado.

##### Integral de línea de campos vectoriales
Sea $\vec{f} : H \subset R^{n} \ \to \ R^n$ un campo vectorial coninuo en $H$.
Sea $C \subset H$ suave de ecuación $\overline{X} = \overline{g}(t)$. Se llama integral de línea de $\vec{F}$ sobre la curva $C$ o circulación de $\vec{F}$ sobre $C$
$$\LARGE \int_{C}\vec{F} . d\overline{s} \ = \ \int_{a}^{b}\vec{F}(\overline{g}(t))\ . \ \overline{g’}(t)dt$$

##### Ejemplo
![[Pasted image 20231108183536.png]]

- $\overline{g}$ debe estar [[Paramterización|parametrizada]]
- $a$ y $b$  se consiguen de los extremos ( $t \in [0,2]$ ).

##### Propiedades de la integral de línea
- Influencia de la parametrización.
	- **Campo escalar** $f$ : Parametrizando $C$ de manera que sea "suave y simple" la integral no depende de la parametrización que se utilice. $$\LARGE \int_{C_{AB}}\ \ F\ ds \ =\ \int_{C_{BA}}\ F\ ds $$
	- **Campo Vectorial** $\overline{F}$ : Parametrizando $C$ de manera que sea "suave y simple" la integral no depende de la parametrización *siempre que se respete su orientación.* De no ser así tendra el signo contrario$$\LARGE \int_{C_{AB}}\ \vec{F}\ d\vec{s} \ =\ -\int_{C_{BA}}\ \vec{F}\ d\vec{s} $$

##### Sentido positivo de Circulación
![[Pasted image 20231108185537.png]]