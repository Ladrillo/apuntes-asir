# Configuración Básica de Nginx en Ubuntu

**Introducción:**
En esta lección, aprenderemos los fundamentos de la configuración de Nginx en un sistema Ubuntu. Cubriremos cómo instalar Nginx, iniciar el servicio, encontrar el documento de bienvenida predeterminado, editar dicho documento, ubicar el archivo de configuración principal de Nginx y entender su estructura y funcionamiento.

**Instalación y Puesta en Marcha:**
Para instalar Nginx en Ubuntu, ejecuta los siguientes comandos en tu terminal:
`sudo apt update`
`sudo apt install nginx`

Una vez instalado, puedes iniciar el servicio Nginx con:
`sudo systemctl start nginx`

Para asegurarte de que el servicio se inicie automáticamente al arrancar el sistema, ejecuta:
`sudo systemctl enable nginx`

**Localización del Documento de Bienvenida:**
El documento de bienvenida predeterminado de Nginx se encuentra en el directorio `/var/www/html` en el archivo `index.html` (o nombre similar). Puedes acceder a este documento visitando la dirección IP de tu servidor en un navegador web.

**Edición del Documento de Bienvenida:**
Puedes editar el documento de bienvenida manualmente utilizando un editor de texto. Por ejemplo, puedes usar `nano`:
`sudo nano /var/www/html/index.html`
Realiza los cambios necesarios en el archivo y guarda los cambios. El archivo HTML puede tener un nombre ligeramente distinto.

**Localización del Archivo de Configuración:**
El archivo de configuración principal de Nginx se encuentra en `/etc/nginx/nginx.conf`. Este archivo contiene la configuración global de Nginx, incluidas las directivas relacionadas con el comportamiento del servidor, el registro, las rutas de los archivos, y más.

**Explicación del Archivo de Configuración:**
El archivo de configuración de Nginx está estructurado de manera modular y utiliza bloques de servidor (o hosts virtuales) para definir la configuración específica de cada sitio web o aplicación. Los archivos de configuración de estos bloques de servidor se encuentran en el directorio `/etc/nginx/sites-available`. Para activar un bloque de servidor, se crea un enlace simbólico al archivo de configuración correspondiente en el directorio `/etc/nginx/sites-enabled`.

Es importante entender la sintaxis y las directivas de configuración de Nginx antes de realizar cambios en estos archivos.

**Conclusión:**
En esta lección, hemos cubierto los pasos básicos para configurar Nginx en un sistema Ubuntu. Desde la instalación hasta la edición de documentos de bienvenida y la comprensión del archivo de configuración principal, ahora tienes una base sólida para empezar a trabajar con Nginx en tus proyectos web. Recuerda siempre realizar pruebas y verificar la configuración antes de implementarla en un entorno de producción.
