---
tags: [ollama, ia-local, hardware]
---

# Modelos instalados (Ollama)

## Hardware objetivo

Intel i5, 8 GB RAM. Regla de oro: **no correr varios modelos a la vez**, y evitar tener Docker + un modelo cargado + ngrok simultaneamente en tareas exigentes (puede saturar la maquina).

## Modelos recomendados (ligeros)

| Modelo | Uso |
|---|---|
| `qwen2.5:3b` | El que usamos en el bot de Telegram. El mas "pesado" de los tres, cuidado con el uso simultaneo de otras cosas |
| `phi3:mini` | Alternativa mas ligera si el equipo se ralentiza |
| `gemma2:2b` | La opcion mas ligera de las tres |

## Comandos utiles

```powershell
ollama list                    # ver modelos instalados
ollama pull <modelo>            # descargar/actualizar un modelo
ollama rm <modelo>               # eliminar un modelo (libera disco)
ollama stop <modelo>              # liberar RAM sin desinstalar el modelo
```

Si el equipo se queda "pillado" tras usar el bot de Telegram, lo mas probable es que el modelo siga cargado en RAM. Solucion rapida:

```powershell
ollama stop qwen2.5:3b
```

O si no responde: icono de Ollama en la bandeja del sistema -> Quit Ollama.

## Todo esto por script

El modulo `OllamaManager` (opcion 4 del bootstrap) automatiza list/pull/rm/probar-con-prompt desde un menu, sin escribir estos comandos a mano.

## Ver tambien

- [[Bot de Telegram - Arquitectura]]
- [[Como usar el bootstrap]]
