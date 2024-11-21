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




