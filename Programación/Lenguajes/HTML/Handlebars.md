Las Handlebars son un sistema de plantillas para HTML y otros lenguajes web. Permiten generar contenido dinámico en páginas web al combinar datos con la estructura del documento. Utilizan una sintaxis especial en la que se definen marcadores o placeholders en el HTML, que luego son reemplazados por valores provenientes de objetos de datos en el lado del servidor o en el navegador.

La documentación oficial esta [acá](https://handlebarsjs.com/guide/).

### Log
The `log` helper allows for logging of context state while executing a template.
```html
 {{log 'this is a simple log output'}}
```

También se pueden usar variables en el log.