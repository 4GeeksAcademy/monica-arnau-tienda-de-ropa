# Plan: página de inicio

## Objetivo

Crear `index.html` en la raíz siguiendo `specs/home/spec.md`, `DESIGN.md` y la estructura común de `docs/reference/base.html`. Este plan describe el trabajo; no implementa la página.

## Pasos

1. Partir de la estructura de `base.html`; adaptar las rutas relativas para la raíz y conservar la navbar y el footer compartidos.
2. Añadir los metadatos de la portada, el CDN de Tailwind CSS v4 y microdatos Schema.org para `WebPage` y `Organization`, sin inventar datos oficiales.
3. Construir el `<main>` con una campaña y su enlace al catálogo, seguida de secciones separadas de nuevos lanzamientos y más vendidos, con al menos tres tarjetas en cada sección.
4. Crear o seleccionar imágenes según la dirección creativa de la spec; optimizarlas, añadir texto alternativo y dimensiones, y reservar `loading="lazy"` para imágenes fuera de la primera pantalla.
5. Aplicar las utilities de Tailwind de `DESIGN.md`: estilo editorial, paleta neutra, tipografía de sistema y composición adaptable a móvil, tablet y escritorio.
6. Revisar jerarquía semántica, accesibilidad, enlaces existentes, desbordamiento horizontal y restricciones del proyecto: sin JavaScript propio, CSS adicional, dependencias ni cambios a `server.py`.