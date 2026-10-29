# Especificación: barra de navegación común

## Objetivo

Definir una barra de navegación superior coherente, accesible y adaptable para las páginas funcionales de Maison Élise. Esta especificación define el resultado esperado; no autoriza modificar contenido ajeno a la barra de navegación.

## Alcance

Aplicar a:

- `index.html`
- `catalogo.html`
- `carrito.html`
- `checkout.html`
- Todos los archivos `productos/*.html`

No aplicar a `docs/reference/base.html`, que es una plantilla de referencia y no una página funcional de la tienda.

## Estructura y componentes

Dentro del `<header>` de cada página, la navegación debe incluir, en este orden:

1. Enlace de marca «Maison Élise» al inicio.
2. Enlace «Catálogo».
3. Enlace «Carrito».
4. Enlace «Checkout».
5. Formulario de búsqueda dirigido al catálogo.
6. Texto informativo «Mi cuenta (no disponible)», sin enlace ni apariencia de control.

Usar un único landmark para la navegación principal: `<nav aria-label="Navegación principal">`.

Debajo de la navegación debe aparecer el aviso:

> La búsqueda abre el catálogo de demostración; no interpreta la consulta.

## Textos y accesibilidad

- La marca debe tener `aria-label="Maison Élise, inicio"`.
- El campo de búsqueda debe tener una etiqueta accesible asociada con el texto «Buscar prendas». Puede estar visualmente oculta con `sr-only`.
- El campo debe usar `name="q"` y el formulario debe usar `method="get"`.
- El botón de envío debe decir «Buscar».
- El placeholder, si se incluye, no reemplaza la etiqueta.
- «Mi cuenta» debe comunicar claramente que la función no está disponible.
- Los enlaces, el campo y el botón deben tener estados de foco visibles.
- El estado de página actual debe indicarse con `aria-current="page"` y distinguirse visualmente sin depender únicamente del color.

## Rutas y estado activo

Las rutas deben ser relativas y válidas según la ubicación de cada archivo:

- En páginas de la raíz: `index.html`, `catalogo.html`, `carrito.html` y `checkout.html`.
- En páginas dentro de `productos/`: anteponer `../` a esos destinos.
- El formulario debe enviar a `catalogo.html` o `../catalogo.html`, según corresponda.

Marcar como página actual únicamente:

- `index.html`: enlace de marca.
- `catalogo.html`: enlace «Catálogo».
- Fichas de `productos/`: enlace «Catálogo».
- `carrito.html`: enlace «Carrito».
- `checkout.html`: enlace «Checkout».

## Diseño adaptable

- Mantener fondo blanco y separación inferior sutil respecto al contenido.
- Usar serif para la marca (`font-serif text-2xl`) y sans serif para navegación y controles.
- Usar el borgoña `#713E43` para el estado activo, el foco y el botón de búsqueda.
- Centrar el contenido en un contenedor `max-w-7xl`, con espaciado horizontal adaptable (`px-4 sm:px-6 lg:px-8`).
- Permitir que los elementos se reorganicen en pantallas pequeñas; no debe producirse scroll horizontal.
- El formulario y sus controles deben permanecer visibles y utilizables en todos los tamaños.

## Comportamiento y límites

- La búsqueda navega mediante GET al catálogo e incluye la consulta en `q`; no filtra los productos.
- Los enlaces principales navegan a páginas existentes.
- «Mi cuenta» es informativo y no debe aparentar abrir una vista o menú.
- La barra no debe sugerir persistencia del carrito ni procesamiento de pedidos o pagos.
- No añadir JavaScript propio, CSS adicional, bibliotecas ni dependencias para implementar la navegación.
- Mantener iguales la estructura, el orden, los textos y el tratamiento visual en todas las páginas; solo cambian las rutas relativas y el estado activo.

## Criterios de aceptación

- [ ] Las 24 páginas funcionales —cuatro páginas de raíz y veinte fichas de producto— contienen una navegación principal con los seis elementos especificados y en el orden indicado.
- [ ] La navegación usa `aria-label="Navegación principal"` y no introduce landmarks principales duplicados.
- [ ] Marca, catálogo, carrito y checkout enlazan a destinos existentes con rutas relativas correctas.
- [ ] El formulario de búsqueda usa `method="get"`, `name="q"`, una etiqueta accesible «Buscar prendas» y un botón «Buscar».
- [ ] El aviso sobre el alcance limitado de la búsqueda aparece en todas las páginas.
- [ ] «Mi cuenta» comunica su indisponibilidad y no es un enlace ni un botón.
- [ ] Solo el destino correspondiente a la página actual tiene `aria-current="page"`, conforme al mapeo de esta especificación.
- [ ] La navegación puede usarse con teclado y todos sus controles interactivos muestran foco visible.
- [ ] El layout se adapta a móvil, tablet y escritorio sin ocultar controles ni provocar scroll horizontal.
- [ ] No se añade JavaScript propio, CSS adicional ni dependencias.
- [ ] Los cambios de implementación, cuando se realicen, se limitan a la barra de navegación y su aviso asociado; el resto del contenido HTML permanece intacto.
