# 📋 Changelog de Versiones — APK PalomaGest

Historial de versiones publicadas del APK de Android.

---


## [4.1.0] — 2026-09-07

### 📴 Modo Offline para los contornos: catálogos, calendario, competiciones y mercado

- **Catálogos y perfil offline (Fase C1)**: colores, razas, clima, categorías y vademécum se consultan y editan sin conexión — se sincronizan al reconectar (operaciones idempotentes por usuario+lista+valor, sin duplicados)
- **Onboarding 100% offline**: una cuenta nueva sin datos móviles completa el asistente entero, incluidas las listas base del palomar (FIX: el wizard enviaba `listType` en vez de `type`)
- **Calendario de tratamientos offline (Fase C2)**: el calendario mensual de dosis se deriva del espejo local con la misma lógica del servidor — abre al instante sin conexión
- **Retirar paciente de un tratamiento (Fase C3)**: botón "Retirar paciente" en la ficha médica, con historial y réplica multi-dispositivo por sincronización (paridad con el DELETE REST)
- **Competiciones y Mercado en lectura offline (Fase C4)**: caché global de solo lectura con TTL de 24 h y aviso "Datos de hace Xh"; las escrituras siguen validándose en el servidor
- **Perfil del palomar editable sin conexión** (nombre, ubicación, logo), con aviso de guardado offline
- Los formularios de alta (paloma, captura, tratamiento, compra-venta) leen catálogos cache-first desde el primer uso
- 158 tests automáticos (+22); C5 (merge campo-a-campo) queda condicionada a demanda real

---


## [4.2.0] — 2026-09-07

### 🔐 Login simplificado + FIX del cuelgue de Google + auditoría completa

- **Solo Google y Telegram**: eliminado el registro/login por correo (básico y sin verificación). Si tu cuenta era de correo, entra con **Google usando el mismo correo** — tu palomar se vincula automáticamente
- **FIX Google colgado**: nuevo flujo de redirección completa (sin popups) — tras elegir tu cuenta y aceptar, la app vuelve sola; funciona en web, PWA y APK
- **APK**: tras el login con Google, la sesión vuelve automáticamente al shell nativo de la app (deep link interno) — antes quedabas atrapado en la versión web
- Auditoría exhaustiva (67 rutas API + motor offline + UI): 1 crítico + 9 bugs de alto impacto corregidos — informe completo en `docs/auditoria-v4.2.0.md` del repo
- FIX crítico: un usuario ya no puede borrar imágenes de otros usuarios (aislamiento por carpeta en Cloudinary)
- FIX crítico: el trabajo offline ya NO se pierde al expirar la sesión — la cola de sincronización sobrevive al re-login
- FIX catálogos offline (colores, razas, clima, categorías, vademécum): ahora se leen del espejo local correctamente tras el primer sync
- FIX calendario de tratamientos offline: los días coinciden exactamente con el servidor en cualquier zona horaria (incluida Cuba)
- FIX: tratamientos y reproducciones borrados sin conexión ya NO reaparecen en las vistas online
- FIX: máximo 3 pichones por reproducción también por la vía online; los puntos de premios ya no se duplican al corregir resultados
- MiniApp de Telegram: arranque corregido (expansión, tema y drawer desde el primer segundo)
- Pagos con Telegram Stars idempotentes: un reintento del webhook ya no extiende la licencia otro año
- 182 tests automáticos (+24 de regresión)

---

## [4.0.0] — 2026-09-06

### 🚀 Nueva generación: flujo Cuenta → Palomar y navegación renovada

- **NUEVO flujo de alta**: "Empezar Gratis" crea primero la **cuenta** (correo, Google o Telegram) y **después** se configura el palomar — fin del error "Acceso denegado, abre desde Telegram"
- **Logo del palomar elegido por el usuario**: se sube desde galería/cámara en el paso de configuración y en Configuración → Perfil (la foto de Telegram ya no lo sobrescribe)
- **Cerrar sesión** ahora existe en la UI (hoja "Más" en web/PWA)
- Landing renovado: icono oficial centrado sobre el badge de versión
- Configuración reorganizada: color e icono propios por lista (colores, razas, clima, categorías) con contador de ítems
- Administración también por correo (ADMIN_EMAIL) además del ID de Telegram
- Modo offline auditado y documentado por fases (docs/offline-fases-restantes.md)
- En la **APK se conserva el drawer** clásico junto a la barra inferior — el cambio de barra flotante aplica solo a web/PWA

---

## [3.10.0] — 2026-09-06

### 🔐 Cuentas con Google + edición de capturas sin conexión

- **"Continuar con Google"** en el login: crea tu cuenta o entra con un toque, sin contraseñas
- Si ya tenías cuenta con email, Google se **vincula automáticamente** (conservas tu contraseña: ambos accesos funcionan)
- Login verificado 100% en servidor (firma, audiencia y email verificado) con las mismas sesiones revocables de siempre
- **Edita capturas sin conexión**: corrige nombre, anilla, color, sexo, raza, fecha, hora, clima y observaciones en campo
- **Elimina capturas offline** con confirmación — el borrado se sincroniza y se propaga a tus otros dispositivos
- El historial de éxitos por palomo abre **instantáneo** desde la copia local (estadísticas y gráfico mensual incluidos)
- Mantiene todo el modo offline de v3.8/v3.9: las 5 entidades consultan, crean, editan y sincronizan sin datos

---

## [3.9.0] — 2026-09-06

### 📴 Modo Offline completo: Tratamientos, Reproducción y Compra/Venta

- **Registra tratamientos en el campo sin conexión** (con vademécum y frecuencias guardados en el equipo)
- Consulta y búsqueda de tratamientos offline; cierre de tratamiento offline (se marca terminado y recalcula duración)
- **Registra cruces sin conexión**: elige padres y corredores desde la copia local del palomar
- Evolución de fase del cruce, marcar cruce fallido y **registrar pichones offline** — todo sin datos
- **Compra/venta de palomas sin conexión**: la compra crea la paloma y la transacción en una sola operación; la venta registra la baja y la venta juntas
- Transacciones de artículos (accesorios, granos, medicina) también offline
- Resumen de compras/ventas calculado en local cuando no hay red
- Reglas de negocio centralizadas en el servidor: la cola offline nunca produce datos inconsistentes (fechas imposibles, cruces duplicados, ventas ajenas)

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
