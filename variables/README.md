# Qué son las variables

En JavaScript, una variable es un contenedor que se utiliza para almacenar datos o valores que pueden cambiar a lo largo de la ejecución de un programa. 
Las variables permiten manejar y manipular datos de manera eficiente en el código.


# Tipos de variables en JS

Se puede  declarar variables usando tres palabras clave principales: `var`, `let` y `const`. :

**var**: Es la forma tradicional de declarar variables en JavaScript. Las variables declaradas con var tienen un ámbito global, dependiendo de dónde se declaren.
```javascript
var nombre = "Juan";
var edad = 30;
```

**let**: Introducido en ES6 (ECMAScript 2015), let es la forma moderna de declarar variables. 
Las variables declaradas con let tienen un ámbito de bloque, lo que significa que solo están disponibles dentro del bloque {} donde se declaran.

```javascript
let nombre = "Ana";
let edad = 25;
```

**const**: Introducido en ES6, const se utiliza para declarar variables constantes, es decir, variables que no pueden ser reasignadas una vez definidas. 
Al igual que let, const tiene un ámbito de bloque.

```javascript
const pi = 3.1416;
const nombre = "Carlos";

```


# Tipos de variables / (tipos de datos)

JavaScript es un lenguaje de tipado dinámico, lo que significa que no se requiere especificar el tipo de dato al declarar una variable, 
ya que JavaScript determina el tipo automáticamente. Principales tipos de datos en JavaScript:


* **Number**: Representa números, ya sean enteros o decimales.

```javascript
let edad = 30;          // Número entero
let precio = 19.99;     // Número decimal
```

**String**: Representa texto. Se puede declarar usando comillas simples ' ', dobles " " o backticks ` `.
 


```javascript
let nombre = "Pedro";
let saludo = 'Hola, ¿cómo estás?';
let mensaje = `Hola, ${nombre}`; // Con backticks se pueden realizar operaciones o hacer referencia a variables
```

**Boolean**: Representa valores lógicos: true o false.
 

```javascript
let esMayorDeEdad = true;
let estaLloviendo = false;

```
**Null**: Representa la ausencia intencional de un valor. Es un tipo especial que indica que una variable no tiene valor.
 


```javascript
let valor = null;
```

**Undefined**: Indica que una variable ha sido declarada, pero aún no se le ha asignado ningún valor.
 


```javascript
let resultado;
console.log(resultado); // undefined
```

**Object**: Es una estructura de datos compleja que permite almacenar colecciones de datos y entidades más complejas. Los objetos se definen con llaves {}.
 


```javascript
let persona = {
    nombre: "Carlos",
    edad: 35,
    esEstudiante: false
};
```
**Array**: Un tipo especial de objeto que se utiliza para almacenar listas de elementos. Los arrays se definen con corchetes [].
 



```javascript
let frutas = ["manzana", "pera", "naranja"];

```

**Function**: Las funciones también son un tipo de dato en JavaScript. Pueden ser almacenadas en variables y utilizadas como cualquier otro tipo de dato.
 

```javascript
let saludar = function() {
    return "Hola!";
};

```

**Symbol** (ES6): Representa un valor único que no puede ser duplicado. Se utiliza principalmente para crear propiedades únicas en objetos.
   


```javascript
let simbolo = Symbol('descripcion');
```

## Ejemplos 


```javascript
// Declaración de variables con diferentes tipos de datos
let nombre = "Laura";       // String
let edad = 28;              // Number
let esCasado = false;       // Boolean
let direccion = null;       // Null
let ciudad;                 // Undefined

// Declaración de objetos y arrays
let persona = {
    nombre: "Laura",
    edad: 28
};

let colores = ["rojo", "verde", "azul"]; // Array

// Declaración de constantes
const PI = 3.14159;
const URL_BASE = "https://api.ejemplo.com";
```

# Diferencia entre var, const y let

## Ámbito (Scope):

* **var** tiene ámbito global o funcional, lo que significa que una variable definida con var estará accesible fuera de un bloque {} (por ejemplo, un **if** o **for**).
* **let** y **const** tienen ámbito de bloque, lo que significa que solo están disponibles dentro del bloque {} donde se declaran.

```javascript
if (true) {
    var x = 10;   // Ámbito global o funcional
    let y = 20;   // Ámbito de bloque
    const z = 30; // Ámbito de bloque
}

console.log(x); // 10
console.log(y); // Error: y is not defined
console.log(z); // Error: z is not defined
```


