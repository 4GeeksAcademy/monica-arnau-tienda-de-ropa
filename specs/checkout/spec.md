# Especificación: checkout de demostración

## Objetivo

Definir una página de checkout estática para el prototipo de Maison Élise. Debe presentar de forma clara los tres pasos del recorrido de compra —datos personales, dirección de entrega y pago— y mantener la identidad visual, la accesibilidad y la navegación del resto del sitio.

El checkout es exclusivamente demostrativo: no crea pedidos, no envía datos personales o financieros a ningún servicio y no procesa pagos.

## Fuentes y relación con otras vistas

La implementación debe respetar:

- [AGENTS.md](../../AGENTS.md): restricciones técnicas, estructura del checkout, accesibilidad y límites de procesamiento.
- [CONTEXT.md](../../CONTEXT.md): alcance del prototipo y criterios de aceptación.
- [DESIGN.md](../../DESIGN.md): dirección visual y patrones compartidos.
- [Spec del carrito](../carrito/spec.md): contenido fijo, importes ilustrativos y comportamiento no persistente.
- Las specs de [base-layout](../base-layout/spec.md), [home](../home/spec.md), [catalog](../catalog/spec.md) y [view-products](../view-products/spec.md), en lo relativo a navegación y patrones comunes.

El checkout debe poder abrirse directamente como página estática y no depender de que el usuario haya llegado desde el carrito ni de que exista un estado de compra persistente.

## Alcance

- Crear `checkout.html` en la raíz del proyecto.
- Mostrar los tres pasos en una sola página, en este orden:
  1. Datos personales.
  2. Dirección de entrega.
  3. Pago con tarjeta.
- Mostrar un resumen de pedido que coincida con los datos fijos de `carrito.html`.
- Permitir navegar entre el carrito y el checkout mediante enlaces válidos.
- Mantener la navegación y el footer coherentes con las demás páginas.
- Indicar con claridad que se trata de una demostración y que no se completará ninguna compra.

No se requiere un paso a paso dinámico, autenticación, backend, persistencia ni integración con un proveedor de pagos.

## Contenido y resumen del pedido

El resumen debe corresponder al carrito definido en [specs/carrito/spec.md](../carrito/spec.md):

- Camisa Claire: 89,00 €.
- Pantalón Jules: 125,00 €.
- Mocasines Étienne: 145,00 €.
- Subtotal ilustrativo: 359,00 €.
- Impuestos ilustrativos: 71,80 €.
- Total ilustrativo: 430,80 €.

Si estos datos cambian en el carrito, se debe actualizar también el resumen del checkout para que ambos sean idénticos. No presentar el impuesto del 20 % ni ningún otro importe como una condición fiscal o comercial real.

El resumen no debe insinuar que el carrito se conserva entre páginas. Identificar productos, cantidades e importes como datos de ejemplo.

## Estructura y navegación

La página debe incluir:

- Documento HTML5 completo con `lang="es"`, UTF-8, viewport, título y descripción propios.
- El CDN oficial de Tailwind CSS v4 permitido por el proyecto, sin scripts propios.
- Navbar compartida con enlaces válidos a inicio, catálogo y carrito; identificar checkout como página actual cuando se incluya en la navegación.
- Un enlace para saltar al contenido principal, siguiendo el patrón compartido cuando corresponda.
- Un `<main>` con un único `<h1>` descriptivo, por ejemplo, “Checkout de demostración”.
- Tres secciones numeradas, cada una con título visible y un identificador estable para permitir navegación mediante anclas.
- Enlaces de ancla entre pasos si se ofrecen accesos rápidos; no simular que esos enlaces avanzan o validan un flujo dinámico.
- Un resumen del pedido visible y claramente etiquetado.
- Un enlace para volver a `carrito.html`.
- Footer coherente con el resto de las vistas.

## Pasos y campos

### Paso 1: datos personales

Presentar los campos de demostración apropiados, como nombre, apellidos, correo electrónico y teléfono. Cada campo que se muestre debe tener una etiqueta asociada y un tipo de entrada apropiado.

### Paso 2: dirección de entrega

Presentar los campos de demostración apropiados, como dirección, ciudad, código postal y país. Cada campo que se muestre debe tener una etiqueta asociada y un tipo de entrada apropiado.

### Paso 3: pago con tarjeta

