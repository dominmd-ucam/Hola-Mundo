## **Proceso de Desarrollo del Prompt y Validación de Accesibilidad / Process of Prompt Development and Accessibility Validation**

### **En Español:**

#### **1. Desarrollo del Prompt: 📝**

El **prompt** fue creado para ayudar a un asistente de programación, como **GitHub Copilot** o un asistente de IA similar, a **modificar código HTML** con el objetivo de mejorar la accesibilidad, cumpliendo con los estándares establecidos por **WCAG 2.2** (Web Content Accessibility Guidelines).  

El desarrollo del **prompt** sigue estos pasos:  
1. **Semántica y estructura 🏗️**: Se instruyó al asistente para que mejorara la estructura del HTML utilizando las etiquetas adecuadas de HTML5 (`<header>`, `<main>`, `<section>`, `<footer>`) y asegurándose de que los encabezados estuvieran correctamente estructurados (`<h1>`, `<h2>`, etc.).  
2. **Atributos ARIA 🌐**: El asistente fue guiado para agregar **atributos ARIA** a los elementos interactivos (botones, formularios, enlaces, etc.), como `aria-label`, `role`, y `aria-live`, para mejorar la accesibilidad.  
3. **Imágenes y contenido visual 🖼️**: Se pidió añadir descripciones claras en los atributos `alt` para las imágenes y asegurarse de que los elementos decorativos tuvieran el atributo `aria-hidden="true"`.  
4. **Contraste y navegación 🎨**: Se establecieron las pautas para asegurarse de que el **contraste de color** fuera adecuado y que todos los elementos fueran accesibles por teclado.  
5. **Navegación por teclado ⌨️**: Se instruyó al asistente a verificar que todos los elementos interactivos fueran accesibles con la tecla `Tab` y que tuvieran indicaciones visibles de enfoque.

#### **2. Pasos Seguidos para Validar la Accesibilidad ✅:**

El proceso de validación de la accesibilidad se llevó a cabo con las siguientes herramientas:  
1. **WAVE 🌊**: Se utilizó la herramienta **WAVE** para identificar errores y advertencias en la accesibilidad.  
2. **Lighthouse 🔦**: La herramienta **Lighthouse** de Chrome fue usada para generar un informe de accesibilidad y realizar una auditoría.  
3. **axe DevTools 🛠️**: Se utilizó la extensión **axe DevTools** en Chrome para realizar pruebas automáticas de accesibilidad.  

Para cada iteración:  
- Se ajustó el código según las recomendaciones del asistente (GitHub Copilot o similar).  
- Se realizaron pruebas de validación para asegurar que el código cumpliera con los criterios **AA/AAA** de WCAG 2.2.  
- Si el código no cumplía con los estándares, se volvió a modificar el **prompt** y se repitieron las pruebas.

### **In English:**

#### **1. Prompt Development Process 📝:**

The **prompt** was created to assist a programming assistant, such as **GitHub Copilot** or a similar AI assistant, in **modifying HTML code** to improve accessibility, following the standards set by **WCAG 2.2** (Web Content Accessibility Guidelines).  

The development of the **prompt** followed these steps:  
1. **Semantic Structure 🏗️**: The assistant was instructed to improve the HTML structure by using appropriate HTML5 tags (`<header>`, `<main>`, `<section>`, `<footer>`) and ensuring the headers were correctly structured (`<h1>`, `<h2>`, etc.).  
2. **ARIA Attributes 🌐**: The assistant was guided to add **ARIA attributes** to interactive elements (buttons, forms, links, etc.), such as `aria-label`, `role`, and `aria-live`, to enhance accessibility.  
3. **Images and Visual Content 🖼️**: Instructions were given to add meaningful descriptions in the `alt` attributes for images, ensuring that decorative elements had the `aria-hidden="true"` attribute.  
4. **Contrast and Navigation 🎨**: Guidelines were set to ensure adequate **color contrast** and that all elements were accessible via keyboard.  
5. **Keyboard Navigation ⌨️**: The assistant was instructed to verify that all interactive elements were accessible with the `Tab` key and had visible focus indicators.

#### **2. Accessibility Validation Steps ✅:**

The accessibility validation process was carried out with the following tools:  
1. **WAVE 🌊**: The **WAVE** tool was used to identify errors and warnings in accessibility.  
2. **Lighthouse 🔦**: **Lighthouse** from Chrome was used to generate an accessibility report and run an audit.  
3. **axe DevTools 🛠️**: The **axe DevTools** Chrome extension was used for automated accessibility testing.  

For each iteration:  
- The code was adjusted according to the assistant's recommendations (GitHub Copilot or similar).  
- Validation tests were run to ensure the code met **AA/AAA** WCAG 2.2 criteria.  
- If the code did not meet the standards, the **prompt** was modified and the tests were repeated.

---

## **Problemas Encontrados y Soluciones Aplicadas** 🚧🔧

