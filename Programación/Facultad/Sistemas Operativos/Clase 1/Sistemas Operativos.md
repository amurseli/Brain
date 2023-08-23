---
 tags: Clase, Sisop
---
Clase 1 | 23-08-2023
### ¿Que es un sistema operativo?

El [[Sistema Operativo]] es un software que facilita la ejecución de programas para el usuario. Es la capa de software que maneja los recurss de una computadora para sus usuarios y aplicaciones.

El Sistema Operativo actua como **Referee**, media las interacciones entre todos los que quieren usar los recursos. 
Provee una abstracción del hardware para simplifaicar el diseño de las aplicaciones. También provee una sensación de homogeneidad entre todas las aplicaciones, haciendolas similares.

La capa del sistema operatio que se encarga de la comunicacion entre el hardware y las aplicaciones se conoce como [[Kernel]], el cual utiliza las [[SisCall]] para comunicarse con el hardware. Write() es un ejemplo de SisCall.

##### Virtualización
Lo mismo que la abstracción. Creo un concepto para hacerle creer al usuario que habla con componentes físicos.


### Proceso
Se alojan en el disco, y todos menos el Kernel viven en el [[User Space]]. Cada proceso tiene un ID, PID. También cada proceso tiene varios [[File Descriptors]]. Cada vez que el Kernel crea un proceso, lo guarda en un tabla interna llamada Process Table. Siempre que se crea uno, también se crean siempre tres file descriptors, stdin, stdout y stderr.

