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
