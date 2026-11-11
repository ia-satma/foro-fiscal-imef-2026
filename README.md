# Foro Fiscal IMEF 2026 · Reformas Fiscales 2027 — landing

Sitio estático en un solo `index.html` (HTML, CSS y JS). No requiere build.

**Evento:** martes 17 de noviembre de 2026, 8:00 a 11:00 h · Club Industrial, Salón Panorámico, San Pedro Garza García, N.L.
Organiza IMEF Grupo Monterrey. Evento presentado por Basham, Ringe y Correa. Vale 3 puntos DPC.

## Archivos
- `index.html`: la landing completa.
- `img/`: logos, fondo de portada (`fondo-hero.webp`), QR de WhatsApp, imagen para redes (`og.jpg`).
- `img/p/`: fotos recortadas de ponentes y socios de IMEF (`<clave>.webp` 720 px, `<clave>-s.webp` 440 px, `<clave>-av.webp` avatar).
- `video/`: semblanzas en 720p H.264 (`sem-<clave>.mp4`) con su póster (`sem-<clave>.jpg`) y el promo general.
- `server.js`: servidor estático con módulos nativos de Node.js (soporta rangos para video).

## Editar contenido (todo al inicio del `<script>` final de `index.html`)
- **Liga de registro:** variable `REGISTRO` (hoy abre un correo a eventos@imefmty.com). Todos los botones de registro la usan.
- **Videos:** lista `VIDEOS`. Cada fila es un video de la galería; `listo:false` lo oculta.
  - Promo general: sube `video/promo-general.mp4` (y, si quieres, reemplaza el póster `video/promo-general.jpg`). La página detecta sola si el MP4 existe; mientras no exista, muestra el póster con el aviso "Muy pronto".
  - Semblanzas de IMEF (`video/sem-concepcion.mp4`, `sem-mancilla`, `sem-leon`, `sem-garza`, `sem-reyna`) y promos por panel (`video/promo-isr.mp4`, `promo-justicia`, `promo-aduanera`, `promo-defensa`, `promo-contexto`): sube el MP4 y su póster JPG con ese nombre y cambia `listo:false` a `listo:true`.
  - Formato recomendado: 1280×720, H.264 + AAC, `-movflags +faststart`, unos 2 MB por minuto.
- **Personas:** objeto `P` (nombre, cargo, empresa, papel en el foro, semblanza).
- **Fecha del contador:** constantes `INICIO` y `FIN` (hora de Monterrey, UTC-6).
- **Programa:** bloque `#agenda` (cada fila lleva `data-ini` y `data-fin` para la etiqueta "En vivo").

## Tipografía
Lexend (Google Fonts) es la letra del sitio. Si el equipo del visitante tiene Bukra instalada, los títulos la usan (`local()`); el archivo de Bukra no se publica porque es una fuente con licencia.

## Animación
GSAP 3.12.5 + ScrollTrigger desde cdnjs. Si el visitante pide reducir movimiento (o GSAP no carga), todo se muestra completo y sin animación.

## Publicar en GitHub Pages
Settings → Pages → Deploy from a branch → rama `main`, carpeta `/ (root)`.

## Usar en Replit
Importa este repositorio desde GitHub. Replit usa `.replit` para correr `npm start` en el puerto 3000.
