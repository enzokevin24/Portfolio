# Guía Paso a Paso: Publicación en GitHub Pages

Esta guía resume el proceso exacto para subir el portfolio de **Enzo Eduardo Camaño** a GitHub y activarlo como sitio web público con **GitHub Pages**.

---

## 1. Crear o Verificar la Cuenta de GitHub

1. Ingresá a [https://github.com/](https://github.com/).
2. Si todavía no tenés cuenta, seleccioná **Sign up** con tu correo personal y elegí un nombre de usuario profesional (por ejemplo: `enzocamano` o `enzo-camano`).
3. Verificá tu correo electrónico antes de crear el repositorio.

---

## 2. Crear el Repositorio Público

1. En GitHub, presioná **New repository**.
2. En **Repository name**, escribí exactamente:
   ```text
   tuusuario.github.io
   ```
   *(Ejemplo: si tu usuario es `enzocamano`, el repositorio debe llamarse `enzocamano.github.io`.)*
3. Seleccioná visibilidad **Public**.
4. Creá el repositorio con **Create repository**.

---

## 3. Subir los Archivos del Proyecto

Podés subirlos desde la interfaz web de GitHub o mediante Git en la terminal:

### Opción A: Desde la web de GitHub
1. Abrí tu repositorio recién creado y tocá **Add file → Upload files**.
2. Arrastrá **el contenido interno** de la carpeta del portfolio (no la carpeta contenedora padre), asegurándote de que queden en la raíz:
   - `index.html`
   - `README.md`
   - `bitacora_ia.md`
   - carpeta `css/` con `estilos.css`
   - carpeta `js/` con `script.js`
   - carpeta `assets/` con `img/*.svg`
   - carpeta `docs/` con la documentación `.md` y `.html`
   > **Importante:** No subas archivos privados o borradores innecesarios (como el CV en PDF original si contiene teléfono/datos personales).
3. Escribí como mensaje de commit: `Primera versión 0.1 del portfolio personal`.
4. Confirmá con **Commit changes**.

### Opción B: Desde la terminal (Git)
```bash
git init
git add index.html README.md bitacora_ia.md css/ js/ assets/ docs/
git commit -m "Primera versión 0.1 del portfolio personal"
git branch -M main
git remote add origin https://github.com/tuusuario/tuusuario.github.io.git
git push -u origin main
```

---

## 4. Activar GitHub Pages

1. Entrá a la pestaña **Settings** del repositorio.
2. En el menú lateral izquierdo, hacé clic en **Pages**.
3. En **Build and deployment → Source**, elegí **Deploy from a branch**.
4. En **Branch**, seleccioná `main` y la carpeta `/(root)`.
5. Guardá con **Save** y esperá entre 1 y 3 minutos hasta que aparezca la URL pública:
   ```text
   https://tuusuario.github.io
   ```

---

## 5. Lista de Pruebas Obligatorias Post-Publicación

- [ ] Abrir la URL pública `https://tuusuario.github.io` y comprobar que carga sin error 404.
- [ ] Verificar que también funciona `https://tuusuario.github.io/docs/` para mostrar la documentación.
- [ ] Probar todos los enlaces del menú superior (`#inicio`, `#sobre-mi`, `#proyectos`, `#habilidades`, `#contacto`).
- [ ] Probar los botones de filtro (`Todos`, `Software`, `Robótica`, `Barbería & Gestión`) y abrir el modal de evidencia de cada proyecto.
- [ ] Probar el botón **Copiar correo**.
- [ ] Reducir el ancho de la ventana del navegador o abrir desde el celular para confirmar que el menú móvil y las tarjetas se adaptan sin desbordes horizontales.
- [ ] Pedir a un compañero que abra el enlace e identifique quién sos y qué tres trabajos realizaste.

---

## 6. Solución Rápida de Errores Frecuentes

| Problema | Qué revisar |
| :--- | :--- |
| **Error 404 al abrir el sitio** | Revisá que el repositorio se llame exactamente `tuusuario.github.io` y que `index.html` esté en la raíz (no dentro de una subcarpeta). |
| **No cargan los estilos CSS** | Comprobá que la carpeta se llame `css` en minúsculas y que `<link rel="stylesheet" href="css/estilos.css">` coincida letra por letra. |
| **No se ven las imágenes** | Verificá que la carpeta `assets/img/` se haya subido con los 4 archivos `.svg` en minúsculas. |
| **El menú no baja a la sección** | Confirmá que `href="#proyectos"` coincida con `id="proyectos"` en el HTML. |
| **No aparecen los últimos cambios** | Verificá que el último commit terminó de desplegarse en la pestaña *Actions* y recargá con `Ctrl + F5`. |

