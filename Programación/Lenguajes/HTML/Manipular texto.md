---
tags: Tutoriales, Borrable
---
## Cambiar Tamaños

To make the letter smaller in the provided code, you can adjust the font size for the specific part of the HTML where you want a smaller letter. You mentioned that you want to make the "letra" (letter) smaller. Here's an example of how you can modify the code to achieve that:

~~~html
<div class="text-center flex flex-col justify-center">
  <div class="text-4xl font-bold">{{header.letra}}</div> <!-- Adjusted font size here -->
  <div class="text-xs">{{header.codigo_identificatorio}}</div>
  <div class="whitespace-nowrap mt-3">{{header.emisor.condicion_iva}}</div>
</div>

~~~

In the modified code, I changed the `text-6xl` class to `text-4xl` for the "letra" (letter) element. This will decrease the font size, making the letter smaller while leaving the other elements unchanged. You can adjust the `4xl` value to your preferred size, with larger numbers indicating larger text sizes. This change should make the "letra" appear smaller compared to the other parts of the section.

## Mover posiciones absolutas

Se puede usar código como este para modificar las posiciones absolutas, pero por lo que parece, hay muchisimas formas diferentes en base a si es verdadermanete absoluta o es en relacion a otro elemento.

~~~html
<div style="margin-top: -20px;">
~~~

## Dibujar borde en un div

~~~html
<div style="border: 1px solid black; padding: 10px;">
~~~

## Posicion de un div

Evidentemente se pueden usar cosas como `height:60px;` 

```html
<div class="text-xs whitespace-nowrap mt-2 mb-6">
  <b>COD </b>
  {{header.codigo_identificatorio}}
</div>
```

Ejemplo de texto formatteado, la parte de `mt-2 mb-6` representa Margin top y Margin Bottom


## Horizontal Rule

Dibujar una Horizontal Rule es posible con:

```html
<hr class="col-span-3 border-t-2 border-gray-500"></hr>
```

Donde:
1. `col-span-3`: Esta clase indica que el elemento `<hr>` se extiende a lo largo de 3 columnas dentro de un diseño de cuadrícula CSS. Esto se usa típicamente cuando tienes un diseño basado en cuadrícula y deseas que un elemento ocupe múltiples columnas.
2. `border-t-2`: Esta clase agrega un borde superior al elemento `<hr>`, y el 2 representa el grosor del borde. En este caso, es un borde superior de 2 píxeles de grosor. 
3. `border-gray-500`: Esta clase establece el color del borde en una tonalidad de gris. El número 500 generalmente representa el nivel de tonalidad, siendo números más altos indicativos de tonos más oscuros.

## CSS Grid

Puedo hacer una grid rápidamente usando CSS Grid, así:

```html
 <div class="grid grid-cols-[1fr,0fr,1fr] gap-x-4 gap-y-2"> 
 </div>
```

1. `grid`: Esta parte de la clase indica que este elemento debe usar un diseño de cuadrícula.
    
2. `grid-cols-[1fr,0fr,1fr]`: Esta parte especifica las columnas de la cuadrícula. El valor es un array responsive que define los tamaños de las columnas. Aquí, está utilizando el siguiente formato: `[1fr, 0fr, 1fr]`.
    
    - `1fr` significa que la columna ocupa una parte igual del espacio disponible.
    - `0fr` significa que la columna ocupa el menor espacio posible, efectivamente haciéndola invisible.
    
    El array `[1fr, 0fr, 1fr]` indica una cuadrícula con tres columnas, donde las columnas exteriores ocupan una parte igual del espacio, y la columna central tiene un ancho de cero, lo que la hace efectivamente invisible.
3. `gap-x-4`: Esta parte especifica el espacio horizontal (espaciado) entre columnas. La clase `gap-x-4` indica un espaciado de `4` unidades entre columnas. Esto agrega un espaciado entre las columnas en el diseño de cuadrícula.
    
4. `gap-y-2`: Esta parte especifica el espacio vertical (espaciado) entre filas. La clase `gap-y-2` indica un espaciado de `2` unidades entre filas. Esto agrega un espaciado entre las filas en el diseño de cuadrícula.
    

En resumen, esta clase crea un diseño de cuadrícula con tres columnas, donde las columnas exteriores ocupan una parte igual del espacio, y la columna central tiene un ancho efectivo de cero (oculta). También añade un espaciado horizontal de `4` unidades y un espaciado vertical de `2` unidades entre columnas y filas, respectivamente. Este tipo de diseño puede ser útil para crear diseños específicos donde ciertas columnas deben estar ocultas o ocupar muy poco espacio, al mismo tiempo que se mantiene un espaciado visualmente atractivo entre elementos.


## Meta

Todo el código es en relación a lo visto en [[Nuevos Pdfs]]. Powered by CHATGPT

