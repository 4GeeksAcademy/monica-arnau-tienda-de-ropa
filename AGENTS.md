# Instrucciones para agentes

## Objetivo del proyecto

Implementar un prototipo visual y navegable para una tienda online de una marca francesa de ropa, respetando los requisitos descritos en `CONTEXT.md`.

El resultado debe sentirse como una tienda editorial de moda: elegante, cuidada, fácil de recorrer y adaptable a diferentes tamaños de pantalla.

## Antes de empezar

- Revisa `README.es.md` y la estructura actual del repositorio.
- Conserva `server.py` sin cambios, salvo que exista una necesidad técnica concreta que no pueda resolverse con archivos estáticos.
- Mantén la implementación dentro de las tecnologías permitidas.
- Si una interacción necesita estado o procesamiento que no puede lograrse con HTML estático, haz explícita esa limitación en vez de presentar una acción falsa como funcional.

## Tecnologías y restricciones

- Usa HTML5 semántico y Tailwind CSS v4 a través de su CDN oficial.
- No uses React, otros frameworks, JavaScript propio ni hojas de estilos CSS adicionales.
- No añadas dependencias o herramientas de compilación sin una necesidad justificada.
- El script del CDN de Tailwind está permitido por el requisito del proyecto; no añadas scripts propios para gestionar estado o interacciones.
- Para conservar Schema.org sin lógica ejecutable, prioriza atributos de microdatos HTML (`itemscope`, `itemtype` e `itemprop`).

## Archivos y vistas

Crea estas páginas HTML estáticas en la raíz del proyecto:

- `index.html`: página de inicio.
- `catalogo.html`: catálogo.
- `producto.html`: detalle de producto.
- `carrito.html`: carrito de demostración.
- `checkout.html`: checkout en tres pasos.

Los enlaces internos deben usar rutas relativas y apuntar a páginas existentes. El servidor actual sirve `index.html` en `/` y archivos estáticos por ruta, así que no dependas de un router o backend.

### Navegación y pie de página

Repite una navbar y un footer coherentes en las cinco páginas.

La navbar debe incluir:

- Logo con enlace a `index.html`.
- Campo de búsqueda accesible; puede enviar la búsqueda mediante un formulario GET o enlazar al catálogo.
- Enlace o menú de cuenta claramente identificado.
- Enlaces principales al catálogo y al carrito.

El footer debe incluir:

- Categorías: calzado, camisas, pantalones y accesorios.
- Enlaces legales: términos y condiciones, política de privacidad y sobre la marca.
- Información de contacto.

Si esos enlaces no tienen páginas propias, no los dirijas a rutas inexistentes: usa una sección válida, un ancla existente o un destino informativo disponible.

### Inicio (`index.html`)

- Añade una sección hero para una campaña o selección especial, con imagen, título, texto y llamada a la acción.
- Incluye una sección de nuevos lanzamientos.
- Incluye una sección de más vendidos.
- Usa cards con imagen, nombre, precio y enlace al detalle del producto o catálogo.
- Añade microdatos Schema.org para la organización de la marca cuando resulte natural.

### Catálogo (`catalogo.html`)

- Incluye filtros visuales de categoría y talla antes de los productos.
- Presenta una cuadrícula de 20 productos como referencia, con diseño adaptable.
- Los filtros no deben aparentar filtrar dinámicamente si no existe implementación para ello. Puedes representarlos como controles visuales o formularios HTML sin prometer resultados que el sitio estático no pueda ofrecer.
- En escritorio, prioriza una cuadrícula de cuatro columnas; reduce columnas progresivamente en tablet y móvil.

### Producto (`producto.html`)

- Usa un diseño de dos columnas en escritorio: imagen a la izquierda e información a la derecha.
- En pantallas pequeñas, apila las columnas y conserva la prioridad visual de la imagen y los datos esenciales.
- Incluye nombre, referencia, talla, precio, cantidad y botón «Agregar al carrito».
- Añade descripción detallada, materiales y escenarios de uso.
- Incluye microdatos Schema.org de tipo `Product`, con propiedades apropiadas como nombre, imagen, descripción, referencia y oferta cuando haya datos disponibles.
- Sin JavaScript ni backend, el botón no puede actualizar un carrito persistente. En el prototipo, puede enlazar al carrito de demostración, pero el texto y el comportamiento deben dejar claro que se trata de una simulación.

### Carrito (`carrito.html`)

