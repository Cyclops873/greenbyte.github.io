---
title: "Docker Compose en Linux: Instalación Paso a Paso desde la CLI 🐳"
date: 2025-09-05 15:30:00 -0600
categories: [contenedores,linux]
tags: [docker,instalación,tutorial,cli]
author: jose-hernandez
---

![Linux-Docker](/assets/img/posts/DC-Setup/Inicio.png "Docker Setup Guide")

### Instalación + primer contenedor + "Hola Mundo" en pocos minutos. Sin experiencia previa necesaria. ¡Empezamos!


## Paso 1: Instalar Docker
Primero, necesitamos instalar Docker, que es el software que nos permite crear y manejar contenedores.

1. Actualiza tus repositorios:
```bash
sudo apt update
```

2. Instala Docker:
```bash
sudo apt install docker.io -y
```

3. Habilita Docker para que inicie automáticamente y arráncalo: 
```bash
sudo systemctl enable docker
sudo systemctl start docker
```

4. Verifica que Docker esté instalado correctamente:
```bash
docker --version
```
> Deberías ver algo como: Docker version 24.0.0, build ...
{: .prompt-info }

## Paso 2: Instalar Docker Compose
Docker Compose permite levantar varios contenedores con un solo comando usando un archivo docker-compose.yml.

1. Descarga la última versión de Docker Compose:
```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

2. Dale permisos de ejecución:
```bash
sudo chmod +x /usr/local/bin/docker-compose
```

3. Verifica la instalación: 
```bash
docker-compose --version
```
> Deberías ver algo como: Docker Compose version v2.x.x
{: .prompt-info }

## Paso 3: Crear un archivo docker-compose.yml 

Este archivo le dice a Docker qué contenedor levantar.

1. Crea una carpeta para tu proyecto y entra en ella:
```bash
mkdir mi-primer-contenedor
cd mi-primer-contenedor
```

2. Crea el archivo docker-compose.yml:
```bash
nano docker-compose.yml
```

3. Copia esto dentro (es muy sencillo, solo levanta un contenedor de “Hello World”):
```yaml
version: "3.9"

services:
  hello:
    image: hello-world
```
>Guarda y cierra el archivo (Ctrl+O, Ctrl+M y Ctrl+X en nano).
{: .prompt-info }

## Paso 4: Levantar el contenedor

Ahora solo necesitamos ejecutar un comando:
```bash
sudo docker-compose up
```
- Docker Compose descargará la imagen hello-world (si no la tienes) y la ejecutará.
- Verás un mensaje que dice algo como:
![Hello-World!](/assets/img/posts/DC-Setup/hello-world!.png "HelloWorld Success")

## Paso 5: Detener el contenedor

Cuando termines, puedes detenerlo con:
```bash
sudo docker-compose down
```
Esto apaga y limpia el contenedor.

### ✅ ¡Listo! Acabas de levantar tu primer contenedor Docker usando Docker Compose de manera sencilla.