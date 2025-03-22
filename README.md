<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - IFOBE</title>
    <!-- Vinculando Bootstrap 5 -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Vinculando el archivo de CSS personalizado -->
    <link rel="stylesheet" href="styloslogin.css">
</head>
<body>
    <!-- Encabezado con el nombre del instituto -->
    <header class="header text-center p-3 bg-primary text-white">
        <h1 class="title">INSTITUTO IFOBE - SEDE CAUCASIA</h1>
    </header>

    <!-- Contenedor del formulario de login -->
    <div class="container d-flex justify-content-center align-items-center vh-100">
        <div class="row w-100 d-flex justify-content-center">
            <!-- Logo a la izquierda -->
            <div class="col-md-4 d-flex justify-content-center align-items-center">
                <img id="logo" src="img/logo aprobado IFOBE_b SIN FONDO.png" alt="IFOBE Logo" class="img-fluid" style="max-width: 200px;">
            </div>
            <!-- Formulario de login -->
            <div class="col-md-4">
                <div class="login-form p-4 border rounded">
                    <h3 class="text-center mb-4">Iniciar sesión</h3>
                    <form id="loginForm">
                        <div class="mb-3">
                            <label for="email" class="form-label">Correo Electrónico</label>
                            <input type="email" class="form-control" id="email" placeholder="Ingresa tu correo" required>
                        </div>
                        <div class="mb-3">
                            <label for="password" class="form-label">Contraseña</label>
                            <input type="password" class="form-control" id="password" placeholder="Ingresa tu contraseña" required>
                        </div>
                        <button type="submit" class="btn btn-primary w-100">Iniciar sesión</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Scripts de Bootstrap y jQuery -->
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>

    <!-- Script para validación de login -->
    <script>
        document.getElementById("loginForm").addEventListener("submit", function(event) {
            event.preventDefault();
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;

            if (email === "Admin@ifobe.edu.co" && password === "Admin2024@") {
                window.location.href = "login.html"; // Redirige a la página principal
            } else {
                alert("Credenciales incorrectas. Intenta nuevamente.");
            }
        });
    </script>
</body>
</html>

