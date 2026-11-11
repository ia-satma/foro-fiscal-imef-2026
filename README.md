# Foro Fiscal IMEF 2026 · Reformas Fiscales 2027 — landing

Sitio estático. No requiere build.

**Evento:** martes 17 de noviembre de 2026, 8:00 a 11:00 h · Club Industrial, Salón Panorámico, San Pedro Garza García, N.L.
Organiza IMEF Grupo Monterrey. Evento presentado por Basham, Ringe y Correa. Vale 3 puntos DPC.

## Archivos
- `index.html`: la landing completa (HTML, CSS y JS en un solo archivo; Lexend desde Google Fonts).
- `img/`: logos, fondo, QR de WhatsApp y fotos de ponentes (`img/p/`).
- `server.js`: servidor estático con módulos nativos de Node.js.

## Editar contenido
Desde `index.html`:
- **Liga de registro:** variable `REGISTRO` al inicio del script (hoy abre un correo a eventos@imefmty.com).
- Fecha del contador: constantes `INICIO` y `FIN` (hora de Monterrey, UTC-6).
- Programa: listas `.agenda` (cada fila lleva `data-ini` y `data-fin` para la etiqueta "En vivo").
- Semblanzas: objeto `P` en el script.

## Publicar en GitHub Pages
Settings → Pages → Deploy from a branch → rama `main`, carpeta `/ (root)`.

## Usar en Replit
Importa este repositorio desde GitHub. Replit usa `.replit` para correr `npm start` en el puerto 3000.
