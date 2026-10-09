# Guion de explicación: HTML, Bootstrap y CSS

**Proyecto:** David Chu's China Bistro  
**Duración estimada:** 5–6 minutos  
**Archivos:** `index.html`, `css/styles.css` y `css/bootstrap.min.css`

> Nota para quien presenta: el HTML enlaza `bootstrap.min.css`, que está comprimido y no es práctico para leer. Para mostrar reglas concretas de Bootstrap, abre `css/bootstrap.css`, la versión legible equivalente. El CSS propio de esta clase está en `css/styles.css` y aquí define principalmente el encabezado.

## 1. Introducción — 0:00

**En pantalla:** Mostrar la página en el navegador y luego abrir `index.html` en VS Code.

**Narración:**

> En esta clase vamos a entender cómo se construye el encabezado de David Chu's China Bistro. Veremos tres capas: HTML para la estructura, Bootstrap para componentes y diseño adaptable, y `styles.css` para la apariencia particular de este restaurante.

## 2. Documento y hojas de estilo — 0:25

**En pantalla:** Resaltar `doctype`, `html`, el contenido de `head` y los tres enlaces `link` a CSS y fuentes.

**Narración:**

> `<!doctype html>` declara un documento HTML moderno. El atributo `lang="en"` indica que el contenido de la página está en inglés. En `head`, `charset` define la codificación y `viewport` permite que el ancho de la página se adapte a la pantalla.

> Aquí se cargan primero las reglas de Bootstrap y después `styles.css`. Ese orden importa: Bootstrap aporta los estilos generales y el CSS del proyecto puede personalizarlos o sobrescribirlos. Las dos fuentes externas son Oxygen y Lora.

## 3. Qué aporta Bootstrap — 1:05

**En pantalla:** Abrir `css/bootstrap.css` y buscar `.container`, `.navbar`, `.navbar-toggle`, `.collapse`, `.hidden-xs`, `.visible-md` y `.glyphicon`.

**Narración:**

> Bootstrap es un conjunto de estilos y componentes ya preparados. En vez de escribir desde cero toda la barra, el contenedor y las reglas para cada tamaño de pantalla, aplicamos clases como `container`, `navbar` y `navbar-default` directamente en el HTML.

> Las clases de visibilidad, como `visible-md`, `visible-lg` y `hidden-xs`, cambian qué elementos se muestran según el ancho del dispositivo. Las clases `glyphicon` muestran iconos usando la fuente de iconos incluida con Bootstrap.

> El enlace carga `bootstrap.min.css`, que contiene esencialmente las mismas reglas que `bootstrap.css`, pero comprimidas para producción. Para aprender o buscar selectores resulta más cómodo inspeccionar la versión sin minificar.

## 4. Estructura de marca y encabezado — 1:50

**En pantalla:** Volver a `index.html`, enfocar `<header>`, `#header-nav`, `.container`, `.navbar-header` y `.navbar-brand`.

**Narración:**

> El contenido visible empieza en `header`. La barra usa `navbar navbar-default`; el `div` con `container` centra el contenido y limita su ancho de acuerdo con los puntos de quiebre de Bootstrap.

> `navbar-header` agrupa la marca y el botón para móviles. El enlace con `visible-md visible-lg` reserva el logo para pantallas medianas y grandes. El nombre va dentro de un `h1`, y la imagen de la estrella incluye texto alternativo para describir la certificación.

## 5. Botón colapsable — 2:30

**En pantalla:** Resaltar el botón `navbar-toggle`, sus atributos `data-*`, `aria-expanded` y los tres `span.icon-bar`.

**Narración:**

> En una pantalla pequeña, el botón sirve para desplegar o cerrar la navegación. `data-toggle="collapse"` le indica al JavaScript de Bootstrap que use el comportamiento colapsable, y `data-target="#collapsable-nav"` identifica el elemento que debe abrirse.

