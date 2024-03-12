### Objetivos de Rust

Rust es un lenguaje de bajo nivel que prioriza la velocidad, la seguridad y la concurrencia. Se siente como un lenguaje de alto nivel, pero con una alta performance.


#### Tipos de datos

i8, i16, i32, i64
u8, u16, u32, u64
usize, isize
f32, f64
bool
char (unicode)

### Declaración de variables

Las variables son inmutables por default, se llaman *bindings*.
``let t = true;
``
Para hacerlas mutables, se utiliza **mut**
``let mut punto = (1_u8, 2_u8);``

El comando *shadow* nos permite pisar variables no mutables, descartanbdo el valor anterior.

Existen también los structus,

```
Struct Persona{
		
}
```
