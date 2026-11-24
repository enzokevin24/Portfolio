# Bitácora Ampliada y Guía de Autoría para Exposición Oral

Este documento complementa a [`../bitacora_ia.md`](../bitacora_ia.md) con preguntas y respuestas rápidas para cumplir la **Regla de Autoría** de la cátedra:

> *"Ningún fragmento se considera terminado si no podés explicar qué hace, indicar dónde se encuentra y realizar una modificación sencilla."*

---

## 1. Preguntas Frecuentes en la Corrección

### ¿Por qué usaste etiquetas como `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` y `<footer>` en lugar de solo `<div>`?
Porque son **etiquetas semánticas de HTML5**. Le indican al navegador, a los buscadores y a los lectores de pantalla qué función cumple cada bloque (`<article>` encierra cada proyecto independiente, `<nav>` agrupa los enlaces de navegación). Se encuentran en [`../index.html`](../index.html).

### ¿Cómo funciona el menú de navegación interna?
Cada enlace del `<nav>` apunta a un identificador con numeral (`href="#proyectos"`), y la sección destino tiene el mismo atributo `id` (`id="proyectos"`). Además, en [`../css/estilos.css`](../css/estilos.css) se definió `scroll-behavior: smooth` y `scroll-padding-top: 5.5rem` para que el desplazamiento sea suave y el encabezado fijo no tape el título de la sección.

### ¿Cómo se hicieron los colores rojos y blancos con degradados?
En la parte superior de [`../css/estilos.css`](../css/estilos.css), dentro de `:root`, se declararon variables CSS (`--red-900`, `--red-700`, `--red-600`, `--gradient-brand`, `--gradient-surface`). Si quiero cambiar un tono de rojo en todo el sitio, alcanza con editar una sola variable en `:root`.

### ¿Cómo funcionan las animaciones de entrada y de los bloques?
- **Entrada inicial (Hero):** Se hace solo con CSS usando `@keyframes heroFadeUp` y `@keyframes heroCardIn` aplicados a las clases `.anim-hero` y `.anim-hero-card`.
- **Bloques al hacer scroll:** Se usa `IntersectionObserver` en [`../js/script.js`](../js/script.js). Cuando un elemento `.reveal-block` entra al menos un 12 % en la pantalla (`threshold: 0.12`), JavaScript le agrega la clase `.is-visible`, activando la transición CSS de `opacity` y `transform: translate3d(...)`.

### ¿Qué pasa si alguien entra desde un dispositivo que prefiere menos animaciones?
En [`../css/estilos.css`](../css/estilos.css) se incluyó la media query `@media (prefers-reduced-motion: reduce)`, que desactiva animaciones y transiciones largas automáticamente para mejorar la accesibilidad.

### ¿Cómo se ejecuta EduEventos (Python Tkinter) en GitHub Pages?
No se ejecuta Python en GitHub Pages porque GitHub Pages aloja únicamente sitios estáticos (`HTML`, `CSS`, `JS` e imágenes). Por eso se muestra mediante una ficha técnica estructurada y una maqueta visual SVG (`assets/img/proyecto-edueventos.svg`) dentro de un modal interactivo.

---

## 2. Modificaciones Sencillas que Podés Hacer en Vivo

1. **Cambiar un color del degradado:** Editar `--red-700` o `--gradient-brand` en `css/estilos.css` (líneas 7 a 28).
2. **Actualizar tu enlace de GitHub:** Agregar un bloque de tarjeta de GitHub en la sección `#contacto` de `index.html` apenas crees tu repositorio `usuario.github.io`.
3. **Agregar un cuarto proyecto:** Duplicar un bloque `<article class="project-card reveal-block">` en `index.html` y asignar `data-category` acorde.

