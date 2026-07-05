---
tags: [telegram, n8n, ollama, arquitectura]
---

# Bot de Telegram - Arquitectura

## Flujo del workflow

`automation/workflows/telegram-asistente-ia-local.json`:

```
Telegram Trigger -> Consultar Ollama (HTTP Request) -> Responder en Telegram
```

1. **Telegram Trigger**: recibe cada mensaje enviado al bot.
2. **Consultar Ollama**: hace `POST` a `http://host.docker.internal:11434/api/generate` con el texto recibido, usando el modelo `qwen2.5:3b`.
3. **Responder en Telegram**: envia la respuesta del modelo de vuelta al mismo chat.

## Por que `host.docker.internal` y no `localhost`

n8n corre dentro de Docker; Ollama corre nativo en Windows. Son redes distintas. `host.docker.internal` es la direccion especial que Docker Desktop expone para que un contenedor alcance servicios del host.

**Requisito:** Ollama debe escuchar en todas las interfaces, no solo en loopback puro:

```powershell
[System.Environment]::SetEnvironmentVariable('OLLAMA_HOST', '0.0.0.0', 'User')
```

(reiniciar terminal y Ollama despues de esto).

## Por que hace falta ngrok

Telegram exige una **URL HTTPS publica** para registrar el webhook del bot - `http://localhost:5678` no vale. Solucion para desarrollo local: tunel con ngrok.

```powershell
ngrok http 5678
```

Copiar la URL HTTPS que da ngrok y ponerla en `infrastructure/.env`:

```
N8N_PROTOCOL=https
N8N_HOST=<subdominio>.ngrok-free.app
WEBHOOK_URL=https://<subdominio>.ngrok-free.app/
```

Despues, reiniciar n8n (`docker compose down && docker compose up -d`) y reactivar el workflow.

**Limitacion de la cuenta gratuita de ngrok:** la URL cambia cada vez que se reinicia el tunel. Si el bot deja de responder, revisar primero si ngrok sigue corriendo y si la URL en `.env` sigue siendo la misma.

## Credencial de Telegram en n8n

Se crea a mano en la UI de n8n (Credentials -> Add Credential -> Telegram API), pegando el token que da `@BotFather`. No se gestiona por script porque n8n guarda las credenciales cifradas en su propia base de datos, no como variable de entorno simple.

## Ver tambien

- [[Modelos instalados]]
- [[Gestion de workflows de n8n]]
- [[Docker Compose - n8n]]

## Ampliacion: comandos /buscar y /enviar (acceso a archivos)

El workflow `telegram-asistente-ia-local-v2.json` anade dos comandos ademas de la conversacion normal:

- `/buscar <texto>`: busca archivos por nombre dentro de `knowledge/`, `docs/` y `projects/` (montadas como solo lectura en `/data/knowledge`, `/data/docs`, `/data/projects` dentro del contenedor).
- `/enviar <ruta>`: envia un archivo concreto por Telegram (ej. `/enviar docs/PROGRESS.md`).

### Seguridad: filtro de chat autorizado

El primer nodo tras el trigger (`IF - Chat autorizado`) compara el chat ID del mensaje contra un valor fijo en el propio nodo. Si no coincide, el flujo simplemente termina sin responder - nadie mas que el chat autorizado puede usar el bot.

**Como obtener tu chat ID**: escribir a `@userinfobot` en Telegram, o revisar la pestana "Executions" de n8n tras enviar un mensaje de prueba (el campo `message.chat.id` del Telegram Trigger).

### Por que solo lectura (`:ro`)

Las carpetas se montan de solo lectura a proposito: el bot puede leer y enviar archivos, pero no puede modificarlos ni borrarlos desde Telegram. Si en el futuro se quiere permitir escritura, hay que cambiar el `:ro` por `:rw` en `docker-compose.yml` de forma consciente.
