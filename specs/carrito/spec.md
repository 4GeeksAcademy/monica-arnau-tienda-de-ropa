# Especificación: carrito de demostración

## Objetivo

Definir una página completa de carrito para el prototipo estático de Maison Élise. La página debe mostrar una selección fija de productos de ejemplo y un resumen legible de importes, manteniendo la identidad visual y las reglas de accesibilidad del proyecto.

El carrito es demostrativo: no almacena selecciones, no actualiza cantidades y no realiza compras.

## Fuente de requisitos

La implementación debe respetar:

- [AGENTS.md](../../AGENTS.md): tecnologías permitidas, navegación, accesibilidad y verificación.
- [CONTEXT.md](../../CONTEXT.md): alcance y límites funcionales del prototipo.
- [DESIGN.md](../../DESIGN.md): identidad visual y patrones de interfaz.
- La navegación compartida del sitio y las reglas de consistencia acordadas para el proyecto.

Si hay instrucciones antiguas que se contradicen con la arquitectura actual, deben alinearse antes o junto con la implementación. El detalle de producto existente usa fichas individuales en `productos/`; no se deben inventar rutas de producto que no existan.

## Alcance

- Crear `carrito.html` en la raíz del proyecto.
- Mostrar tres productos fijos de ejemplo.
- Presentar precio unitario, cantidad y total por producto, además del resumen de importes.
- Proporcionar una ruta para continuar al checkout demostrativo en `checkout.html`.
- Indicar que el contenido es ilustrativo y que el carrito no es persistente.
- Mantener el diseño adaptable, la navegación y el footer coherentes con el resto del sitio.

Esta vista no incluye lógica de carrito, persistencia, modificación de cantidades, eliminación de productos ni procesamiento de pedidos.

## Contenido y datos

- Mostrar exactamente tres productos de demostración.
- Cada producto debe incluir:
  - Imagen o miniatura local correspondiente a ese producto.
  - Texto alternativo útil y fiel a la imagen.
  - Nombre del producto.
  - Precio unitario en euros.
  - Cantidad fija de demostración.
  - Total de línea, calculado como precio unitario por cantidad.
- Mostrar un resumen diferenciado con:
  - Subtotal.
  - Impuestos.
  - Total.
- Los importes deben ser aritméticamente coherentes entre sí: subtotal igual a la suma de los totales de línea y total igual a subtotal más impuestos.
- Los valores son ilustrativos. No presentar tasas, impuestos, descuentos, gastos de envío ni políticas comerciales como información real si no están definidos por el proyecto.
- Usar formato uniforme de precios en euros, por ejemplo `89,00 €`.
- Incluir un aviso visible que indique que los productos, cantidades e importes son de demostración y no representan un pedido real.

## Estructura de la página

La página debe incluir:

- Documento HTML5 con `lang="es"`, UTF-8, viewport, título y descripción adecuados.
- El CDN oficial de Tailwind CSS v4 previsto por el proyecto; no incluir scripts propios.
- Navbar coherente con el resto de las vistas.
- Un enlace para saltar al contenido principal si se usa ese patrón en las demás páginas.
- Un `<main>` con un único `<h1>` descriptivo, como “Carrito de demostración”.
- Una lista semántica de productos, organizada para que cada línea pueda leerse con claridad.
- Un bloque de resumen con etiquetas visibles para cada importe.
- Un enlace o botón de navegación identificado como “Comprar” o “Continuar al checkout”, que apunte a `checkout.html` cuando dicha página exista.
- Un enlace para volver al catálogo.
- Footer coherente con el resto del sitio.

No implementar un panel lateral en lugar de una página completa.

## Interacciones y límites funcionales