> Las tres barras se dibujan con `span` y la clase `icon-bar`. `aria-expanded` comunica el estado del menú a tecnologías de asistencia, y `sr-only` aporta una etiqueta accesible que no se muestra visualmente.

## 6. Navegación — 3:05

**En pantalla:** Recorrer `#collapsable-nav`, `#nav-list`, los elementos `li` y el teléfono.

**Narración:**

> El panel que se pliega tiene el identificador `collapsable-nav`, el mismo que señala el botón. Dentro hay una lista alineada a la derecha con las clases de Bootstrap `nav`, `navbar-nav` y `navbar-right`.

> Cada opción combina un icono con texto. La clase `hidden-xs` oculta el salto de línea en pantallas extra pequeñas para ahorrar espacio. El número telefónico usa un enlace `tel:`, que puede iniciar una llamada desde un dispositivo compatible. Su bloque también se oculta en pantallas extra pequeñas.

> “About” y “Awards” todavía apuntan a `#`, así que son enlaces de ejemplo. “Menu” sí apunta a `menu-categories.html`.

## 7. CSS propio: colores, marca y tipografía — 3:50

**En pantalla:** Abrir `css/styles.css`, recorrer `body`, `#header-nav`, `#logo-img` y `.navbar-brand`.

**Narración:**

> Ahora vemos los estilos propios del sitio. El selector `body` establece el tamaño base del texto, el color blanco, el fondo burdeos y la fuente Oxygen. Como ese fondo se aplica a todo el cuerpo, también queda visible en el área debajo del encabezado.

> `#header-nav` selecciona la barra por su identificador: la vuelve amarilla y quita el borde y las esquinas redondeadas que traía Bootstrap. Esto muestra cómo el CSS del proyecto ajusta el componente genérico.

> `#logo-img` dibuja el logo como fondo, evita que se repita y reserva un espacio de 150 por 150 píxeles. Los márgenes controlan la separación respecto a los elementos vecinos.

> `.navbar-brand` baja el bloque de marca con `padding-top`. El selector más específico `.navbar-brand h1` personaliza el nombre: usa Lora, cambia el color, tamaño, mayúsculas, grosor, sombra y márgenes. Las reglas de `:hover` y `:focus` quitan el subrayado al interactuar con el enlace. El párrafo de certificación recibe su propio tamaño y espaciado.

## 8. CSS propio: enlaces, teléfono y botón — 4:45

**En pantalla:** Resaltar `#nav-list`, `#phone` y las reglas de `.navbar-toggle` y `.icon-bar`.

**Narración:**

> Las reglas de `#nav-list` ajustan el margen de la lista, el color y la alineación de sus enlaces, el fondo al pasar el cursor y el tamaño de los iconos. Así el menú hereda la estructura de Bootstrap pero adopta los colores y proporciones del restaurante.

> `#phone` y sus selectores internos alinean a la derecha el número y el texto de entrega, con pequeños ajustes de margen y relleno. Al final, el botón y sus barras reciben un borde burdeos, y el botón se recoloca con `margin-top` y `clear`.

> Observa que `#nav-list` y `#phone` comienzan con `#`: son selectores de identificador. `.navbar-brand` comienza con punto: selecciona una clase. Los selectores pueden combinarse, por ejemplo `#phone div`, para apuntar a un `div` que está dentro del elemento con id `phone`.

## 9. JavaScript y resumen — 5:30

**En pantalla:** Mostrar los `<script>` al final de `body`; luego comparar la página en anchura amplia y estrecha.

**Narración:**

> Al final se cargan jQuery, Bootstrap y el JavaScript propio. jQuery debe estar antes que Bootstrap porque los componentes JavaScript de esta versión dependen de él. Ese código permite que el botón active el comportamiento de colapsar el menú.

> En resumen: Bootstrap da una base reutilizable y adaptable; `styles.css` define la identidad visual; y el HTML conecta estructura, clases y contenido. Puedes cambiar el ancho del navegador para observar las clases responsivas y editar un color en `styles.css` para ver cómo una regla propia modifica el componente.
