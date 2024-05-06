# Guía Básica de Ubuntu LTS para Principiantes

1. **Cambio a la carpeta home y verificación del directorio actual:**
    - Cambiar al directorio home del usuario: `cd ~`
    - Verificar el directorio actual: `pwd`

2. **Activación y uso del usuario root:**
    - Activar el usuario root: `sudo su`
    - Cambiar al usuario root: `su root`
    - Volver al usuario normal: `exit`

3. **Creación de directorio y archivo script:**
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

4. **Listar contenidos con detalles:**

    - Ver los contenidos del directorio incluyendo detalles: `ls -lah`

5. **Pausa para explicar detalles de `index.js` (suponiendo que existe en el directorio actual):**

    - **Permisos:** Representan las acciones permitidas sobre el archivo por el dueño, grupo y otros.
    - **Usuario dueño y grupo:** Indican el propietario del archivo y el grupo al que pertenece.
    - **Tamaño:** Muestra el tamaño del archivo.
    - **Fecha:** Indica la última fecha de modificación.
    - Ejemplo de listado detallado: `-rw-r--r-- 1 usuario grupo 1.1K Jan 10 10:00 index.js`

6. **Cambios de permisos con `chmod`:**
    - Cambiar permisos usando símbolos:
      - Añadir permiso de ejecución para el usuario: `chmod u+x index.js`
      - Quitar permiso de escritura para el grupo: `chmod g-w index.js`
      - Añadir permiso de lectura para otros: `chmod o+r index.js`
    - Cambiar permisos usando números:
      - Establecer permisos con números (dueño=lectura y escritura, grupo=lectura, otros=nada): `chmod 640 index.js`
    - Ejemplos adicionales para una visión exhaustiva:
      - Añadir todos los permisos a todos: `chmod 777 index.js`
      - Establecer permisos específicos para dueño, grupo y otros con símbolos combinados: `chmod u=rwx,g=rx,o=r index.js`

7. **Hacer el script ejecutable y ejecutarlo:**
    - Hacer el script `script.sh` ejecutable:

    ```bash
    chmod +x script.sh
    ```

    - Ejecutar el script:

    ```bash
    ./script.sh
    ```

8. **Ejecución del script como usuario root sin permisos explícitos:**
    - Aunque el script no tenga permisos de ejecución para otros usuarios, root puede ejecutarlo:
      - Cambiar a usuario root: `sudo su`
      - Navegar al directorio del script: `cd mi-proyecto`
      - Ejecutar el script como root: `./script.sh`
      - Salir del usuario root: `exit`
