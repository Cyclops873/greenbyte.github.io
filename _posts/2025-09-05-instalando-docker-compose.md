---
title: "Docker Compose en Linux: Instalación Paso a Paso desde la CLI 🐳"
date: 2025-09-05 15:30:00 -0600
categories: [contenedores,linux]
tags: [docker,instalación,cli,tutorial]
---

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
