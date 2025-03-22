<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - IFOBE</title>
    <!-- Vinculando Bootstrap 5 -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Vinculando el archivo de CSS personalizado -->
    <link rel="stylesheet" href="stylos.css">
</head>
<body>
    <!-- Pantalla de carga -->
    <div id="loading" class="loading-screen">
        <div class="spinner-border text-primary" role="status">
            <span class="visually-hidden">Cargando...</span>
        </div>
    </div>

    <!-- Encabezado con el nombre del instituto -->
    <header class="header">
        <h1 class="title">INSTITUTO IFOBE - SEDE CAUCASIA</h1>
    </header>

    <!-- Contenedor del formulario de login -->
    <div class="container-fluid d-flex justify-content-center align-items-center vh-100">
        <div class="row w-100">
            <!-- Columna para el logo -->
            <div class="col-lg-6 d-flex justify-content-center align-items-center logo-container">
                <img id="logo" src="img/logo aprobado IFOBE_b SIN FONDO.png" alt="IFOBE Logo" class="img-fluid logo">
            </div>
            <!-- Columna para el formulario de login -->
            <div class="col-lg-6 d-flex justify-content-center align-items-center">
                <div class="login-form p-5 border rounded">
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

    <!-- Vinculando Bootstrap JS y jQuery -->
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>

    <!-- Script para validación de login -->
    <script>
        document.getElementById("loginForm").addEventListener("submit", function(event) {
            event.preventDefault();
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;

            // Comprobamos las credenciales
            if (email === "Admin@ifobe.edu.co" && password === "Admin2024@") {
                // Redirigimos a index.html
                window.location.href = "login.html";
            } else {
                alert("Credenciales incorrectas. Intenta nuevamente.");
            }
        });

        // Desaparecer el cargador cuando la página cargue
        window.onload = () => {
            document.getElementById("loading").style.display = "none";
        };
    </script>
</body>
</html>
