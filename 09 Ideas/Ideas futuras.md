---
tags: [ideas, backlog]
---

# Ideas futuras

Backlog de mejoras que han ido surgiendo durante el desarrollo, sin comprometerse todavia a hacerlas.

- [ ] **URL fija para el webhook de Telegram**: sustituir ngrok (URL cambia en cada reinicio con cuenta gratuita) por un dominio propio + Cloudflare Tunnel, si en algun momento se tiene un dominio disponible.
- [ ] **Cambiar de modelo segun la carga**: usar `phi3:mini` o `gemma2:2b` automaticamente si el equipo detecta poca RAM libre, en vez de siempre `qwen2.5:3b`.
- [ ] **Automatizar backups periodicos**: programar `Invoke-ProjectBackup` + `Invoke-BackupRotation` con el Programador de tareas de Windows, en vez de ejecutarlo a mano.
- [ ] **Dashboard con mas detalle**: anadir uso de RAM/CPU actual, no solo estado on/off.
- [ ] **API propia** y/o **interfaz web**: mencionado en el brief original (seccion 13) como posible ampliacion futura sin rediseñar la arquitectura base.
- [ ] **Procesamiento de imagenes en el bot de Telegram**: requiere un modelo de vision en Ollama (ej. llava, qwen2-vl), mas pesado que los modelos de solo texto actuales. Pospuesto por limitaciones de RAM (8 GB) mientras Docker + ngrok + modelo ya estan en uso simultaneo. Retomar si se mejora el hardware o se libera carga de otros servicios.
- [ ] **Vault como "red neuronal" visual**: la vista de grafo nativa de Obsidian (icono de grafo en la barra lateral) ya muestra las notas como nodos conectados por los wikilinks `[[...]]` que se han ido usando en todo el vault. Cuantos mas capitulos del manual y notas cruzadas existan, mas conectado se vera ese grafo de forma organica - no hace falta ninguna herramienta extra, solo seguir enlazando notas relacionadas entre si. Si se quiere ir mas lejos (colores por carpeta/tag, agrupaciones visuales), se puede configurar en Settings -> Core plugins -> Graph view -> Groups.
- [ ] **Que el agente de IA (bot de Telegram) tenga acceso semantico al contenido del vault**, no solo busqueda por nombre de archivo como los comandos `/buscar` y `/enviar` actuales. Ver los 3 niveles de sofisticacion discutidos: (1) comando explicito que lee una nota concreta, (2) busqueda por palabra clave en el contenido - el siguiente paso logico dado el hardware actual, (3) busqueda semantica real (RAG) con embeddings, mas exigente en RAM y con una pieza de infraestructura nueva (base vectorial). Empezar por el nivel 2 cuando se retome esto.

## Ver tambien

- [[Modelos instalados]]
- [[Bot de Telegram - Arquitectura]]
