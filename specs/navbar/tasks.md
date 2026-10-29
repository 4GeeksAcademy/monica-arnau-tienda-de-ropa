# Tareas: homogeneizar la barra de navegación

- [x] Revisar las 24 páginas incluidas en el alcance y anotar sus rutas relativas y el destino que debe marcarse como página actual.
- [x] Normalizar la navegación y el aviso en `index.html`, `catalogo.html`, `carrito.html` y `checkout.html`: enlaces Marca, Catálogo, Carrito y Checkout; búsqueda GET a `catalogo.html` con etiqueta «Buscar prendas», campo `name="q"` y botón «Buscar»; cuenta «Mi cuenta (no disponible)» sin enlace; aviso «La búsqueda abre el catálogo de demostración; no interpreta la consulta.»
- [x] Aplicar la misma estructura y textos a los 20 archivos `productos/*.html`, usando rutas `../` a las páginas de raíz y marcando «Catálogo» como página actual.
- [x] Verificar en las 24 páginas el orden de los seis elementos, rutas válidas, un único `aria-current="page"` correcto, etiqueta accesible, foco visible, diseño adaptable y aviso de búsqueda; confirmar que no se modificó contenido fuera de la barra/aviso ni se añadieron CSS, JavaScript o dependencias.
