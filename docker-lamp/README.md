# Docker con MySQL, PHPMyAdmin y Apache (con PHP) 

# docker-compose.yml

Archivo para crear los contenedores

```yml
version: '3.8'
services:

  mysql:
    image: mysql:8.0
    container_name: mysql_container
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: my_database
      MYSQL_USER: mysql_user
      MYSQL_PASSWORD: mysql_password
    ports:
      - "3316:3306"
    volumes:
      - ./mysql_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin/phpmyadmin:latest
    container_name: phpmyadmin_container
    environment:
      PMA_HOST: mysql
      PMA_USER: mysql_user
      PMA_PASSWORD: mysql_password
    ports:
      - "8086:80"
    depends_on:
      - mysql


  apache:
    image: php:8.2-apache
    container_name: apache_container
    volumes:
      - ./www:/var/www/html
    ports:
      - "8085:80"
    depends_on:
      - mysql  
```


## Creación de la BD

Se crea la tabla estudiantes y se agregan algunos registros de prueba
```sql
CREATE TABLE `estudiantes` (
  `id` int NOT NULL,
  `nombre` tinytext NOT NULL,
  `grupo` varchar(10) NOT NULL,
  `f_nac` date NOT NULL
);

INSERT INTO `estudiantes` (`id`, `nombre`, `grupo`, `f_nac`) VALUES
(1, 'LOPEZ AGUIRRE SANTIAGO', '102-A', '2014-12-11'),
(2, 'URSUA GUTIERREZ GUILLERMO', '106-A', '2007-12-21');

ALTER TABLE `estudiantes`
  ADD PRIMARY KEY (`id`);

ALTER TABLE `estudiantes`
  MODIFY `id` int NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

```


## Driver para contenedor de apache

Para poder establecer conexión con el contenedor de MySQL, se instala el driver `pdo_mysql` conectándose al contenedor de Apache

```bash
apt-get update && apt-get install -y libpq-dev libonig-dev
docker-php-ext-install pdo_mysql
```

# Código para conexión a la BD desde PHP

```html
<?php
// Conexión a la BD
$dsn = "mysql:host=mysql;dbname=my_database;charset=utf8mb4";
$user = "mysql_user";
$password = "mysql_password";

try {
    $pdo = new PDO($dsn, $user, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Connection failed: " . $e->getMessage());
}

// Manejador de método post
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $nombre = $_POST['nombre'];
    $grupo = $_POST['grupo'];
    $f_nac = $_POST['f_nac'];

    $stmt = $pdo->prepare("INSERT INTO estudiantes (nombre, grupo, f_nac) VALUES (?, ?, ?)");
    $stmt->execute([$nombre, $grupo, $f_nac]);
}

// Fetch all estudiantes
$estudiantes = $pdo->query("SELECT * FROM estudiantes")->fetchAll(PDO::FETCH_ASSOC);
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estudiantes</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center">Estudiantes CR</h1>

        <!-- Agregar estudiante  -->
        <div class="card mb-4">
            <div class="card-header">Agregar estudiante</div>
            <div class="card-body">
                <form method="POST" action="">
                    <div class="mb-3">
                        <label for="nombre" class="form-label">Nombre</label>
                        <input type="text" class="form-control" id="nombre" name="nombre" required>
                    </div>
                    <div class="mb-3">
                        <label for="grupo" class="form-label">grupo</label>
                        <input type="text" class="form-control" id="grupo" name="grupo" required>
                    </div>
                    <div class="mb-3">
                        <label for="f_nac" class="form-label">Fecha de nacimiento</label>
                        <input type="date" class="form-control" id="f_nac" name="f_nac" required>
                    </div>
                    <button type="submit" class="btn btn-primary">Agregar estudiante</button>
                </form>
            </div>
        </div>

        <div class="card">
            <div class="card-header">Estudiantes</div>
            <div class="card-body">
                <table class="table table-bordered">
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Nombre</th>
                            <th>Grupo</th>
                            <th>Fecha de nacimiento</th>
                        </tr>
                    </thead>
                    <tbody>
                        <?php foreach ($estudiantes as $estudiante): ?>
                            <tr>
                                <td><?php echo htmlspecialchars($estudiante['id']); ?></td>
                                <td><?php echo htmlspecialchars($estudiante['nombre']); ?></td>
                                <td><?php echo htmlspecialchars($estudiante['grupo']); ?></td>
                                <td><?php echo htmlspecialchars($estudiante['f_nac']); ?></td>
                            </tr>
                        <?php endforeach; ?>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

```  



