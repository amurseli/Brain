---
tags:
  - Sisop
  - Clase
  - Tutoriales
---

Las variables de entorno son valores configurables a nivel del sistema operativo que proporcionan información y configuración a programas y aplicaciones. Estas variables almacenan datos como rutas de directorios, configuraciones de idioma, claves de acceso, y otros datos que los programas pueden utilizar para funcionar correctamente.

Para nuestro tp, [Shell](https://github.com/fiubatps/sisop_2023b_g16) en [[C]], tuvimos que crear un sistema de expansión de las mismas, es decir, que la shell reciba la variable en el formato `$USER` y nuestro código se encargaría de reemplazarla con el valro correspondiente.

```C
static char* expand_environ_var(char *arg)
{
	char *var_value;
	size_t len;
	if (arg[0] == '$') {
		if (arg[1] == '?') {
			sprintf(arg, "%i", status);

		} else {
			var_value = getenv(arg + 1);

			if (var_value == NULL) {
				arg = NULL;
				return arg;
			}

			len = strlen(var_value);
			if (len > strlen(arg)) {
				arg = (char *) realloc(arg,
				                       (len + 1) * sizeof(char));
			}
			strcpy(arg, var_value);
		}
	}

	return arg;
}
```