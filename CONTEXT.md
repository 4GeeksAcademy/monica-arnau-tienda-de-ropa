# Contexto del proyecto: tienda online de moda francesa

## Objetivo

Crear un prototipo visual y navegable para una tienda online de una marca francesa de ropa. La experiencia debe ser elegante, clara, adaptable a móvil y escritorio, y representar el recorrido desde la página de inicio hasta el checkout.

## Tecnologías y restricciones

- HTML5 semántico.
- Tailwind CSS v4 mediante el CDN indicado en el README del proyecto.
- No usar React, frameworks adicionales, JavaScript propio ni CSS adicional.
- No modificar `server.py`, salvo que una necesidad justificada lo requiera.
- El contenido será un prototipo estático: no hay backend, pagos reales ni persistencia del carrito.

## Vistas

1. **Inicio (`index.html`)**: navegación reutilizable, campaña destacada, nuevos lanzamientos, más vendidos y pie de página.
2. **Catálogo (`catalogo.html`)**: navegación, filtros visuales de categoría y talla, y cuadrícula de referencia de 20 productos.
3. **Producto (`producto.html`)**: imagen y datos del producto, selector visual de talla y cantidad, botón de añadir al carrito y descripción de materiales y usos.
4. **Carrito (`carrito.html`)**: vista completa con tres productos de ejemplo, cantidades, precios, subtotal, impuestos y total.
5. **Checkout (`checkout.html`)**: flujo visual de tres pasos: datos personales, dirección de entrega y pago con tarjeta.

La navbar y el footer deben mantenerse coherentes en todas las vistas.

## Dirección visual

Proponer una identidad de moda francesa contemporánea: composición editorial, tipografía sobria, espacio en blanco generoso, paleta neutra y fotografía de producto protagonista. El diseño debe priorizar la legibilidad y evitar que los adornos compitan con los productos.

## Alcance funcional

Los enlaces deben permitir recorrer las páginas y las acciones deben tener un comportamiento coherente con un prototipo estático. Al no haber JavaScript propio ni backend, no se simularán operaciones persistentes: el carrito tendrá datos de ejemplo y el checkout no procesará pagos reales.

## Criterios de aceptación

- Las cinco vistas existen y pueden abrirse desde la navegación.
- La navegación y el footer son consistentes en todas ellas.
- El catálogo muestra 20 productos como referencia.
- El carrito incluye tres productos y un resumen completo de importes.
- El checkout presenta claramente sus tres pasos.
- La interfaz es usable en móvil, tablet y escritorio, sin desbordamiento horizontal.
- El producto y la marca incluyen datos estructurados Schema.org cuando corresponda.
- Se prueba la URL pública con PageSpeed Insights, buscando una puntuación de al menos 80.
