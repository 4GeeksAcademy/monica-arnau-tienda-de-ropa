# Especificación: vistas de detalle de producto

## Objetivo

Definir los requisitos para crear vistas de detalle navegables para los productos del catálogo de Maison Élise. Cada producto debe abrir su propia ficha, mostrando información coherente con su nombre, categoría, imagen y precio del catálogo. La experiencia debe conservar la identidad editorial de la tienda y las limitaciones del prototipo estático.

Esta especificación define el resultado esperado; no implementa HTML, JavaScript ni recursos de imagen.

## Fuente de requisitos

La implementación debe respetar:

- [AGENTS.md](../../AGENTS.md): tecnologías permitidas, restricciones funcionales, navegación y accesibilidad.
- [CONTEXT.md](../../CONTEXT.md): alcance de las vistas de producto y recorrido entre páginas.
- [DESIGN.md](../../DESIGN.md): identidad visual y composición para detalle de producto.
- [Spec del catálogo](../catalog/spec.md): catálogo de 20 productos y sus datos de referencia.
- La plantilla compartida descrita en [spec de base-layout](../base-layout/spec.md), si está disponible en el repositorio.

En caso de conflicto, prevalecen las restricciones técnicas del proyecto: HTML estático, Tailwind CSS v4 por CDN oficial, sin JavaScript propio, sin CSS adicional, sin frameworks y sin cambios a `server.py`.

## Alcance

- Crear una ficha individual accesible para cada uno de los 20 productos que aparecen en `catalogo.html`.
- Hacer que cada enlace de producto desde el catálogo conduzca a la ficha correspondiente, no a una ficha genérica compartida.
- Mantener navegación de regreso al catálogo y navegación común a inicio y carrito.
- Presentar la información como demostración: no hay inventario, disponibilidad, carrito persistente, procesamiento de pedidos ni pago real.

La convención de rutas debe ser estática y explícita. Se recomienda un archivo HTML por producto en una carpeta dedicada `productos/`, con nombres de archivo simples, estables y sin tildes. El mapa de identificadores, nombres y rutas debe declararse en la implementación y validarse contra los 20 nombres de `catalogo.html`; no se deben inventar rutas con parámetros esperando que un router inexistente las resuelva.

Esta especificación no requiere modificar la portada, el carrito, el checkout, el catálogo más allá de sus enlaces a fichas ni `server.py`. No añade filtros, reseñas, recomendaciones automáticas, variantes funcionales, inventario ni pagos.

## Correspondencia de productos y datos

- Deben existir exactamente 20 fichas, una por cada tarjeta actual del catálogo.
- Nombre y precio deben coincidir literalmente con el catálogo, incluidos acentos, idioma y formato en euros. No cambiar los datos del catálogo para hacerlos coincidir con las fichas.
- La categoría debe corresponder a la clasificación mostrada en la tarjeta. Si una tarjeta contiene una clasificación o nombre aparentemente inconsistente, conservar el dato del catálogo y señalarlo como cuestión editorial pendiente; no corregirlo como parte de la implementación de las fichas sin autorización.
- Cada ficha tendrá una referencia ilustrativa única, claramente identificada como código de demostración, y debe usar la misma referencia en su contenido visible y sus microdatos, si se incluyen.
- La descripción, los materiales, el color y las sugerencias de uso deben corresponder a la fotografía y a lo que el nombre del producto respalda. Si el material o una característica no se puede verificar, redactar de forma prudente o identificarla como información ilustrativa; no afirmar composición, procedencia, certificaciones ni propiedades técnicas inventadas como hechos.
- No presentar reseñas, descuentos, valoraciones, disponibilidad, número de unidades, envíos garantizados ni atributos de oferta como reales.

### Inventario de referencia

Usar esta lista como base para garantizar la cobertura de las fichas y enlazar de forma uno-a-uno con el catálogo:

1. Camisa Claire — `assets/images/catalogo-camisa-claire.webp` — 89,00 €.
2. Chaqueta Émile (tarjeta en categoría Camisas) — `assets/images/catalogo-chaqueta-emile.webp` — 159,00 €.
3. Abrigo Simone — `assets/images/catalogo-abrigo-simone.webp` — 219,00 €.
4. Camisa Amélie — `assets/images/catalogo-camisa-amelie.webp` — 95,00 €.
5. Camisa Louise — `assets/images/catalogo-camisa-louise.webp` — 105,00 €.
6. Pantalón droit Camille — `assets/images/catalogo-pantalon-camille.webp` — 119,00 €.
7. Pantalón Jules — `assets/images/catalogo-pantalon-jules.webp` — 125,00 €.
8. Pantalón fluido Margot — `assets/images/catalogo-pantalon-margot.webp` — 132,00 €.
9. Bailarinas Céleste — `assets/images/catalogo-bailarinas-celeste.webp` — 110,00 €.
10. Zapatillas de ville Léon — `assets/images/catalogo-zapatillas-leon.webp` — 125,00 €.
11. Mocasines Étienne — `assets/images/catalogo-mocasines-etienne.webp` — 145,00 €.
12. Sandalias Anaïs — `assets/images/catalogo-sandalias-anais.webp` — 98,00 €.
13. Bolso Louise — `assets/images/catalogo-bolso-louise.webp` — 175,00 €.
14. Sac porté Éloïse — `assets/images/catalogo-bolso-eloise.webp` — 148,00 €.
15. Sac seau Noémie — `assets/images/catalogo-bolso-noemie.webp` — 162,00 €.
16. Montre Héloïse — `assets/images/catalogo-reloj-heloise.webp` — 135,00 €.
17. Blouse Adèle — `assets/images/catalogo-blusa-adele.webp` — 99,00 €.
18. Segunda Chaqueta Émile — `assets/images/catalogo-chaqueta-emile-otra.webp` — 142,00 €.
19. Chaqueta Élise — `assets/images/catalogo-chaqueta-elise.webp` — 172,00 €.
20. Manteau Étoile — `assets/images/catalogo-abrigo-etoile.webp` — 225,00 €.

