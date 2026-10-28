# Especificación: página de inicio

## Objetivo

Definir los requisitos para crear `index.html`, la portada del prototipo de Maison Élise. La página debe presentar una campaña, facilitar el acceso a las prendas y enlazar con el catálogo y el detalle de producto, respetando la plantilla común de `docs/reference/base.html`.

Esta especificación define el resultado esperado; no implementa HTML ni crea archivos de imagen.

## Fuente de requisitos

La implementación debe respetar `AGENTS.md`, `CONTEXT.md`, `DESIGN.md` y la estructura compartida descrita en `specs/base-layout/spec.md`. En caso de conflicto, prevalecen las restricciones técnicas: HTML estático, Tailwind CSS v4 por CDN, sin JavaScript propio, sin CSS adicional y sin cambios a `server.py`.

## Alcance

La página se guardará como `index.html` en la raíz y tendrá:

1. El documento HTML5 y la navbar común de `docs/reference/base.html`.
2. Un `<main>` con una campaña principal, nuevos lanzamientos y más vendidos.
3. Tarjetas de producto que enlacen a `producto.html`.
4. Microdatos Schema.org para la página y la organización de la marca.
5. El footer común de la plantilla.

No incluir catálogo completo, filtros, una ficha de producto completa, carrito, checkout ni controles que aparenten mantener estado. No crear una segunda versión de la navbar o del footer.

## Estructura y metadatos

- Usar `<!doctype html>`, `<html lang="es">` y los metadatos de codificación y viewport.
- Usar un título descriptivo, por ejemplo, `Maison Élise | Moda contemporánea`, y una descripción breve y propia de la marca.
- Incluir el CDN Browser oficial de Tailwind CSS v4 indicado en `README.es.md`. No añadir otros scripts, dependencias, fuentes externas ni hojas CSS.
- Mantener los landmarks `<header>`, `<nav>`, `<main>` y `<footer>` de la plantilla. El `<main>` deja de estar vacío y contiene toda la composición específica de la portada.
- Mantener un solo `<h1>` descriptivo en la página y ordenar los encabezados de sección como `<h2>`.
- Como `base.html` vive en `docs/reference/`, ajustar sus destinos relativos al copiar su estructura a la raíz: marca a `index.html`, catálogo a `catalogo.html` y carrito a `carrito.html`. La búsqueda puede enviar por GET a `catalogo.html`. La cuenta permanece identificada como no disponible, sin menú simulado ni ruta inventada.
- Conservar las secciones y enlaces del footer compartido; las categorías pueden apuntar al catálogo común y los textos legales sin página propia no deben apuntar a rutas inexistentes.

## Contenido de la portada

### Campaña principal

- Presentar una selección o campaña de temporada mediante una imagen protagonista, un título breve, una frase descriptiva y una llamada a la acción hacia `catalogo.html`.
- La imagen debe tener texto alternativo que describa la escena y la prenda relevante. No retrasar la imagen principal con `loading="lazy"`; declarar `width` y `height` cuando se conozcan.
- Mantener el texto legible y la acción visible tanto si la composición apila texto e imagen en móvil como si los combina en escritorio.

### Nuevos lanzamientos

- Mostrar una sección con al menos tres tarjetas de prendas nuevas.
- Cada tarjeta incluye imagen, texto alternativo, nombre, precio en euros y enlace descriptivo a `producto.html`.
- Las imágenes que queden fuera de la primera pantalla pueden usar `loading="lazy"` y dimensiones declaradas cuando estén disponibles.

### Más vendidos

- Mostrar una sección diferenciada con al menos tres tarjetas de prendas destacadas, con imagen, nombre, precio y enlace a `producto.html`.
- Se permite reutilizar productos entre las secciones si se mantiene clara la diferencia editorial entre novedades y selección destacada.
- Presentar los precios con formato coherente, por ejemplo `89,00 €`.

Los nombres, precios, referencias e imágenes son datos de demostración. No afirmar disponibilidad, popularidad real, descuentos ni características de producto que no estén respaldadas por el prototipo.

## Dirección visual e imágenes

