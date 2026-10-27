# Especificación: plantilla HTML común

## Objetivo

Definir una plantilla HTML semántica y adaptable que sirva como base visual común para las páginas de la tienda. La plantilla se guardará en `docs/reference/base.html`.

Esta especificación no implementa la plantilla. El archivo `base.html` deberá incluir únicamente la estructura compartida y un área principal vacía, sin contenido específico de las cinco vistas.

## Fuente de requisitos

La implementación debe respetar las instrucciones de `AGENTS.md`, el alcance de `CONTEXT.md` y las pautas visuales de `DESIGN.md`. En caso de conflicto, mantener las restricciones técnicas del proyecto: HTML estático, Tailwind CSS v4 por CDN, sin JavaScript propio, sin CSS adicional y sin cambios a `server.py`.

## Alcance de la plantilla

El documento `docs/reference/base.html` debe contener:

1. Estructura básica completa de documento HTML5.
2. Metadatos esenciales para codificación, viewport y título provisional.
3. Inclusión de Tailwind CSS v4 mediante el CDN Browser indicado en `README.es.md`.
4. Un `<header>` con navegación común.
5. Un `<main>` semántico, presente pero vacío para que cada página añada su propio contenido.
6. Un `<footer>` común con grupos de enlaces e información de contacto.

No debe contener hero, productos, filtros, formularios de producto, carrito, pasos de checkout ni otro contenido específico de una vista.

## Estructura semántica

- Usar `<!doctype html>` y `<html lang="es">`.
- Incluir `<head>` con `meta charset`, `meta name="viewport"` y un `<title>` provisional apropiado para una plantilla.
- Cargar Tailwind CSS v4 desde el CDN oficial browser indicado por el README del proyecto.
- Organizar el documento en `<header>`, `<nav>`, `<main>` y `<footer>`.
- El `<main>` debe estar vacío, sin encabezados, texto, tarjetas ni contenido de ejemplo. Puede llevar un `id` o clases de layout, pero no contenido editorial.
- Mantener una jerarquía de landmarks clara y no duplicar landmarks innecesariamente.

## Navbar compartida

La navbar debe ser visualmente coherente con el estilo de la marca y contener:

- Logo o nombre tipográfico de la marca, enlazado a `index.html`.
- Enlace al catálogo (`catalogo.html`).
- Campo de búsqueda con etiqueta accesible y forma de envío válida para un prototipo estático; puede dirigir al catálogo.
- Entrada de cuenta claramente identificada. Al no existir una vista de cuenta ni JavaScript de interacción, no debe aparentar abrir un menú funcional ni enlazar a una ruta inexistente.
- Enlace al carrito (`carrito.html`).

Los enlaces de navegación deben usar destinos relativos existentes. Los controles deben tener nombres accesibles y estados de foco visibles. La distribución debe adaptarse a móvil sin provocar scroll horizontal.

## Footer compartido

El footer debe agrupar de forma legible estas secciones:

- **Categorías:** calzado, camisas, pantalones y accesorios.
- **Legal / marca:** términos y condiciones, política de privacidad y sobre la marca.
- **Contacto:** información de contacto de demostración claramente identificada como tal si no hay datos oficiales disponibles.

No dirigir enlaces a páginas inexistentes. Las categorías pueden conducir al catálogo común mientras no existan filtros funcionales. Los elementos legales o de marca sin destino implementado deben mostrarse como texto informativo o enlazarse a un ancla real ya presente, sin inventar rutas.

## Dirección visual y layout

Aplicar las decisiones de `DESIGN.md`:

- Estética editorial, sobria y cálida, propia de una marca francesa contemporánea.
- Paleta neutra: fondo marfil, superficies claras, texto carbón, bordes beige y acento borgoña apagado; verde oliva solo como acento alternativo puntual.
- Titulares con serif de sistema y texto de interfaz con sans serif de sistema.
- Espacio en blanco generoso, bordes discretos y sin sombras pesadas ni adornos que compitan con el producto.
- Usar utilities de Tailwind, sin hoja CSS adicional ni estilos inline.
- Diseño mobile-first, con contenedor fluido, ancho máximo razonable y breakpoints estándar de Tailwind.
- En móvil, reorganizar navbar y footer para que sean legibles y no desborden el viewport.

## Accesibilidad

- Usar textos de enlace descriptivos, no etiquetas genéricas como «aquí».
- Etiquetar el campo de búsqueda con `<label>` visible o texto accesible equivalente.
- Asegurar contraste adecuado y foco visible para todos los controles interactivos.
- Mantener orden de navegación por teclado coherente con el orden visual.
- No usar solo color para distinguir un enlace o estado.
- Declarar el idioma del documento en español.

## Restricciones técnicas

- HTML5 semántico y Tailwind CSS v4 por CDN.
- No incluir React, otros frameworks, JavaScript propio, CSS adicional ni bibliotecas de iconos o tipografía.
- El script de Tailwind CDN es la única inclusión de script permitida por esta especificación.
- No modificar `server.py`.
- No añadir comportamientos que impliquen estado persistente, menú desplegable real o procesamiento de formularios.

## Criterios de aceptación

- Existe `docs/reference/base.html` con la estructura descrita.
- El documento contiene el CDN de Tailwind CSS v4 y no contiene JavaScript propio ni CSS adicional.
- Navbar, `<main>` vacío y footer están presentes y semánticamente organizados.
- Navbar y footer incluyen todos los elementos requeridos sin rutas internas rotas.
- El `<main>` no contiene contenido específico de inicio, catálogo, producto, carrito o checkout.
- Las clases de Tailwind permiten reflujo en móvil, tablet y escritorio sin scroll horizontal.
- La plantilla conserva la identidad visual definida en `DESIGN.md` y no altera `server.py`.
