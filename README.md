<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - IFOBE</title>
    <!-- Vinculando Bootstrap 5 -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Vinculando el archivo de CSS personalizado -->
    <link rel="stylesheet" href="stylos.css">
    /* Estilo para el filtro difuso que solo afecta al fondo */
.background-blur {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    filter: blur(303px); /* Difuminar la imagen un poco */
    z-index: 1; /* Asegura que esté por debajo del contenido */
}

/* Estilos para el encabezado */
.header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100px; /* Altura del encabezado */
    background-color: rgba(241, 240, 240, 0.5); /* Fondo oscuro semitransparente */
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 2; /* Asegura que esté por encima del fondo */
}

.title {
    color: #003366; /* Azul oscuro */
    font-size: 2rem;
    font-style: italic; /* Cursiva */
    text-transform: uppercase; /* Mayúsculas */
    text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.7); /* Sombra para mejor visibilidad */
}

/* Estilo para el logo */
.logo-container {
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Personalizamos el tamaño del logo */
.logo {
    max-width: 80%;
    max-height: 80%;
    object-fit: contain;
}

/* Estilo para el formulario de login */
.login-form {
    background-color: #f8f9fa;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
}

/* Espaciado entre campos */
.mb-3 {
    margin-bottom: 1.5rem;
}

/* Filtro para desactivar el difuminado solo en el contenedor principal */
.container-fluid {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 5;
    filter: none;
}

/* Estilo para el cargador (loading screen) */
.loading-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
}

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
