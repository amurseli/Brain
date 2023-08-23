---
 tags: Tutoriales, Clase, C
---
Clase 1 | 22-08-2023

En la primera clase hicimos un repaso de [[C]] y presentaron el tp final.


### Tipos de datos y agrupación de variables

##### Ejemplos de reserva de memoria

![[Cvars.png]]


##### Structs
Tipos de datos compuestos por otros tipos de datos. Es útil hacerles un SizeOf() para ver cuanto ocupan

```C
 struct S {  
	int a; 
	char b; 
	int c; 
    char d; 
}; 
      
struct S s = {1,2,3,4};
```


- C, [[C++]] y [[Rust]] son lenguajes de bajo nivel para que el programador pueda tener un control absoluto de dónde y cómo se ejecuta el código.
- El tamaño en bytes de los tipos depende de la arquitectura y del compilador. En `#include <cstdint>`  se puede tener acceso a tipos con tamaños específicos como uint64_t 
- El compilador puede guardar las variables en posiciones de memoria múltiplos de 4 (depende de la arquitectura y de los flags de compilación): variables alineadas son accedidas más rápidamente que las desalineadas.
- Como contra, la alineación despedicia espacio (padding) hay un tradeoff entre velocidad y espacio. 
- El tamaño de un puntero no depende de a que tipo apunta; todos los punteros ocupan el mismo tamaño (que depende de la arquitectura). • A los strings en C/C++ escritos en el código del programa el compilador les agrega el caracter nulo (byte 0). Tenerlo en cuenta!!



### Endianess
Tema visto también en Orga del Computador, por temas históricos, algunas computadoras guardan los datos al revés, en lo que se conoce como Little Endian. Las Mac lo guardan en Big Endian.

```c
short i = 0x1234; 
((unsigned char*)&i) == {0x12, 0x34} // Primer byte es el *mas* significativo // --> arquitectura big endian 
((unsigned char*)&i) == {0x34, 0x12} // Primer byte es el *menos* significativo // --> arquitectura little endian
```

Se resuelve fácilmente con los métodos de libreria `htonl(), htons(), ntohl(), ntohs()`.

### Segmentos de Memoria

Existen cuatro partes diferentes en un código en C:

- Code Segment: de solo lectura y ejecutable, a donde va el código y las constantes.
- Data Segment: variables creadas al inicio del programa y son válidas hasta que este termina; pueden ser de acceso global o local.
- Stack: variables creadas al inicio de una llamada a una función y destruidas automáticamente cuando esta llamada termina.
- Heap: variables cuya duración esta controlada por el programador (run-time).

##### Lifetime y Scope

- Duración (lifetime): tiempo desde que a la variable se le reserva memoria hasta que esta es liberada. Determinado por el segmento de memoria que se usa. 
- Visibilidad (scope): Cuando una variable se la puede acceder y cuando esta oculta.

##### Static
Static es una palabra reservada de C con dos usos diferentes. En el data segment, la variable declarada como static solo puede usarse en ese módulo en específico. En un scope reducido, como dentro de una función, conserva el valor entre llamados en diferentes scopes.


##### [[Cache Friendly]]

Se dice que un código es cache friendly cuando hace uso del hecho de que, al pedir el contenido de una dirección de memoria, el computador trae esa informacion y la cercana, haciendo que pedir devuelta a la información contigua sea muchísimo mas rápido.

Ejemplo: Un array de punteros vs un array con los elementos de interés.

En el primer caso, la CPU va a leer el primer elemento, ir a buscar la dirección a la memoria, y traerse todo un bloque al cache. Así por cada elemento del array de punteros.
En el segundo caso, los elementos de interés están directamente ahí, contiguos, acelerando mucho el proceso de busqueda y bajando un nivel de indirección.

