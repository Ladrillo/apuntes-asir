# Ejercicios Prácticos sobre el Uso de `chmod` para Nuevos Administradores de Linux

## Ejercicio 1: Visualización de Permisos Predeterminados

1. Crea un nuevo archivo llamado `testfile1.txt` usando el comando `touch`.
2. Usa `ls -l` para ver los permisos predeterminados asignados a este archivo.

## Ejercicio 2: Cambiando Permisos Numéricamente

1. Cambia los permisos de `testfile1.txt` para permitir solo al propietario leer y escribir en el archivo.
2. Verifica el cambio con `ls -l`.

## Ejercicio 3: Permitiendo Acceso al Grupo

1. Modifica `testfile1.txt` para permitir a los miembros del grupo leer y escribir en el archivo.
2. Verifica el cambio y explica qué implica la configuración de permisos `660`.

## Ejercicio 4: Eliminación de Acceso Público

1. Asegura que `testfile1.txt` sea inaccesible para cualquier persona fuera del grupo y del propietario del archivo.
2. Revisa los permisos y explica las implicaciones de la configuración `660`.

## Ejercicio 5: Usando Permisos Simbólicos

1. Cambia los permisos de `testfile1.txt` para permitir a todos leer el archivo, usando modo simbólico.
2. Revisa y discute el cambio realizado.

## Ejercicio 6: Restricción de Acceso de Escritura

1. Usa permisos simbólicos para remover el acceso de escritura para el grupo en `testfile1.txt`.
2. Verifica y discute el cambio.

## Ejercicio 7: Archivos Ejecutables

1. Crea un script llamado `script.sh` con un simple comando echo.
2. Cambia los permisos del script para ser ejecutable solo por el propietario.
3. Verifica el cambio y ejecuta el script.

## Ejercicio 8: Cambio de Permisos Recursivo

1. Crea un directorio `testdir` y coloca múltiples archivos dentro de él.
2. Cambia los permisos recursivamente para permitir solo al propietario leer y escribir los archivos en `testdir`.
3. Verifica los cambios en varios archivos dentro del directorio.

## Ejercicio 9: Usando `chmod` con `umask`

1. Discute cómo `umask` afecta los permisos predeterminados de los nuevos archivos y directorios.
2. Crea un archivo y un directorio después de establecer un valor de `umask` y observa cómo se afectan los permisos.

## Ejercicio 10: Permisos Especiales

1. Establece el bit de pegado en un directorio que creas.
2. Discute qué hace el bit de pegado y cuándo podría ser útil.
3. Verifica la configuración del bit de pegado con `ls -ld`.
