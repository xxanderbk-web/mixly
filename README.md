[GUIA_PLAY_STORE.md](https://github.com/user-attachments/files/25675631/GUIA_PLAY_STORE.md)
# 🚀 Guía: Publicar Mixly en Play Store

## Archivos que debes subir a mixly.lat
```
index.html   ← actualizado
manifest.json
sw.js
icons/
  icon-72.png
  icon-96.png
  icon-128.png
  icon-144.png
  icon-152.png
  icon-192.png
  icon-384.png
  icon-512.png
```

---

## PASO 1 — Verificar que la PWA funciona

1. Sube todos los archivos a tu servidor (GitHub, Netlify, etc.)
2. Abre **mixly.lat** en Chrome del celular
3. Aparecerá un banner "Instalar Mixly" → tócalo
4. Si no aparece: menú ⋮ → "Añadir a pantalla de inicio"
5. Verifica que abre sin barra del navegador ✓

---

## PASO 2 — Generar el APK con PWABuilder

1. Ve a **https://www.pwabuilder.com**
2. Escribe `https://mixly.lat` y presiona Enter
3. Espera el análisis (30 segundos)
4. Haz clic en **"Package for stores"**
5. Selecciona **Android**
6. Descarga el paquete `.zip`

---

## PASO 3 — Firmar el APK (requerido por Google)

PWABuilder genera un archivo `assetlinks.json` que debes subir a:
```
https://mixly.lat/.well-known/assetlinks.json
```
Crea la carpeta `.well-known/` en tu servidor y sube ese archivo.

---

## PASO 4 — Crear cuenta de desarrollador Google

1. Ve a **https://play.google.com/console**
2. Paga el registro único de **USD $25**
3. Completa tu perfil de desarrollador

---

## PASO 5 — Crear la app en Play Console

1. "Crear aplicación"
2. Nombre: **Mixly**
3. Idioma: Español
4. Tipo: App (no juego)
5. Gratis / De pago: Gratis

---

## PASO 6 — Completar ficha de Play Store

### Descripción corta (80 chars):
```
Sistema de gestión para bares: stock, recetas y costeo
```

### Descripción completa:
```
Mixly es el sistema de gestión diseñado especialmente para bares 
y bartenders profesionales.

✅ INVENTARIO — Control de stock en barra y bodega, alertas de 
mínimos, pedidos sugeridos por proveedor.

🍹 RECETARIO — Crea tus cócteles con ingredientes del catálogo, 
calcula el costo en tiempo real.

💰 COSTEO — Conoce el margen de cada receta al instante.

📋 FICHAS TÉCNICAS — Genera fichas imprimibles con colores 
personalizados para tu barra.

⏱ TIMERS — Temporizadores para jarabes, macerados y preparaciones.

📉 MERMAS — Registra y analiza pérdidas con reportes mensuales en Excel.

📦 PRODUCTOS — Catálogo maestro con precio por unidad, proveedor 
y stock mínimo.

Diseñado para funcionar en celular durante el servicio.
```

### Categoría: **Negocios**

### Screenshots requeridos:
- Mínimo 2 capturas de pantalla del celular (1080x1920px)
- Toma capturas de Inventario, Recetario y Home

---

## PASO 7 — Subir el APK

1. En Play Console → "Versiones" → "Producción"
2. "Crear nueva versión"
3. Sube el archivo `.aab` que generó PWABuilder
4. Notas de versión: "Primera versión de Mixly"
5. Guardar → Revisar → Enviar

---

## PASO 8 — Esperar revisión

Google demora entre **1 y 3 días hábiles** en revisar apps nuevas.
Recibirás un email cuando esté aprobada.

---

## ⚠️ Requisitos importantes

- El dominio debe tener **HTTPS** (mixly.lat ya lo tiene ✓)
- El `assetlinks.json` debe estar accesible públicamente
- Las capturas deben mostrar la app real, no mockups

---

## 💡 Tips

- Si PWABuilder da score bajo, revisa que `sw.js` y `manifest.json` 
  sean accesibles desde el navegador antes de generar el APK
- Para iOS (App Store), el proceso es diferente y más costoso ($99/año)
- Una vez publicada en Play Store, las actualizaciones se aplican 
  automáticamente al actualizar mixly.lat — no necesitas re-subir el APK
