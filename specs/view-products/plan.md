# Plan: vistas de detalle de producto

## Objetivo

Implementar una ficha HTML individual para cada uno de los 20 productos de `catalogo.html`, de acuerdo con `specs/view-products/spec.md`, `DESIGN.md`, `AGENTS.md` y `CONTEXT.md`. Las vistas deben enlazarse una a una desde el catálogo y mantener explícitas las limitaciones del prototipo estático. Este plan describe el trabajo; no implementa las fichas.

## Pasos

1. **Confirmar el inventario y el mapa de rutas.** Revisar los 20 nombres, categorías, precios, imágenes y alts vigentes en `catalogo.html`; comprobar contra la especificación y los recursos en `assets/images/`. Definir un nombre de archivo HTML estable, sencillo y sin tildes para cada producto en `productos/`. Registrar una tabla de correspondencia producto → archivo → imagen y asegurar que todas las rutas serán únicas y relativas a la ubicación de las páginas. No cambiar datos editoriales del catálogo como parte de este trabajo; anotar inconsistencias para revisión.
2. **Resolver contenido prudente para cada ficha.** Preparar nombre, categoría, precio exacto, referencia ilustrativa única, descripción en español y alt coherentes con la imagen correspondiente. Verificar qué materiales, cuidados, colores y medidas están realmente respaldados. Omitir datos no verificables o etiquetarlos claramente como orientativos/de demostración; no inventar composiciones, disponibilidad, reseñas ni promociones.
3. **Definir y construir una estructura HTML común.** Crear cada una de las 20 páginas como documento HTML5 independiente, con `lang="es"`, UTF-8, viewport, título y descripción propios, y únicamente el CDN Browser oficial de Tailwind CSS v4. Reutilizar el patrón de navbar/footer y navegación compartida, ajustando los enlaces relativos para `productos/`. Mantener landmarks semánticos, un solo `<h1>`, migas de pan accesibles y enlace visible de retorno al catálogo.
4. **Implementar el detalle de producto.** Aplicar la composición de dos columnas en escritorio —imagen principal a la izquierda e información a la derecha— y apilarla en móvil. Presentar categoría, nombre, precio, referencia, descripción y detalles respaldados. Usar la imagen local de la ficha, alt conciso, dimensiones correctas y carga no diferida para la imagen prioritaria. Mantener componentes, tono, paleta y tipografía coherentes entre las veinte páginas.
5. **Representar claramente las interacciones de demostración.** Para prendas y calzado, incluir opciones de talla solo si existe base en el contenido de referencia y distinguir las escalas. No ofrecer tallas para accesorios de talla única ni afirmar disponibilidad. Etiquetar controles visibles y explicar que son ilustrativos. Si se ofrece una llamada a carrito, hacer que conduzca al carrito de demostración y aclarar que no guarda la selección; no implementar formularios de envío, JavaScript, persistencia ni acciones que aparenten compra real.
6. **Enlazar las tarjetas con su ficha individual.** Sustituir, en `catalogo.html`, únicamente el destino de cada enlace de producto por su ruta estática específica, comprobando correspondencia exacta nombre/precio/imagen → página. Mantener sin cambios el diseño de tarjetas, contenido, filtros y demás enlaces salvo que la spec requiera resolver un destino relacionado con la navegación.
7. **Añadir microdatos solo con datos visibles.** Si se usa Schema.org `Product`, implementarlo con microdatos HTML, nunca JSON-LD ni scripts. Incluir solo propiedades respaldadas y consistentes con la ficha visible; no declarar rating, inventario, disponibilidad ni ofertas ficticias.
8. **Verificar las 20 rutas y la experiencia adaptable.** Comprobar que cada enlace del catálogo conduce a una página única, que no hay fichas huérfanas, y que cada documento responde correctamente. Revisar título, H1, nombre, precio, imagen, alt, rutas relativas, migas de pan y regreso al catálogo. Validar con teclado, foco y etiquetas; probar móvil, tablet y escritorio, consola/solicitudes de imagen y ausencia de scroll horizontal.
9. **Revisar límites del proyecto y registrar resultados.** Confirmar que no se añadieron JavaScript propio, CSS adicional, dependencias, router ni cambios a `server.py`. Ejecutar PageSpeed Insights solo si la URL pública está disponible; registrar URL, fecha, modalidad y puntuación realmente obtenida, o mantenerlo pendiente si no se ejecuta. No presentar las verificaciones previstas como realizadas antes de probarlas.

## Restricciones

- No implementar más vistas que las veinte fichas individuales requeridas ni alterar portada, carrito, checkout o filtros del catálogo.
- No crear rutas dinámicas ni query strings como sustituto de páginas estáticas.
- No inventar información de producto, enlace, variante, material o disponibilidad.
- No añadir frameworks, JavaScript propio, hojas CSS, dependencias o cambios a `server.py`.
- No hacer commit salvo que se solicite explícitamente.
