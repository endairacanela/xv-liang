# XV's Liang — Invitación digital

Invitación web para los XV años de Liang (19 de diciembre, Salón Eclipse Eventos, Chetumal).
Los invitados abren el sobre virtual, ven la invitación, la galería de fotos, el mapa del salón
y confirman su asistencia por WhatsApp.

## Tecnología
- HTML, CSS y JavaScript sin dependencias ni paso de compilación (todo vive en `public/index.html`).
- Alojado en Netlify; `public/_headers` define la caché y el `noindex` para que no aparezca en buscadores.
- Vista previa al compartir (WhatsApp, Facebook, iMessage) mediante etiquetas Open Graph y `public/og-image.jpg`.

## Estructura
- `public/index.html` — la invitación completa
- `public/images/` — fotos de la galería, mapa y logo
- `public/og-image.jpg` — imagen de vista previa (1200×630)
- `public/favicon*`, `public/icon-*.png`, `public/site.webmanifest` — íconos

## Ejecutar localmente
Cualquier servidor estático sirve, por ejemplo:

```bash
netlify dev --port 8889
# o bien
npx serve public
```

## Cambios comunes
- **Dirección del sitio**: si cambias el nombre del sitio en Netlify o usas un dominio propio,
  actualiza las tres URLs `https://website-e44492.netlify.app` en el bloque "Vista previa" de `public/index.html`.
- **Música**: copia un archivo (p. ej. `musica.mp3`) a `public/` y escribe su ruta en
  `<audio id="bgm" ... src="">`. El botón de música aparece automáticamente.
- **Número de WhatsApp / textos de confirmación**: enlaces `wa.me` en la sección de confirmación.
