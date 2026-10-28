# Especificación: página de catálogo

## Objetivo

Definir los requisitos para crear `catalogo.html`, el catálogo del prototipo de Maison Élise. La página debe permitir explorar una selección de 20 productos de demostración y acceder al detalle de producto, respetando la plantilla común y la identidad visual de la portada.

Esta especificación define el resultado esperado; no implementa HTML ni crea archivos de imagen.

## Fuente de requisitos

La implementación debe respetar:

- [AGENTS.md](../../AGENTS.md): restricciones técnicas, accesibilidad y comportamiento del prototipo.
- [CONTEXT.md](../../CONTEXT.md): alcance del catálogo y recorrido entre vistas.
- [DESIGN.md](../../DESIGN.md): identidad visual y componentes compartidos.
- [README.es.md](../../README.es.md): CDN Browser oficial de Tailwind CSS v4.
- [Spec de base-layout](../base-layout/spec.md): estructura de la plantilla común `docs/reference/base.html`.
- [Spec de home](../home/spec.md): marca, patrón de tarjetas y formato del contenido de producto.

En caso de conflicto, prevalecen las restricciones técnicas: HTML estático, Tailwind CSS v4 por CDN, sin JavaScript propio, sin CSS adicional y sin cambios a `server.py`.

## Alcance

La página se guardará como `catalogo.html` en la raíz y tendrá:

1. El documento HTML5, la navbar y el footer definidos por la plantilla común.
2. Un `<main>` con título, una breve introducción y una indicación del carácter demostrativo del catálogo.
3. Filtros visuales de categoría y talla antes de los productos.
4. Una cuadrícula adaptable con exactamente 20 tarjetas de producto.
5. Enlaces al detalle de producto y a las vistas disponibles mediante la navegación compartida.

No crear otra plantilla común ni rediseñar la navbar o el footer. No incluir hero de campaña, ficha completa, carrito, checkout, ordenación, paginación ni acciones que requieran estado persistente.

## Estructura y navegación compartida

- Usar `<!doctype html>`, `<html lang="es">`, codificación UTF-8 y metadatos de viewport.
- Incluir un título descriptivo, como `Catálogo | Maison Élise`, y una descripción propia de esta vista.
- Cargar únicamente el script del CDN Browser de Tailwind CSS v4 indicado en el README. No añadir otros scripts, fuentes externas, bibliotecas ni hojas CSS.
- Mantener los landmarks `<header>`, `<nav>`, `<main>` y `<footer>`. El contenido del catálogo se incorpora al `<main>` de la plantilla.
- Usar un único `<h1>`, por ejemplo «Catálogo», y encabezados de sección y de producto con jerarquía ordenada.
- Adaptar las rutas de la plantilla al contexto de la raíz: marca a `index.html`, catálogo a `catalogo.html` y carrito a `carrito.html`. No copiar los prefijos relativos propios de `docs/reference/`.
- Identificar el enlace al catálogo como página actual mediante `aria-current="page"` y un tratamiento visual que no dependa solo del color.
- Mantener la búsqueda con etiqueta visible. Si envía mediante GET al catálogo, indicar que solo abre el catálogo de demostración: no interpreta la consulta ni modifica los productos.
- Conservar la cuenta identificada como no disponible, sin desplegables simulados ni rutas inventadas.
- Mantener en el footer las categorías calzado, camisas, pantalones y accesorios; términos y condiciones, política de privacidad, sobre la marca y contacto. Las categorías pueden llevar al catálogo sin aplicar filtros. Para los demás elementos, usar destinos existentes o texto informativo; identificar los datos de contacto de demostración.

## Contenido del catálogo

### Cabecera

- Presentar el título y una introducción breve en español, con tono editorial y directo.
- Mostrar un recuento coherente con la cuadrícula, por ejemplo «20 productos de demostración».
- No afirmar inventario real, disponibilidad, descuentos ni popularidad de las prendas.

### Filtros visuales

- Situar los filtros de categoría y talla después de la cabecera y antes de la cuadrícula, tanto en el orden del documento como en el visual.
- Usar controles nativos con etiquetas visibles asociadas mediante `for` e `id`. Agruparlos con un título o una leyenda comprensible.
- Incluir las categorías calzado, camisas, pantalones y accesorios, además de una opción general «Todas las categorías».
- Incluir una opción «Todas las tallas» y ejemplos de tallas identificados como orientativos; no sugerir que una única escala sirve para ropa, calzado y accesorios.
- Mantener los controles deshabilitados y acompañarlos de un aviso visible: «Filtros de demostración: no modifican los productos mostrados».
- No añadir un botón «Aplicar», «Limpiar» ni otra acción que aparente cambiar los resultados. No enviar formularios de filtros a servicios ni crear enlaces con parámetros que prometan filtrar.
- El recuento y los 20 productos permanecen estáticos; no presentar estados de carga, resultados vacíos ni mensajes de filtrado.

### Cuadrícula y tarjetas

