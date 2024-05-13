# Ejercicios Avanzados de Práctica para Administradores de Linux Novatos

## Ejercicio 1: Bienvenido al Mundo de Linux

### Creación de Usuario Inicial

- **Paso 1:** Agrega un nuevo usuario llamado `luke` y asígnalo al grupo `rebeldes`.
  - *Verificación:* Verifica la creación y asignación de grupo del usuario consultando `/etc/passwd` y `/etc/group` usando `grep luke /etc/passwd` y `grep rebeldes /etc/group`.

### Explora el Universo de Linux

- **Paso 2:** Inicia sesión como `luke`. Deberás establecer una contraseña con al menos 12 caracteres, incluyendo símbolos y números.
  - *Verificación:* Confirma que estás usando la cuenta `luke` ejecutando `whoami`.

## Ejercicio 2: Creando Personajes Fantásticos

### Dando Vida a tus Personajes

- **Paso 1:** Crea un usuario llamado `obiwan` con un directorio de inicio alternativo en `/home/force` y asigna bash como el shell predeterminado.
  - *Verificación:* Confirma la creación del directorio de inicio y la asignación de shell con `ls -ld /home/force` y `grep obiwan /etc/passwd`.

### Experimenta con Contraseñas Mágicas

- **Paso 2:** Crea un usuario llamado `yoda` con la contraseña `doordonot` (¡una contraseña obviamente insegura!) y obliga un cambio de contraseña en el primer inicio de sesión.
  - *Verificación:* Verifica la creación del usuario inspeccionando su entrada en `/etc/passwd` y valida la política de contraseña con `sudo chage -l yoda`.

## Ejercicio 3: Conquistando el Reino de los Privilegios

### Ascenso al Poder

- **Paso 1:** Agrega al usuario `luke` al grupo `sudo` y asegúrate de que no necesite contraseña para operaciones de sudo.
  - *Verificación:* Confirma los privilegios de `luke` ejecutando `sudo -l -U luke`.

## Ejercicio 4: Modificando Atributos y Habilidades

### Ajustes de Habilidad

- **Paso 1:** Cambia la contraseña del usuario `luke` a una más segura y establece que expire cada 30 días.
  - *Verificación:* Verifica el cambio de contraseña y la política de expiración usando `sudo chage -l luke`.

### Expansión de Habilidades

- **Paso 2:** Agrega al usuario `obiwan` al grupo `jedis` y también al grupo `root`.
  - *Verificación:* Usa `groups obiwan` para verificar la adición a ambos grupos.

### Transformación del Poder

- **Paso 3:** Cambia el shell predeterminado del usuario `yoda` a `/bin/csh`.
  - *Verificación:* Confirma el cambio de shell revisando `/etc/passwd` con `grep yoda /etc/passwd`.

## Ejercicio 5: El Gran Final - Destrucción y Renacimiento

### Eliminando Amenazas

- **Paso 1:** Elimina al usuario `yoda` pero conserva su legado manteniendo su directorio de inicio y creando una copia de seguridad del mismo.
  - *Verificación:* Asegúrate de que el usuario ha sido eliminado de `/etc/passwd` y que el directorio de inicio está respaldado en otro lugar.

### La Caída del Imperio

- **Paso 2:** Elimina completamente al usuario `obiwan`, borrando también su hogar mágico y todos los archivos y subdirectorios.
  - *Verificación:* Confirma que el directorio de inicio de `obiwan` ya no existe con `ls /home` y verifica la eliminación del usuario con `id obiwan`.

## Desafía tu Destino

¡Has completado los desafíos! Continúa explorando el vasto mundo de Linux y descubre nuevos poderes con cada comando ejecutado.