- Las cantidades son fijas y no deben presentarse como controles editables.
- No añadir controles falsos para cambiar cantidades, eliminar productos, guardar el carrito o aplicar cupones.
- El enlace al checkout es navegación hacia una página demostrativa, no una confirmación de compra.
- No afirmar que los productos se han añadido desde una ficha ni que las selecciones se conservan entre páginas.
- No crear formularios que aparenten actualizar el carrito o enviar un pedido.
- Si `checkout.html` aún no existe al implementar el carrito, no publicar un enlace roto. Coordinar ambos cambios para que el enlace quede disponible cuando exista la página de checkout.

## Navegación compartida

- La marca enlaza a `index.html`.
- El catálogo enlaza a `catalogo.html`.
- El enlace al carrito apunta a `carrito.html` y puede marcarse con `aria-current="page"`.
- El buscador, la cuenta y cualquier otro elemento compartido deben conservar los mismos textos, destinos y explicación de disponibilidad que el resto de las páginas.
- Todas las rutas deben ser relativas y apuntar a páginas existentes.
- Al implementar el carrito, actualizar la navegación compartida en las vistas afectadas, incluidas las fichas dentro de `productos/`, para que el carrito tenga un destino real y consistente.

## Diseño adaptable

- Seguir `DESIGN.md`: estilo editorial sobrio, fondo claro, superficies neutras, bordes discretos y acento de marca.
- En escritorio, presentar la lista de productos y el resumen en columnas cuando haya espacio suficiente.
- En móvil, apilar el resumen debajo de los productos.
- Evitar tablas rígidas que provoquen scroll horizontal. Si se utiliza una tabla, debe ser accesible y adaptarse a pantallas pequeñas.
- Usar breakpoints estándar de Tailwind y mantener áreas de interacción cómodas.
- Asegurar que nombre, precio, cantidad y total de cada producto sigan siendo legibles en pantallas estrechas.

## Accesibilidad

- Usar landmarks semánticos como `<header>`, `<nav>`, `<main>`, `<section>` y `<footer>`.
- Mantener un único `<h1>` y una jerarquía ordenada de encabezados.
- Usar enlaces para navegar y no simular botones de acción sin comportamiento.
- Proporcionar texto alternativo apropiado para las imágenes.
- Mantener foco visible y contraste suficiente.
- Etiquetar claramente subtotal, impuestos y total; no depender solo del color para diferenciar importes.
- Asegurar que el orden de lectura y de teclado sea coherente.

## Restricciones técnicas

- HTML5 semántico y Tailwind CSS v4 por CDN oficial.
- Sin JavaScript propio, frameworks, CSS adicional, dependencias nuevas o cambios a `server.py`, salvo autorización expresa.
- No añadir almacenamiento local, cookies ni otros mecanismos para aparentar persistencia.
- No procesar pagos ni enviar datos personales o financieros.

## Criterios de aceptación

- Existe `carrito.html` y puede abrirse mediante una ruta estática.
- Se muestran exactamente tres productos de ejemplo.
- Cada línea contiene imagen, nombre, precio unitario, cantidad y total.
- El subtotal coincide con la suma de las líneas; el total coincide con subtotal más impuestos.
- Se indica claramente que los datos son demostrativos y no persistentes.
- El enlace al checkout apunta a `checkout.html` cuando la página exista; no hay enlaces internos rotos.
- La navbar y el footer son coherentes con el resto del sitio.
- La página es usable en móvil, tablet y escritorio, sin desbordamiento horizontal.
- No se sugieren funciones de edición, persistencia, compra o pago que no estén implementadas.
- No se añaden scripts, CSS, frameworks, dependencias ni cambios al servidor.

## Verificación prevista

- Abrir `carrito.html` mediante el servidor estático del proyecto.
- Comprobar destinos de enlaces internos y disponibilidad de imágenes.
- Verificar los cálculos del subtotal, los impuestos y el total.
- Revisar presentación en móvil, tablet y escritorio.
- Probar navegación con teclado, foco visible, orden de lectura y textos alternativos.
- Revisar consola y solicitudes de recursos en el navegador.
- Registrar solo las comprobaciones ejecutadas y no extrapolar resultados a páginas no revisadas.
