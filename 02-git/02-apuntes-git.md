# Configuración y Uso de Git en Ubuntu LTS

Este documento proporciona instrucciones detalladas para verificar la versión de Git, instalarlo si es necesario, configurarlo y comenzar a usarlo en Ubuntu LTS.

## Prerrequisitos

Tener acceso a una terminal en Ubuntu.
Privilegios de superusuario (sudo) para instalar paquetes.

## Pasos

### 1. Verificar la versión de Git

Primero, verifica si Git ya está instalado y su versión.

    git --version

Si Git está instalado, este comando devolverá la versión instalada. Si no, procede al siguiente paso para instalarlo.

### 2. Instalar Git

Si Git no está instalado, puedes instalarlo utilizando `apt`.

    sudo apt update
    sudo apt install git

### 3. Configurar Git

Configura tu nombre, correo electrónico y el nombre predeterminado de la rama principal en Git.

    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email@example.com"
    git config --global init.defaultBranch main

### 4. Crear un proyecto

Crea una carpeta para tu proyecto y un archivo `index.js` dentro de esta.

    mkdir mi-proyecto
    cd mi-proyecto
    echo "console.log('Hola Mundo');" > index.js

### 5. Iniciar un repositorio de Git

Inicializa un nuevo repositorio de Git en la carpeta del proyecto.

    git init

### 6. Stage todos los archivos para commit

Prepara todos los archivos del proyecto para el próximo commit.

    git add .

### 7. Crear un commit

Realiza un commit con los cambios añadidos.

    git commit -m 'Commit inicial: Añadido index.js con console.log'

## Comandos Comunes de Git

A continuación, se presenta un resumen de los comandos más comunes en Git:

- `git --version`: Muestra la versión de Git instalada.
- `git status`: Muestra el estado actual del repositorio, incluyendo cambios no stageados.
- `git init`: Inicializa un nuevo repositorio de Git en la carpeta actual.
- `git add <archivo>`: Prepara un archivo específico para el próximo commit.
- `git add .`: Prepara todos los archivos con cambios para el próximo commit.
- `git commit -m "mensaje"`: Realiza un commit de los cambios stageados con un mensaje descriptivo.
- `git diff`: Muestra las diferencias entre la situación actual y el commit más reciente.
