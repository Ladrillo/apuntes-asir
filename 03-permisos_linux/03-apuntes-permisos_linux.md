# Guía Básica de Ubuntu LTS para Principiantes

## Cambio a la carpeta home y verificación del directorio actual

- Cambiar al directorio home del usuario: `cd ~`
- Verificar el directorio actual: `pwd`

## Activación y uso del usuario root

- Activar el usuario root: `sudo su`
- Cambiar al usuario root: `su root`
- Volver al usuario normal: `exit`

## Creación de directorio y archivo script

- Crear una carpeta y un archivo script dentro de ella:

```bash
mkdir mi-proyecto
cd mi-proyecto
touch script.sh
```

- Escribir un comando simple en el script:

```bash
echo "echo 'hello world'" > script.sh
```

## Listar contenidos con detalles

- Ver los contenidos del directorio incluyendo detalles: `ls -lah`

## Usando chmod

### Introducción a `chmod`

`chmod` significa "cambiar modo", y es un comando en Linux usado para cambiar los permisos de acceso de objetos en el sistema de archivos (archivos y directorios). Los permisos controlan las acciones que los usuarios pueden realizar sobre estos objetos.

### Tipos de Permisos

- **Leer (r)**: Permiso para leer el contenido del archivo.
- **Escribir (w)**: Permiso para modificar o eliminar el contenido del archivo.
- **Ejecutar (x)**: Permiso para ejecutar un archivo, como en el caso de scripts y programas.

### Categorías de Permisos

- **Propietario**: El usuario que creó el archivo. Típicamente tiene todos los permisos.
- **Grupo**: Usuarios que son parte del grupo del archivo. A menudo tienen menos permisos que el propietario.
- **Otros**: Todos los demás usuarios que tienen acceso al sistema de archivos.

### Notación de Permisos Numéricos (Octal)

Los permisos pueden establecerse utilizando códigos numéricos:

- **7** - Leer, escribir y ejecutar (rwx)
- **6** - Leer y escribir (rw-)
- **5** - Leer y ejecutar (r-x)
- **4** - Solo leer (r--)
- **3** - Escribir y ejecutar (-wx)
- **2** - Solo escribir (-w-)
- **1** - Solo ejecutar (--x)
- **0** - Sin permisos (---)

Cada dígito en un código de tres dígitos representa una categoría diferente (propietario, grupo, otros). Por ejemplo, `chmod 755` establece permisos de leer, escribir y ejecutar para el propietario, y leer y ejecutar para el grupo y los demás.

### Notación de Permisos Simbólicos

Alternativamente, los permisos pueden establecerse simbólicamente:

- **u** (usuario): el propietario del archivo
- **g** (grupo): usuarios que son parte del grupo del archivo
- **o** (otros): cualquier otra persona
- **a** (todos): todos los anteriores

Operaciones:

- **+** añade un permiso
- **-** elimina un permiso
- **=** establece exactamente estos permisos

Ejemplos:

- `chmod u+x archivo`: Añade permiso de ejecución al propietario.
- `chmod go-rwx archivo`: Elimina todos los permisos del grupo y otros.
- `chmod a=r archivo`: Establece permiso de lectura para todos y elimina todos los demás permisos.

### Permisos Especiales

- **Bit pegajoso (t)**: Los archivos dentro del directorio solo pueden ser renombrados o eliminados por el propietario del archivo, el propietario del directorio o el usuario root.
- **SetUID (s)**: El ejecutable se ejecuta con los permisos del propietario del archivo.
- **SetGID (s)**: El ejecutable se ejecuta con los permisos del grupo.

Ejemplo: `chmod +t directorio` establece el bit pegajoso en un directorio.

### Usando `chmod` Recursivamente

- Para cambiar los permisos de un directorio y todo su contenido, usa la opción `-R`.
  Ejemplo: `chmod -R 644 directorio`

### Comprensión de `umask`

- El comando `umask` establece los permisos de creación predeterminados para nuevos archivos y directorios. Efectivamente "enmascara" permisos que no están establecidos.
- Ejemplo: Un `umask` de `022` permite al propietario todos los permisos pero restringe algunos permisos para el grupo y otros.

### Comandos Prácticos

- Ver permisos: `ls -l`
- Cambiar permisos: `chmod [opciones] modo archivo`
- Establecer permisos predeterminados: `umask valor`

Al dominar estos conceptos y comandos, los usuarios pueden gestionar efectivamente los permisos de archivos en sistemas Linux, asegurando niveles adecuados de acceso y seguridad.

## Hacer un script ejecutable y ejecutarlo

- Hacer el script `script.sh` ejecutable:

```bash
chmod +x script.sh
```

- Ejecutar el script:

```bash
./script.sh
```

## Ejecución de un script como usuario root sin permisos explícitos

- Aunque el script no tenga permisos de ejecución para otros usuarios, root puede ejecutarlo:
  - Cambiar a usuario root: `sudo su`
  - Navegar al directorio del script: `cd mi-proyecto`
  - Ejecutar el script como root: `./script.sh`
  - Salir del usuario root: `exit`
