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


## Iterfaz creada usando bootstrap




  
```javascript

```





```javascript

```





```javascript

```







```javascript

```





```javascript

```





```javascript

```





```javascript

```







```javascript

```





```javascript

```





```javascript

```





```javascript

```