## Reasignación:

* **var** y **let** permiten la reasignación del valor.
* **const** no permite la reasignación. 


```javascript
var a = 10;
a = 15; // Esto es válido

let b = 20;
b = 25; // Esto es válido

const c = 30;
c = 35; // Error: Assignment to constant variable

```

# Declaración Múltiple

* **var** permite declarar la misma variable varias veces sin errores.
* **let** y **const** no permiten la redeclaración.

```javascript
var x = 5;
var x = 10; // Válido

let y = 15;
let y = 20; // Error: y ya fue declarado

const z = 25;
const z = 30; // Error: z  ya fue declarado
```



## En resumen

* **var**: Forma antigua, ámbito global o funcional, permite redeclaración y reasignación (se sugiere evitar su uso).
* **let**: Forma moderna, ámbito de bloque, permite reasignación, pero no redeclaración.
* **const**: Forma moderna, ámbito de bloque, no permite reasignación ni redeclaración.



# Almacenamiento de datos en el navegador.

Para guardar variables en el navegador, se suelen usar dos tecnologías de almacenamiento web muy comunes: **LocalStorage** y **SessionStorage**. Ambas permiten almacenar datos en el navegador del usuario de manera sencilla usando pares clave-valor. La diferencia principal entre ambas es:

* **LocalStorage**: Los datos se guardan de manera persistente, incluso si cierras la ventana o reinicias el navegador. La información solo se borra manualmente o a través de JavaScript.
* **SessionStorage**: Los datos solo se guardan durante la sesión del navegador. Si cierras la ventana o pestaña, se pierden.

## Ejemplo: Guardar Valores en el LocalStorage


```javascript
// Guardar un valor numérico
let numero = 42;
localStorage.setItem('miNumero', numero);

// Guardar una cadena de texto
let cadena = "Hola, esto es un texto";
localStorage.setItem('miCadena', cadena);

// Guardar una estructura JSON
let objetoJSON = {
    nombre: "Juan",
    edad: 30,
    activo: true
};
// Convertir el objeto JSON a cadena de texto con JSON.stringify()
localStorage.setItem('miObjetoJSON', JSON.stringify(objetoJSON));
```

## Recuperar Variables desde el LocalStorage

Para recuperar las variables guardadas, se puede usar  el método `getItem`. Cuando se trata de objetos JSON, es necesario utilizar `JSON.parse()`  para convertir la cadena de vuelta a un objeto.

```javascript
// Recuperar un valor numérico
let numeroGuardado = localStorage.getItem('miNumero');
numeroGuardado = Number(numeroGuardado); // Convertir de string a número
console.log("Número guardado:", numeroGuardado);

// Recuperar una cadena de texto
let cadenaGuardada = localStorage.getItem('miCadena');
console.log("Cadena guardada:", cadenaGuardada);

// Recuperar una estructura JSON
let objetoJSONGuardado = localStorage.getItem('miObjetoJSON');
objetoJSONGuardado = JSON.parse(objetoJSONGuardado); // Convertir de string a objeto JSON
console.log("Objeto JSON guardado:", objetoJSONGuardado);
```


# Eliminar Valores desde el LocalStorage 

Para eliminar un elemento específico del LocalStorage, se puede usar `removeItem`. Si se  desea borrar todo el almacenamiento, se puede usar `clear`.

```javascript
// Eliminar un solo elemento
localStorage.removeItem('miNumero');

// Limpiar todo el LocalStorage
localStorage.clear();
```

## Métodos para usar localStorage
* `setItem(clave, valor)`: Guarda un valor en el LocalStorage.
* `getItem(clave)`: Recupera un valor del LocalStorage.
* `removeItem(clave)`: Elimina un valor específico del LocalStorage.
* `clear()`: Elimina todos los valores del LocalStorage.

```javascript
// Guardar diferentes tipos de datos en LocalStorage
localStorage.setItem('miNumero', 100);                // Número
localStorage.setItem('miCadena', 'Hola Mundo');       // Cadena
localStorage.setItem('miObjetoJSON', JSON.stringify({ // Objeto JSON
    nombre: "Pedro",
    edad: 25,
    pais: "España"
}));

// Recuperar los datos guardados
let numeroRecuperado = Number(localStorage.getItem('miNumero'));
let cadenaRecuperada = localStorage.getItem('miCadena');
let objetoJSONRecuperado = JSON.parse(localStorage.getItem('miObjetoJSON'));

// Mostrar los datos recuperados
console.log('Número Recuperado:', numeroRecuperado);
console.log('Cadena Recuperada:', cadenaRecuperada);
console.log('Objeto JSON Recuperado:', objetoJSONRecuperado);

```

