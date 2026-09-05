# 📋 Changelog de Versiones — APK PalomaGest

Historial de versiones publicadas del APK de Android.

---

## [3.8.0] — 2026-09-06

### 📴 Modo Offline: tus datos sin conexión + sync automática

- Consulta palomas y capturas sin datos móviles (copia local en el dispositivo, siempre disponible)
- **Registra capturas en el campo sin conexión** — se sincronizan solas al reconectar
- Alta de palomas, edición de perfil y baja también funcionan offline
- Sincronización bidireccional automática: al abrir la app, al recuperar la red y al volver a primer plano
- Panel de sincronización en Configuración: estado, cambios pendientes y botón "Sincronizar ahora"
- Operaciones idempotentes: si la conexión se corta a mitad de sync, nada se duplica
- Base de datos migrada a índices de sincronización por usuario (Prisma 7 + soft deletes)

---

## [3.7.0] — 2026-09-05

### 🔒 Auditoría de seguridad completa (5 fases) + estabilidad y rendimiento

- Todas las rutas API exigen sesión válida: cerrados los accesos sin autenticación y los accesos cruzados entre usuarios
- Protección anti fuerza bruta en el login + límite global de 300 peticiones/minuto
- Sesiones revocables: los tokens se invalidan al cambiar la contraseña o cerrar sesión
- 8 cabeceras de seguridad y aislamiento cross-origin (CSP, HSTS, COOP/CORP)
- Monitorización de errores con Sentry: los fallos se detectan y corrigen antes
- **FIX MiniApp de Telegram**: desbloqueados recursos web que degradaban la app (expansión, tema y datos nativos)
- Base de datos migrada a Prisma 7 (motor liviano sin Rust): consultas más rápidas
- 26 correcciones de renderizado y estado de React: interfaz más fluida
- Dependencias actualizadas y auditadas: 0 vulnerabilidades conocidas en producción

## [3.6.2] — 2026-09-01

### ↩️ Botón de retroceso de Android

- El botón de retroceso del sistema ya no cierra la app — retrocede a la pantalla anterior (palomas, capturas, tratamientos, reproducción, formularios)
- Si el menú lateral está abierto, el botón de retroceso lo cierra primero
- En la pantalla principal, doble pulsación para salir (con aviso)

## [3.6.1] — 2026-09-01

### 🎯 Fixes Android: capturas, perfil de paloma e icono unificado

- FIX: "Registro no encontrado" al abrir el detalle de capturas por palomo (la petición no enviaba el JWT)
- FIX: chips de rol/estado ya no se recortan en el perfil de la paloma
- Icono oficial de la APK unificado en web, PWA y Telegram

## [3.6.0] — 2026-08-31

### 🔄 Auto-actualización de la APK desde GitHub Releases

- La app comprueba GitHub Releases al iniciar y detecta versiones nuevas
- Dialog de actualización: "Actualizar ahora" o "Después" (se ofrece de nuevo al reiniciar)
- Descarga del APK con barra de progreso + instalación nativa de Android
- Gestión del permiso "Instalar apps desconocidas" (Android 8+)

---
## [3.5.3] — 2026-08-30

### 🎨 Nuevo icono de la app
- Paloma en vuelo con gradiente neón magenta→cian sobre azul marino profundo
- Rediseño completo en todas las densidades (adaptivo, legacy y redondo) + splash screen a juego

### 📱 FIX barras del sistema (edge-to-edge)
- **El encabezado ya no invade la barra de estado superior**
- **La barra de navegación inferior ya no invade la barra de gestos**
- El cristal del header y del bottom-nav se extiende elegantemente BAJO las barras del sistema
- Ajuste también en el menú lateral (drawer) y las hojas inferiores (notificaciones)
- Iconos claros en la barra de estado, coherentes con el tema oscuro Aurora

### 🆕 Mejoras
- Landing con botón de descarga directa del APK (hero + footer)
- Migraciones de base de datos formales (`migrate deploy` en cada deploy, sin sincronización destructiva)
- Cuentas de email verificadas tras el primer login exitoso

---

## [3.5.2] — 2026-08-30
