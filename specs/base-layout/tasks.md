# Tareas: plantilla HTML común

Marca cada tarea como completada cambiando `[ ]` por `[x]` al ejecutarla.

## Preparación

- [x] Crear `docs/reference/` si aún no existe.
- [x] Crear `docs/reference/base.html` como documento HTML5 en español.
- [x] Añadir metadatos de codificación, viewport y título provisional.
- [x] Incluir Tailwind CSS v4 mediante el CDN Browser oficial indicado en el README.

## Estructura y navegación

- [x] Añadir `<header>` y `<nav>` semánticos con diseño responsive.
- [ ] Incluir marca enlazada a `index.html`.
- [ ] Incluir enlace al catálogo (`catalogo.html`) y al carrito (`carrito.html`).
- [ ] Añadir búsqueda con etiqueta accesible y destino válido para prototipo estático.
- [x] Mostrar acceso a cuenta sin simular un menú ni enlazar a una ruta inexistente.
- [x] Añadir `<main>` semántico completamente vacío.

## Footer

- [x] Crear un `<footer>` responsive con sección de categorías.
- [ ] Incluir calzado, camisas, pantalones y accesorios, sin destinos rotos.
- [x] Añadir enlaces o texto informativo para términos, privacidad y marca, sin rutas inexistentes.
- [x] Incluir contacto; identificarlo como información de demostración si no hay datos oficiales.

## Diseño, accesibilidad y límites

- [x] Aplicar la estética editorial y la paleta neutra de `DESIGN.md` con utilities de Tailwind.
- [x] Usar tipografía de sistema y espaciado generoso; evitar CSS adicional y estilos inline.
- [ ] Asegurar adaptación a móvil, tablet y escritorio sin scroll horizontal.
- [ ] Verificar etiquetas accesibles, contraste, foco visible y orden de teclado.
- [x] Confirmar que no haya JavaScript propio, frameworks, dependencias ni contenido específico de una vista.
- [x] Confirmar que `server.py` no se haya modificado.

## Revisión final

- [x] Comprobar que existen los landmarks `<header>`, `<nav>`, `<main>` vacío y `<footer>`.
- [ ] Revisar los enlaces internos para asegurar que no apunten a páginas inexistentes.
- [ ] Comparar la plantilla con los criterios de aceptación de `spec.md`.