Identificar claramente que el pago es una simulación. No pedir, enviar ni procesar números de tarjeta, código de seguridad, fecha de vencimiento ni otros datos financieros reales.

Para representar visualmente el paso de pago se pueden usar datos ficticios estáticos o controles inactivos claramente identificados como ejemplos. No permitir introducir datos reales de tarjeta.

### Comportamiento seguro de los campos

- Los campos son muestras visuales, no un formulario que envía datos.
- No añadir una acción de envío, botón de confirmación de compra ni un formulario que pueda enviar valores a `checkout.html`, a una URL externa o a una query string.
- No usar datos personales o financieros reales en valores de ejemplo.
- Si se usan controles deshabilitados para mostrar el diseño, explicarlo con un aviso visible; no hacerlos parecer editables.
- No afirmar que la validación nativa, el guardado o el envío están disponibles si los campos son solo una representación estática.

## Interacciones y límites funcionales

- Los tres pasos permanecen visibles en una sola página; no implementar un flujo dinámico.
- No crear pedidos, reservar productos, enviar formularios ni guardar información.
- No integrar servicios de pago ni solicitar datos reales de tarjeta.
- No incluir un botón “Pagar”, “Confirmar pedido” o equivalente que sugiera una compra funcional.
- La acción principal disponible debe ser navegación segura, por ejemplo, volver al carrito.
- Si se muestra un control sin funcionalidad, debe estar inactivo y acompañado de una explicación inequívoca.

## Diseño adaptable

- Seguir `DESIGN.md`: estilo editorial sobrio, paleta neutra, espacios generosos y jerarquía visual clara.
- En escritorio, organizar los pasos y el resumen en columnas solo cuando el espacio lo permita.
- En móvil, usar una sola columna y mantener el orden de lectura: pasos y campos, resumen, navegación.
- Utilizar breakpoints estándar de Tailwind y evitar anchos rígidos o scroll horizontal.
- Asegurar que los campos de muestra y el resumen sean legibles en móvil, tablet y escritorio.

## Accesibilidad

- Utilizar landmarks semánticos como `<header>`, `<nav>`, `<main>`, `<section>` y `<footer>`.
- Mantener un único `<h1>` y una jerarquía ordenada de encabezados.
- Asociar cada etiqueta visible con su control correspondiente.
- Usar tipos de entrada adecuados cuando se muestren campos.
- Mantener foco visible, contraste suficiente y orden de lectura y teclado coherente.
- Identificar los pasos con números y títulos; no depender solo del color.
- Comunicar el carácter demostrativo y la falta de procesamiento mediante texto, no solo mediante apariencia visual.

## Restricciones técnicas

- HTML5 semántico y Tailwind CSS v4 por CDN oficial.
- No usar JavaScript propio, frameworks, CSS adicional ni dependencias nuevas.
- No modificar `server.py` salvo que exista una necesidad técnica justificada y aprobada.
- No enviar datos personales o financieros a ningún destino.
- No afirmar que el checkout está conectado a un sistema de pedidos o pagos.

## Criterios de aceptación

- Existe `checkout.html` y puede servirse mediante una ruta estática.
- Se muestran claramente los tres pasos requeridos y en el orden especificado.
- Los campos visibles tienen etiquetas asociadas y tipos apropiados; los controles de demostración no permiten enviar información.
- No existe un botón ni un formulario que cree pedidos o transmita datos personales o financieros.
- El resumen coincide con los productos e importes definidos en la spec del carrito.
- Se indica visiblemente que el checkout es demostrativo y que no procesa pagos.
- La navegación a inicio, catálogo y carrito apunta a destinos existentes.
- El layout es usable en móvil, tablet y escritorio y no produce desbordamiento horizontal.
- No se añaden scripts, CSS, frameworks, dependencias ni modificaciones al servidor.

## Verificación prevista

- Abrir `checkout.html` directamente mediante el servidor estático.
- Comprobar que los enlaces internos y las anclas de los pasos tienen destinos válidos.
- Comparar productos, subtotal, impuestos y total con `carrito.html`.
- Revisar que no haya formularios o controles capaces de enviar datos personales o financieros.
- Revisar presentación en móvil, tablet y escritorio.
- Comprobar con teclado el orden de lectura y navegación, el foco visible y las etiquetas de los campos.
- Revisar consola y solicitudes de recursos en el navegador.
- Registrar solo las pruebas realmente ejecutadas y especificar qué páginas cubrieron.