- Implementa una página completa, no un panel lateral.
- Muestra tres productos de ejemplo.
- Para cada producto, incluye miniatura, nombre, precio unitario, cantidad y total por producto.
- Añade un resumen con subtotal, impuestos y total.
- Incluye un botón o enlace «Comprar» que lleve a `checkout.html`.
- Indica que los datos son de demostración si es necesario para evitar confundirlos con un carrito persistente.

### Checkout (`checkout.html`)

- Presenta los tres pasos en orden y con títulos visibles:
  1. Datos personales.
  2. Dirección de entrega.
  3. Pago con tarjeta.
- Usa etiquetas `<label>` asociadas a cada campo y tipos de entrada HTML apropiados (`email`, `tel`, `text`, etc.).
- Añade atributos `required` cuando corresponda para aprovechar la validación nativa del navegador.
- No recolectes ni proceses pagos reales. El formulario es demostrativo y no debe enviar datos de tarjeta a ningún servicio.
- Sin JavaScript propio, no implementes un paso a paso dinámico. Puedes mostrar las tres secciones en una sola página y permitir navegar entre ellas con enlaces de ancla.

## HTML, accesibilidad y contenido

- Usa landmarks apropiados: `<header>`, `<nav>`, `<main>`, `<section>` y `<footer>`.
- Mantén una jerarquía de encabezados ordenada y un `<h1>` descriptivo por página.
- Usa enlaces para navegar y botones para acciones.
- Añade texto alternativo útil a las imágenes; usa `alt=""` solo para imágenes puramente decorativas.
- Asegura contraste suficiente y estados de foco visibles para navegación por teclado.
- Los controles de formulario deben tener etiquetas visibles, no depender únicamente de placeholders.
- Usa lenguaje claro en español y precios con formato coherente.
- Evita texto de relleno y enlaces sin destino válido.

## Diseño adaptable y Tailwind

- Diseña primero para pantallas pequeñas y usa breakpoints de Tailwind para ampliar el layout en tablet y escritorio.
- Revisa especialmente la navegación, los filtros, las grids, las tablas o listas del carrito y los formularios en móvil.
- Evita anchos fijos que provoquen scroll horizontal.
- Mantén consistentes el espaciado, los colores, los radios y la tipografía entre las páginas.
- No añadas CSS propio para resolver detalles que puedan expresarse con utilities de Tailwind.

## Imágenes y rendimiento

- Prefiere imágenes optimizadas y de dimensiones adecuadas.
- Evita descargar imágenes de gran tamaño para mostrarlas en miniaturas.
- Incluye `width` y `height` cuando sea posible para reducir cambios de layout.
- Usa `loading="lazy"` para imágenes fuera de la primera pantalla; no retrases innecesariamente la imagen principal del hero.
- Si se usan imágenes remotas, comprueba que sean accesibles y que sus URLs no sean enlaces temporales.
- Evita recursos y dependencias que no aporten valor al prototipo.
- Verifica la URL pública en PageSpeed Insights y busca al menos 80 puntos; registra el resultado sin afirmar que se ha medido si no se ha ejecutado la prueba.

## Flujo de Git

- No desarrolles durante periodos prolongados directamente en `main`.
- Usa ramas por vista o funcionalidad, por ejemplo:
  - `feat/home`
  - `feat/catalog`
  - `feat/product-detail`
  - `feat/cart-checkout`
- Abre al menos una PR por cada parte importante del trabajo, según las convenciones del equipo.
- Usa commits descriptivos y acotados, por ejemplo:
  - `feat: add responsive home page`
  - `feat: build product catalog`
  - `feat: add cart and checkout prototype`
  - `fix: improve mobile navigation`
- No incluyas cambios ajenos al proyecto en una rama o PR.
- No hagas commits salvo que se indique
- Cada vez que solicitemos una propuesta de commit, mantén el estándar establecido aquí

## Verificación antes de entregar

- Comprueba que `/` carga `index.html` y que las demás páginas se abren mediante sus rutas.
- Recorre los enlaces de navegación y llamadas a la acción.
- Revisa cada vista en móvil, tablet y escritorio.
- Comprueba que no haya scroll horizontal en móvil ni controles inaccesibles.
- Revisa la consola y los recursos de imagen en el navegador.
- Ejecuta PageSpeed Insights sobre la URL pública si está disponible.
- Resume qué se implementó, qué se verificó y qué limitaciones conserva el prototipo estático.
