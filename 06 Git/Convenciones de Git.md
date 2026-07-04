---
tags: [git, convenciones]
---

# Convenciones de Git

Fuente completa: `docs/ARCHITECTURE.md`, seccion 6.

## Ramas

- `main`: siempre estable, siempre instalable con `install.ps1`.
- `feature/<modulo>-<descripcion>`: desarrollo de cada pieza del roadmap.
- `docs/<tema>`: cambios exclusivos de documentacion.

## Commits

En ingles, formato `tipo(modulo): descripcion corta` (ej. `feat(doctor): add docker version check`).

## Que NUNCA se commitea

Definido en `.gitignore` (fusionado con las reglas que ya tenia el usuario antes de este proyecto):

- `infrastructure/.env` (contiene contraseñas y la clave de cifrado de n8n)
- `infrastructure/volumes/` (datos de los contenedores)
- `backups/*` (excepto `.gitkeep`)
- `external/*` y `archive/*` (excepto `.gitkeep`)
- `bootstrap/logs/`, `*.log`
- `node_modules/`, `__pycache__/`, bases de datos locales, `.vscode/` (heredado del proyecto anterior del usuario)

## Leccion aprendida: `.ps1` deben ser ASCII puro

No es una regla de Git en si, pero afecta a que se puede commitear con confianza: cualquier `.ps1`/`.psm1`/`.psd1` con tildes, enes o guiones largos puede romperse al ejecutarse en PowerShell 5.1 sin BOM UTF-8. Ver [[Arquitectura del proyecto]] para el detalle tecnico.

## Ver tambien

- [[Arquitectura del proyecto]]