Las rutas de imagen de esta lista son las actuales del catálogo; la implementación debe comprobarlas en el momento de crear las fichas y no suponer que recursos inexistentes cargan correctamente.

## Estructura de cada ficha

Cada archivo debe ser un documento HTML5 completo y contener:

- `lang="es"`, UTF-8, viewport, título y descripción SEO únicos y descriptivos.
- El CDN Browser oficial de Tailwind CSS v4 previsto por el proyecto, sin otros scripts.
- La navbar y el footer comunes, con rutas relativas válidas desde la ubicación de la ficha. La marca conduce a inicio; el catálogo y carrito conservan sus destinos existentes. No dejar enlaces rotos por el nivel de directorio.
- Un único `<h1>` que identifique el producto.
- Migas de pan simples y accesibles, por ejemplo: Inicio → Catálogo → Nombre del producto. Cada elemento navegable debe tener un destino existente; el producto actual se debe identificar como tal sin enlazarse a sí mismo.
- Un enlace visible para volver al catálogo.
- Un área principal de producto con imagen y detalles.
- Secciones o agrupaciones con encabezados claros para descripción, detalles/materiales y cuidados cuando exista información respaldada.
- Una nota visible de demostración donde se presenten acciones no funcionales.

No añadir una imagen hero de campaña, filtros del catálogo, ventanas modales, pestañas que requieran JavaScript ni elementos que sugieran una interacción inexistente.

## Presentación de producto

### Imagen

- Usar como imagen principal la fotografía local asociada al producto en el inventario de referencia. No reutilizar imágenes de otro producto para completar fichas.
- Mantener fotografía y texto alternativo coherentes con el producto real mostrado. No describir colores, materiales o usos que no se distingan ni estén respaldados.
- Usar `width` y `height` correctos, conservar una proporción adecuada al recurso y evitar saltos de layout.
- La imagen principal debe estar disponible en la carga inicial: no usar `loading="lazy"` en el recurso prioritario visible al inicio de la ficha.
- Optimizar las imágenes y no descargar originales sobredimensionados. Preferir los WebP locales ya disponibles cuando sigan correspondiendo al producto.
- No incluir galerías con controles falsos. Si se muestran vistas adicionales, deben ser recursos reales del mismo producto y ser comprensibles sin scripts.

### Información

- Mostrar categoría, nombre, precio en euros y referencia ilustrativa de manera fácil de localizar.
- Incluir descripción en español claro, con tono editorial sobrio y datos compatibles con el catálogo y la imagen.
- Cuando se incluyan materiales, cuidados o medidas, indicar solo datos verificados o marcarlos claramente como orientativos/de demostración. No inventar composición textil precisa.
- No mostrar precios tachados, descuentos ni impuestos desglosados que no estén definidos por el proyecto.

### Talla, cantidad y acción de carrito

- Presentar selector de talla solo para productos donde corresponda. Usar opciones visuales y etiquetas explícitas, diferenciando tallaje de ropa, calzado y accesorios; no asumir una escala universal.
- Si se ofrecen controles HTML para talla o cantidad, etiquetarlos de forma visible y usar elementos nativos accesibles. Aclarar que su selección es ilustrativa y no se valida contra inventario.
- Los accesorios de talla única no deben presentar opciones de talla ficticias.
- No simular opciones o variantes concretas que no se puedan verificar en las fuentes del catálogo.
- El botón «Agregar al carrito» no puede añadir productos a un estado persistente en el prototipo sin JavaScript o backend. Si se incluye, su comportamiento debe limitarse a un enlace válido al carrito demostrativo y la interfaz debe explicar claramente que no guarda esta selección ni actualiza el carrito. No presentarlo como compra funcional.
- Si se decide no mostrar una acción falsa, ofrecer en su lugar un enlace claramente rotulado a `carrito.html` indicando que el carrito es una demostración. No añadir formularios que envíen datos sin procesamiento.

## Diseño adaptable y coherencia visual

