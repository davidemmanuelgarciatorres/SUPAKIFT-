# SUPAKIFT – sitio web

Sitio estático (HTML/CSS/JS, sin dependencias ni build). Hosting: GitHub + Cloudflare. No requiere Netlify.

## Publicar
1. Sube el contenido de esta carpeta a un repositorio de GitHub, con `index.html` en la raíz.
2. En Cloudflare: Workers & Pages → Create → Pages → Connect to Git → elige el repositorio y la rama `main`.
3. Framework preset: None. Build command: vacío. Build output directory: `/` (la raíz).
4. Cada `git push` a `main` publica una nueva versión. Dominio propio: Custom domains en el proyecto.

## Antes de publicar
1. Reemplaza `https://TU-DOMINIO` en `index.html` (canonical, og:url, og:image, JSON-LD), `sitemap.xml` y `robots.txt`.
2. Agrega fotos en `img/` (WebP): `hero.webp`, `servicio-1.webp` … `servicio-8.webp`, `og.jpg` (1200×630). Si una falta, el sitio la oculta sin romperse.

## Archivos
- `_headers`: encabezados de seguridad y caché (Cloudflare los aplica automáticamente).
- `404.html`: página de error personalizada (Cloudflare la sirve sola si existe en la raíz).
- No se necesitan redirecciones: es una sola página con anclas.

## Edición
Bloque `CONFIG` al inicio del script de `index.html`: horario (`hours`), redes (`social`), proyectos del portafolio (`PROYECTOS`: titulo, categoria, descripcion, img, url).

## Formulario
Solo prepara el mensaje; el cliente lo envía por WhatsApp o correo. Para recibir solicitudes en servidor más adelante, reemplazar la función `enviar` por un `fetch` a una Cloudflare Pages Function.
