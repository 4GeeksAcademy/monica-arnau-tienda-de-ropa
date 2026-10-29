# Plan: homogeneizar la barra de navegación

## Objetivo

Alinear la barra de navegación superior de las páginas funcionales con `specs/navbar/spec.md`. La implementación debe limitar los cambios en los HTML a la barra y al aviso de búsqueda asociado; el resto del contenido debe permanecer intacto.

## Pasos

1. **Inventariar las páginas y sus variantes actuales.** Revisar las cuatro páginas HTML de la raíz (`index.html`, `catalogo.html`, `carrito.html` y `checkout.html`) y los veinte archivos `productos/*.html`. Registrar la estructura actual de navegación, la etiqueta de página activa, el formulario de búsqueda y el aviso existente, para conservar el contexto de cada documento.
2. **Definir y aplicar una estructura común.** Normalizar dentro del `<header>` el landmark `<nav aria-label="Navegación principal">` con marca, Catálogo, Carrito, Checkout, formulario de búsqueda y cuenta informativa, en el orden de la especificación. Mantener los textos, el estilo adaptable y los estados de foco establecidos. Añadir o normalizar el aviso de búsqueda inmediatamente debajo de la navegación.
3. **Adaptar rutas y estado actual por página.** Usar rutas relativas válidas: destinos desde la raíz en páginas raíz y prefijo `../` desde `productos/`. Marcar únicamente el destino actual con `aria-current="page"`: marca en inicio, Catálogo en catálogo y productos, Carrito en carrito y Checkout en checkout.
4. **Respetar el comportamiento estático y los límites.** Configurar el formulario para enviar mediante GET al catálogo con `name="q"`; no implementar filtrado, JavaScript, cuenta, persistencia de carrito ni procesamiento de pedidos o pagos. No modificar elementos ajenos a la navegación y su aviso.
5. **Verificar la implementación.** Confirmar que las 24 páginas tienen los seis elementos en el orden requerido, que todas las rutas existen y son correctas según la ubicación, que el formulario y la etiqueta son accesibles, que el aviso está presente y que hay un único destino activo. Revisar que los estados de foco sean visibles y que la navegación no provoque desbordamiento horizontal en móvil, tablet y escritorio.

## Límites de implementación

- No editar contenido del `<main>`, footer, metadatos, imágenes ni secciones que no formen parte de la navegación o del aviso de búsqueda.
- No modificar `docs/reference/base.html`, ya que es una plantilla de referencia fuera del alcance.
- No añadir CSS, JavaScript, bibliotecas ni dependencias.
- No cambiar `server.py` ni el comportamiento de otras funciones de las páginas.
- No realizar commits salvo que se soliciten expresamente.