- Seguir `DESIGN.md`: diseño editorial, sobrio y cálido; fondo marfil, superficies claras, texto carbón, bordes neutros y acento borgoña apagado, con oliva solo como acento puntual.
- Usar tipografía serif del sistema para títulos y sans serif de sistema para cuerpo, navegación, controles y precios.
- En escritorio, usar dos columnas: imagen del producto a la izquierda e información a la derecha. Mantener una separación cómoda y un orden de lectura intuitivo.
- En móvil, apilar las columnas; mantener la imagen, el nombre, el precio y la explicación de demostración visibles en un orden claro.
- Utilizar contenedor fluido de ancho máximo y breakpoints estándar de Tailwind. Evitar dimensiones rígidas, desbordamiento horizontal y controles recortados.
- Mantener consistencia entre las 20 fichas y con navbar/footer compartidos, inicio y catálogo. Los patrones de color, botones, bordes, espaciado y foco deben ser comunes.
- Aplicar estilos con utilities de Tailwind; no añadir hojas CSS ni estilos inline.

## Accesibilidad y SEO

- Usar landmarks semánticos (`header`, `nav`, `main`, `section`, `footer`) y estructura de encabezados ordenada, con un único `h1`.
- Proporcionar enlace de salto al contenido principal si la plantilla compartida lo incluye; conservarlo en todas las fichas.
- Asociar etiquetas visibles a controles de talla y cantidad. No depender de placeholders, iconos ni color para expresar su función o estado.
- Usar texto alternativo conciso y específico para la imagen principal; evitar repetir en el `alt` todo el contenido de la ficha. Si una imagen es puramente decorativa, usar `alt=""`.
- Proporcionar foco visible, contraste suficiente y orden de teclado coherente. Los enlaces deben tener propósito entendible fuera del contexto visual.
- Escribir títulos y meta descripciones únicos por producto, evitando contenido genérico duplicado. No prometer disponibilidad o funcionalidades inexistentes.
- Añadir microdatos Schema.org con HTML (`itemscope`, `itemtype`, `itemprop`) de tipo `Product` solo cuando sus valores visibles y verificables estén disponibles. Incluir nombre, imagen, descripción, referencia y precio/oferta conforme a los datos mostrados. No usar JSON-LD ni scripts; no crear disponibilidad o rating ficticios.

## Límites funcionales y restricciones técnicas

- No JavaScript propio, frameworks, librerías, fuentes externas, dependencias nuevas ni CSS adicional.
- No modificar `server.py` ni crear un router. El servidor estático debe poder servir todos los archivos por rutas relativas.
- No afirmar que talla, cantidad, selección, carrito, disponibilidad, reserva, compra o pago se guardan o procesan.
- No añadir acciones de favoritos, reseñas, alertas de stock, comparación ni recomendaciones dinámicas.
- Los enlaces internos deben apuntar a archivos existentes; no depender de query strings o rutas dinámicas para distinguir productos.
- Mantener todas las páginas HTML de producto enlazadas desde las 20 tarjetas correspondientes del catálogo.

## Criterios de aceptación

- Existen exactamente 20 fichas, una para cada tarjeta de producto del catálogo, y ninguna ficha huérfana.
- Cada enlace de tarjeta conduce a la ficha propia del producto; regresar a `catalogo.html` es posible desde cada vista.
- Nombre y precio coinciden exactamente entre catálogo y detalle; cada ficha usa su imagen asociada y texto alternativo fiel.
- Las rutas relativas a imágenes, inicio, catálogo, carrito y demás recursos funcionan desde la ubicación de las fichas.
- Cada página tiene metadatos propios, un único `<h1>`, navegación compartida y contenido semántico y accesible.
- Las fichas tienen layout de dos columnas en escritorio y contenido apilado y utilizable en móvil, sin scroll horizontal.
- Talla, cantidad y acción de carrito, si aparecen, se explican como elementos demostrativos sin estado persistente ni inventario.
- Materiales, medidas, cuidados y propiedades estructuradas no se inventan ni contradicen la imagen.
- Los microdatos `Product`, si se incluyen, son HTML válido y coinciden con el contenido visible; no se incluye JSON-LD ni JavaScript adicional.
- No se añaden frameworks, dependencias, hojas CSS, otros scripts ni cambios a `server.py`.

## Verificación prevista para la implementación

- Comparar automáticamente o manualmente los 20 enlaces de tarjeta con los 20 archivos de detalle; detectar destinos duplicados no intencionados, rotos u huérfanos.
- Abrir cada URL de producto y verificar respuesta HTTP correcta, título, nombre, precio, imagen, alt y enlace de regreso al catálogo.
- Comprobar que las rutas a recursos locales funcionan en la ubicación elegida y que no hay solicitudes fallidas en la consola del navegador.
- Revisar páginas representativas de ropa, calzado y accesorios, además de validar los 20 títulos/precios/URLs; probar tamaños móvil, tablet y escritorio.
- Comprobar teclado, foco visible, etiquetas de controles, jerarquía de encabezados, contraste y textos alternativos.
- Confirmar que no se aparentan operaciones persistentes de talla, cantidad, carrito o compra y que cualquier interacción de demostración se explica junto a ella.
- Validar microdatos Schema.org si se implementan y comprobar que no contienen datos ficticios no visibles.
- No marcar pruebas ni auditorías como realizadas por redactar esta especificación; registrar resultados solo tras ejecutar las verificaciones.
