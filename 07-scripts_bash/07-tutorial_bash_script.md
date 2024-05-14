
# Tutorial: Crear un Script de Bash en Ubuntu para Crear un Usuario

En este tutorial, aprenderás cómo crear un script de Bash en Ubuntu que toma un nombre desde la entrada estándar, crea un usuario con ese nombre, le asigna su propia carpeta de inicio y lo añade al grupo `sudoers`.

## Paso 1: Crear el Archivo del Script

Primero, abre una terminal y crea un nuevo archivo para tu script. Utiliza el comando `touch` seguido del nombre del archivo. En este ejemplo, llamaremos al archivo `crear_usuario.sh`.

```bash
touch crear_usuario.sh
```

## Paso 2: Editar el Script

Abre el archivo `crear_usuario.sh` en tu editor de texto favorito, por ejemplo, `nano` o `vim`.

```bash
nano crear_usuario.sh
```

## Paso 3: Escribir el Script

A continuación, añade el siguiente contenido al archivo:

```bash
#!/bin/bash

# Pedir el nombre del usuario
echo "Introduce el nombre del usuario:"
read nombre_usuario

# Crear el usuario con su propia carpeta de inicio
sudo useradd -m $nombre_usuario

# Añadir el usuario al grupo sudo
sudo usermod -aG sudo $nombre_usuario

# Informar al usuario de que el proceso ha sido completado
echo "El usuario $nombre_usuario ha sido creado y añadido al grupo sudo."
```

### Explicación del Script

1. `#!/bin/bash`: Esta línea indica que el archivo debe ser interpretado por el shell de Bash.
2. `echo "Introduce el nombre del usuario:"`: Muestra un mensaje en la terminal solicitando el nombre del nuevo usuario.
3. `read nombre_usuario`: Lee la entrada del usuario y la almacena en la variable `nombre_usuario`.
4. `sudo useradd -m $nombre_usuario`: Crea un nuevo usuario con el nombre proporcionado y le asigna una carpeta de inicio.
5. `sudo usermod -aG sudo $nombre_usuario`: Añade el nuevo usuario al grupo `sudo`, otorgándole permisos de administrador.
6. `echo "El usuario $nombre_usuario ha sido creado y añadido al grupo sudo."`: Informa al usuario de que el proceso ha finalizado.

## Paso 4: Hacer el Script Ejecutable

Guarda y cierra el archivo. Luego, haz que el script sea ejecutable utilizando el comando `chmod`.

```bash
chmod +x crear_usuario.sh
```

## Paso 5: Ejecutar el Script

Finalmente, ejecuta el script desde la terminal.

```bash
./crear_usuario.sh
```

## Conclusión

Con estos sencillos pasos, has creado un script de Bash que crea un nuevo usuario en Ubuntu, le asigna una carpeta de inicio y lo añade al grupo `sudoers`.
