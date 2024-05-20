# Examen Final - Sistemas Operativos

## Datos

- Fecha: 20/05/2024
- Nombre y Apellidos: ___________________

## Instrucciones

Todos los ejercicios deben ser respondidos **a mano en los huecos previstos** al pie de cada enunciado.

Utiliza un papel de borrador para "ensayar" la respuesta. Las respuestas ilegibles serán consideradas inválidas.

Verifica cada comando y cada secuencia de comandos en un Terminal de Linux Ubuntu: los comandos que no ejecuten correctamente, o las secuencias incorrectas de comandos no recibirán ninguna puntuación.

## Ejercicios

El punto de partida es un Ubuntu LTS recién instalado en el portátil de un trabajador de tu empresa.

### Ejercicio 1 - Verificando los usuarios del sistema

Ejecuta un comando para listar los usuarios del sistema operativo:

```bash

```

### Ejercicio 2 - Creando una contraseña para el usuario root

El usuario root no tiene la contraseña activada, y por lo tanto no podemos usarlo. Ejecuta un comando para crear una contraseña para root:

```bash

```

### Ejercicio 3 - Verificación

Ejecuta tres comandos utilizando un usuario normal (no root): uno para visualizar qué usuario eres, otro para ver cuál es el directorio actual en el sistema de archivos, y otro para colocarte en la carpeta home del usuario en cuestión.

```bash



```

### Ejercicio 4 - Manipulando permisos

Crea un archivo desde la carpeta home de un usuario normal, y cambia los permisos del archivo para que tenga Read, Write y Execute por parte del usuario, pero solo Read para el grupo del usuario, y ningún permiso para otros.

```bash


```

Crea otro archivo y cambia los permisos para que el usuario propietario del archivo y su grupo tengan permiso Read, y ningún permiso para nadie más.

```bash


```

### Ejercicio 5 - Creando usuarios nuevos

Ejecuta un comando para crear un usuario nuevo, y otro para añadir el nuevo usuario al grupo de usuarios capaces de usar sudo.

```bash


```

### Ejercicio 6 - Iniciando un proyecto nuevo

Ejecuta un comando para crear un directorio, otro para moverte dentro del nuevo directorio, otro para crear un archivo **index.html** dentro del directorio, y otro para inicializar un repositorio de Git.

```bash




```

### Ejercicio 7 - Uso básico de Git

¿Cuáles son los tres comandos que se usan habitualmente para (1) añadir todos los cambios de un proyecto a la lista de cambios para incluir en un commit, (2) crear un commit con el mensaje "fantástico commit" y (3) empujar el commit a Github?

```bash


```

### Ejercicio 8 - Encontrando directorios y archivos

¿Qué comando puedes usar para encontrar todos los directorios dentro de home que se llamen o bien **proyecto** o **Proyecto**?

```bash


```

¿Cómo puedes encontrar todos los archivos con la extensión **.jpg** o **.JPG** utilizando un único comando?

```bash


```

### Ejercicio 9 - Encontrando texto

Imagina que en tu directorio actual tienes un archivo **don_quijote.txt**. Deseamos saber **cuántas veces** aparece en él la palabra "caballero" **en singular, pero sin sensibilidad a las mayúsculas**. Dicho de otra forma, "caballero" o "Caballero" serían resultados válidos de la búsqueda, mientras que "caballeros" no lo sería.

```bash


```

### Ejercicio 10 - Creando scripts en Bash

Escribe un pequeño script para crear un archivo **hola_mundo.txt** en tu carpeta home, escribiendo la cadena "Hola, Mundo" en su interior.

```bash
#!/bin/bash



```

Imagina que tienes tu script listo en un archivo **mi_script.sh** pero te encuentras con que no es ejecutable. ¿Qué comando usarías para hacer el script ejecutable?

```bash

```
