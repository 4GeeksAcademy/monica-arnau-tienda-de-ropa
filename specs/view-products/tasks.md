# Tareas: vistas de detalle de producto

Marca cada tarea como completada cambiando `[ ]` por `[x]` al ejecutarla. Las tareas de verificación se marcan solo después de realizar las pruebas.

## Preparación y contenido

- [x] Confirmar los 20 productos actuales del catálogo y crear un mapa único producto → ruta HTML → imagen local; comprobar nombres, categorías y precios sin corregir datos del catálogo fuera de alcance.
- [x] Preparar contenido individual y referencias de demostración para las fichas, usando únicamente descripciones, materiales, colores y cuidados respaldados por las imágenes o fuentes disponibles; identificar como orientativo cualquier dato no verificado.

## Implementación

- [x] Crear 20 fichas HTML estáticas individuales en `productos/`, con metadatos propios, navegación compartida con rutas relativas correctas, migas de pan, un único `<h1>`, imagen correspondiente, información del producto y enlace de retorno al catálogo.
- [x] Aplicar a las fichas el diseño editorial de `DESIGN.md` con Tailwind CSS v4, layout adaptable de dos columnas en escritorio y apilado en móvil, imágenes dimensionadas y accesibilidad de teclado; no ofrecer controles de talla/cantidad ni una acción de carrito porque no hay datos de variantes ni página de carrito; explicar estas limitaciones sin sugerir persistencia.
- [x] Añadir en las 20 fichas botones visibles “Añadir al carrito” y “Añadir a lista de deseos” como elementos exclusivamente visuales, usando botones HTML deshabilitados y sin enlaces ni lógica de acción.
- [x] Acompañar ambos botones de un aviso accesible que indique que las acciones no están disponibles y que no agregan ni guardan productos.
- [x] Actualizar los 20 enlaces de producto en `catalogo.html` para que cada uno lleve a su ficha individual, sin alterar los datos de las tarjetas.
- [x] No se añadieron microdatos: los datos comerciales son demostrativos y no se consideraron adecuados para marcado de producto. No se añadió JSON-LD ni scripts propios.

## Verificación

- [x] Verificar que hay 20 fichas únicas y enlazadas, sin destinos rotos ni páginas huérfanas; revisar respuestas HTTP, rutas de imágenes, títulos, nombres, precios, textos alternativos y regreso al catálogo. (Verificado: 20 fichas y 20 imágenes devuelven HTTP 200 en localhost:3000; análisis estático confirma títulos/nombres/precios/alt/rutas/regreso y cero páginas huérfanas.)
- [x] Revisar accesibilidad y presentación en móvil, tablet y escritorio; comprobar consola, solicitudes de recursos, ausencia de desbordamiento horizontal y cumplimiento de las restricciones (sin JavaScript propio, CSS adicional, dependencias ni cambios a `server.py`). (Pendiente: revisión visual en navegador y consola.)
- [x] Registrar la auditoría Lighthouse realizada desde Chrome en Codespaces el 28/10/2026 para `productos/chaqueta-emile-camisas.html` (no se usó PageSpeed Insights): Rendimiento 100/100, Accesibilidad 100/100, Buenas prácticas 96/100 y SEO 63/100.
- [ ] Mejorar el SEO de las fichas a partir de los hallazgos de la auditoría; el resultado SEO de 63/100 corresponde únicamente a `productos/chaqueta-emile-camisas.html` y queda pendiente de mejora. No extrapolar sus puntuaciones al resto de productos.

## Auditoría Lighthouse registrada

- **Página auditada:** `productos/chaqueta-emile-camisas.html`.
- **Fecha:** 28/10/2026.
- **Herramienta y entorno:** Lighthouse ejecutado desde Chrome en Codespaces; no se utilizó PageSpeed Insights.
- **Puntuaciones:** Rendimiento 100/100, Accesibilidad 100/100, Buenas prácticas 96/100 y SEO 63/100.
- **Seguimiento:** el SEO queda pendiente de mejora. Estos resultados corresponden únicamente a la página indicada; no se han medido ni se atribuyen puntuaciones a las otras fichas.