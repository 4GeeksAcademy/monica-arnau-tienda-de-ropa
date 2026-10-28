# Plan: implementar el carrito de demostración

## Objetivo

Implementar `carrito.html` según [spec.md](spec.md), manteniendo la navegación coherente y sin aparentar persistencia ni operaciones reales.

## Archivos afectados

- **Crear `carrito.html`** en la raíz: página completa con tres productos de demostración, importes, aviso de carrito no persistente, enlace de regreso al catálogo y navbar/footer compartidos.
- **Actualizar `index.html` y `catalogo.html`** para mantener el estilo y el estado de navegación coherentes con la nueva página.
- **Actualizar las 20 fichas HTML de `productos/`**: sustituir el texto de carrito no disponible por un enlace relativo a `../carrito.html`.
- **No modificar `checkout.html` en esta fase**: todavía no existe.

## Orden recomendado

1. Elegir tres productos existentes y fijar cantidades e importes demostrativos. Comprobar precio por cantidad, subtotal, impuestos y total.
2. Crear `carrito.html` con el resumen, el aviso demostrativo y la navegación común. No incluir un enlace a un checkout inexistente.
3. Actualizar de forma coherente los enlaces de carrito en inicio, catálogo y las fichas de producto.
4. Añadir el enlace «Continuar al checkout» en una tarea posterior, cuando `checkout.html` exista.

## Verificación básica

- Abrir `carrito.html` mediante el servidor estático y comprobar las rutas de navegación.
- Comprobar que cargan las imágenes y que hay exactamente tres productos.
- Verificar los cálculos de cada línea, subtotal, impuestos y total.
- Revisar el layout en móvil y la navegación con teclado, incluido el foco visible.
- Confirmar que ninguna página afectada enlaza a una ruta inexistente y que el carrito se identifica como demostrativo, sin persistencia.

Este archivo documenta el plan; no implica que los cambios o las verificaciones se hayan realizado.
