# Bordes usando CSS

##  Borde sencillo con color y grosor
El borde básico se define con la propiedad border, que puede especificar el grosor, el estilo y el color.


```CSS
/* Ejemplo de borde sólido, rojo y de 2 píxeles de grosor */
.div1 {
    border: 2px solid red;
}
```
##  Bordes con diferentes estilos
CSS permite diferentes estilos de bordes: solid, dashed, dotted, double, groove, ridge, inset, outset.


```CSS
/* Ejemplos de diferentes estilos de borde */
.div2 {
    border: 3px dashed blue;     /* Línea discontinua (dashed) */
}

.div3 {
    border: 4px dotted green;    /* Línea de puntos (dotted) */
}

.div4 {
    border: 5px double black;    /* Línea doble */
}

.div5 {
    border: 6px groove gray;     /* Borde con estilo de surco (groove) */
}
```


##  Bordes con colores diferentes para cada lado
Especificar un color de borde diferente para cada lado usando propiedades específicas como border-top, border-right, border-bottom, border-left.


```CSS
/* Bordes con colores diferentes en cada lado */
.div6 {
    border-top: 3px solid red;
    border-right: 3px solid green;
    border-bottom: 3px solid blue;
    border-left: 3px solid orange;
}

```
##  Bordes con radio en las esquinas (bordes redondeados)
Para redondear las esquinas de un borde, se utiliza la propiedad border-radius.


```CSS
/* Bordes con esquinas redondeadas */
.div7 {
    border: 2px solid #3498db;
    border-radius: 10px;       /* Redondear todas las esquinas a 10px */
}

.div8 {
    border: 3px solid #e74c3c;
    border-radius: 50%;        /* Bordes totalmente redondeados, círculo u óvalo */
}
```

##  Bordes personalizados con diferentes radios en cada esquina
Personalizar cada esquina de forma independiente usando propiedades específicas de border-radius.


```CSS
/* Bordes con diferentes radios en cada esquina */
.div9 {
    border: 2px solid #2ecc71;
    border-radius: 10px 20px 30px 40px; /* Esquinas: superior-izq, superior-der, inf-der, inf-izq */
}
```
##  Bordes con sombra
Añadir una sombra a los bordes utilizando la propiedad box-shadow.


```CSS
/* Borde con sombra */
.div10 {
    border: 2px solid #8e44ad;
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3); /* Sombra con desplazamiento x/y y desenfoque */
}
```

##  Bordes usando la propiedad abreviada
Definir bordes de manera abreviada con la propiedad border, y también puedes usar abreviaciones para cada lado (border-top, border-right, etc.).


```CSS
/* Ejemplo usando propiedad abreviada */
.div11 {
    border: 2px solid #f39c12;     /* Todos los lados con el mismo grosor, estilo y color */
}

/* Bordes específicos para cada lado usando abreviación */
.div12 {
    border-width: 2px 4px 6px 8px; /* Grosor: arriba, derecha, abajo, izquierda */
    border-style: solid dashed dotted double;
    border-color: red green blue orange;
}
```
##  Bordes solo en un lado del elemento
Aplicar bordes únicamente a un lado si lo deseas, usando propiedades como border-top, border-right, etc.


```CSS
/* Borde solo en la parte inferior */
.div13 {
    border-bottom: 3px solid purple;
}

/* Borde solo en la parte izquierda */
.div14 {
    border-left: 5px dashed teal;
}
```
# Ejemplos completos en HTML y CSS
Aquí hay un ejemplo HTML con estilos CSS para las clases descritas:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejemplos de Bordes en CSS</title>
    <style>
        .div1 { border: 2px solid red; }
        .div2 { border: 3px dashed blue; }
        .div3 { border: 4px dotted green; }
        .div4 { border: 5px double black; }
        .div5 { border: 6px groove gray; }
        .div6 {
            border-top: 3px solid red;
            border-right: 3px solid green;
            border-bottom: 3px solid blue;
            border-left: 3px solid orange;
        }
        .div7 { border: 2px solid #3498db; border-radius: 10px; }
        .div8 { border: 3px solid #e74c3c; border-radius: 50%; }
        .div9 { border: 2px solid #2ecc71; border-radius: 10px 20px 30px 40px; }
        .div10 { border: 2px solid #8e44ad; box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3); }
        .div11 { border: 2px solid #f39c12; }
        .div12 {
            border-width: 2px 4px 6px 8px;
            border-style: solid dashed dotted double;
            border-color: red green blue orange;
        }
        .div13 { border-bottom: 3px solid purple; }
        .div14 { border-left: 5px dashed teal; }
    </style>
</head>
<body>
    <div class="div1">Borde sólido rojo</div>
    <div class="div2">Borde discontinua azul</div>
    <div class="div3">Borde de puntos verde</div>
    <div class="div4">Borde doble negro</div>
    <div class="div5">Borde surco gris</div>
    <div class="div6">Bordes de diferentes colores en cada lado</div>
    <div class="div7">Borde con esquinas redondeadas (10px)</div>
    <div class="div8">Borde redondeado en forma de círculo</div>
    <div class="div9">Borde con diferentes radios en cada esquina</div>
    <div class="div10">Borde con sombra</div>
    <div class="div11">Borde usando propiedad abreviada</div>
    <div class="div12">Borde específico para cada lado con abreviación</div>
    <div class="div13">Borde solo en la parte inferior</div>
    <div class="div14">Borde solo en la parte izquierda</div>
</body>
</html>
```

La siguiente imagen muestra el resultado de aplicar los estilos a diferentes elementos div. 
<img src='https://raw.githubusercontent.com/mergutm/programacionWeb/refs/heads/main/bordes/imgs/bordes.png'>
