# PicConvert

Una extensión de navegador ligera que convierte imágenes entre formatos PNG, JPG, WEBP y AVIF — completamente local, sin subida de datos.

> Basado en Chromium · Manifest V3 · Sin rastreo · 100% procesado en el navegador

[English](README.md) | [中文](README_zh.md) | Español | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

---

## ¿Por qué PicConvert?

La mayoría de herramientas de conversión de imágenes requieren subir tus archivos a un servidor remoto. PicConvert hace todo dentro de tu navegador usando la API Canvas — tus datos nunca salen de tu dispositivo.

| Ventaja | Detalle |
|---------|---------|
| 🔒 **100% Privado** | Todo el procesamiento ocurre en la memoria de tu navegador. Sin servidores, sin subidas, sin rastreo. |
| ⚡ **Conversión Instantánea** | Imágenes ≤5MB se convierten en menos de 500ms. Sin esperar respuestas del servidor. |
| 🎯 **Cero Dependencias** | Construido con JavaScript nativo y APIs nativas de Chrome. Sin frameworks, sin bloat. |
| 🌍 **6 Idiomas** | Detecta automáticamente el idioma de tu navegador — inglés, español, alemán, japonés, francés, chino. |
| 📋 **Copiar y Guardar** | Clic derecho en cualquier imagen para guardar como archivo O copiar directamente al portapapeles. |
| 📁 **Arrastrar y Soltar** | Arrastra imágenes locales al popup para conversión rápida. |

---

## Características

| Característica | Descripción |
|----------------|-------------|
| 🖼️ **4 Formatos** | Convertir a PNG (sin pérdida), JPG (alta calidad), WEBP (compacto) o AVIF (mejor compresión) |
| 📋 **Copiar al Portapapeles** | Clic derecho → Copiar como PNG/JPG/WEBP/AVIF — pegar directamente en correos, chats, documentos |
| 📊 **Comparación de Tamaño** | Notificación toast muestra tamaño original vs convertido con porcentaje de ahorro |
| 🎚️ **Calidad Ajustable** | Ajusta fino la calidad de exportación para JPG, WEBP y AVIF mediante deslizadores en el popup |
| 🔗 **Limpieza Inteligente de Enlaces** | Elimina parámetros de seguimiento CDN (`w=`, `h=`, `format=`, `watermark=`, etc.) para obtener imágenes originales |
| 📁 **Arrastrar y Soltar** | Arrastra archivos de imagen locales al popup para convertir sin clic derecho |
| 🌐 **Soporte Cross-Origin** | Obtiene imágenes de cualquier sitio web vía Service Worker — evita problemas de CORS y canvas taint |
| 🔤 **i18n en 6 Idiomas** | Menú contextual y UI se adaptan automáticamente al idioma de tu navegador (EN/ES/DE/JA/FR/ZH-CN) |
| 🛡️ **Relleno Blanco JPG** | Rellena automáticamente fondos transparentes con blanco al convertir PNG → JPG |
| ⏱️ **Protección contra Duplicados** | Ignora clics repetidos en la misma imagen dentro de 2 segundos |
| 📦 **Manejo de Imágenes Grandes** | Imágenes >20MB muestran un indicador de procesamiento asíncrono en lugar de congelar la UI |

---

## Vista Previa

<!-- Reemplazar con capturas reales -->
<p align="center">
  <img src="assets/popup.png" alt="PicConvert Popup" width="360">
</p>

<p align="center">
  <img src="assets/context-menu.png" alt="Menú Contextual PicConvert">
</p>

---

## Navegadores Soportados

| Navegador | Estado |
|-----------|--------|
| Google Chrome | ✅ Totalmente soportado |
| Microsoft Edge | ✅ Totalmente soportado |
| Brave | ✅ Soportado |
| Opera | ✅ Soportado |
| Vivaldi | ✅ Soportado |
| Cualquier navegador basado en Chromium | ✅ Soportado (Manifest V3) |

---

## Instalación

### Desde Código Fuente (Modo Desarrollador)

1. Abre la página de extensiones de tu navegador:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Activa el **Modo desarrollador** (interruptor arriba a la derecha)
3. Haz clic en **Cargar desempaquetado** y selecciona la carpeta `pic-convert`
4. El icono ✨ PicConvert aparecerá en tu barra de herramientas

