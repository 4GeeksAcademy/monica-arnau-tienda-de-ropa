# Plan: página de catálogo

## Objetivo

Implementar `catalogo.html` en la raíz conforme a `specs/catalog/spec.md`, reutilizando la plantilla común, la identidad de `DESIGN.md` y el patrón de tarjetas de la página de inicio. Este plan define el trabajo y las verificaciones; no implica que la página ya esté implementada.

## Pasos

1. **Revisar los componentes y recursos existentes.** Contrastar `docs/reference/base.html`, `index.html` y las specs de base-layout y home para reutilizar navbar, footer y tarjetas sin crear variantes. Revisar las imágenes de `assets/images/`; confirmar que cada recurso elegido existe, carga y representa fielmente su texto alternativo. No inventar rutas locales ni duplicar tarjetas para alcanzar el recuento.
2. **Preparar el documento y la navegación compartida.** Crear `catalogo.html` como documento HTML5 en español, con metadatos propios, título descriptivo y solo el CDN Browser oficial de Tailwind v4. Adaptar los enlaces al contexto de la raíz, marcar el catálogo como página actual y conservar destinos existentes para navegación y footer.
3. **Construir la cabecera del catálogo.** Añadir al `<main>` un único `<h1>`, una introducción editorial breve y el recuento estático «20 productos de demostración». No afirmar disponibilidad, popularidad ni promociones reales.
4. **Añadir filtros no funcionales claramente identificados.** Colocar antes de la cuadrícula controles nativos de categoría y talla, con etiquetas visibles asociadas, opciones «Todas las categorías» y «Todas las tallas», y ejemplos de tallas orientativos. Dejarlos deshabilitados y mostrar el aviso de que no modifican los productos; no añadir botones de aplicar/limpiar ni formularios que sugieran filtrado.
5. **Crear la cuadrícula de productos.** Incorporar exactamente 20 tarjetas distintas, representando calzado, camisas, pantalones y accesorios. Cada una tendrá imagen, texto alternativo fiel, nombre concreto, precio de demostración en euros y enlace descriptivo a `producto.html`. Indicar junto a la cuadrícula que todos los enlaces abren la misma ficha de demostración; no inventar rutas ni parámetros de producto. Resolver la selección de imágenes antes de enlazarlas y usar recursos accesibles y optimizados.
6. **Aplicar el diseño adaptable y accesible.** Usar utilities de Tailwind y el sistema visual editorial de `DESIGN.md`: fondo marfil, texto carbón, bordes neutros y acento borgoña discreto. Diseñar mobile-first con filtros apilados y cuadrícula de una columna en móvil, dos o tres en tablet y cuatro en escritorio. Mantener foco visible, contraste, orden de teclado y ausencia de scroll horizontal.
7. **Verificar contra la spec.** Contar las 20 tarjetas y cotejar el recuento; revisar etiquetas y estado deshabilitado de filtros, categorías representadas, enlaces internos, textos de demostración, carga y dimensiones de imágenes, y diseño en móvil/tablet/escritorio. Abrir `/catalogo.html` y confirmar que `/` sigue sirviendo el inicio. Revisar consola y recursos; si hay URL pública, ejecutar PageSpeed Insights y anotar solo el resultado realmente medido.

## Límites de implementación

- No añadir JavaScript propio, CSS adicional, dependencias, búsqueda o filtros dinámicos, estado persistente ni cambios a `server.py`.
- No enlazar a páginas inexistentes ni presentar el catálogo, inventario o ficha como funcionalidad real.
- La verificación de PageSpeed queda pendiente si no hay URL pública o no se ejecuta la prueba; no afirmar resultados no medidos.
