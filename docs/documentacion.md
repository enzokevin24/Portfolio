# Documentación Técnica del Portfolio — Enzo Eduardo Camaño

**Materia:** Aplicaciones Informáticas II — 6º E  
**Institución:** Instituto Privado Mixto San Agustín (Córdoba Capital)  
**Versión:** 0.1 (Sitio estático para GitHub Pages)

---

## 1. Propósito del Proyecto

Este portfolio web presenta de forma ordenada el perfil académico, laboral y práctico de **Enzo Eduardo Camaño**. Fue construido con **HTML5 semántico**, **CSS3 puro** y **JavaScript nativo**, sin frameworks ni servidores externos, para funcionar directamente en **GitHub Pages**.

### ¿Por qué se eligió esta estructura?
- Responde punto por punto a la guía de clase: encabezado con navegación interna, presentación profesional, sección *Sobre mí*, sección *Proyectos* con tres trabajos reales, sección *Habilidades*, sección *Contacto* segura y pie de página.
- Incluye el detalle completo de los **tres trabajos representativos**:
  1. **EduEventos** (software escolar en Python y Tkinter).
  2. **Autito Seguidor de Línea** (robótica educativa con sensores IR).
  3. **Formación en Barbería y Organización de Turnos** (oficio práctico y gestión de tiempos).

---

## 2. Arquitectura de Archivos y Rutas Relativas

```text
ENZO/
├── index.html                   # Documento principal (raíz obligatoria para GitHub Pages)
├── README.md                    # Portada técnica del repositorio en GitHub
├── bitacora_ia.md               # Bitácora obligatoria de consultas con IA
├── css/
│   └── estilos.css              # Variables de color, tipografía, layout, hover y animaciones
├── js/
│   └── script.js                # Scroll reveal, barra de progreso, filtros, modal y menú móvil
├── assets/
│   └── img/
│       ├── enzo-perfil.jpg          # Foto de perfil recortada de Enzo
│       ├── proyecto-edueventos.svg  # Maqueta visual de EduEventos (Tkinter)
│       ├── proyecto-robotica.svg    # Esquema del autito seguidor de línea
│       └── proyecto-barberia.svg    # Ficha visual de barbería y gestión de turnos
└── docs/
    ├── index.html               # Versión HTML interactiva de esta documentación para exponer
    ├── docs.css                 # Estilos dedicados de la documentación web
    ├── documentacion.md         # Documentación técnica completa en Markdown
    ├── guia-github-pages.md     # Guía paso a paso para publicar en GitHub Pages
    └── bitacora-ia.md           # Guía de autoría y preguntas frecuentes de defensa oral
```

> **Nota sobre rutas relativas:** Todos los enlaces usan minúsculas, guiones medios y rutas relativas (`css/estilos.css`, `js/script.js`, `assets/img/...`) para evitar errores 404 en servidores Linux como GitHub Pages, que distinguen entre mayúsculas y minúsculas.

---

## 3. Sistema Visual: Paleta Roja y Blanca con Degradados

La identidad cromática combina **blanco limpio** con **tonos rojos carmesí y escarlata** y degradados suaves para lograr energía visual sin perder legibilidad:

| Token CSS | Valor | Función |
| :--- | :--- | :--- |
| `--red-900` | `#7f1d1d` | Títulos destacados y extremo oscuro del degradado |
| `--red-700` | `#b91c1c` | Acento principal, botones e íconos |
| `--red-600` | `#dc2626` | Foco de teclado, bordes activos y extremo claro del degradado |
| `--red-50` | `#fef2f2` | Superficies suaves, chips destacados y fondos tintados |
| `--bg-background` | `#ffffff` | Fondo general de lectura |
| `--text-foreground` | `#18181b` | Texto principal de alto contraste sobre blanco |
| `--gradient-brand` | `linear-gradient(135deg, #7f1d1d 0%, #b91c1c 52%, #dc2626 100%)` | Botones primarios, banner de contacto, badges y barra de progreso |
| `--gradient-surface` | `linear-gradient(180deg, #ffffff 0%, #fff4f4 100%)` | Fondo de la presentación (Hero) y secciones alternadas |

