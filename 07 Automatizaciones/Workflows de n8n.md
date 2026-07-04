---
tags: [n8n, automatizaciones]
---

# Workflows de n8n

Lista de workflows del proyecto. El archivo fuente de cada uno vive en `automation/workflows/`.

## Telegram - Asistente IA Local

- **Archivo**: `automation/workflows/telegram-asistente-ia-local.json`
- **Estado**: activo, probado end-to-end.
- **Que hace**: recibe mensajes de Telegram y responde usando el modelo local `qwen2.5:3b` via Ollama.
- **Dependencias**: tunel ngrok activo, credencial "Telegram account" configurada en n8n, Ollama escuchando en `0.0.0.0`.
- Ver detalle completo: [[Bot de Telegram - Arquitectura]]

## Como anadir un workflow nuevo a esta lista

1. Construir y probar el workflow en la UI de n8n.
2. Exportarlo con el **N8n Manager** (opcion 3 del bootstrap, exportar workflows).
3. Copiar el JSON exportado a `automation/workflows/` con un nombre descriptivo.
4. Anadir una entrada aqui con: archivo, estado, que hace, dependencias.

## Ver tambien

- [[Gestion de workflows de n8n]]
