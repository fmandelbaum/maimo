---
marp: true
---

# CSS

* CSS (https://www.w3.org/Style/CSS/) es una especificación modular (CSS Color, Selectors, Media Queries, CSS Paged Media, CSS Transitions, CSS Animations, CSS 2D/3D Transformations, CSS Flexible Box Layout, CSS Grid Layout, CSS Regions...)
* No todos los módulos deben estar al mismo nivel (versión). Ejemplo: CSS puede incorporar módulos de nivel 2, 3 y 4
* No todos los navegadores implementan todos los módulos (https://caniuse.com)
* Permite mejorar progresivamente la experiencia del usuario

---

# Bordes Redondeados

```css
.bordes-redondos {
  border-radius: 1rem;
}
```

```css
.redondo-arriba {
  border-top-left-radius: 1rem;
  border-top-right-radius: 1rem;
}
```

Permite especificar "redondez" para los bordes de las cajas. Cada una de las cuatro esquinas se puede especificar de manera independiente.

---

# Color RGBA

```css
p {
  background-color: rgba(255, 0, 0, 0.5);
}

span {
  color: rgba(128, 128, 128, 0.7);
}
```

Permite especificar la opacidad (o transparencia) del color (canal Alpha): `rgba(Rojo, Verde, Azul, Alpha);`

---

# Gradiente Lineal

* `linear-gradient(to BORDE, COLOR1, COLOR2, ..., COLORn)`
* `linear-gradient(ÁNGULO, COLOR1, COLOR2, ..., COLORn)`

Ejemplos:

```css
.lineal {
  background: linear-gradient(to right, #000, #777, #fff);
}

.angular {
  background: linear-gradient(45deg, #000, #fff);
}
```

---

# Gradiente Circular

* `radial-gradient(COLOR1, COLOR2, ..., COLORn)`
* `radial-gradient(ellipse closest-side, COLOR1, COLOR2, ..., COLORn)`

Ejemplos:

```css
.circular {
  background: radial-gradient(red, #0f0, rgba(0, 0, 255, 1));
}

.eliptico {
  background: radial-gradient(ellipse closest-side #000, #fff);
}
```

---

# Múltiples Fondos

* Permite usar más de un fondo
* Se declaran en el orden de aparición
* `background: FONDO1, FONDO2, ..., FONDOn`

Ejemplo:

```css
div.multifondo {
  background: url(img/fondo.png),
              linear-gradient(to right #000 #fff),
              url(img/fondo2.png);
  background-repeat: no-repeat no-repeat repeat;
  background-position: bottom-right, left, right;
}
```

---

# WebFonts

* Permite usar tipografías que quien visita el sitio no tiene instaladas en su dispositivo
* Google Fonts (https://fonts.google.com/)
* Adobe Fonts (https://fonts.adobe.com/)
* Font Awesome [iconos] (https://fontawesome.com/)

```css
@font-face {
  font-family: MiTipografia;
  src: URL;
}

.tipo-especial {
  font-family: MiTipografia, sans-serif;
}
```

---

# Sombreados

* Se pueden definir uno o más (separados por coma) efectos de sombra para una caja o para el texto
* Si la caja tiene bordes redondeados, la sombra también

Ejemplos:

```css
.caja-sombra-roja {
  box-shadow: 0.25rem 0.25rem 0.5rem #f00;
}

.texto-sombra-azul {
  text-shadow: 1px 1px 2px blue;
}
```

---

# Transiciones

* Permiten "suavizar la transición" de propiedades CSS, por ejemplo: cuando se hace hover sobre un botón
* `transition: PROPIEDAD TIEMPO FUNCIÓN`

Ejemplo:

```css
a {
  background: #9c3;
}

a:hover {
  background: #690;
  transition: background 0.3s ease;
}
```

---

# Dark Mode

* Con un media query se puede detectar la preferencia del usuario para el "modo oscuro" y especificar CSS diferentes para que nuestro sitio o app soporte dicho modo:

```css
@media (prefers-color-scheme: dark) {
  body {
    color: #fff;
    background: #333;
  }
}

@media (prefers-color-scheme: light) {
  body {
    color: #333;
    background: #fff;
  }
}
```
