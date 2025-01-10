# Cuerpo base


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.tailwindcss.com"></script>
    <title>Utilizando Tailwind</title>
</head>
<body>


</body>
</html>

```

## Fondo con degradado

```html
<body class="bg-gradient-to-r from-blue-100 via-blue-100 to-fuchsia-200 bg-rose-50 place-items-center flex-col space-y-28">
```
 
 Puedes ver más ejemplos en:
 <a href='https://tailwindcss.com/docs/background-clip#cropping-to-text'> degradados </a>


## Agregar botones al inicio del body

Agregar botones para el evento de mostrar dos tarjetas

```html
    <div class="flex items-center place-content-evenly flex space-x-10 ">
        <div class="bg-purple-300 hover:bg-purple-400  text-lg font-sans hover:font-serif hover:font-bold  rounded-lg py-4 w-96 text-center cursor-pointer"
            id="acerca">Acerca De</div>
        <div class="bg-purple-300 hover:bg-purple-400  text-lg hover:font-serif hover:font-bold rounded-lg py-4 w-96 text-center cursor-pointer"
            id="login">REGISTRATE</div>
    </div>
```

Hasta este punto, se debe tener 

![alt text](https://raw.githubusercontent.com/mergutm/programacionWeb/refs/heads/main/tailwind/images/botones.png)

<img src="https://raw.githubusercontent.com/mergutm/programacionWeb/refs/heads/main/tailwind/images/botones.png">
https://raw.githubusercontent.com/mergutm/programacionWeb/refs/heads/main/tailwind/images/botones.png

```html
   

```


