# Tareas: página de inicio

Marca cada tarea como completada cambiando `[ ]` por `[x]` al ejecutarla.

## Documento y estructura compartida

- [x] Crear `index.html` en la raíz como documento HTML5 en español.
- [x] Añadir metadatos de codificación, viewport, título descriptivo y resumen de la página.
- [x] Incluir Tailwind CSS v4 mediante el CDN Browser oficial indicado en `README.es.md`.
- [x] Adaptar la navbar de `docs/reference/base.html` a la raíz, conservando marca, catálogo, búsqueda accesible, cuenta informativa y carrito.
- [ ] Adaptar el footer común, conservando categorías, información legal/de marca y contacto sin enlaces rotos.
- [x] Mantener `<header>`, `<nav>`, `<main>` y `<footer>` como landmarks y evitar duplicar la navegación compartida.

## Contenido de inicio

- [x] Añadir dentro de `<main>` una campaña con imagen protagonista, un único `<h1>`, texto breve y llamada a `catalogo.html`.
- [x] Crear la sección «Nuevos lanzamientos» con al menos tres tarjetas.
- [x] Crear la sección «Más vendidos» con al menos tres tarjetas y diferenciarlas editorialmente de las novedades.
- [x] Incluir en cada tarjeta imagen, texto alternativo, nombre, precio en euros y enlace descriptivo a `producto.html`.
- [x] Usar únicamente contenido de demostración y evitar afirmar disponibilidad, popularidad, descuentos o características no verificadas.

## Imágenes y datos estructurados

- [x] Crear o seleccionar imágenes siguiendo la dirección creativa de `specs/home/spec.md`, sin usar recursos locales inexistentes.
- [x] Optimizar las imágenes y declarar `width` y `height` cuando estén disponibles.
- [x] No aplicar `loading="lazy"` a la imagen principal; permitirlo en imágenes secundarias fuera de la primera pantalla.
- [x] Añadir microdatos Schema.org `WebPage` y `Organization` sin inventar datos oficiales ni `SearchAction` no funcional.

## Diseño, accesibilidad y límites

- [x] Aplicar la paleta, tipografía de sistema y estilo editorial definidos en `DESIGN.md` mediante utilities de Tailwind.
- [x] Adaptar la campaña y las tarjetas a móvil, tablet y escritorio sin provocar scroll horizontal.
- [x] Verificar encabezados ordenados, textos alternativos, enlaces descriptivos, contraste y foco visible.
- [ ] Confirmar que los enlaces internos apunten a páginas existentes y que no haya acciones que aparenten mantener estado.
- [x] Confirmar que no se añadieron JavaScript propio, CSS adicional, dependencias ni cambios a `server.py`.

## Revisión final

- [ ] Comparar `index.html` con los criterios de aceptación de `specs/home/spec.md`.
- [ ] Abrir la portada y revisar visualmente la navegación, las imágenes y el layout en móvil, tablet y escritorio.