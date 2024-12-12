# Ejemplo usando GIT

Ejemplo de una página básica


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página de prueba</title>
</head>

<body>
    <nav>
        <div class="box">
            <a href="#">
                Inicio
            </a>
        </div>
        <div class="box">
            <a href="#">
                Noticias
            </a>
        </div>
    </nav>

</body>

</html>
```

## subir el archivo al repo

```bash
$ git add .
$ git commit -m "inicio"
[main 84c6068] inicio
 2 files changed, 45 insertions(+)
 create mode 100644 git/pruebas/index.html
```

## Subir los cambios Push
```bash
$ git push
Username for 'https://github.com': merg@gs.utm.mx
Password for 'https://merg@gs.utm.mx@github.com': 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 662 bytes | 331.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
To https://github.com/mergutm/programacionWeb.git
   f51b6c9..84c6068  main -> main
```

# Creación de una rama (branch)

```bash
$ git checkout -b menu/noticias      
Switched to a new branch 'menu/noticias'
```

## Lista de ramas


```bash
$ git branch
  main
* menu/noticias
```


## Archivo de noticias.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Noticias</title>
</head>
<body>
    <h1>Noticias del dia</h1>
</body>
</html>
```


## Agregando noticias


```bash
$ git add noticias.html 
$ git commit -m "new noticias"
[menu/noticias ecba4e0] new noticias
 1 file changed, 11 insertions(+)
 create mode 100644 git/pruebas/noticias.html
```



Se indica que se debe agregar una rama, usando el comando que muestra git
```bash
$ git push
fatal: The current branch menu/noticias has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin menu/noticias

```



```bash
$     git push --set-upstream origin menu/noticias
Username for 'https://github.com': merg@gs.utm.mx
Password for 'https://merg@gs.utm.mx@github.com': 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 590 bytes | 590.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: 
remote: Create a pull request for 'menu/noticias' on GitHub by visiting:
remote:      https://github.com/mergutm/programacionWeb/pull/new/menu/noticias
remote: 
To https://github.com/mergutm/programacionWeb.git
 * [new branch]      menu/noticias -> menu/noticias
Branch 'menu/noticias' set up to track remote branch 'menu/noticias' from 'origin'.

```

# Cambiando a main

```bash
$ git checkout main
M	git/pruebas/README.md
M	git/pruebas/index.html
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
```

