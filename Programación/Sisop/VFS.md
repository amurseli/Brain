### FileSystem Abstraction Layer

- Es un tipo genérico de interfaz para cualquier tipo de filesystem que es posible sólo porque el kernel implementa una capa de abstracción que rodea esta interface para con el sistema de archivo de bajo nivel.

- Esta capa de abstracción habilita a Linux a soportar sistemas de archivos deferentes, incluso si estos difieren en características y comportamiento.

- Esto es posible porque VFS provee un modelo común de archivos que pueda representar cualquier característica y comportamiento general de cualquier sistema de archivos.


VFS presenta una serie de estructuras que modelan un filesystem, estas estructuras se denominan objetos (programadas en C). Estos Objetos son:

- El **super bloque**, que representa a un sistema de archivos.

- El **inodo**, que representa a un determinado archivo.

- El **dentry**, que representa una entrada de directorio, que es un componente simple de un path.

- El **file** que representa a un archivo asociado a un determinado proceso


### Inodos
¿Para que sirven?:

1. **Identificación Única:** Cada archivo y directorio en un sistema de archivos Unix-like tiene un inodo asociado. Este inodo actúa como una especie de tarjeta de identificación única para ese archivo o directorio.

2. **Metadatos:** Los inodos almacenan metadatos importantes sobre un archivo o directorio, como el propietario, los permisos de acceso, la hora de creación, la hora de la última modificación, el tamaño y el número de enlaces a ese inodo.

3. **Punteros a Datos:** Además de los metadatos, los inodos contienen punteros a bloques de datos. Estos bloques de datos son donde se almacena realmente el contenido del archivo. Dependiendo del tamaño del archivo y de la organización del sistema de archivos, puede haber uno o más bloques de datos asociados a un inodo.

4. **Enlaces Duros:** Un inodo puede tener varios enlaces duros apuntando a él. Los enlaces duros permiten que varios nombres de archivo se refieran al mismo inodo, y por lo tanto, al mismo conjunto de datos en el disco. Esto es útil para compartir el mismo contenido entre diferentes ubicaciones en el sistema de archivos sin duplicar físicamente los datos.

5. **Eliminación de Archivos:** Cuando eliminas un archivo, el sistema operativo libera el inodo asociado y los bloques de datos correspondientes si no hay más enlaces duros que apunten a ellos. Esto es diferente de la eliminación real del contenido, que solo ocurre cuando no hay más referencias (enlaces) al inodo.