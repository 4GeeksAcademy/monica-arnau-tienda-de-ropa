# Plan: plantilla HTML común

## Objetivo

Crear `docs/reference/base.html` como estructura reutilizable para las páginas de la tienda, siguiendo `spec.md`, `AGENTS.md`, `CONTEXT.md` y `DESIGN.md`. Este plan describe el trabajo; no implementa la plantilla.

## Pasos

1. Crear el archivo `docs/reference/base.html` como documento HTML5 en español, con metadatos esenciales y título provisional.
2. Añadir Tailwind CSS v4 mediante el CDN Browser indicado por el README, sin incorporar JavaScript propio, CSS adicional ni dependencias.
3. Construir un `<header>` y una `<nav>` responsive con marca enlazada al inicio, catálogo, búsqueda accesible, cuenta y carrito; evitar destinos inexistentes.
4. Añadir un `<main>` semántico vacío para que las páginas incorporen contenido específico posteriormente.
5. Construir un `<footer>` adaptable con categorías, enlaces legales/de marca y contacto, sin enlaces rotos.
6. Aplicar la identidad de `DESIGN.md`: paleta neutra, acento borgoña discreto, tipografía de sistema editorial, espacio generoso y utilities de Tailwind.
7. Revisar semántica, accesibilidad, foco visible y adaptación móvil/tablet/escritorio; confirmar que no se modificó `server.py`.
