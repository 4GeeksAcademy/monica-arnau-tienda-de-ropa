# Sistema de diseño — tienda de moda francesa

## 1. Dirección de estilo

La tienda debe transmitir una marca francesa contemporánea y de calidad: editorial, sobria y cálida. La ropa y las fotografías son protagonistas; los elementos de interfaz deben acompañar sin competir.

### Principios visuales

- **Editorial:** titulares con presencia, imágenes amplias y composiciones con aire.
- **Sobriedad:** pocos colores, adornos discretos y jerarquía visual clara.
- **Cercanía:** textos directos en español y navegación fácil de entender.
- **Funcionalidad:** llamadas a la acción visibles y controles reconocibles.
- **Coherencia:** los mismos patrones de navegación, botones, espaciado y tarjetas en todas las páginas.

Evitar clichés visuales asociados a Francia, como acumular iconos de la Torre Eiffel, banderas o adornos temáticos. La identidad debe apoyarse en la fotografía, la tipografía y la composición.

## 2. Colores

Usar una paleta cálida y neutra, aplicada de forma consistente con clases utility de Tailwind.

| Uso | Color orientativo | Referencia Tailwind |
|---|---|---|
| Fondo principal | Marfil suave `#F8F7F4` | `bg-stone-50` |
| Superficies y tarjetas | Blanco cálido `#FFFFFF` | `bg-white` |
| Texto principal | Carbón `#242321` | `text-stone-900` |
| Texto secundario | Gris cálido `#716F6B` | `text-stone-600` |
| Bordes y separadores | Beige grisáceo `#E7E3DC` | `border-stone-200` |
| Acento de marca | Borgoña apagado `#713E43` | `text-[#713E43]`, `bg-[#713E43]` |
| Acento alternativo | Verde oliva discreto `#656B55` | `text-[#656B55]` |

### Reglas de uso

- Mantener el fondo general claro; reservar los fondos oscuros para llamadas de atención puntuales.
- Usar el color de acento principalmente en botones principales, enlaces destacados, etiquetas de campaña y estados activos.
- Mantener buen contraste entre texto y fondo, especialmente en botones y texto pequeño.
- No comunicar disponibilidad, errores o selección únicamente mediante color; acompañar el color con texto o indicadores visibles.
- Evitar gradientes y colores saturados que desvíen la atención del producto.

## 3. Tipografía

Usar una combinación tipográfica editorial con las familias de sistema disponibles, sin añadir dependencias externas:

- **Titulares:** serif del sistema, por ejemplo `font-serif`, para aportar carácter editorial.
- **Texto, navegación, controles y precios:** sans serif del sistema, por ejemplo `font-sans`, para favorecer la lectura.

### Jerarquía recomendada

- **H1:** grande, claro y con pocas palabras; `text-3xl` en móvil y hasta `text-5xl` en escritorio.
- **H2:** encabezados de sección; `text-2xl` en móvil y `text-3xl` en escritorio.
- **H3:** nombre de producto o subtítulo de bloque; `text-lg` o `text-xl`.
- **Cuerpo:** `text-sm` o `text-base`, con interlineado cómodo.
- **Metadatos:** `text-xs` o `text-sm`, en color secundario y sin bajar el contraste en exceso.

Usar mayúsculas con moderación, principalmente para etiquetas pequeñas. Mantener los precios y referencias fáciles de localizar y leer.

## 4. Layout y composición

### Reglas generales

- Diseñar primero para móvil y ampliar con breakpoints de Tailwind.
- Centrar el contenido en un contenedor fluido con ancho máximo; evitar anchos fijos que produzcan scroll horizontal.
- Usar espacio en blanco generoso y espaciado consistente entre secciones.
- Preferir layouts en una columna en pantallas pequeñas y dividirlos en columnas a medida que haya espacio.
- Mantener las imágenes con proporciones coherentes dentro de cada tipo de componente.

### Breakpoints orientativos

- **Móvil:** una columna para contenido principal y tarjetas; filtros apilados.
- **Tablet:** dos columnas cuando el contenido lo permita; catálogo de dos o tres columnas.
- **Escritorio:** catálogo de cuatro columnas; producto en dos columnas; checkout y carrito con contenido y resumen en columnas cuando resulte cómodo.

Usar los breakpoints estándar de Tailwind, como `sm:`, `md:`, `lg:` y `xl:`. El diseño debe seguir siendo utilizable sin depender de un ancho de pantalla específico.

### Composición por vista

