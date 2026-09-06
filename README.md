# 🕊️ PalomaGest — APK para Android

App Android oficial de **PalomaGest**, la gestión integral de palomares.
La APK envuelve la web app (Next.js) con Capacitor y se conecta a la misma
API en la nube: tu cuenta y tus datos están sincronizados entre web, PWA y Android.

## 📥 Descargar

| Versión | APK | Android mínimo |
|---------|-----|----------------|
| **v3.10.0** (actual) | [PalomaGest-v3.10.0.apk](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/download/v3.10.0/PalomaGest-v3.10.0.apk) | 7.0 (API 24) |
| v3.9.0 | [Release v3.9.0](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/tag/v3.9.0) | 7.0 (API 24) |
| v3.8.0 | [Release v3.8.0](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/tag/v3.8.0) | 7.0 (API 24) |
| v3.7.0 | [Release v3.7.0](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/tag/v3.7.0) | 7.0 (API 24) |
| v3.6.2 | [Release v3.6.2](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/tag/v3.6.2) | 7.0 (API 24) |
| v3.5.3 | [Release v3.5.3](https://github.com/ReidelAlcantara/PalomaGest-APK/releases/tag/v3.5.3) | 7.0 (API 24) |

> 💡 Enlace siempre actualizado a la última versión:
> https://github.com/ReidelAlcantara/PalomaGest-APK/releases/latest

## 📲 Instalación

1. Descarga el APK desde el enlace de arriba (desde tu teléfono).
2. Abre el archivo descargado. Android pedirá permiso para **instalar apps de fuentes desconocidas** — actívalo para tu navegador o gestor de archivos.
3. Instala y abre **PalomaGest**.
4. Inicia sesión con tu cuenta de email o crea una nueva (30 días de prueba gratis).

> La app Android usa el mismo backend que https://gestion-de-palomares-web-telegram-e.vercel.app — no es necesario volver a registrarse si ya tienes cuenta.

## ✨ Novedades v3.10.0

- 🔐 **Continuar con Google**: crea tu cuenta o entra con un toque, sin contraseñas
- 🔗 Vincula Google a tu cuenta email existente (conservas la contraseña)
- ✏️ Edita y elimina capturas sin conexión (con confirmación)
- 📊 Historial de éxitos por palomo instantáneo desde la copia local

Historial completo: [CHANGELOG-APK.md](./CHANGELOG-APK.md)

## 🔐 Firmas y confianza

- APK firmado (esquema v2/v3) con keystore propio del proyecto
- Package: `com.ada.palomagest.com`
- Actualiza directamente sobre versiones anteriores sin desinstalar

## 🛠️ Compilar desde el código

El código fuente vive en el repo principal
[ReidelAlcantara/Gestion-De-Palomares-Web-Telegram-Escritorio](https://github.com/ReidelAlcantara/Gestion-De-Palomares-Web-Telegram-Escritorio)
(scripts `mobile:build`, `mobile:sync` y proyecto Android con Capacitor 8).
