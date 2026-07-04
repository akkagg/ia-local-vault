---
tags: [prompts, plantilla]
---

# Plantilla de prompt

Usar esta estructura al disenar prompts para el modelo local (via Ollama Manager, opcion 5, o desde el bot de Telegram):

```
Rol: [quien es el asistente en este contexto]
Contexto: [informacion de fondo necesaria]
Tarea: [que debe hacer exactamente]
Formato de salida: [como debe responder: lista, parrafo corto, JSON...]
Restricciones: [longitud maxima, tono, que evitar]
```

## Notas sobre modelos ligeros (2-4B parametros)

Los modelos como `qwen2.5:3b`, `phi3:mini` o `gemma2:2b` responden mejor con instrucciones **cortas y directas** que con prompts largos y ambiguos. Evitar pedir varias tareas encadenadas en un solo prompt.

## Prompts guardados

(Anadir aqui los prompts que funcionen bien, con una breve nota de para que sirven)