## Ejemplo usando SessionStorage


```javascript
// Guardar diferentes tipos de datos en sessionStorage
sessionStorage.setItem('miNumero', 42);                 // Número
sessionStorage.setItem('miCadena', 'Hola Session');     // Cadena
sessionStorage.setItem('miObjetoJSON', JSON.stringify({ // Objeto JSON
    nombre: "Luis",
    edad: 29,
    pais: "Colombia"
}));

// Recuperar los datos guardados
let numeroRecuperado = Number(sessionStorage.getItem('miNumero'));
let cadenaRecuperada = sessionStorage.getItem('miCadena');
let objetoJSONRecuperado = JSON.parse(sessionStorage.getItem('miObjetoJSON'));

// Mostrar los datos recuperados
console.log('Número Recuperado desde sessionStorage:', numeroRecuperado);
console.log('Cadena Recuperada desde sessionStorage:', cadenaRecuperada);
console.log('Objeto JSON Recuperado desde sessionStorage:', objetoJSONRecuperado);
```


## Métodos para usar SessionStorage
* `setItem(clave, valor)`: Guarda un valor en el SessionStorage.
* `getItem(clave)`: Recupera un valor del SessionStorage.
* `removeItem(clave)`: Elimina un valor específico del SessionStorage.
* `clear()`: Elimina todos los valores del SessionStorage.

# Diferencias Clave entre localStorage y sessionStorage

| Característica | `localStorage`                                         | `sessionStorage`                                         |
|----------------|--------------------------------------------------------|----------------------------------------------------------|
| Persistencia   | Persistente (permanece hasta que se borre manualmente) | Solo durante la sesión (se elimina al cerrar la pestaña) |
| Capacidad      | Aproximadamente 5-10 MB según el navegador             | Aproximadamente 5 MB según el navegador                  |
| Accesibilidad  | Disponible en todas las pestañas y ventanas abiertas   | Solo accesible en la pestaña o ventana actual            |



# Juego de dados

Como ejemplo se muestra el desarrollo de un juego usando  HTML / JavaScript / bootstrap. 

* El juego consiste en lanzar un dado por parte del **programa** (se muestra en la consola para fines de debug), pero este valor queda oculto hasta que tira el dado el **jugador**.  
* El valor de tirado por el **progama** se representa en un div de tipo **card**, así mismo se tiene otro div para el **jugador**.
* Se tienen 2 botones, uno para el programa y otro para el jugador. Alternadamente tira el programa y el jugador (sólo uno a la vez).
* Tira primero el programa, este valor queda oculto (pero se muestra en consola). 
* Al hacer click sobre cada botón se genera un valor aleatorio.
* En un componente alert de bootstrap se muestra quien ganó (el que obtuvo el valor más alto) o si empataron.
* El resultado se muestra para ambas partes en los elementos card después de que tira el **jugador**.
* En una tabla, se muestra cuántos juegos ha ganado el **programa**, el **jugador** y el número de **empates**.
* Finalmente, el historial de victorias y empates deberá guardarse en el localStorage del navegador.



## Interfaz creada usando bootstrap

<img src = 'https://github.com/mergutm/programacionWeb/blob/main/variables/imgs/dados01.png'>

### Fragmento   para tarjeta (card) de computadora
```html
<div class="col col-md-6 text-center">
     <button id="btn-computadora" class="btn btn-primary w-75">
         Computadora 
     </button>
     <div class="card mt-3 w-100">
         <div class="card-body">
             <h4 class="card-title">Computadora</h4>
             <p id="card-computadora" class="card-text display-5">?</p>
         </div>
     </div>
</div>
```

Dentro de la tabla, las cuentas de victorias o empates se tendrán en un fragmento como:
```html
<tbody>
  <tr>
    <td id="cuenta-computadora">0</td>
    <td id="cuenta-jugador">0</td>
    <td id="cuenta-empates">0</td>
  </tr>
</tbody>
```


## Lógica de carga/almacenamiento de las variables usando LocalStorage

Se obtiene el valor almacenado previamente en localStorage. Si no hay valor se inicializa con 0.

