# Versionamiento / manejo de versiones

Es una práctica que permite a los desarrolladores rastrear y gestionar los cambios realizados en el código fuente de un proyecto a lo largo del tiempo.
* Este proceso **es esencial para colaborar en equipo** y asegurar que el trabajo de diferentes personas no se traslape entre sí. 
* Aplica principalmente a los archivos de código fuente, pero también puede incluir documentos, configuraciones y otros recursos relacionados con un proyecto.

Tiene entre otros, los siguientes beneficios:
* **Volver a versiones anteriores**: Si  se comete un error, es posible retroceder a una versión que funcionaba correctamente.
* **Comparar versiones**: Se puede  ver exactamente qué cambios se han realizado entre dos versiones. Diferencias (*diffs*).
* **Colaborar con otros**: Diferentes personas pueden trabajar en el mismo proyecto al mismo tiempo sin sobrescribir el trabajo de los demás.
* **Crear ramas**: Se pueden crear diferentes versiones a un proyecto para experimentar con nuevas ideas sin afectar la versión principal.
* **Previene la pérdida de datos**: Al guardar un historial de los cambios, se reduce el riesgo de perder trabajo por errores accidentales.
* **Mejora la organización**: Mantiene un registro claro de los cambios y quién los realizó.
* **Permite la experimentación**: Es posible probar nuevas ideas sin miedo a romper el código principal (main).


# Herramientas para manejo de versiones

* **Git**: Es el sistema de control de versiones más utilizado en la actualidad. Es de código abierto, distribuido y muy flexible. Git fue creado en 2005 por Linux, mientras que GitHub fue creado en 2008 y le pertenece a Microsoft.
* **SVN (Subversion)**: Otro sistema de control de versiones popular, aunque menos flexible que Git.
* **Mercurial**: Una alternativa a Git, conocido por su simplicidad y facilidad de uso.
* **Perforce** y **TFS**: Soluciones corporativas.



# Conceptos básicos sobre manejo de versiones
* **Repositorio**: Es un lugar donde se almacenan todas las versiones de tu proyecto.
* **Commit**: Es una instantánea de un proyecto en un momento dado. Cada vez que se realiza un cambio y se guarda, se está creando un nuevo commit.
* **Branch**: Es una rama de desarrollo. Se pueden  crear diferentes ramas para trabajar en características nuevas sin afectar la rama principal.
* **Merge**: Es la acción de combinar dos ramas.


# Comandos básicos

### Inicializar un repositorio de Git
Inicializa un nuevo repositorio de Git en el directorio actual.
Este comando creará un directorio .git en el directorio actual, donde se almacenarán los metadatos y el historial del proyecto.
```bash
git init
```


### Agregar archivos a la rama actual
Agrega un archivo o una serie de archivos al área de preparación para un commit.

Este comando agrega todos los archivos de la carpeta actual al área de preparación.
```bash
git add .
```

cualquier cambio que  hecho en archivo.txt se marcará como listo para ser incluido en el próximo commit.

```bash
git add archivo.txt
```



### Estado del repositorio
Muestra el estado del repositorio, incluidos los archivos que se han modificado pero no se han registrado.
```bash
git status
```
Esto  proporciona una lista de archivos modificados, nuevos y eliminados que aún no se han agregado al siguiente commit.


### Registrar un cambio con un mensaje
Realiza un commit de los cambios preparados en el área de preparación. Guarda los cambios en el historial del repositorio con un mensaje que describe el propósito del commit.


```bash
git commit -m "Agregar archivo inicial"
```


### Crear una nueva rama

Crea y cambia a una nueva rama.
```bash
git checkout -b nueva-rama
```


### Cambiar a la nueva rama 

```bash
git checkout nueva-funcionalidad
```

### historial de commits
Muestra el historial de commits del repositorio.
```bash
git log
```








