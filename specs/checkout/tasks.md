# Tareas: checkout de demostración

Marca cada tarea con `[x]` solo después de completarla. Las tareas de verificación se marcan únicamente tras ejecutar las comprobaciones correspondientes.

## Preparación

- [ ] Leer `AGENTS.md`, `CONTEXT.md`, `DESIGN.md` y `specs/checkout/spec.md`; confirmar las restricciones técnicas y de seguridad antes de editar archivos.
- [ ] Revisar `carrito.html` y confirmar los productos e importes que debe reflejar el checkout: Camisa Claire (89,00 €), Pantalón Jules (125,00 €), Mocasines Étienne (145,00 €), subtotal ilustrativo (359,00 €), impuestos ilustrativos (71,80 €) y total ilustrativo (430,80 €).
- [ ] Revisar la navegación y el footer existentes para reutilizar sus textos, estructura y estilos coherentemente.

## Implementación de `checkout.html`

- [ ] Crear `checkout.html` en la raíz como documento HTML5 completo con `lang="es"`, UTF-8, viewport, título y descripción propios, y el CDN oficial de Tailwind CSS v4.
- [ ] Añadir navbar y footer coherentes con las vistas existentes, con rutas relativas válidas a inicio, catálogo y carrito, y marcar checkout como página actual.
- [ ] Añadir enlace de salto al contenido principal si se mantiene ese patrón en las demás vistas.
- [ ] Crear un `<main>` con un único `<h1>` que identifique el checkout como demostrativo.
- [ ] Añadir tres secciones visibles, numeradas y en orden: datos personales, dirección de entrega y pago con tarjeta; asignar identificadores a las secciones si se ofrecen enlaces de ancla.
- [ ] Añadir campos de muestra para datos personales y dirección, cada uno con etiqueta asociada y tipo HTML apropiado; mantenerlos inactivos para impedir el envío de datos.
- [ ] Representar el paso de pago sin solicitar números de tarjeta, código de seguridad, vencimiento u otros datos financieros reales; acompañarlo de una explicación visible de que es una simulación.
- [ ] Confirmar que no hay formulario enviable, botón de pago o confirmación de compra, ni controles que transmitan o guarden información.
- [ ] Añadir un resumen visible con los tres productos, cantidades e importes coincidentes con `carrito.html`; identificar todos los valores como ilustrativos.
- [ ] Añadir un enlace con destino válido para volver a `carrito.html`.
- [ ] Aplicar el diseño adaptable de `DESIGN.md`: resumen y contenido organizados para escritorio y apilados en móvil, sin anchos rígidos ni scroll horizontal.
- [ ] Aplicar HTML semántico, jerarquía de encabezados ordenada, foco visible, contraste suficiente y orden de lectura coherente.
- [ ] Confirmar que `checkout.html` no añade JavaScript propio, CSS adicional, frameworks, dependencias ni cambios a `server.py`.

## Conexión con el carrito

- [ ] Actualizar `carrito.html` para añadir un enlace «Comprar» o «Continuar al checkout» con destino `checkout.html`.
- [ ] Comprobar que `carrito.html` y `checkout.html` enlazan entre sí y que el resto de enlaces de navegación apunta a páginas existentes.
- [ ] Tras implementar y verificar el enlace, actualizar `specs/carrito/tasks.md` y marcar su tarea condicionada de checkout como completada.

## Verificación

- [ ] Abrir `checkout.html` directamente mediante el servidor estático y confirmar que responde correctamente.
- [ ] Abrir `carrito.html`, seguir el enlace al checkout y probar el enlace de retorno al carrito.
- [ ] Comparar nombres, cantidades y precios de los productos, así como subtotal, impuestos y total, entre ambas páginas.
- [ ] Comprobar que se muestran los tres pasos en el orden especificado y que sus títulos y anclas, si las hay, son correctos.
- [ ] Inspeccionar el HTML para confirmar que no existen formularios enviables, destinos externos de envío, botones de compra ni campos para datos financieros reales.
- [ ] Comprobar que cada control de muestra tiene etiqueta asociada y está inactivo, y que los avisos explican claramente la naturaleza demostrativa del checkout.
- [ ] Revisar la presentación en móvil, tablet y escritorio; confirmar que no hay desbordamiento horizontal.
- [ ] Probar la navegación con teclado y verificar el orden de foco y los indicadores visibles.
- [ ] Revisar consola del navegador y solicitudes de recursos; anotar resultados y páginas efectivamente comprobadas.
