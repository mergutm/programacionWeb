# Creación de archivo Dockerfile

Un **Dockerfile** es un archivo de texto que contiene un conjunto de instrucciones para construir una imagen de Docker. 
Las imágenes de Docker son plantillas ligeras y portátiles que contienen todo lo necesario para ejecutar una aplicación: el sistema operativo base, bibliotecas, dependencias y el código de la aplicación.

El Dockerfile especifica:

* **La base de la imagen**: Por ejemplo, un sistema operativo o una imagen previamente construida (FROM ubuntu:24.10).
* **Instrucciones para configurar el entorno**: Por ejemplo, instalar software, configurar variables de entorno y definir puertos.
* **El comando o aplicación predeterminada**: Lo que se ejecuta cuando el contenedor basado en esa imagen arranca.


## Instrucciones comunes en un Dockerfile
* `FROM`: Define la imagen base.
* `RUN`: Ejecuta comandos durante la construcción de la imagen.
* `COPY` o `ADD`: Copian archivos al sistema de archivos de la imagen.
* `CMD`: Define el comando por defecto para ejecutar el contenedor.
* `WORKDIR`: Establece el directorio de trabajo dentro del contenedor.
* `ENV`: Configura variables de entorno.


##  Por qué usar Dockerfiles
* **Reproducibilidad**: Cualquiera puede construir un contenedor idéntico siguiendo las mismas instrucciones.
* **Portabilidad**: Las aplicaciones empaquetadas en imágenes Docker funcionan igual en cualquier máquina que tenga Docker instalado.
* **Eficiencia**: Permite crear entornos de desarrollo y producción consistentes y ligeros.

```Dockerfile
# Use the official Ubuntu image as the base
FROM ubuntu:24.10

# Set environment variables to prevent interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Update and install necessary packages
RUN apt-get update && apt-get install -y \
    curl \
    gnupg \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Add Node.js 23.x repository
RUN curl -fsSL https://deb.nodesource.com/setup_23.x | bash -

# Install Node.js and npm
RUN apt-get update && apt-get install -y \
    nodejs vim openssh-server \
    && rm -rf /var/lib/apt/lists/*

# Verify installation
RUN node --version && npm --version

RUN npm install -g nodemon


# Set default command to run bash
CMD ["bash"]
```

### Base de la imagen
```Dockerfile
FROM ubuntu:24.10
```

Se utiliza la imagen oficial de Ubuntu 24.10 como base. 
Esto significa que la imagen contendrá un sistema operativo mínimo basado en Ubuntu.

### Evitar mensajes interactivos durante la instalación
```Dockerfile
ENV DEBIAN_FRONTEND=noninteractive
```

Define la variable de entorno **DEBIAN_FRONTEND** como noninteractive.
Esto asegura que las herramientas de instalación no muestren ventanas emergentes o mensajes que requieran interacción del usuario.


### Actualizar el sistema e instalar paquetes esenciales

```Dockerfile
RUN apt-get update && apt-get install -y \
    curl \
    gnupg \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*
```
* Actualiza la lista de paquetes disponibles (apt-get update).

Instala herramientas básicas como:
* **curl**: Para transferir datos desde o hacia un servidor.
* **gnupg**: Para manejar claves GPG (necesario para repositorios seguros).
* **ca-certificates**: Para manejar certificados SSL/TLS.
* Elimina la caché de apt para reducir el tamaño final de la imagen.



### Añadir el repositorio de Node.js 23.x
```Dockerfile
RUN curl -fsSL https://deb.nodesource.com/setup_23.x | bash -
```
Descarga y ejecuta un script oficial de NodeSource que configura el sistema para instalar la versión 23.x de Node.js.



### Instalar Node.js, npm y herramientas adicionales
```Dockerfile
RUN apt-get update && apt-get install -y \
    nodejs vim openssh-server \
    && rm -rf /var/lib/apt/lists/*
```
Instala:
* nodejs: JavaScript runtime.
* vim: Editor de texto.
* openssh-server: Servidor SSH.

### Verificar la instalación
```Dockerfile
RUN node --version && npm --version
```
Comprueba que Node.js y npm están instalados correctamente imprimiendo sus versiones.

### Instalar nodemon globalmente
```Dockerfile
RUN npm install -g nodemon
```

Instala nodemon, una herramienta que reinicia automáticamente aplicaciones Node.js cuando detecta cambios en el código.


### Definir el comando predeterminado
```Dockerfile
CMD ["bash"]
```

Especifica que el contenedor, por defecto, ejecutará el comando bash al iniciarse.
Esto proporciona acceso a una línea de comandos interactiva.


## Compilación del Dockerfile

```bash
docker build -t ubuntu-node23 .
```




```bash
docker run -p 3010:3000 -v $(pwd)/code:/code  --restart always --name dev-node-app ubuntu-node23
```
# Archivo YML

```yml
services:
  app:
    build: .
    container_name: ubuntu-nodejs-dev
    stdin_open: true       # Keep the container's standard input open
    tty: true              # Allocate a pseudo-TTY
    restart: always        # Ensure the container restarts automatically
    ports:
      - 3020:3000
    environment:
      - NODE_ENV=development
    volumes:
      - ./code:/code
```


