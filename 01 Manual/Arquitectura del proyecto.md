---
tags: [manual, arquitectura]
---

# Arquitectura del proyecto

Resumen para consulta rapida. La fuente completa y autoritativa es `docs/ARCHITECTURE.md` en la raiz del repositorio.

## Estructura de carpetas

```
IA-LOCAL/
├── bootstrap/       -> software de preparacion del entorno (scripts PowerShell)
├── infrastructure/  -> Docker, docker-compose.yml, .env
├── automation/      -> workflows de n8n, scripts
├── ai/              -> configuracion/prompts de modelos Ollama
├── knowledge/       -> este vault de Obsidian
├── docs/            -> ARCHITECTURE.md, PROGRESS.md, manual tecnico
├── resources/       -> iconos, diagramas, plantillas
├── backups/         -> backups con rotacion automatica
├── workspace/       -> IA-LOCAL.code-workspace
├── archive/         -> material descartado
├── projects/        -> proyectos personales sueltos, fuera del bootstrap
└── external/        -> repos de terceros clonados
```

## Principio clave

Una responsabilidad por carpeta y por modulo. Ningun modulo del bootstrap importa archivos internos de otro: la comunicacion pasa por funciones exportadas (ver [[Convenciones de Git]] para el flujo de trabajo asociado).


## Ver tambien

- [[Como usar el bootstrap]]
- [[Docker Compose - n8n]]
