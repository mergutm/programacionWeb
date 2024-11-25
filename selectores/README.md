# Selectores en CSS

Los selectores son la forma de apuntar y definir a qué elementos aplicar estilos en CSS.
Entender cómo funcionan los selectores permite tener un mayor control sobre el diseño de una página web.
CSS proporciona una gran flexibilidad con una amplia variedad de selectores para satisfacer las necesidades de estilo de cualquier página.
Aprender a usar estos selectores de manera eficiente es clave para crear hojas de estilo limpias, precisas y mantenibles.



# Tipos de Selectores en CSS
1. Selector de Elemento (o Tipo)

Selecciona todos los elementos HTML de un tipo específico (por ejemplo, todos los párrafos `<p>`, todos los encabezados `<h1>`, etc.).
* Sintaxis: El nombre del elemento sin ningún prefijo.



```css
/* Selecciona todos los elementos <p> y los hace de color azul */
p {
    color: blue;
}
```


### Ejemplo:


```html
<p>Este es un párrafo.</p>
<p>Este es otro párrafo.</p>
```

En este caso, ambos párrafos serán de color azul.

2. Selector de Clase

Selecciona elementos que tienen un atributo class específico.
* Sintaxis: Punto (`.`) seguido del nombre de la clase.



```css
/* Selecciona todos los elementos con la clase "resaltado" */
.resaltado {
    background-color: yellow;
    font-weight: bold;
}
```


### Ejemplo:


```html
<p class="resaltado">Este texto está resaltado.</p>
<div class="resaltado">Este div también está resaltado.</div>
```

Ambos elementos tendrán un fondo amarillo y el texto en negrita.

3. Selector de ID

Selecciona un elemento que tenga un atributo id específico (los IDs deben ser únicos en una página).
* Sintaxis: Almohadilla o numeral (#) seguido del nombre del ID.



```
/* Selecciona el elemento con el ID "encabezado-principal" */
#encabezado-principal {
    font-size: 24px;
    color: green;
}
```

### Ejemplo:


```html
<h1 id="encabezado-principal">Encabezado Principal</h1>
```

El texto del encabezado principal será verde y de 24 píxeles.

4. Selector Universal

Selecciona todos los elementos en la página.
* Sintaxis: Un asterisco (`*`).



```
/* Aplica un margen de 0 a todos los elementos */
* {
    margin: 0;
    padding: 0;
}
```

### Ejemplo:


```html
<h1>Encabezado</h1>
<p>Texto en un párrafo.</p>
```

Todos los márgenes y rellenos se eliminarán para todos los elementos.

5. Selector de Atributo

Selecciona elementos que tengan un atributo específico o un atributo con un valor específico.
* Sintaxis: Corchetes alrededor del atributo ([attribute]) o atributo con valor específico ([attribute="value"]).



```css
/* Selecciona todos los elementos con el atributo title */
[title] {
    border-bottom: 1px dotted black;
}

/* Selecciona todos los elementos <input> de tipo "text" */
input[type="text"] {
    background-color: lightgray;
}
```

### Ejemplo:


```html
<div title="Información">Este div tiene un título.</div>
<input type="text" name="nombre">
```

El `<div>` tendrá una línea inferior de puntos y el campo de texto tendrá un fondo gris claro.



# Selectores Combinados

Permiten seleccionar elementos en base a relaciones entre ellos.

1. Selectores descendentes:

Selecciona elementos que están dentro de otros.

* Sintaxis: Elemento contenedor seguido por un espacio y el elemento descendiente.




```css
/* Selecciona todos los <p> que están dentro de un <div> */
div p {
    color: red;
}
```

### Ejemplo:


```html
<div>
    <p>Párrafo dentro de un div.</p>
</div>
<p>Párrafo fuera de un div.</p>
```

Solo el primer párrafo (dentro del `<div>`) será rojo.

2. Selectores hijos directos:

Selecciona elementos que son hijos directos de otro elemento.

* Sintaxis: Elemento contenedor seguido por el símbolo `>` y el hijo.




```css
/* Selecciona solo los <p> que son hijos directos de un <div> */
div > p {
    color: blue;
}
```

Ejemplo:


```html
<div>
    <p>Párrafo hijo directo de div.</p>
    <section>
        <p>Párrafo dentro de una sección dentro de un div.</p>
    </section>
</div>
```

Solo el primer <p> dentro del <div> será azul.

## Selector de Clase Combinada

Aplica estilos solo a elementos que tienen varias clases específicas al mismo tiempo.



```css
/* Selecciona elementos que tienen ambas clases "boton" y "activo" */
.boton.activo {
    background-color: green;
}
```

Ejemplo:


```html
<button class="boton activo">Botón Activo</button>
<button class="boton">Botón Inactivo</button>
```

## Solo el botón con ambas clases tendrá un fondo verde.

Selector de Pseudo-clase

Aplica estilos a un estado específico de un elemento (por ejemplo, cuando el cursor pasa sobre él).
Ejemplos comunes: `:hover`, `:focus`, `:first-child`.



```css
/* Cambia el color del texto cuando se pasa el cursor por encima del enlace */
a:hover {
    color: orange;
}

/* Selecciona el primer párrafo dentro de su contenedor */
p:first-child {
    font-weight: bold;
}
```

Ejemplo:


```html
<a href="#">Enlace al que se puede pasar el cursor.</a>
<div>
    <p>Primer párrafo (en negrita).</p>
    <p>Segundo párrafo.</p>
</div>
```

El primer párrafo será negrita, y el enlace cambiará a naranja cuando el cursor esté sobre él.




