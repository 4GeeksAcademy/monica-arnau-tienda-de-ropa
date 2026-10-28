# Tareas: carrito de demostración

Marca cada tarea con `[x]` solo después de completarla. Las tareas de verificación se marcan únicamente tras ejecutar las comprobaciones.

## Preparación

- [ ] Elegir tres productos existentes y confirmar para cada uno la imagen local, el texto alternativo, el precio unitario y una cantidad fija de demostración.
- [ ] Calcular los totales de línea, el subtotal, los impuestos ilustrativos y el total; comprobar que las operaciones son coherentes y documentar los valores elegidos para usarlos en la página.
- [ ] Confirmar si `checkout.html` existe antes de decidir el enlace de continuación. Si no existe, no crear un enlace a una ruta inexistente.

## Implementación

- [ ] Crear `carrito.html` como documento HTML5 completo con idioma español, metadatos, CDN de Tailwind CSS v4 permitido y sin JavaScript propio ni CSS adicional.
- [ ] Añadir navbar y footer coherentes con las páginas existentes, con rutas relativas válidas y el carrito identificado como página actual.
- [ ] Añadir un `<main>` con un único `<h1>` descriptivo, enlace de salto al contenido si se mantiene ese patrón en las demás vistas y un enlace para volver al catálogo.
- [ ] Presentar exactamente tres productos en una lista semántica; cada producto debe mostrar imagen, alt, nombre, precio unitario, cantidad fija y total de línea.
- [ ] Añadir un resumen visible con subtotal, impuestos y total, usando los importes comprobados en preparación.
- [ ] Añadir un aviso claro de que productos, cantidades e importes son demostrativos y que el carrito no guarda selecciones ni representa un pedido real.
- [ ] Implementar la presentación adaptable: productos y resumen en columnas cuando haya espacio y apilados en móvil, sin desbordamiento horizontal.
- [ ] Actualizar `index.html` y `catalogo.html` para que la navegación al carrito sea coherente y apunte a `carrito.html`.
- [ ] Actualizar las 20 fichas de `productos/` para sustituir el indicador de carrito no disponible por un enlace relativo válido a `../carrito.html`.

## Checkout — tarea condicionada

- [ ] Cuando `checkout.html` exista, añadir en `carrito.html` un enlace «Comprar» o «Continuar al checkout» con destino válido. No completar esta tarea antes de que exista la página.

## Verificación

- [ ] Abrir `carrito.html` mediante el servidor estático y comprobar que carga correctamente.
- [ ] Comprobar que las tres imágenes cargan y que la página muestra exactamente tres productos.
- [ ] Verificar cada total de línea, el subtotal, los impuestos y el total frente a los valores definidos.
- [ ] Revisar que los enlaces al inicio, catálogo y carrito tienen destinos válidos desde las páginas afectadas; confirmar que no se dejó un enlace roto a `checkout.html` mientras no exista.
- [ ] Revisar la presentación en móvil, tablet y escritorio y confirmar que no hay scroll horizontal.
- [ ] Comprobar con teclado el orden de navegación, el foco visible, las etiquetas de importes y los textos alternativos.
- [ ] Revisar consola y solicitudes de recursos; registrar solo las comprobaciones realmente realizadas.
