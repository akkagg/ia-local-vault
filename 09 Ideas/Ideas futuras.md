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
- [ ] Poblar el resto del vault con notas de uso real conforme se vayan creando mas workflows y prompts.

## Ver tambien

- [[Modelos instalados]]
- [[Bot de Telegram - Arquitectura]]
