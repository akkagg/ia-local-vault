---
tags: [manual, bootstrap]
---

# Como usar el bootstrap

El punto de entrada unico es `bootstrap/install.ps1`. Al ejecutarlo:

```powershell
cd C:\Users\avyev\Desktop\IA-LOCAL\bootstrap
.\install.ps1
```

Primero muestra el **Dashboard** automaticamente (estado de Docker, n8n, modelos de Ollama y ultimo backup), y despues entra al menu principal:

| Opcion | Modulo         | Que hace                                                            |
| ------ | -------------- | ------------------------------------------------------------------- |
| 0      | Dashboard      | Ver el estado operativo de nuevo                                    |
| 1      | Doctor         | Comprobar que las herramientas necesarias estan instaladas          |
| 2      | Docker Manager | up / down / restart / status / logs de los contenedores             |
| 3      | N8n Manager    | Exportar/importar workflows, backup del volumen de n8n, abrir la UI |
| 4      | Ollama Manager | Ver, descargar, eliminar y probar modelos de IA local               |
| 5      | Backup Manager | Backup completo del proyecto con rotacion automatica                |
| 6      | Update Manager | Actualizar la imagen de n8n y los modelos de Ollama                 |
| 9      | Salir          | Cierra el bootstrap                                                 |

## Nota sobre archivos descargados

Cualquier `.ps1` nuevo descargado desde el navegador queda marcado por Windows como "de Internet" y se bloquea. Antes de ejecutarlo:

```powershell
Get-ChildItem -Recurse -Filter *.ps*1 | Unblock-File
```

## Ver tambien

- [[Arquitectura del proyecto]]
- [[Docker Compose - n8n]]
- [[Gestion de workflows de n8n]]
- [[Modelos instalados]]
