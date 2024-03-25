---
tags:
  - Clase
  - Redes
---
Clase 2 | 22-03-2024

# Transport Layer

### Multiplexing y Demultiplexing

La capa de *Transporte* permite a las Aplicaciones comunicarse. Multiplexar es enviar hilos diferente de información por un solo medio, como un cable ethernet o wi-fi. Demultiplexar es lo inverso, distribuir lo recibido por un único medio a sus respectivos procesos.

>[!Importante]
>El transporte en internet es *best effort*. Intenta lo mejor que puede que la información llegue de un lugar a otro, pero nada lo asegura.

La capa de transporte proporciona además una facilidad en el diseño de la red: equipos más simples, protocolos menos complejos. Proporciona también multiplexado en la somunicaciones y una mínima verificación de errores.

Puede proveer además:
- Confiabilidad de las comunicaciones.
- Control de flujo.
- Seguridad.

---

### [[UDP]]

UDP (User Datagram Protocol) es un protocolo rápido, no confiable y que no requiere conexión ni estado. Además, es más ligero que su contraparte, puesto que necesita menos datos para pode enviar información

                     0      7 8     15 16    23 24    31
                    +--------+--------+--------+--------+
                    |    Puerto de    |    Puerto de    |
                    |      Origen     |     Destino     |
                    +--------+--------+--------+--------+
                    |                 |                 |
                    |    Longitud     |    Checksum     |
                    +--------+--------+--------+--------+
                    |
                    |          octetos de datos ...
                    +---------------- ...

Los puertos (el de origen y el de destino), pueden ser cualquiera de los 65536 posibles, o $2^{16}$ 
El puerto de origen indica el puerto de donde salió el mensaje (para que el receptor pueda responder) y el de destino indica el lugar al que va dirigido el mensaje

El Checksum es una cuenta para una mínima verificación de errores.

##### ¿Cuando usamos UDP?

Siempre que necesitamos velocidad en el envío, y que no nos importe que la información sea realmente confiable, como el [[DNS]]

---

### Principios de las comunicaciones confiables

Una conexión confiable tiene como principio asegurar la entrega, el orden de los paquetes y la integridad de estos.

#### Tipos de flujo

- Stop & Wait: El concepto de, al mandar un paquete, esperar un acknowledgement (ACK), si no se recibe, se madna nuevamente.
- Continuo:  Ordenas los paquetes de forma continua hasta cierto largo, una vez que se envía ese décimo paquete, se manda el ACK de el primero. Una vez que te llega el ACK del primero, se manda el paquete 11, y así. El largo de la ventana depende de lo que se tarde en recibir los paquetes.
- Go-Back-N: Si un paquete se pierde, se envían todos desde el último que tuvo un ACK
- Selective Repeat: Se manda solo el paquete por el que no se recibió el ACK


>[!Tip]
>Comandos Importantes
>```Shell
>nmap -v [server] //Scan open ports
>netstat -an |less
>```
