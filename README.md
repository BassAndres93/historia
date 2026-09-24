<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Sara ❤️</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f7f3ed;
            color: #333;
            display: flex;
            justify-content: center;
            padding: 20px 10px;
        }

        .container {
            width: 100%;
            max-width: 420px;
            background: #faf8f5;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.05);
            padding: 20px;
            text-align: center;
        }

        .title-top {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 20px;
            font-style: italic;
        }

        /* Card Polaroid */
        .polaroid {
            background: white;
            padding: 15px 15px 25px 15px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            margin-bottom: 25px;
        }

        .polaroid img {
            width: 100%;
            height: 280px;
            object-fit: cover;
            border-radius: 8px;
        }

        .polaroid-caption {
            font-size: 1.3rem;
            font-weight: 600;
            color: #444;
            margin-top: 15px;
        }

        /* Envelope / Carta Secreta */
        .envelope-btn {
            background: #e8d0be;
            border: none;
            padding: 15px 25px;
            border-radius: 25px;
            width: 100%;
            font-size: 1rem;
            color: #5a4032;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .letter-content {
            display: none;
            background: #fcf8f2;
            border: 1px solid #ebdccb;
            padding: 20px;
            border-radius: 12px;
            margin-top: 15px;
            text-align: left;
            font-size: 0.95rem;
            line-height: 1.6;
            color: #555;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.02);
        }

        .letter-content p {
            margin-bottom: 12px;
        }

        /* Proposal Section */
        .proposal {
            margin: 30px 0;
            padding: 20px;
            background: #fdf6f0;
            border-radius: 15px;
        }

        .proposal h3 {
            font-size: 1.3rem;
            color: #4a382c;
            margin-bottom: 15px;
        }

        .proposal-btn {
            background: #d88a8a;
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1rem;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(216, 138, 138, 0.4);
            transition: transform 0.2s;
        }

        .proposal-btn:active {
            transform: scale(0.98);
        }

        /* Counter Section */
        .counter-section {
            margin-top: 30px;
            border-top: 1px solid #eae0d5;
            padding-top: 25px;
        }

        .counter-section h4 {
            font-size: 1rem;
            color: #777;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }

        .timer-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 8px;
            margin-bottom: 20px;
        }

        .timer-box {
            background: #ffffff;
            padding: 10px 5px;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.04);
        }

        .timer-number {
            font-size: 1.3rem;
            font-weight: bold;
            color: #333;
        }

        .timer-label {
            font-size: 0.65rem;
            color: #888;
            text-transform: uppercase;
            margin-top: 4px;
        }

        .start-date {
            font-size: 0.9rem;
            color: #666;
            margin-bottom: 20px;
            font-style: italic;
        }

        .footer-photo {
            width: 100%;
            border-radius: 15px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            margin-top: 10px;
        }

        .watermark {
            font-size: 0.75rem;
            color: #aaa;
            margin-top: 20px;
            letter-spacing: 2px;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="title-top">Hay algo que quiero decirte...</div>

        <!-- Foto Principal Polaroid -->
        <div class="polaroid">
            <!-- Reemplaza esta URL por tu foto favorita con ella -->
            <img src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=800" alt="Nosotros">
            <div class="polaroid-caption">Byron y Sara </div>
        </div>

        <!-- Botón / Sobre Desplegable -->
        <button class="envelope-btn" onclick="toggleLetter()">
            💌 <span>Desplegar</span>
        </button>

        <!-- Carta Oculta -->
        <div class="letter-content" id="letter">
            <p><strong>Para ti:</strong></p>
            <p>Hay algo que todavía no te he confesado. Algo que mis ojos llevan tiempo intentando decirte cada vez que te miran, aunque mis palabras nunca hayan sabido cómo hacerlo.</p>
<p>Este detalle de la flor te la queria dar el dia del las flores amarillas , pero por mi timidez no pude darsela, solo tuve el valor de darle la cadenita </p>
<p>Cuando vi que se pudo la cadena del girasol, mi corazon latio a mil y no supe como reaccionar y al despedirme de ti , no me flueyeron las palabras</p>
<p>Contigo pasó algo diferente. Sin pedir permiso, te fuiste colando en mis pensamientos y estas dos semanas an sido mis mejores días, porque tu estas presente.</p>
 <p>Y entonces entendí que había una pregunta que no dejaba de rondarme la cabeza.</p>
            <p style="text-align: right;"><em>— Byron</em></p>
        </div>

        <!-- Sección de Propuesta -->
        <div class="proposal">
            <h3>¿Me darias la oportunidad de conocerte mejor y crear nuestra propia historia?</h3>
            <button class="proposal-btn" onclick="celebrate()">Sí, quiero ❤️</button>
        </div>

        <!-- Contador de Tiempo -->
        <div class="counter-section">
            <h4>Primeros minutos de alegria</h4>
            <div class="timer-grid">
                <div class="timer-box">
                    <div class="timer-number" id="days">0</div>
                    <div class="timer-label">Días</div>
                </div>
                <div class="timer-box">
                    <div class="timer-number" id="hours">0</div>
                    <div class="timer-label">Horas</div>
                </div>
                <div class="timer-box">
                    <div class="timer-number" id="minutes">0</div>
                    <div class="timer-label">Minutos</div>
                </div>
                <div class="timer-box">
                    <div class="timer-number" id="seconds">0</div>
                    <div class="timer-label">Segundos</div>
                </div>
            </div>
            
            <div class="start-date" id="start-date-text">Desde el 25 de septiembre de 2026</div>

            <!-- Foto de abajo -->
            <!-- Reemplaza esta URL por otra foto de ustedes dos -->
            <img class="footer-photo" src="https://images.unsplash.com/photo-1522673607200-164d1b6ce486?q=80&w=800" alt="Juntos">
        </div>

        <div class="watermark">HECHO CON AMOR</div>
    </div>

    <script>
        // Función para mostrar / ocultar la carta
        function toggleLetter() {
            const letter = document.getElementById('letter');
            if (letter.style.display === 'block') {
                letter.style.display = 'none';
            } else {
                letter.style.display = 'block';
            }
        }

        // Mensaje al hacer clic en "Sí, quiero"
        function celebrate() {
            alert("¡Me haces la persona más feliz del mundo! ❤️");
        }

        // Configuración de la fecha de inicio
        // Cambia el año, mes (0=Ene, 8=Sep, 11=Dic) y día según la fecha especial de ustedes
        const startDate = new Date(2026, 8, 24, 0, 0, 0); 

        function updateTimer() {
            const now = new Date();
            const diff = now - startDate;

            if (diff < 0) {
                // Si la fecha es futura, muestra ceros
                document.getElementById('days').innerText = '0';
                document.getElementById('hours').innerText = '0';
                document.getElementById('minutes').innerText = '0';
                document.getElementById('seconds').innerText = '0';
                return;
            }

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
            const minutes = Math.floor((diff / 1000 / 60) % 60);
            const seconds = Math.floor((diff / 1000) % 60);

            document.getElementById('days').innerText = days;
            document.getElementById('hours').innerText = hours;
            document.getElementById('minutes').innerText = minutes;
            document.getElementById('seconds').innerText = seconds;
        }

        setInterval(updateTimer, 1000);
        updateTimer();
    </script>
</body>
</html>