- Seguir `DESIGN.md`: estilo editorial, sobrio y cálido; fondo marfil, superficies claras, texto carbón, bordes neutros y acento borgoña apagado. Usar verde oliva solo de forma puntual.
- Usar serif de sistema en titulares y sans serif de sistema en navegación, cuerpo y precios. Aplicar espacio generoso y bordes discretos, sin sombras pesadas ni clichés visuales franceses.
- Diseñar primero para móvil. La campaña debe apilarse en pantallas estrechas; las tarjetas deben fluir de una columna a dos y, en escritorio, hasta cuatro columnas según el espacio disponible. No fijar anchos que provoquen scroll horizontal.
- Propuesta de imagen original para la campaña: retrato editorial de cuerpo entero de una modelo con abrigo de lana borgoña y prendas neutras, en una calle urbana de piedra clara tras la lluvia, luz natural suave y encuadre vertical. La ropa debe ser el foco; evitar logos visibles, texto incrustado, banderas y monumentos reconocibles.
- Propuesta para las tarjetas: fotografías de producto originales con fondo claro y luz natural, alternando una camisa blanca de algodón, un pantalón recto oscuro, un bolso de cuero burdeos y calzado de piel. Mantener encuadres y escala visual consistentes.
- Las imágenes son una dirección creativa para producir o seleccionar recursos del prototipo, no recursos ya generados. No enlazar archivos locales que no existan; si se incorporan imágenes, usar recursos accesibles, optimizados y con texto alternativo fiel a su contenido.

## Schema.org propuesto

Usar microdatos HTML, no JSON-LD ni scripts, de acuerdo con `AGENTS.md`:

- Marcar la página como `https://schema.org/WebPage` y asignar `name` a su título descriptivo.
- Representar la marca como `https://schema.org/Organization`, anidada como `publisher` de la página. Incluir `name` (`Maison Élise`) y `url` (`index.html` o la URL canónica real cuando se conozca). Añadir `logo`, `image`, `description` o `email` solo si hay recursos y datos auténticos disponibles; identificar cualquier contacto de demostración y no inventar una dirección oficial.
- No añadir `sameAs`, reseñas, puntuaciones, ofertas ni `SearchAction` sin destinos y datos reales. El formulario de búsqueda que solo dirige al catálogo no demuestra que exista una búsqueda funcional.
- Las tarjetas de producto no necesitan declararse como ofertas ni contener datos estructurados adicionales en esta vista.

## Accesibilidad y comportamiento

- Usar elementos semánticos y nombres de enlace que indiquen el destino o la prenda; evitar enlaces genéricos como «aquí».
- Asegurar texto alternativo útil para imágenes informativas y `alt=""` únicamente en imágenes decorativas.
- Conservar etiquetas accesibles, contraste suficiente y foco visible en enlaces y controles heredados de la navbar.
- Usar enlaces para navegar. Las llamadas a la acción deben llevar a páginas existentes; no incluir botones que sugieran añadir al carrito ni acciones que requieran estado.
- No presentar filtros, búsqueda dinámica, inventario ni personalización que el prototipo estático no implemente.

## Criterios de aceptación

- Existe `index.html` en la raíz y sigue la plantilla común sin duplicar la navbar ni el footer.
- Contiene un `<main>` con campaña, nuevos lanzamientos y más vendidos; hay un solo `<h1>` y encabezados ordenados.
- La campaña incluye imagen, texto y llamada a `catalogo.html`; ambas secciones de producto muestran al menos tres tarjetas con nombre, precio, imagen y enlace a `producto.html`.
- Las imágenes tienen descripciones alternativas apropiadas; las principales no usan carga diferida y las secundarias pueden usarla.
- Los metadatos de Schema.org usan microdatos HTML para `WebPage` y `Organization`, sin datos de marca o actividad inventados.
- Los enlaces heredados apuntan a destinos válidos desde la raíz y no se añaden rutas sin implementar.
- El diseño se adapta a móvil, tablet y escritorio sin desbordamiento horizontal y mantiene el sistema visual de `DESIGN.md`.
- No hay JavaScript propio, CSS adicional, dependencias ni cambios a `server.py`.