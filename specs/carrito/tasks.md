# Tareas: carrito de demostración

Marca cada tarea con `[x]` solo después de completarla. Las tareas de verificación se marcan únicamente tras ejecutar las comprobaciones.

## Preparación

- [x] Elegir tres productos existentes y confirmar para cada uno la imagen local, el texto alternativo, el precio unitario y una cantidad fija de demostración: Camisa Claire (`catalogo-camisa-claire.webp`, 89,00 €, cantidad 1), Pantalón Jules (`catalogo-pantalon-jules.webp`, 125,00 €, cantidad 1) y Mocasines Étienne (`catalogo-mocasines-etienne.webp`, 145,00 €, cantidad 1). Los nombres, precios y alt se tomaron de `catalogo.html`; las tres imágenes existen en `assets/images/`.
- [x] Calcular los totales de línea, el subtotal, los impuestos ilustrativos y el total; comprobar que las operaciones son coherentes y documentar los valores elegidos para usarlos en la página: líneas de 89,00 €, 125,00 € y 145,00 €; subtotal 359,00 €; impuesto ilustrativo del 20%: 71,80 €; total 430,80 €.
- [x] Confirmar si `checkout.html` existe antes de decidir el enlace de continuación. Si no existe, no crear un enlace a una ruta inexistente. Confirmado: no existe; se omite el enlace hasta implementarlo.

## Implementación

- [x] Crear `carrito.html` como documento HTML5 completo con idioma español, metadatos, CDN de Tailwind CSS v4 permitido y sin JavaScript propio ni CSS adicional.
- [x] Añadir navbar y footer coherentes con las páginas existentes, con rutas relativas válidas y el carrito identificado como página actual.
- [x] Añadir un `<main>` con un único `<h1>` descriptivo, enlace de salto al contenido si se mantiene ese patrón en las demás vistas y un enlace para volver al catálogo.
- [x] Presentar exactamente tres productos en una lista semántica; cada producto debe mostrar imagen, alt, nombre, precio unitario, cantidad fija y total de línea.
- [x] Añadir un resumen visible con subtotal, impuestos y total, usando los importes comprobados en preparación.
- [x] Añadir un aviso claro de que productos, cantidades e importes son demostrativos y que el carrito no guarda selecciones ni representa un pedido real.
- [x] Implementar la presentación adaptable: productos y resumen en columnas cuando haya espacio y apilados en móvil, sin desbordamiento horizontal.
- [x] Revisar `index.html` y `catalogo.html`: ambas páginas ya enlazan a `carrito.html` con la navegación compartida coherente; no requirieron cambios.
- [x] Actualizar las 20 fichas de `productos/` para sustituir el indicador de carrito no disponible por un enlace relativo válido a `../carrito.html`; comprobar que cada ficha tiene ese enlace y ya no conserva el aviso anterior.

## Checkout — tarea condicionada

- [ ] Cuando `checkout.html` exista, añadir en `carrito.html` un enlace «Comprar» o «Continuar al checkout» con destino válido. No completar esta tarea antes de que exista la página.

## Verificación

- [x] Abrir `carrito.html` mediante el servidor estático y comprobar que carga correctamente (HTTP 200 en `http://127.0.0.1:3000/carrito.html`).
- [x] Comprobar que las tres imágenes cargan (HTTP 200) y que la página muestra exactamente tres productos.
- [x] Verificar cada total de línea, el subtotal, los impuestos y el total frente a los valores definidos: 89,00 €, 125,00 €, 145,00 €; subtotal 359,00 €; impuestos ilustrativos 71,80 €; total 430,80 €.
- [x] Revisar que los enlaces locales del carrito tienen destinos válidos; confirmar que inicio y catálogo enlazan a `carrito.html`, que las 20 fichas enlazan a `../carrito.html` y que no hay enlace a `checkout.html` mientras no exista.
- [ ] Revisar la presentación en móvil, tablet y escritorio y confirmar que no hay scroll horizontal.
- [ ] Comprobar con teclado el orden de navegación, el foco visible, las etiquetas de importes y los textos alternativos.
- [ ] Revisar consola y solicitudes de recursos; registrar solo las comprobaciones realmente realizadas.
