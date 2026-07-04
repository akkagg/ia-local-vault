---
tags: [n8n, backups]
---

# Gestion de workflows de n8n

El modulo `N8nManager` (opcion 3 del bootstrap) ofrece dos formas de backup, **no intercambiables**:

## Exportar workflows (opcion 1)

- Genera un JSON legible en `backups/n8n/workflows/`.
- Solo contiene la logica de los workflows (nodos, conexiones).
- **No incluye credenciales** (tokens, contrasenas guardadas en n8n).
- Util para versionar en git y ver diffs entre versiones de un workflow.

## Backup completo (opcion 3)

- Copia entero el volumen de datos de n8n (`infrastructure/volumes/n8n/`) a `backups/n8n/full-<fecha>/`.
- Incluye workflows, credenciales cifradas y la base de datos interna (SQLite).
- Es la unica copia que realmente restaura n8n a un estado identico.

## Importar workflows (opcion 2)

Pide la ruta de un JSON exportado. Tras importar, **hay que reasignar manualmente las credenciales** en cada nodo que las use (los IDs de credencial no coinciden entre instancias distintas de n8n).

## Ver tambien

- [[Workflows de n8n]] (07 Automatizaciones) - lista de workflows activos
- [[Bot de Telegram - Arquitectura]]