---

## Uso

### Conversión por Clic Derecho

1. Haz clic derecho en cualquier imagen de una página web
2. Selecciona **PicConvert** del menú contextual
3. Elige **Guardar como** o **Copiar como**
4. Elige tu formato: PNG, JPG, WEBP o AVIF
5. Listo — el archivo se descarga instantáneamente, o la imagen se copia al portapapeles

### Arrastrar y Soltar

1. Haz clic en el icono de PicConvert en tu barra de herramientas para abrir el popup
2. Arrastra un archivo de imagen local a la zona de drop
3. Selecciona tu formato destino
4. El archivo convertido se descarga automáticamente

### Configuración de Calidad

Abre el popup para ajustar la calidad de exportación para JPG, WEBP y AVIF usando los deslizadores. PNG siempre es sin pérdida. La configuración se guarda automáticamente.

---

## Estructura del Menú Contextual

```
PicConvert
├── Guardar como PNG (Sin pérdida)
├── Guardar como JPG (Alta calidad)
├── Guardar como WEBP (Compacto)
├── Guardar como AVIF (Mejor compresión)
├── Copiar como PNG (Sin pérdida)
├── Copiar como JPG (Alta calidad)
├── Copiar como WEBP (Compacto)
└── Copiar como AVIF (Mejor compresión)
```

Los menús **Copiar como** y **Guardar como** solo aparecen al hacer clic derecho en imágenes o enlaces que apuntan a archivos de imagen (`.png`, `.jpg`, `.jpeg`, `.webp`, `.avif`, `.gif`, `.bmp`, `.jfif`, `.svg`).

---

## Privacidad

PicConvert está construido con la privacidad como principio fundamental:

- ✅ **Cero subida de datos** — Todo el procesamiento de imágenes ocurre en la memoria de tu navegador
- ✅ **Sin análisis** — Sin rastreo, sin telemetría, sin llamadas remotas
- ✅ **Sin cookies** — Sin lectura ni escritura de cookies del navegador
- ✅ **Sin historial de navegación** — Sin acceso a tus datos de navegación
- ✅ **Solo memoria temporal** — Las imágenes existen en memoria durante la conversión y se destruyen inmediatamente después
- ✅ **Permisos mínimos** — Solo solicita lo estrictamente necesario: `contextMenus`, `downloads`, `offscreen`, `storage`, `clipboardWrite`

---

## Cómo Funciona

```
Clic derecho en imagen
       ↓
Service Worker obtiene blob de imagen (evita CORS)
       ↓
Envía blob al documento Offscreen (DOM oculto con acceso a Canvas)
       ↓
Canvas dibuja imagen a resolución nativa
       ↓
Exporta como formato destino con calidad especificada
       ↓
Retorna URL de datos → dispara descarga o copia al portapapeles
       ↓
Destruye todos los recursos temporales (blob, canvas, elemento de imagen)
```

> **¿Por qué Offscreen?** El Manifest V3 de Chrome ejecuta el fondo como Service Worker, que no tiene acceso al DOM. La API Canvas requiere un DOM, por lo que usamos la API Offscreen de Chrome para crear un documento oculto para el procesamiento de imágenes.

---

## Calidad de Exportación por Defecto

| Formato | Calidad | Notas |
|---------|---------|-------|
| PNG | Sin pérdida | Sin configuración de calidad — siempre preserva calidad total y transparencia |
| JPG | 92 | Alta calidad, buen equilibrio entre tamaño y claridad |
| WEBP | 90 | Formato moderno, ~25-35% más pequeño que JPG con calidad equivalente |
| AVIF | 70 | Próximo formato, ~20-30% más pequeño que WEBP, mejor para entrega web |

Todos los valores de calidad son ajustables mediante deslizadores en el popup (rango: 10–100).

---

## Licencia

Copyright © 2026 PicConvert. Todos los derechos reservados.

---

## ❤️ Apoyar

Si PicConvert te resulta útil, ¡considera apoyar el proyecto!

<!-- Agrega tu enlace de apoyo aquí -->
**[👉 Apoyar PicConvert](https://annmax1983.github.io/PicConvert/)**

---

> **Nota:** Todas las funciones principales de conversión siempre permanecerán gratuitas y sin limitaciones.
