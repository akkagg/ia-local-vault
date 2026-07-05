---
tags: [manual, glosario]
---

# Manual - Cap 10 - Glosario general

---

Glosario consolidado de todos los capitulos, en orden alfabetico. Cada termino enlaza (mentalmente) al capitulo donde se explica en contexto.

- **ASCII puro**: texto que usa solo los caracteres basicos ingleses (sin tildes, eñes ni simbolos especiales), evitando problemas de codificacion en PowerShell 5.1. (Cap 1)
- **Contenedor**: entorno aislado donde corre un servicio (ej. n8n), sin instalarse directamente en el sistema operativo del host. (Cap 1)
- **Credencial (n8n)**: datos de acceso a un servicio externo (ej. token de Telegram), guardados cifrados dentro de la base de datos de n8n. (Cap 4)
- **Dashboard**: vista de estado operativo (servicios corriendo ahora mismo), distinta del diagnostico de instalacion que hace Doctor. (Cap 2)
- **Daemon de Docker**: proceso en segundo plano que gestiona los contenedores; si no esta corriendo, ningun comando `docker` funciona. (Cap 3)
- **Docker Compose**: herramienta que describe y orquesta uno o varios contenedores a partir de un archivo declarativo (`docker-compose.yml`). (Cap 3)
- **Execution**: cada vez que un workflow de n8n se ejecuta, ya sea manualmente o disparado por un trigger. (Cap 4)
- **host.docker.internal**: nombre de dominio especial que Docker Desktop expone dentro de los contenedores para alcanzar servicios que corren en el host, no dentro de Docker. (Cap 5, Cap 6)
- **Loopback (127.0.0.1)**: interfaz de red que solo acepta conexiones del propio equipo; no es la misma ruta que usan los contenedores para hablar con el host. (Cap 5)
- **Manifiesto de modulo (`.psd1`)**: archivo que describe un modulo de PowerShell (version, funciones exportadas, archivo `.psm1` asociado), sin contener la logica en si. (Cap 2)
- **Merge conflict**: situacion en la que Git no puede combinar automaticamente dos cambios distintos sobre la misma parte de un archivo. (Cap 9)
- **MOC (Map of Content)**: nota que actua como indice tematico, enlazando a otras notas relacionadas sin desarrollar el contenido ella misma. (Cap 8)
- **Modulo (PowerShell)**: conjunto de funciones relacionadas, empaquetado en un `.psm1` con su manifiesto `.psd1`. (Cap 1)
- **Nodo (n8n)**: cada bloque individual de un workflow (trigger, peticion HTTP, envio de mensaje, etc.). (Cap 4)
- **Parametros de un modelo (ej. "3b")**: tamaño del modelo en miles de millones de parametros; mas parametros implica mejores respuestas pero mayor consumo de RAM y mas lentitud. (Cap 5)
- **PATH**: lista de carpetas donde el sistema operativo busca ejecutables cuando escribes un comando. (Cap 2)
- **Personal Access Token (PAT)**: credencial que GitHub genera para autenticar operaciones de Git por HTTPS, en sustitucion de la contrasena de la cuenta. (Cap 9)
- **Recrear un contenedor**: destruir el contenedor actual y crear uno nuevo con la imagen actualizada, sin tocar los datos del volumen asociado. (Cap 7)
- **Repositorio remoto**: copia del repositorio alojada en un servidor (ej. GitHub), usada como punto de sincronizacion entre dispositivos. (Cap 9)
- **Rotacion de backups**: eliminar automaticamente las copias mas antiguas cuando se supera un numero maximo, para no llenar el disco indefinidamente. (Cap 7)
- **Tunel (ngrok)**: servicio que expone temporalmente un puerto local a traves de una URL publica HTTPS. (Cap 6)
- **Vista de grafo**: representacion visual del vault donde cada nota es un nodo y cada wikilink una conexion entre nodos. (Cap 8)
- **Volumen (Docker)**: carpeta del host montada dentro de un contenedor, que persiste aunque el contenedor se destruya y recree. (Cap 3)
- **Webhook**: URL que un servicio externo llama automaticamente cuando ocurre un evento, en vez de que tu sistema tenga que preguntar constantemente si hay algo nuevo. (Cap 6)
- **Wikilink**: enlace interno de Obsidian con sintaxis `[[Nombre de la nota]]`, que ademas alimenta la vista de grafo. (Cap 8)

## Ver tambien

- [[Manual Tecnico - Indice]]
- [[Manual - Cap 9 - Sincronizacion del vault entre dispositivos]]
