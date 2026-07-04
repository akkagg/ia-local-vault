---
tags: [docker, n8n, infraestructura]
---

# Docker Compose - n8n

## Servicio

`infrastructure/docker-compose.yml` define un unico servicio, `n8n`, en la red `ia-local-network`, expuesto en `http://localhost:5678` (puerto configurable via `.env`).

## Variables clave en `.env`

| Variable | Para que sirve |
|---|---|
| `N8N_BASIC_AUTH_USER` / `_PASSWORD` | Login de acceso a la UI de n8n |
| `N8N_ENCRYPTION_KEY` | Cifra las credenciales guardadas dentro de n8n. Si se pierde o cambia, se pierden las credenciales guardadas |
| `N8N_DATA_PATH` | Carpeta en el host donde vive todo el volumen de datos (por defecto `./volumes/n8n`) |
| `N8N_PROTOCOL` / `N8N_HOST` / `WEBHOOK_URL` | Solo necesarias para webhooks (ej. Telegram), ver [[Bot de Telegram - Arquitectura]] |

`.env` nunca se sube a git (ver [[Convenciones de Git]]).

## Comandos habituales

Todos se ejecutan desde `infrastructure/`, o mejor, desde el menu del bootstrap (opcion 2, Docker Manager):

```powershell
docker compose up -d       # levantar
docker compose down        # detener (los datos no se pierden)
docker compose ps          # ver estado
docker compose logs --tail 50 n8n   # ver logs
```

## Problema conocido: "failed to connect to the docker API"

Significa que **Docker Desktop no esta corriendo**, no que algo este mal configurado. Solucion: abrir Docker Desktop y esperar a que el icono de la bandeja deje de estar animado (15-40 segundos), luego repetir el comando.

## Ver tambien

- [[Como usar el bootstrap]]
- [[Gestion de workflows de n8n]]
