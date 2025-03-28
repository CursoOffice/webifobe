<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inicio de Sesión - Gen 10</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <style>
        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #121212;
            margin: 0;
            padding: 10px;
            position: relative;
            transition: 0.3s, color 0.3s;
            background:local;
        }
        
        .dark-mode {
            background: #f4f4f4;
            color: #121212;
        }

        .video-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }
        .video-background video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: blur(5px) brightness(0.6);
        }
        
        .login-container {
            background: rgba(255, 255, 255, 0.9);
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            text-align: center;
            width: 100%;
            max-width: 320px;
            transition:  0.3s;
            background:;
        }
        .dark-mode .login-container {
            background: rgba(171, 242, 83, 0.8);
            color: white;
        }

        .login-container .logo {
            max-width: 80%;
            height: auto;
            margin-bottom: 15px;
        }
        .theme-toggle, .language-toggle {
            position: absolute;
            top: 20px;
            cursor: pointer;
            background: white;
            padding: 8px 10px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            font-size: 24px;
        }
        .theme-toggle { right: 100px; }
        .language-toggle { right: 40px; }
    </style>
    <script>
        let texts = {};

        function validarLogin(event) {
            event.preventDefault();
            var email = document.getElementById("email").value;
            var password = document.getElementById("password").value;
            
            if (email === "admin@ifobe.edu.com" && password === "Admin2024@") {
                Swal.fire({
                    icon: 'success',
                    title: texts.success_title,
                    text: texts.success_message,
                    timer: 2000,
                    showConfirmButton: false
                }).then(() => {
                    window.location.href = "home.html";
                });
            } else {
                Swal.fire({
                    icon: 'error',
                    title: texts.error_title,
                    text: texts.error_message,
                    confirmButtonColor: '#00796b'
                });
            }
        }

        function toggleTheme() {
            document.body.classList.toggle("dark-mode");
        }

        function toggleLanguage() {
            const lang = document.documentElement.lang === "es" ? "en" : "es";
            document.documentElement.lang = lang;
            updateTexts(lang);
        }

        function updateTexts(lang) {
            const translations = {
                es: {
                    welcome: "¡Bienvenido!",
                    motivational: "\"El aprendizaje nunca se detiene. ¡Sigue avanzando!\"",
                    email: "Correo Electrónico*",
                    password: "Contraseña*",
                    login: "Iniciar Sesión",
                    success_title: "¡Bienvenido a Gen 10 - IFOBE!",
                    success_message: "Recuerda que el aprendizaje es un viaje, no un destino.",
                    error_title: "Credenciales incorrectas",
                    error_message: "Sigue intentando, el éxito es para los persistentes."
                },
                en: {
                    welcome: "Welcome!",
                    motivational: "\"Learning never stops. Keep moving forward!\"",
                    email: "Email Address*",
                    password: "Password*",
                    login: "Login",
                    success_title: "Welcome back!",
                    success_message: "Remember, learning is a journey, not a destination.",
                    error_title: "Incorrect credentials",
                    error_message: "Keep trying, success is for the persistent."
                }
            };
            texts = translations[lang];
            document.querySelector("h3").textContent = texts.welcome;
            document.querySelector(".motivational-message").textContent = texts.motivational;
        }

        document.addEventListener("DOMContentLoaded", function() {
            updateTexts("es");
        });
    </script>
</head>
<body>
    <div class="video-background">
        <video autoplay muted loop>
            <source src="img/fondo.ifobe (1).mp4" type="video/mp4">
            Tu navegador no soporta el elemento de video.
        </video>
    </div>
    
    <div class="theme-toggle" onclick="toggleTheme()">🌙/☀️</div>
    <div class="language-toggle" onclick="toggleLanguage()">🌍</div>
    
    <div class="login-container">
        <img src="img/Logogen10.png" alt="Logo" class="logo">
        <h3 class="mb-3"></h3>
        <p class="motivational-message"></p>
        <form onsubmit="validarLogin(event)">
            <div class="mb-3 text-start">
                <label for="email" class="form-label">Correo Electrónico*</label>
                <input type="email" class="form-control" id="email" placeholder="Ingrese su correo" required>
            </div>
            <div class="mb-3 text-start">
                <label for="password" class="form-label">Contraseña*</label>
                <input type="password" class="form-control" id="password" placeholder="Ingrese su contraseña" required>
            </div>
            <button type="submit" class="btn btn-primary w-100">Iniciar Sesión</button>
        </form>
    </div>
</body>
</html>