---

## 4. Explicación del Código (Para Defender en Clase)

### A. HTML5 Semántico (`index.html`)
- `<header>` y `<nav>`: Contienen la marca `EC` y los enlaces internos (`href="#inicio"`, `href="#sobre-mi"`, `href="#proyectos"`, `href="#habilidades"`, `href="#contacto"`). Cada `#id` coincide exactamente con el `id` de su `<section>`.
- `<main>`: Agrupa las 5 secciones principales del sitio.
- `<article class="project-card">`: Cada tarjeta de proyecto utiliza `<dl>` (lista de definición con `<dt>` y `<dd>`) para mostrar ordenadamente **Problema, Solución, Participación, Tecnologías, Evidencia y Aprendizaje**.
- `<footer>`: Cierre institucional con el año (`2026`), nombre del autor y enlace directo para volver arriba o abrir la documentación.

### B. CSS3 y Animaciones de Rendimiento (`css/estilos.css`)
- **Box Model y Layout:** Se usa `box-sizing: border-box`, **CSS Grid** (`hero-grid`, `about-grid`, `projects-grid`, `skills-grid`) y **Flexbox** (`header-inner`, `filter-bar`, `tag-list`) con `@media (max-width: 960px)` y `@media (max-width: 720px)` para adaptarse a tablets y celulares.
- **Animaciones de entrada (Hero):** La regla `@keyframes heroFadeUp` y `@keyframes heroCardIn` animan únicamente `opacity` y `transform: translate3d(...)` con retardos escalonados (`--hero-delay`) para que el título, el texto, los botones y la tarjeta `EC` entren con fluidez al abrir la página.
- **Animación de bloques al hacer scroll:** La clase `.js-ready .reveal-block` arranca oculta y desplazada `28px` hacia abajo; cuando recibe `.is-visible` desde JavaScript, realiza una transición suave hacia su posición final.
- **Accesibilidad:** Incluye enlace de salto (`.skip-link`), anillos de foco `:focus-visible` y `@media (prefers-reduced-motion: reduce)` para desactivar animaciones si el usuario así lo configura en su sistema.

### C. JavaScript Nativo (`js/script.js`)
1. **Mejora progresiva (`js-ready`):** Se agrega al `<html>` apenas carga el script. Si un navegador tuviera JS desactivado, ningún bloque queda invisible.
2. **Barra de progreso (`updateScrollUI`):** Calcula el porcentaje scrolleado y actualiza `transform: scaleX(...)` usando `requestAnimationFrame` para no sobrecargar el navegador.
3. **`IntersectionObserver` para bloques:** Observa cada `.reveal-block` y le suma `.is-visible` cuando aparece en pantalla (luego deja de observarlo con `unobserve`).
4. **`IntersectionObserver` para navegación activa:** Detecta qué sección está visible en pantalla y resalta automáticamente el enlace correspondiente del menú.
5. **Filtros de proyectos:** Lee `data-filter` del botón presionado y compara con `data-category` de cada tarjeta.
6. **Modal de evidencia visual:** Abre una ventana emergente accesible (`role="dialog"`, cierre con botón `✕`, clic afuera o tecla `Escape`) mostrando la imagen SVG y descripción ampliada.
7. **Copiado de correo y Toast:** Copia `enzocamano45@gmail.com` al portapapeles con `navigator.clipboard.writeText()` y muestra un aviso temporal (`#toast`).

---

## 5. Revisión de Privacidad y Seguridad

En cumplimiento de las pautas de la materia:
- **No se publica** el número de teléfono del CV.
- **No se publica** el domicilio particular ni datos familiares.
- **No se publica** la edad exacta ni documento.
- **Sí se publica** únicamente correo electrónico de contacto, ciudad general (`Córdoba Capital, Argentina`) y disponibilidad horaria (`Tardes y fines de semana`).

