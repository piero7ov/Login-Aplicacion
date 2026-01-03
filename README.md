# Login Aplicación — Ejercicio de la Milla Extra ✅

Proyecto educativo de **inicio de sesión (login)** que valida credenciales contra un archivo externo **JSON**, integrando:

- **HTML (Unidad 001):** estructura y jerarquía del documento.
- **CSS (Unidad 002):** estilos modernos (glassmorphism), animaciones y estados interactivos.
- **JavaScript (Unidad 003):** lógica de validación, lectura del JSON con `fetch()` y manipulación del DOM.

> 💡 Este repositorio está construido con una **estructura iterativa**: cada archivo numerado representa una mejora o paso del desarrollo, desde la estructura inicial hasta la validación final.

---

## 1) Introducción y contextualización

El objetivo del proyecto es simular un **login real**: el usuario escribe **email** y **contraseña**, y el sistema muestra un mensaje dinámico de **éxito** o **error** según si las credenciales existen en `usuarios.json`.

Este ejercicio se usa como práctica para comprender cómo se integran **estructura (HTML)**, **presentación (CSS)** y **comportamiento (JS)** en un mismo desarrollo web.

### Unidades implicadas
- **001 – Reconocimiento de las características de lenguajes de marcas**
- **002 – Utilización de lenguajes de marcas en entornos web**
- **003 – Manipulación de documentos web**

---

## 2) Desarrollo técnico (cómo funciona)

### Flujo general (paso a paso)
1. El usuario envía el formulario.
2. JavaScript intercepta el envío con `preventDefault()` (evita recarga).
3. Se limpian espacios con `trim()` y se valida que no falten campos.
4. Se leen los usuarios desde `usuarios.json` usando `fetch()`.
5. Se comparan credenciales recorriendo la lista (búsqueda iterativa con `.find()`):
   - Si existe coincidencia → mensaje de bienvenida ✅
   - Si no existe → mensaje de error ❌
6. Si falla la lectura del JSON (ruta o formato) se captura con `.catch()`.

### Ejemplo real de la lógica (JS)
```js
fetch("usuarios.json")
  .then(res => res.json())
  .then(datos => {
    const usuarioValido = datos.usuarios.find(u => u.email === email && u.password === password);

    if (usuarioValido) {
      mensaje.textContent = `Bienvenido, ${usuarioValido.nombre} ✅`;
      mensaje.style.color = "#aef9d8";
    } else {
      mensaje.textContent = "Email o contraseña incorrectos.";
      mensaje.style.color = "#ffb4b4";
    }
  })
  .catch(err => {
    console.error("Error al leer usuarios.json:", err);
    mensaje.textContent = "No se pudo validar el usuario. Revisa la configuración.";
    mensaje.style.color = "#ffb4b4";
  });
````

---

## 3) Aplicación práctica (cómo ejecutarlo)

⚠️ **Importante:** como se usa `fetch()` para leer `usuarios.json`, debes ejecutar el proyecto en un **servidor local** (no con doble click `file://`).

### Opción A — XAMPP

1. Copia la carpeta del proyecto en `htdocs`.
2. Enciende **Apache**.
3. Abre el archivo final desde el navegador:

   * `http://localhost/Login-Aplicacion/018-comentarios%20en%20el%20codigo.html`

### Opción B — VS Code (Live Server)

1. Instala la extensión **Live Server**
2. Clic derecho en `018-comentarios en el codigo.html` → **Open with Live Server**

### Opción C — Servidor rápido con Python

Dentro de la carpeta del proyecto:

```bash
python -m http.server 8000
```

Luego abre:

* `http://localhost:8000/018-comentarios%20en%20el%20codigo.html`

---

## 4) Estructura iterativa del repositorio 🧩

Este proyecto se desarrolló por **iteraciones**. Cada archivo numerado muestra un avance concreto:

* `001- estructura inicial.html`
* `002- formulario en main.html`
* `003-posicion del fondo.html`
* `004-centramos main.html`
* `005-damos estilo al main.html`
* `006-estilos para formulario.html`
* `007-fuentes personalizadas.html`
* `008-estlizo el boton.html`
* `009-icono de correo.html`
* `010- ahora con la contraseña.html`
* `011-mas estilo.html`
* `012-mejoras finales.html`
* `013-mensaje de validacion.html`
* `014-para lectura de email y contraseña.html`
* `015-hacemos fetch para ver usuarios.html`
* `016-validacion en consola.html`
* `017-validacion final en pantalla.html`
* ✅ **`018-comentarios en el codigo.html`** (versión final comentada)

📌 **Archivo final recomendado para evaluación/uso:** `018-comentarios en el codigo.html`

---

## 5) Datos (JSON)

El archivo `usuarios.json` contiene la lista de usuarios con:

* `nombre`
* `email`
* `password`

> 🔒 Nota educativa: las contraseñas están en texto plano porque es un ejercicio académico. En un sistema real se usaría backend + hashing.

---

Este ejercicio demuestra una integración completa de contenidos:

* **HTML (Unidad 001):** estructura semántica y bien formada.
* **CSS (Unidad 002):** diseño moderno, animaciones y usabilidad.
* **JavaScript (Unidad 003):** lógica de validación, lectura de datos y manipulación del DOM.

Además, el uso de **JSON** conecta el proyecto con escenarios reales de intercambio de datos en aplicaciones web.

---

## Autor

**Piero Olivares**
