# Portafolio — Alejandra Ibarbo Álvarez

Sitio estático (HTML/CSS/JS puro, sin dependencias de build) listo para publicarse en **GitHub Pages**.

## Estructura

```
portafolio/
├── index.html
├── proyecto-nimbo.html        ← página individual de cada proyecto
├── proyecto-ondamovil.html
├── proyecto-cauce.html
├── css/style.css
├── js/script.js
├── assets/images/     ← aquí van tus ilustraciones (ahora hay placeholders SVG)
└── README.md
```

## 1. Agregar o editar proyectos

Cada proyecto tiene su propia página HTML (`proyecto-nimbo.html`, `proyecto-ondamovil.html`, `proyecto-cauce.html`). Dentro de cada una puedes editar directamente:
- El título, año y etiquetas (arriba, en `<header class="project-header">`)
- La imagen de portada (`<div class="project-cover">`)
- El texto de descripción, con secciones "Proceso" y "Resultado" que puedes ampliar o renombrar
- La galería de imágenes adicionales al final (`<div class="project-gallery">`) — agrega tantas `<img>` como quieras dentro de ese bloque
- La navegación "Anterior / Siguiente" al final de la página, que enlaza a los otros proyectos

Para agregar un **nuevo proyecto**: duplica uno de los archivos `proyecto-*.html`, cámbiale el nombre, edita su contenido, y agrega una tarjeta nueva en `index.html` (dentro de `<div class="grid" id="projectGrid">`) que enlace a tu nuevo archivo con `<a class="card project-card" href="tu-archivo.html">`.

## 2. Reemplazar las imágenes

En `assets/images/` hay 6 placeholders (`proyecto-1.svg`, `proyecto-2.svg`, `proyecto-3.svg`, `personal-1.svg`, `personal-2.svg`, `personal-3.svg`). Sustitúyelos por tus ilustraciones reales (`.jpg`, `.png` o `.webp`) **con el mismo nombre de archivo**, o si usas otro nombre, actualiza la ruta correspondiente en el atributo `src` dentro de `index.html` (busca `<img src="assets/images/...`).

Recomendación: exporta las imágenes a un ancho de ~1200px y compréssalas (por ejemplo con [Squoosh](https://squoosh.app)) para que el sitio cargue rápido.

## 3. Editar el resto de textos

Todo el contenido (nombre de proyectos, año, categoría, bio, correo, redes) está directamente en `index.html`, en español y fácil de ubicar por sección:
- `<!-- ============ HERO ============ -->`
- `<!-- ============ TRABAJOS ============ -->`
- `<!-- ============ SOBRE MÍ ============ -->`
- `<!-- ============ CONTACTO ============ -->`

**Pendientes que debes cambiar tú:**
- `tunombre@ejemplo.com` → tu correo real (aparece en la sección de contacto)
- `https://instagram.com/tunombre` → tu usuario real de Instagram
- `https://www.tiktok.com/@tunombre` → tu usuario real de TikTok

## 4. Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `portafolio` o `tuusuario.github.io`).
2. Sube el contenido de esta carpeta a la raíz del repositorio:
   ```bash
   cd portafolio
   git init
   git add .
   git commit -m "Primer despliegue del portafolio"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
   git push -u origin main
   ```
3. En GitHub, ve a **Settings → Pages**.
4. En "Build and deployment", selecciona **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
5. Guarda. En 1-2 minutos tu sitio estará en `https://TU-USUARIO.github.io/TU-REPO/` (o en `https://TU-USUARIO.github.io/` si el repo se llama `TU-USUARIO.github.io`).

## Notas de diseño

- El sitio usa el motivo de "herramienta vectorial" (nodos, trazos, capas) como hilo conductor: nombre en el hero se dibuja como un trazo, las tarjetas muestran "puntos de anclaje" al pasar el cursor, y cada proyecto tiene su propia página con más espacio para imágenes y contexto. La galería usa un visor (lightbox) con navegación por flechas.
- Tipografías vía Google Fonts (Space Grotesk, Inter, JetBrains Mono) — se cargan por CDN, no requieren instalación.
- 100% responsive, con estados de foco visibles y `prefers-reduced-motion` respetado.
- No requiere ningún framework ni paso de compilación: es compatible con GitHub Pages tal cual.
