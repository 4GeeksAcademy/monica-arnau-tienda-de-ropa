# Tareas: página de catálogo

Marca cada tarea como completada cambiando `[ ]` por `[x]` al ejecutarla.

## Preparación y estructura

- [x] Revisar la plantilla, `index.html`, las specs de base-layout y home, y los recursos de imagen existentes; reutilizar sus componentes y crear `catalogo.html` en la raíz con estructura HTML5, `lang="es"`, codificación UTF-8, viewport, título y descripción propios, landmarks comunes y un único `<h1>`.
- [x] Cargar únicamente el CDN Browser oficial de Tailwind CSS v4; no añadir scripts propios, hojas CSS, fuentes externas, bibliotecas ni dependencias.
- [ ] Reutilizar navbar y footer sin rediseñarlos: enlazar marca a `index.html`, catálogo a `catalogo.html` y carrito a `carrito.html`; marcar catálogo con `aria-current="page"`, mantener búsqueda con etiqueta visible y cuenta identificada como no disponible, y conservar en el footer calzado, camisas, pantalones, accesorios, términos, privacidad, sobre la marca y contacto de demostración, sin destinos inexistentes. Pendiente: `carrito.html` aún no existe.

## Cabecera, filtros y productos

- [x] Añadir introducción breve en español y recuento estático coherente: «20 productos de demostración», sin afirmar inventario, disponibilidad, descuentos ni popularidad reales.
- [x] Situar antes de la cuadrícula grupos de controles nativos para categoría y talla, con título o leyenda y etiquetas visibles asociadas mediante `for` e `id`.
- [x] Incluir «Todas las categorías», calzado, camisas, pantalones y accesorios; añadir «Todas las tallas» y ejemplos orientativos que no sugieran una escala común para ropa, calzado y accesorios.
- [x] Deshabilitar los filtros y mostrar el aviso «Filtros de demostración: no modifican los productos mostrados»; no añadir acciones, formularios, estados ni enlaces que aparenten filtrar.
- [x] Crear exactamente 20 tarjetas de demostración distintas, representar las cuatro categorías y organizarlas semánticamente; no duplicar tarjetas solo para completar el total.
- [x] En cada tarjeta incluir imagen, texto alternativo fiel, nombre concreto, precio en euros con formato coherente y enlace descriptivo válido a `producto.html`.
- [x] Aclarar junto a la cuadrícula que todos los enlaces abren la misma ficha de demostración; junto a búsqueda y filtros, explicar sus límites. No inventar rutas/parámetros ni añadir enlaces anidados, reseñas, promociones, estados o acciones de compra/favoritos; el prototipo no ofrece búsqueda real, inventario ni operaciones persistentes.

## Imágenes, diseño y accesibilidad

- [x] Usar imágenes accesibles, optimizadas, de proporciones coherentes y correspondientes a su texto alternativo; no enlazar archivos locales inexistentes, URLs temporales ni originales sobredimensionados.
- [x] Declarar `width` y `height` cuando se conozcan, usar `loading="lazy"` fuera de la primera pantalla y no retrasar innecesariamente las primeras imágenes visibles.
- [x] Aplicar mediante utilities de Tailwind el estilo editorial de `DESIGN.md`, con tipografía de sistema, paleta cálida, contenedor fluido, espaciado generoso y bordes discretos, sin estilos inline ni CSS adicional.
- [x] Diseñar mobile-first con cuadrícula de una columna en móvil, dos o tres en tablet según el espacio y cuatro en escritorio; apilar filtros en móvil y disponerlos horizontalmente cuando haya espacio, evitando anchos fijos, etiquetas recortadas y scroll horizontal en navbar, contenido y footer.
- [x] Mantener jerarquía de encabezados, agrupación semántica, nombres de enlace descriptivos, contraste suficiente, foco visible y orden de teclado coherente; no depender solo de placeholders, color o hover.

## Verificación y restricciones

- [x] Verificar los 20 productos y su recuento, categorías representadas, contenido de cada tarjeta, filtros deshabilitados y avisos de demostración.
- [x] Comprobar que todos los enlaces y anclas apuntan a destinos existentes; abrir `/catalogo.html` y confirmar que `/` sigue sirviendo el inicio. Pendiente: `producto.html` y `carrito.html` aún no existen; ambas rutas se mantienen conforme a la spec.
- [x] Revisar manualmente en móvil, tablet y escritorio la cuadrícula, navegación, filtros y footer; comprobar teclado, foco y consola. Las rutas se comprobaron localmente y las imágenes remotas respondieron correctamente.
- [x] Confirmar que no se añadieron JavaScript propio, CSS adicional, dependencias, estado persistente ni cambios a `server.py`.
- [x] Si hay URL pública, ejecutar PageSpeed Insights buscando al menos 80 puntos y registrar URL, fecha, modalidad y puntuación real; si no se ejecuta, dejarlo pendiente sin afirmar resultados.

### Auditoría local con Lighthouse

- Fecha: 28/10/2026.
- URL de Codespaces analizada: `https://sinister-broomstick-jx5vvjx6gjq2qvj9-3000.app.github.dev/catalogo.html`.
- Modalidad: auditoría local con Lighthouse ejecutada en Chrome; no es una medición de PageSpeed Insights.
- Resultados: rendimiento 92/100, accesibilidad 100/100, buenas prácticas 96/100 y SEO 63/100.
- Objetivo de rendimiento (≥80): cumplido.
- PageSpeed Insights: pendiente; todavía no se ha ejecutado.
