---
tags:
  - Clase
  - Redes
---
Clase 1 | 15-03-2024

### Capas de Protocolo
- **Aplicación**: Https, smtp, DNS
- **[[Clase 2#Transport Layer|Transporte]]**: Se encarga de el transporte confiabley eficiente de los datos. Se encarga del [[Clase 2#Multiplexing y Demultiplexing|Multiplexing y Demultiplexing]], el control de flujo y alguna correción de errores. Los protocolos de esta capa son [[TCP]] y [[UDP]]
- **Red**: Responsable de la transferecia de origen a destino de una o mas redes intermedias. Define que datos son encapsulados, direccionados y enrutados.
- **Enlace**: Se encarga de la trasnferecia confiable de datos entre nodos de una red local y controla el flujo de datos para evitar congestion.
- **Física**: Encargada de la transmisión de bits sin procesar por medios físicos, como fibra óptica o cable de cobre. Define característcias eléctricas, mecánicas y funcionales para el medio físico


### Tiempos y Mediciones
Existen cuatro tiempos diferentes que son relevantes a la hora de calcular cuanto tarda un paquete en viajar de una punta a otra.

##### Tiempo de Inserción
$L$ es el largo del paquete en bits, $R$ es la velocidad de inserción.
$$\LARGE t_{insert} \ = \ \frac{L_{bit}}{R_{\frac{bit}{seg}}}$$
##### Tiempo de Transmisión
$D$ es la distancia desde el emisor al receptor, $C$ es la velocidad de la luz en el vacío, la cual se multiplica por $\frac{2}{3}$ porque el medio de transmisión es cable físico llevando bits.
$$\LARGE t_{transmission} \ = \ \frac{D_{mt}}{\frac{2}{3} C_{\frac{mt}{seg}}}$$
##### Tiempo de Buffer
$K$ es la constante de la cantidad de paquetes que se envían, $\lambda$ es una constante que depdende de los items del buffer.
$$\LARGE t_{buff} \ = \ \frac{K . L_{bit}}{\lambda}$$
##### Tiempo de Procesamiento
El tiempo que se tardeen el leer los paquetes.

# DNS
Es un sistema de internet para traducir nombres de dominio legibles por humanos a direciones IP numéricas. Como por ejemplo, traducir "ejemplo.com" a "192.0.2.1"

Funciona bajo una relación jerárquica, eorganizados en un árbol invertido, donde los TLD(Top level domain), como ".com", ".ar" o ".net" estan al final del nombre, seguidos por aquellos de nivel mas bajo hasta llegar a los hosts infividuales.
