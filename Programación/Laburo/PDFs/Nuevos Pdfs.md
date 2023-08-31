Pasamos de usar los pdfs con el sistema de [[Reyngardt]] , a un sistema nuevo que utiliza [[Html]].

La repositorio esta en el [[Lambda]] de AWS "Emisor-Factura". La estructura del template del Html es la siguiente. Los pdfs usan [[Handlebars]] para generar contenido dinámico desde las [[Query|Querys]] del [[SQL]].

## Container y Paginador

1. **container-template**: Esta plantilla define un contenedor `<div>` con clases de diseño flexbox y otros estilos. Utiliza una estructura condicional (`{{#if outputIsHtml}} ... {{else}} ... {{/if}}`) para determinar si se debe aplicar una clase CSS específica (`h-full`) en función del valor de la variable `outputIsHtml`.

2. **page-number-template**: Esta plantilla representa un contenedor que parece diseñado para mostrar números de página junto con una imagen de fondo. La primera línea coloca el número de página en la esquina inferior derecha del contenedor. La segunda parte coloca una imagen de fondo que se obtiene de un objeto `images` con una propiedad `fondo`. La imagen se ajustará a la caja que contiene.

## Header

Define la información de la factura con un grid layout, como:
**Datos del Emisor (header.emisor)**:

- `razon_social`: Razón social del emisor.
- `domicilio`: Domicilio del emisor.
- `cuit`: CUIT del emisor.
- `ingresos_brutos`: Número de Ingresos Brutos del emisor.
- `inicio_actividades`: Fecha de inicio de actividades del emisor.
- `condicion_iva`: Condición de IVA del emisor.

**Datos del Cliente (header.cliente)**:

- `razon_social`: Razón social del cliente.
- `domicilio`: Domicilio del cliente.
- `cuit`: CUIT del cliente.
- `condicion_iva`: Condición de IVA del cliente.

**Otros Datos del Encabezado (header)**:

- `letra`: Letra de la factura.
- `codigo_identificatorio`: Código identificatorio de la factura.
- `tipo_factura`: Tipo de factura.
- `numero_factura`: Número de la factura.
- `fecha_factura`: Fecha de la factura.
- `moneda`: Moneda utilizada en la factura.
- `cotizacion`: Cotización de la moneda.
- `provincia_destino`: Provincia de destino.
- `fecha_vencimiento`: Fecha de vencimiento.
- `forma_pago`: Forma de pago.

## Details

- La plantilla comienza con un ciclo `{{#each items}}` que recorre cada objeto dentro de la lista `items`.
    
- Dentro del ciclo, se define un `<template>` que contiene una fila de tabla (`<tr>`) con una altura fija (`h-10`) para cada artículo.
    
- Dentro de la fila de la tabla, se definen celdas de datos (`<td>`) para cada campo del artículo, como el código, el nombre del artículo, las observaciones, la cantidad, el precio, el descuento (si está habilitado), el importe, el valor del IVA y el importe con IVA.
    
- Cada celda de datos contiene `{{this.nombre_del_campo}}`, lo que indica que se llenará con el valor correspondiente del objeto actual en la iteración.
    
- El bloque `{{#if opciones.descuento}}` verifica si la opción de descuento está habilitada. Si es así, se muestra una celda para el descuento.
    
- La plantilla completa cierra el ciclo `{{/each}}`, lo que significa que este proceso se repetirá para cada artículo en la lista `items`.

## Footer
Esta parte se utiliza para generar la sección de pie de página de un documento, que muestra información relevante sobre los impuestos, los importes totales, los métodos de pago electrónico y, en caso de ser necesario, detalles relacionados con el código QR generado por AFIP para facturas electrónicas.

- **Subtotales e Impuestos por Porcentaje de IVA**: Esta sección muestra los subtotales de la factura desglosados por los diferentes porcentajes de IVA aplicados (0%, 2.5%, 5%, 10.5%, 21% y 27%). Además, se muestra el valor del IVA correspondiente para cada porcentaje. Si el subtotal es cero, no se muestra. El fondo de esta sección está sombreado y dividido con una línea horizontal.
    
- **Percepciones**: Aquí se presenta una tabla con diferentes tipos de percepciones y sus respectivos valores. Cada percepción se muestra en una fila, con su nombre y valor.
    
- **Importes Totales**: Esta parte muestra los importes totales de la factura, incluyendo el bruto (subtotal), los impuestos, las percepciones y el total general. Estos valores se muestran alineados a la derecha. También hay un fondo sombreado y una línea divisoria.
    
- **Memo**: Se muestra un bloque de texto de tamaño reducido que contiene información adicional o comentarios relevantes. El tamaño de fuente es más pequeño (text-xs).
    
- **Métodos de Pago Electrónico**: Aquí se muestran los métodos de pago electrónico disponibles. Cada método se presenta como un ícono de código de barras junto con el logotipo del proveedor de pago asociado.
    
- **Código QR de AFIP (Administración Federal de Ingresos Públicos)**: Si hay un código QR generado por AFIP presente, se muestra en esta sección junto con detalles adicionales como el CAE (Código de Autorización Electrónico) y la fecha de vencimiento del CAE. Además, se muestra una imagen del comprobante autorizado por AFIP.