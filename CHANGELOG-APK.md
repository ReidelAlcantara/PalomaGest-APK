# 📋 Changelog de Versiones — APK PalomaGest

Historial de versiones publicadas del APK de Android.

---

## [3.5.2] — 2026-08-30

### 🔒 Seguridad
- Autenticación obligatoria en endpoints de perfil de usuario
- Rate limiting anti fuerza bruta en códigos de acceso (8 intentos/10 min) y activación de licencias (10/15 min)
- Webhook de pagos Telegram endurecido: validación de importe real (500 XTR) y firma obligatoria
- Cron jobs protegidos con secret obligatorio

### 🔧 Correcciones
- **Subida de fotos reparada**: perfil de palomas, publicaciones del mercado y logo del palomar vuelven a funcionar (migración a Cloudinary)
- **Activación de licencias por Telegram Stars reparada**: los pagos ahora activan la licencia correctamente
- Gráfico de Evolución Económica en Estadísticas con datos reales de los últimos 6 meses (antes mostraba datos falsos)
- Botones de administrador (Purgar Caché / Forzar Sync) ahora ejecutan acciones reales
- Botón "Limpiar Feed" del panel de notificaciones funcional
- Versión mostrada correctamente en el menú lateral

### 🆕 Mejoras
- `NEXT_PUBLIC_APP_URL` configurada: la APK ahora llama directo a la API de producción
- Diálogo de actualización automática al detectar nuevas versiones

---

## [3.5.1] — 2026-08-17

### Mercado
- Mercado: vincula palomas del palomar al publicar venta
- Al vender: la paloma se da de baja automáticamente del palomar
- Auto-completar título y foto al seleccionar paloma
- Aviso visible: "Al venderse se dará de baja del palomar"

### Interfaz
- Dialog de actualización: muestra novedades en cada release
- Progreso mensual de capturas rediseñado (barras más grandes)
- Podio adaptativo: se muestra con 1, 2 o 3 participantes

---

## [3.5.0] — 2026-08-16

### Plataforma Social
- Competiciones globales compartidas entre todos los criadores
- Rankings automáticos de capturas (semana/mes/año/histórico)
- Sistema de puntos acumulables canjeables por licencia (500 pts = 1 año)
- Premiación automática: 1º=200pts, 2º=120pts, 3º=80pts
- Mercado común: publica y compra palomas/artículos de todos los usuarios

---

## [3.4.0] — 2026-08-15

- Bottom Navigation Bar con 5 items aurora
- Pull-to-refresh en listados con indicador neón
- Haptic feedback nativo para APK (Capacitor)
- Skeleton loaders premium con shimmer aurora
- Búsqueda global de palomas en Command Palette (Ctrl+K)
- Cola de sincronización offline con localStorage
- Indicadores de offline/sincronizando en header

---

> Descarga siempre la última versión en:
> **https://github.com/ReidelAlcantara/PalomaGest-APK/releases/latest**