- Mostrar exactamente 20 productos de ejemplo, con representación de las cuatro categorías. No repetir una tarjeta idéntica únicamente para completar el recuento.
- Reutilizar el patrón visual de tarjetas definido para home: imagen protagonista, nombre, precio en euros y enlace descriptivo al detalle.
- Usar nombres concretos y precios con formato coherente, por ejemplo `89,00 €`.
- Cada tarjeta debe enlazar a `producto.html`. Mientras exista una sola ficha, indicar junto a la cuadrícula que los enlaces abren el mismo detalle de demostración; no aparentar fichas individuales ni inventar rutas o parámetros de producto.
- Evitar enlaces anidados y controles interactivos innecesarios. No incluir favoritos, compra rápida, selección de talla ni botones de añadir al carrito.
- Tratar los nombres, precios, referencias e imágenes como datos de ejemplo. No añadir reseñas, puntuaciones o promociones sin respaldo.

## Dirección visual y diseño adaptable

- Seguir el estilo editorial, sobrio y cálido de `DESIGN.md`: fondo marfil, superficies claras, texto carbón, bordes neutros y acento borgoña apagado; verde oliva solo de forma puntual.
- Usar serif de sistema en titulares y sans serif de sistema en navegación, texto, controles y precios.
- Mantener el espaciado, los bordes, los radios y el tratamiento de tarjetas de home, sin sombras pesadas ni adornos que compitan con las prendas.
- Diseñar primero para móvil: una columna de tarjetas en pantallas estrechas, dos o tres en tablet según el espacio y cuatro en escritorio mediante los breakpoints estándar de Tailwind.
- Apilar los filtros en móvil y permitir su disposición horizontal cuando haya espacio, sin recortar etiquetas ni controles.
- Usar un contenedor fluido con ancho máximo y márgenes adaptables. Evitar anchos fijos, texto cortado y scroll horizontal.
- Aplicar todo el diseño con utilities de Tailwind, sin estilos inline ni CSS adicional.

## Imágenes y rendimiento

- Seleccionar recursos accesibles y optimizados, con encuadres y proporciones consistentes. El texto alternativo debe describir la prenda realmente mostrada.
- No enlazar archivos locales inexistentes ni URLs temporales. Comprobar la accesibilidad de las imágenes remotas antes de incorporarlas.
- Declarar `width` y `height` cuando se conozcan para reducir cambios de layout.
- Usar `loading="lazy"` en las imágenes fuera de la primera pantalla y evitar retrasar innecesariamente las primeras imágenes visibles.
- No descargar originales de gran tamaño para mostrarlos como miniaturas.
- No exigir datos estructurados de ofertas en las tarjetas. Si se añaden datos Schema.org, usar únicamente microdatos HTML con información respaldada, sin JSON-LD ni scripts adicionales.

## Accesibilidad y límites funcionales

- Emplear elementos semánticos para agrupar filtros y productos; las tarjetas pueden organizarse como una lista de artículos.
- Proporcionar nombres de enlace que identifiquen la prenda o el destino. Evitar enlaces genéricos como «aquí».
- Mantener contraste suficiente, foco visible y orden de teclado coherente con el orden visual.
- No depender de placeholders, color o interacción hover para comunicar información esencial.
- Explicar las limitaciones de filtros, búsqueda y detalle compartido junto a los elementos afectados, sin ocultarlas en el footer.
- El catálogo permite navegación estática, no búsqueda real, filtrado, consulta de inventario ni operaciones persistentes.

## Criterios de aceptación

- Existe `catalogo.html` en la raíz, accesible mediante su ruta y desde la navegación compartida.
- Reutiliza la estructura de base-layout y conserva la identidad y el patrón de tarjetas de home, sin introducir variantes de navbar o footer.
- Contiene un único `<h1>`, introducción, recuento de 20 productos y filtros antes de la cuadrícula.
- Los filtros muestran categoría y talla con etiquetas visibles, están deshabilitados y explican que no modifican resultados.
- Hay exactamente 20 tarjetas con imagen, texto alternativo, nombre, precio en euros y enlace válido a `producto.html`; se representan las cuatro categorías.
- Se informa de que los enlaces de producto abren una ficha común de demostración.
- La cuadrícula presenta cuatro columnas en escritorio y reduce columnas en tablet y móvil; navbar, filtros y footer no producen scroll horizontal.
- Todos los enlaces y anclas tienen destinos existentes, y los controles disponibles se pueden recorrer con teclado y foco visible.
- Las imágenes cargan sin errores, mantienen proporciones coherentes y aplican dimensiones y carga diferida cuando corresponde.
- No hay JavaScript propio, CSS adicional, dependencias nuevas ni cambios a `server.py`.

## Verificación prevista para la implementación

- Abrir `/catalogo.html` y recorrer los enlaces de navegación, tarjetas y footer; comprobar también que `/` sigue sirviendo el inicio.
- Revisar móvil, tablet y escritorio, incluida la cuadrícula de cuatro columnas en escritorio y la ausencia de desbordamiento en móvil.
- Contar las 20 tarjetas y comprobar que el recuento visible coincide.
- Verificar teclado, foco, etiquetas, avisos de demostración y ausencia de acciones que aparenten filtrar.
- Revisar la consola y las solicitudes de imágenes para detectar recursos fallidos.
- Si hay URL pública disponible, ejecutar PageSpeed Insights buscando al menos 80 puntos y registrar URL, fecha, modalidad y puntuación real. Si no se ejecuta, dejarlo indicado como pendiente.

Estas verificaciones corresponden a la futura implementación, no se consideran realizadas por redactar esta especificación.