- **Inicio:** hero editorial con imagen protagonista y llamada a la acción; después, bloques separados de nuevos lanzamientos y más vendidos.
- **Catálogo:** título y filtros antes de la cuadrícula; cuatro columnas en escritorio y menos columnas en pantallas estrechas.
- **Producto:** imagen a la izquierda e información a la derecha en escritorio; bloques apilados en móvil.
- **Carrito:** lista de productos y resumen de importes claramente separados; en móvil, apilar el resumen debajo de la lista.
- **Checkout:** tres secciones numeradas y reconocibles; en móvil, formulario en una sola columna.

## 5. Componentes visuales

### Navbar

- Fondo claro y separación sutil respecto al contenido.
- Logo tipográfico visible con enlace al inicio.
- Búsqueda, cuenta, catálogo y carrito con nombres o etiquetas comprensibles.
- En pantallas pequeñas, permitir que los elementos se reorganicen o apilen sin desbordarse.
- Mantener la misma estructura visual en todas las páginas.

### Hero

- Fotografía de campaña amplia y de buena calidad, con texto legible sobre fondo apropiado.
- Título breve, descripción opcional y una acción principal.
- En móvil, apilar texto e imagen si la composición superpuesta dificulta la lectura.
- No retrasar la carga de la imagen principal por lazy loading.

### Tarjetas de producto

- Imagen como elemento principal, con proporción uniforme en una misma colección.
- Mostrar nombre, precio y, cuando corresponda, una etiqueta breve como “Nuevo”.
- Toda la tarjeta o un enlace claramente visible debe llevar a la vista de producto.
- Usar bordes discretos o ausencia de borde; evitar sombras pesadas.
- Las imágenes no visibles inicialmente pueden usar `loading="lazy"`.

### Filtros

- Colocarlos antes del catálogo, con etiquetas visibles para categoría y talla.
- En móvil, distribuirlos en una columna o permitir que ocupen el ancho disponible.
- Usar controles nativos accesibles y estados de foco visibles.
- Si el prototipo no filtra realmente, no presentar los controles como filtros dinámicos funcionales.

### Botones y enlaces

- **Primario:** fondo de acento, texto claro, texto de acción explícito y área de interacción cómoda.
- **Secundario:** fondo claro o transparente, borde discreto y texto oscuro.
- **Enlaces:** subrayado o tratamiento visual que permita reconocerlos como enlaces.
- Incluir estados de foco visibles y mantener contraste suficiente.
- Usar `<a>` para navegación y `<button>` para acciones.

### Formularios

- Etiquetas visibles asociadas a sus campos.
- Campos con bordes neutros, espaciado suficiente y foco perceptible.
- Usar tipos HTML adecuados y validación nativa cuando corresponda.
- No depender solo del placeholder para explicar un campo.

### Carrito y checkout

- Priorizar lectura rápida de producto, cantidades e importes.
- Mostrar subtotal, impuestos y total en un bloque visual diferenciado.
- Usar números alineados y etiquetas explícitas para cada importe.
- En checkout, identificar los pasos con número y título; la secuencia debe entenderse sin depender solo del color.

### Footer

- Fondo neutro o ligeramente contrastado con el contenido principal.
- Agrupar claramente categorías, enlaces legales y contacto.
- Mantener los mismos enlaces y orden en todas las vistas.
- En móvil, apilar las secciones y evitar columnas estrechas.

## 6. Consistencia

- Reutilizar la misma navbar y el mismo footer en las cinco páginas.
- Mantener una escala común de espaciado, tamaños de texto, colores, bordes y radios.
- Repetir el mismo patrón de tarjeta de producto en inicio y catálogo.
- Mantener consistentes el formato de precios, nombres de categorías y estilo de etiquetas.
- Usar español claro en navegación, acciones, formularios y mensajes.
- Asegurar que los enlaces apunten a páginas o secciones existentes.
- No introducir patrones visuales nuevos en una página si contradicen los componentes compartidos.

## 7. Implementación y límites

- Aplicar el diseño con utilities de Tailwind CSS v4 cargado mediante el CDN previsto por el proyecto.
- No crear hojas CSS adicionales ni añadir JavaScript propio.
- No añadir librerías de iconos o fuentes salvo que se autoricen expresamente.
- Preferir texto o símbolos sencillos y accesibles cuando un icono no sea imprescindible.
- El carrito y el checkout son demostrativos: el estilo no debe sugerir que hay persistencia o procesamiento real de pagos.
- Mantener las imágenes optimizadas, con dimensiones apropiadas y texto alternativo descriptivo.
