# Ejercicios Prácticos para Administradores de Linux Novatos

## Ejercicio 1: ¡Bienvenidos al Mundo Linux

### Creación de un Usuario Inicial

- **Paso 1:** Agrega un nuevo usuario llamado `pablito` utilizando el comando `sudo adduser pablito`.
  - *Verificación:* Verifica la creación del usuario consultando `/etc/passwd` usando `grep pablito /etc/passwd`.

### ¡Explora el Universo Linux

- **Paso 2:** Inicia sesión como `pablito` usando el comando `su pablito`. Tendrás que crearle una contraseña para poder hacer esto.
  - *Verificación:* Confirma que estás usando la cuenta `pablito` ejecutando `whoami`.

## Ejercicio 2: Creando Personajes Fantásticos

### ¡Da Vida a tus Personajes

- **Paso 1:** Crea un usuario llamado `merlin` con un directorio de inicio alternativo en `/home/magia` utilizando el comando `sudo useradd -m -d /home/magia merlin`.
  - *Verificación:* Confirma la creación del directorio de inicio con `ls -ld /home/magia`.

### ¡Experimenta con Contraseñas Mágicas

- **Paso 2:** Crea un usuario llamado `gandalf` con la contraseña épica `youshallnotpass` (¡una contraseña obviamente insegura!) usando el comando `sudo useradd -m gandalf -p youshallnotpass`.
  - *Verificación:* Confirma la creación del usuario revisando su entrada en `/etc/passwd`.

## Ejercicio 3: Conquistando el Reino de los Privilegios

### Ascenso al Poder

- **Paso 1:** Agrega al usuario `pablito` al grupo `sudo` utilizando el comando `sudo usermod -aG sudo pablito`.
  - *Verificación:* Confirma los privilegios de `pablito` ejecutando `sudo -l -U pablito`.

## Ejercicio 4: ¡Modificando Atributos y Habilidades

### Ajustes de Habilidad

- **Paso 1:** Cambia la contraseña del usuario `pablito` utilizando el comando `sudo passwd pablito`.
  - *Verificación:* Verifica el cambio de contraseña usando `sudo chage -l pablito`.

### Expansión de Habilidades

- **Paso 2:** Agrega al usuario `merlin` al grupo de hechiceros `magicos` utilizando el comando `sudo usermod -a -G magicos merlin`.
  - *Verificación:* Usa `groups merlin` para verificar la adición al grupo.

### Transformación del Poder

- **Paso 3:** Cambia el shell predeterminado del usuario `gandalf` a `/bin/sh` utilizando el comando `sudo usermod -s /bin/sh gandalf`.
  - *Verificación:* Confirma el cambio de shell revisando `/etc/passwd` con `grep gandalf /etc/passwd`.

## Ejercicio 5: El Gran Final - Destrucción y Renacimiento

### Eliminando las Amenazas

- **Paso 1:** Elimina al usuario `gandalf` pero conserva su legado, manteniendo su directorio de inicio, usando `sudo userdel gandalf`.
  - *Verificación:* Asegúrate de que el usuario se haya eliminado de `/etc/passwd`.

### La Caída del Imperio

- **Paso 2:** Elimina completamente al usuario `merlin`, borrando también su hogar mágico, con `sudo userdel -r merlin`.
  - *Verificación:* Confirma que el directorio de inicio de `merlin` ya no existe con `ls /home` o `id merlin`.

## Desafía tu Destino

¡Has completado los desafíos! Continúa explorando el vasto mundo de Linux y descubre nuevos poderes con cada comando ejecutado.
