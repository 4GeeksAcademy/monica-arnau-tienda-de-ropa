# Regla: barra de navegación común

## Alcance

Esta regla define la barra de navegación que debe repetirse en todas las páginas HTML funcionales de la tienda:

- `index.html`
- `catalogo.html`
- `carrito.html`
- `checkout.html`
- Todos los archivos `productos/*.html`

La plantilla de `docs/reference/base.html` es material de referencia y no sustituye la navegación de las páginas funcionales.

## Estructura y componentes

La barra debe estar dentro del `<header>` común de cada página e incluir, en este orden:

1. **Marca:** enlace tipográfico «Maison Élise» a la página de inicio.
2. **Catálogo:** enlace a `catalogo.html`.
3. **Carrito:** enlace a `carrito.html`.
4. **Checkout:** enlace a `checkout.html`.
5. **Búsqueda:** formulario accesible que envía la consulta al catálogo.
6. **Cuenta:** texto informativo, no un enlace, mientras la cuenta no esté disponible.

Usar un único landmark de navegación principal:

```html
<nav aria-label="Navegación principal">...</nav>
```

No añadir enlaces o acciones que parezcan funcionales si no tienen un destino o comportamiento real.

## Textos y accesibilidad

Usar estos textos de manera consistente:

- Marca: `Maison Élise`, con `aria-label="Maison Élise, inicio"`.
- Enlaces: `Catálogo`, `Carrito` y `Checkout`.
- Etiqueta de búsqueda: `Buscar prendas`.
- Botón de búsqueda: `Buscar`.
- Cuenta: `Mi cuenta (no disponible)`.

El formulario de búsqueda debe usar `method="get"`, el parámetro `q` y una etiqueta `<label>` asociada al campo. El texto de la etiqueta puede ocultarse visualmente con `sr-only`, pero debe seguir disponible para lectores de pantalla. Si se usa un placeholder, no debe reemplazar la etiqueta.

Debajo de la navegación, incluir en todas las páginas este aviso:

> La búsqueda abre el catálogo de demostración; no interpreta la consulta.

El elemento de cuenta debe comunicar su indisponibilidad y no tener apariencia de enlace o botón.

## Enlaces según la ubicación

Todos los enlaces internos deben apuntar a destinos existentes y usar rutas relativas válidas para la ubicación del archivo.

- En las páginas de la raíz, usar destinos como `index.html`, `catalogo.html`, `carrito.html` y `checkout.html`.
- En las fichas de `productos/`, anteponer `../` a esos destinos.
- El formulario de búsqueda debe enviar a `catalogo.html` en la raíz o `../catalogo.html` desde `productos/`.

## Página activa

Marcar con `aria-current="page"` únicamente el destino que corresponda a la página actual:

- Inicio: enlace de la marca.
- Catálogo: enlace «Catálogo».
- Fichas de producto: enlace «Catálogo».
- Carrito: enlace «Carrito».
- Checkout: enlace «Checkout».

El estado activo debe distinguirse visualmente sin depender únicamente del color. Mantener visibles los estados de foco por teclado en todos los enlaces, campos y botones.

## Diseño

- Mantener fondo blanco, borde inferior sutil y paleta neutra del sistema de diseño.
- Usar el logotipo en serif (`font-serif text-2xl`) y los enlaces y controles en sans serif.
- Usar el acento borgoña `#713E43` para el indicador de página activa, el foco y el botón de búsqueda.
- Mantener un contenedor centrado `max-w-7xl`, con espaciado horizontal adaptable (`px-4 sm:px-6 lg:px-8`).
- Permitir que los elementos se reorganicen en pantallas estrechas; la barra no debe provocar desbordamiento horizontal.
- El formulario debe poder reducirse sin ocultar sus controles y el botón debe conservar un área de interacción cómoda.
- No añadir iconos decorativos, hojas CSS propias ni dependencias para representar estos elementos.

## Comportamiento y límites

- La búsqueda realiza una navegación GET al catálogo con el texto en `q`. En este prototipo, el catálogo no interpreta ni filtra la consulta; el aviso debe dejarlo claro.
- La marca y los enlaces principales navegan a las páginas estáticas correspondientes.
- «Mi cuenta» es informativo y no debe simular una función disponible.
- La barra no debe afirmar que el carrito guarda productos ni que checkout procesa pedidos o pagos.
- No añadir JavaScript propio para modificar el comportamiento.
- Mantener la misma estructura, orden, textos y tratamiento visual en todas las páginas; solo cambian las rutas relativas y el estado de página activa.