### **1. Uso excesivo de `<div>` en lugar de etiquetas semánticas**
**Problema:**  
El uso de `<div>` no mejora la semántica ni la accesibilidad, lo que dificulta que los usuarios de lectores de pantalla y otros dispositivos asistivos comprendan mejor la estructura de la página.

**Solución aplicada:**  
Se reemplazó el `<div>` por etiquetas semánticas apropiadas de HTML5, como `<main>`, para mejorar la estructura y accesibilidad del contenido.

**Ejemplo:**  
Antes:
```html
<div class="container">
```
Después:
```html
<main class="container">
```

---

### **2. Uso incorrecto de `<div>` para el pie de página**
**Problema:**  
El uso de `<div>` para secciones importantes como el pie de página reduce la comprensión semántica de la página, especialmente para los lectores de pantalla.

**Solución aplicada:**  
Se reemplazó el `<div class="footer">` por la etiqueta semántica `<footer>`, que es adecuada para definir el pie de página y sigue los estándares HTML5.

**Ejemplo:**  
Antes:
```html
<div class="footer">
```
Después:
```html
<footer>
```

---

### **3. Falta de navegación interna accesible**
**Problema:**  
La página no tenía una navegación interna clara, lo que dificulta la navegación para usuarios que dependen de teclado o lectores de pantalla.

**Solución aplicada:**  
Se añadió un bloque de navegación utilizando la etiqueta `<nav>`, lo que facilita la navegación rápida entre las secciones de la página, especialmente para usuarios de teclado.

**Ejemplo:**  
Antes:  
_No existía navegación interna._  
Después:
```html
<nav>
    <a href="#factura-flores">Factura Flores</a> |
    <a href="#factura-moviles">Factura Móviles</a>
</nav>
```

---

### **4. Mejora en la relación de encabezados y secciones con `aria-labelledby`**
**Problema:**  
Las secciones importantes no estaban claramente asociadas a sus encabezados, lo que puede generar confusión al navegar con lectores de pantalla.

**Solución aplicada:**  
Se implementó el atributo `aria-labelledby` para asociar de manera explícita los encabezados con sus respectivas secciones. Esto mejora la accesibilidad al leer la página con tecnologías asistivas.

**Ejemplo:**  
Antes:
```html
<section id="factura-flores">
    <h2>Factura Flores</h2>
```
Después:
```html
<section id="factura-flores" aria-labelledby="flores-title">
    <h2 id="flores-title">Factura Flores</h2>
```

---

### **5. Inclusión de `aria-label` para enlaces más claros**
**Problema:**  
Los enlaces no tenían descripciones claras, lo que dificultaba que los usuarios de lectores de pantalla comprendieran el propósito del enlace.

**Solución aplicada:**  
Se agregó el atributo `aria-label` a los enlaces, proporcionando una descripción más detallada que ayuda a mejorar la comprensión.

**Ejemplo:**  
Antes:
```html
<a href="factura.xml" target="_blank">XML de Factura Flores</a>
```
Después:
```html
<a href="factura.xml" target="_blank" aria-label="Abrir XML de Factura Flores">XML de Factura Flores</a>
```

---

### **6. Mejora en la visibilidad del enfoque con el teclado**
**Problema:**  
Los enlaces no tenían indicaciones visuales claras cuando se navegaba con el teclado, lo que dificultaba la navegación para usuarios con movilidad reducida.

**Solución aplicada:**  
Se mejoró la visibilidad del enfoque agregando reglas CSS para el pseudo-clase `:focus`, asegurando que los elementos sean claramente visibles al recibir foco.

**Ejemplo:**  
Antes:
```css
.link-list a:hover {
    color: #007bff;
}
```
Después:
```css
.link-list a:hover, .link-list a:focus {
    color: #004494;
    outline: 2px solid #0056b3;
}
```

---

### **7. Mejora del contraste de colores para cumplir con WCAG 2.2**
**Problema:**  
El contraste de colores no cumplía con los estándares de accesibilidad WCAG 2.2, lo que dificultaba la lectura para personas con discapacidad visual.

**Solución aplicada:**  
Se ajustaron los colores para asegurar que tuvieran un contraste suficiente y así cumplir con las normas de accesibilidad.

**Ejemplo:**  
Antes:
```css
.file-type {
    color: #777;
}
```
Después:
```css
.file-type {
    color: #555;
}
```

---

### **Conclusión:**
Estos cambios mejoran significativamente la **estructura semántica**, la **accesibilidad** y la **navegación** de la página, asegurando que cumpla con los estándares de **WCAG 2.2** y ofreciendo una mejor experiencia de usuario para personas con discapacidad. 💪🌍


### **Conclusión 🎯 / Conclusion 🎯**

Este proceso asegura que el código HTML se optimice para que sea **accesible** según los estándares más recientes de la **WCAG 2.2**, proporcionando una mejor experiencia de navegación para usuarios con discapacidad. / This process ensures that the HTML code is optimized to be **accessible** according to the latest **WCAG 2.2** standards, providing a better browsing experience for users with disabilities.

