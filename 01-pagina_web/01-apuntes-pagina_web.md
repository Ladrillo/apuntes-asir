# Creación de una Página Web Simple

Este documento guía a través del proceso de creación de una página web básica utilizando HTML, CSS y JavaScript. Esta guía es ideal para principiantes y asume el uso de Visual Studio Code como editor de código.

## Prerrequisitos

- Tener Visual Studio Code instalado.
- Conocimientos básicos sobre HTML, CSS y JavaScript.

## Pasos

### 1. Crear los archivos de proyecto

Crea una carpeta nueva para tu proyecto y dentro de esta, crea tres archivos: `index.html`, `styles.css` y `script.js`.

```bash
mkdir mi-web
cd mi-web
touch index.html styles.css script.js
```

### 2. Escribir el HTML

Abre `index.html` en Visual Studio Code. Para generar la estructura básica de una página HTML, usa el atajo de Emmet `!` seguido de la tecla `Tab`. Esto creará el siguiente esqueleto:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Documento</title>
</head>
<body>

</body>
</html>
```

### 3. Vincular el CSS y JavaScript

En el elemento `<head>`, agrega un enlace al archivo CSS:

```html
<link rel="stylesheet" href="styles.css">
```

Justo antes de cerrar el elemento `<body>`, agrega el script de JavaScript:

```html
    <script src="script.js"></script>
```

Tu archivo `index.html` debería verse así:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Página Web</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Contenido de la página aquí -->
    <script src="script.js"></script>
</body>
</html>
```

### 4. Escribir CSS

Abre `styles.css` y añade algunos estilos básicos. Por ejemplo, cambia el color de fondo del cuerpo y establece la tipografía:

```css
body {
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
}
```

### 5. Escribir JavaScript

Abre `script.js` y escribe un simple `console.log` para verificar que el script se está cargando correctamente:

```js
console.log('El script se ha cargado correctamente!');
```

## Resultado

Al abrir `index.html` en tu navegador, verás la página estilizada según `styles.css` y en la consola de herramientas para desarrolladores del navegador, deberías ver el mensaje del `console.log`.
