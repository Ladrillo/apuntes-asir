# Guía avanzada para la gestión de usuarios en Linux para superadministradores

## Introducción a la gestión de usuarios

Gestionar usuarios en Linux implica una variedad de tareas desde crear cuentas de usuario hasta eliminarlas cuando ya no son necesarias. Esta guía cubre estos aspectos de manera exhaustiva para superadministradores.

## Creación de Usuarios

- **Agregar un nuevo usuario**: `sudo adduser username`
  - *Verificación*: Verificar consultando `/etc/passwd` usando `cat /etc/passwd` o `grep username /etc/passwd`.
  - *Comentario*: `adduser` es preferido por su naturaleza interactiva, especialmente para principiantes.

## Creación de Usuarios Avanzada

- **Agregar un usuario con un directorio de inicio específico**: `sudo useradd -m -d /home/directorio-alternativo username`
  - *Verificación*: Confirmar listando el directorio de inicio con `ls -ld /home/directorio-alternativo`.
  - *Comentario*: La opción `-m` es para crear el directorio de inicio si no existe y `-d` para especificar un directorio.
- **Agregar un usuario con una contraseña (Ejemplo inseguro!)**: `sudo useradd -m akira -p akirarules`
  - *Verificación*: Confirmar la creación del usuario revisando su entrada en `/etc/passwd`.
  - *Comentario*: La opción `-m` crea el directorio de inicio si no existe. La opción `-p` se utiliza aquí para establecer directamente la contraseña en texto, lo cual **no es recomendable por razones de seguridad**, ya que la contraseña podría ser expuesta a cualquiera que tenga acceso al historial de comandos o a los procesos del sistema.

## Otorgar Acceso Sudo

- **Agregar un usuario existente al grupo sudo**: `sudo usermod -aG sudo username`
  - *Verificación*: Confirmar usando `sudo -l -U username` para ver sus privilegios sudo.
  - *Comentario*: Este comando agrega al usuario al grupo `sudo`, otorgándole privilegios administrativos.

## Modificación de Atributos del Usuario

- **Cambiar la contraseña de un usuario**: `sudo passwd username`
  - *Verificación*: Verificar el cambio usando `sudo chage -l username` para ver la fecha de cambio de contraseña.
- **Agregar un usuario a un grupo suplementario**: `sudo usermod -a -G groupname username`
  - *Verificación*: Usar `groups username` para verificar que el usuario ha sido agregado al grupo.
- **Cambiar el shell predeterminado de un usuario** (este ejemplo cambia al shell `sh`): `sudo usermod -s /bin/sh username`
  - *Verificación*: Confirmar revisando el shell del usuario en `/etc/passwd` con `grep username /etc/passwd`.
  - *Comentario*: Cambiar el shell puede afectar significativamente la experiencia del usuario, asegurarse de la compatibilidad es importante.

## Eliminación de Usuarios

- **Eliminar un usuario (mantener el directorio de inicio)**: `sudo userdel username`
  - *Verificación*: Asegurarse de que el usuario se ha eliminado de `/etc/passwd`.
- **Eliminar un usuario y eliminar el directorio de inicio**: `sudo userdel -r username`
  - *Verificación*: Confirmar verificando que el directorio de inicio del usuario ya no existe con `ls /home` o con `id username`.
  - *Comentario*: Eliminar el directorio de inicio es una buena práctica cuando el usuario ya no necesitará acceso a ningún dato.

## Gestión de Grupos

- **Crear un nuevo grupo**: `sudo groupadd groupname`
  - *Verificación*: Verificar usando `getent group groupname`.
- **Eliminar un grupo**: `sudo groupdel groupname`
  - *Verificación*: Asegurar la eliminación revisando `getent group groupname`.
  - *Comentario*: La gestión de grupos es esencial para organizar permisos y accesos.
- **Agregar un usuario a un grupo**: `sudo usermod -a -G groupname username`
  - *Verificación*: Verificar la adición con `groups username`.
- **Eliminar un usuario de un grupo**: `sudo gpasswd -d username groupname`
  - *Verificación*: Confirmar la eliminación usando `groups username`.

## Controles de Inicio de Sesión del Usuario

- **Bloquear una cuenta de usuario**: `sudo usermod -L username`
  - *Verificación*: Verificar con `sudo passwd -S username` y buscar una L que indica que la cuenta está bloqueada.
- **Desbloquear una cuenta de usuario**: `sudo usermod -U username`
  - *Verificación*: Comprobar con `sudo passwd -S username` para un estado sin una L, indicando que la cuenta está desbloqueada.

## Gestión de Usuarios a Nivel del Sistema

### Visualización de Información del Usuario

- **Listar todos los usuarios**: `cat /etc/passwd`
- **Listar todos los grupos**: `cat /etc/group`

### Gestión de Sesiones de Usuario

- **Forzar la desconexión de un usuario**: `sudo pkill -KILL -u username`
  - *Verificación*: Asegurarse de que el usuario no esté listado en `who`.
- **Ver quién está conectado**: `who`

### Monitorización de la Actividad del Usuario

- **Monitorizar la actividad del usuario en tiempo real**: `sudo w`
- **Ver los últimos inicios de sesión de los usuarios**: `last`

## Automatización de Tareas con Scripts

### Script de Ejemplo para Agregar Múltiples Usuarios

```bash
#!/bin/bash
# Script para agregar una lista de usuarios
# Este script utiliza 'adduser' para agregar usuarios sin requerir una contraseña al crearlos.
set -e  # Salir inmediatamente si un comando sale con un estado no exitoso.
user_list=("user1" "user2" "user3")
for user in "${user_list[@]}"; do
  sudo adduser --disabled-password --gecos "" $user
  echo "Usuario $user agregado exitosamente!"
  # Verificación de la adición
  if grep -q $user /etc/passwd; then
    echo "Verificación: $user existe en /etc/passwd."
  else
    echo "Error: $user no encontrado en /etc/passwd."
  fi
done
```

- Hacer el script ejecutable: chmod +x agregar_usuarios.sh
- Ejecutar el script: ./agregar_usuarios.sh

## Buenas Prácticas

- Revisar regularmente los derechos de acceso de los usuarios.
- Siempre utilizar sudo para tareas administrativas para evitar usar directamente la cuenta de root.
- Mantener la información de usuarios y grupos confidencial y segura.