```javascript
// Variables para almacenar resultados
let c_computadora = parseInt(localStorage.getItem('cuenta-computadora')) || 0;
let c_jugador = parseInt(localStorage.getItem('cuenta-jugador')) || 0;
let c_empates = parseInt(localStorage.getItem('cuenta-empates')) || 0;
```


### Valores iniciales para la tabla

Se utilizan las referencias de las celdas de  la tabla para escribir los valores recuperados o iniciales.
```javascript
// Actualizar tabla con valores iniciales
document.getElementById('cuenta-computadora').textContent = c_computadora;
document.getElementById('cuenta-jugador').textContent = c_jugador;
document.getElementById('cuenta-empates').textContent = c_empates;
```



### Valores temporales para los tiros respectivos 


```javascript
// Variables del juego
let tiro_computadora = 0;
let tiro_jugador = 0;
```



### Referencias a elementos que se deben actuaizar en la página

```javascript
 // Referencias a los elementos del DOM
 const btn_computadora = document.getElementById('btn-computadora');
 const btn_jugador = document.getElementById('btn-jugador');    
       btn_jugador.disabled = true; //deshabilitando btn de jugador
 const mensaje = document.getElementById('mensaje');
 const card_computadora = document.getElementById('card-computadora');
 const card_jugador = document.getElementById('card-jugador');
```



### función para tirar el dado

Se genera un valor entre 1 y 6

```javascript
function tirar_dado() {
  return Math.floor(Math.random() * 6) + 1;
}
```




### Evento para el botón de la computadora

```javascript
 btn_computadora.addEventListener('click', function() {
   tiro_computadora = tirar_dado();
   console.log('Valor de la computadora:', tiro_computadora); // Para debug
   btn_computadora.textContent = `Computadora tira (?)`; // Mantener oculto
   card_computadora.textContent = '-'; // Borrar valor anterior
   card_jugador.textContent = '-';   // Borrar valor anterior del jugador
   btn_jugador.disabled = false; // Habilitar el botón del jugador

   //Habilitar / deshabilitar botones
   btn_computadora.disabled = true;
   btn_jugador.disabled = false;
 });
```


### Evento para el botón del jugador


```javascript

btn_jugador.addEventListener('click', function() {
  tiro_jugador = tirar_dado();
  console.log('Valor del jugador:', tiro_jugador); // Para debug

  // Mostrar valores obtenidos por la computadora y el jugador
  card_computadora.textContent = tiro_computadora;
  card_jugador.textContent = tiro_jugador;

  mostrarResultado();
  actualizarTabla();
  guardarResultadosEnLocalStorage();

  // Reiniciar botones para la siguiente ronda
  // btn_jugador.disabled = true;
  btn_computadora.textContent = `Computadora tira (?)`;

  btn_computadora.disabled = false;
  btn_jugador.disabled = true;
});
```


### Función para mostrar el resultado del juego


```javascript
function mostrarResultado() {
  if (tiro_computadora > tiro_jugador) {
    mensaje.textContent = '¡La computadora gana!';
    mensaje.className = 'alert alert-danger';
    c_computadora++;
  } else if (tiro_jugador > tiro_computadora) {
    mensaje.textContent = '¡El jugador gana!';
    mensaje.className = 'alert alert-success';
    c_jugador++;
  } else {
    mensaje.textContent = '¡Es un empate!';
    mensaje.className = 'alert alert-warning';
    c_empates++;
  }
  mensaje.style.display = 'block'; // Mostrar el alert
}
```



### Función para actualizar la tabla de estadísticas


```javascript
function actualizarTabla() {
  document.getElementById('cuenta-computadora').textContent = c_computadora;
  document.getElementById('cuenta-jugador').textContent = c_jugador;
  document.getElementById('cuenta-empates').textContent = c_empates;
}
```

### Guardar los resultados en el localStorage


```javascript
function guardarResultadosEnLocalStorage() {
  localStorage.setItem('cuenta-computadora', c_computadora);
  localStorage.setItem('cuenta-jugador', c_jugador);
  localStorage.setItem('cuenta-empates', c_empates);
}

```

 
# Screenshots de la aplicación funcionando

<img src = 'https://github.com/mergutm/programacionWeb/blob/main/variables/imgs/dados02.png'>

<img src = 'https://github.com/mergutm/programacionWeb/blob/main/variables/imgs/dados03.png'>
