# Bitácora de Inteligencia Artificial

Registro de consultas, decisiones de diseño y verificaciones realizadas durante la construcción del portfolio personal de **Enzo Eduardo Camaño** para **Aplicaciones Informáticas II (6º E — Instituto San Agustín)**.

---

## Consulta 1 — Planificación de estructura semántica, proyectos reales y privacidad

- **Fecha:** 2026-11-13
- **Herramienta utilizada:** Asistente de IA para desarrollo web
- **Objetivo:** Definir la estructura HTML5 semántica del portfolio adaptada a mi perfil real (CV de taller mecánico, cursos de barbería, proyecto escolar EduEventos en Tkinter y autito seguidor de línea en robótica) respetando las reglas de privacidad de la materia.
- **Prompt completo:**
  > Actuá como mentor de desarrollo web para un estudiante de sexto año (6º E, Instituto San Agustín). Estoy creando mi portfolio personal en HTML, CSS y JavaScript puro para publicarlo en GitHub Pages. No tengo proyectos freelance todavía, pero hice cursos de barbería, trabajé como auxiliar en taller mecánico y participé en proyectos escolares como EduEventos (organizador de eventos escolares con Python y Tkinter) y un autito seguidor de línea en robótica. Quiero una estructura HTML5 semántica con header, nav, main, section (inicio, sobre-mi, proyectos, habilidades, contacto), article para tres proyectos y footer. Indicame también qué datos del CV conviene omitir por privacidad.
- **Parte utilizada:**
  - Se tomó la estructura semántica (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`) y los siete campos obligatorios de cada proyecto (`Problema`, `Solución`, `Participación`, `Tecnologías`, `Evidencia`, `Aprendizaje`).
  - Se incorporaron las secciones de trayectoria escolar/laboral y los tres proyectos reales con ilustraciones SVG propias en `assets/img/`.
- **Cambios realizados por mí:**
  - Reemplacé los proyectos de ejemplo genéricos del código anterior (`antiguo codigo.md`) por los trabajos reales realizados en el colegio y en barbería.
  - Omití el número de teléfono y la edad exacta que figuraban en el CV original, dejando únicamente el correo electrónico profesional, la ciudad general (Córdoba Capital) y la disponibilidad horaria.
- **¿Qué comprendí?**
  - Entendí que GitHub Pages solo sirve archivos estáticos (`HTML`, `CSS`, `JS` e imágenes), por lo que un proyecto hecho en Python/Tkinter se presenta mediante descripción estructurada y maquetas/capturas visuales, no ejecutando Python en el navegador.
  - Comprendí la importancia de mantener coincidencia exacta entre `href="#seccion"` e `id="seccion"` para que el menú interno funcione sin errores.
- **¿Qué descarté y por qué?**
  - Descarté enlazar imágenes inexistentes en formato `.png` sin crear los archivos reales (como ocurría en el borrador viejo) porque romperían las evidencias visuales al subir el sitio a GitHub Pages.

---

## Consulta 2 — Diseño rojo/blanco con degradados, animaciones de bloques y documentación

- **Fecha:** 2026-11-13
- **Herramienta utilizada:** Asistente de IA para desarrollo web
- **Objetivo:** Diseñar una hoja de estilos CSS en tonos rojo y blanco con degradados legibles, agregar animaciones de entrada y scroll en JavaScript puro (`IntersectionObserver`) y generar una carpeta `docs/` en `.md` y `.html` para presentar en clase.
- **Prompt completo:**
  > Creá un CSS moderno usando variables en `:root` con paleta roja y blanca con degradados, manteniendo alto contraste para leer bien el texto y diseño responsive para celular. Agregá en `js/script.js` animaciones suaves de entrada y aparición progresiva de bloques al hacer scroll, filtros por categoría en proyectos, un modal accesible para ver las evidencias y un botón para copiar el correo. Además, generá la documentación completa en una carpeta `docs/` en formato `.md` y `.html` para presentar fácilmente.
- **Parte utilizada:**
  - Variables CSS en `:root` (`--red-900` a `--red-50`, `--gradient-brand`, `--gradient-surface`).
  - Animaciones CSS con `@keyframes` para el Hero y `IntersectionObserver` en `js/script.js` para agregar la clase `.is-visible` a cada `.reveal-block`.
  - Soporte de accesibilidad con `prefers-reduced-motion: reduce`, menú hamburguesa móvil y modal con cierre por tecla `Escape`.
- **Cambios realizados por mí:**
  - Verifiqué que los enlaces internos de la documentación (`docs/index.html`) apunten correctamente a `../index.html` y que todas las rutas sean relativas y en minúsculas.
  - Ajusté los textos y las etiquetas de filtro (`Todos`, `Software`, `Robótica`, `Barbería & Gestión`) para que representen exactamente los tres proyectos del portfolio.
- **¿Qué comprendí?**
  - Aprendí a animar únicamente propiedades rápidas para el navegador (`transform` y `opacity`) para no trabar el desplazamiento en celular.
  - Entendí el patrón de mejora progresiva `.js-ready .reveal-block`: el texto solo se oculta antes de aparecer si JavaScript cargó bien; si falla, el contenido sigue visible.
- **¿Qué descarté y por qué?**
  - Descarté instalar librerías externas pesadas o frameworks (como React o GSAP por CDN complejos) porque la materia pide HTML, CSS y JavaScript puro comprensible, liviano y fácil de explicar en clase.

