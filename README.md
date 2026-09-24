<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para ti ♥</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root { 
            --bg-color: #f7f1eb;
            --card-bg: #fffdfa;
            --accent-color: #a3485e; 
            --accent-hover: #8f3e52;
            --text-color: #4a443f;
            --subtext-color: #8c827a;
            --border-color: #ebdcd0;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: 'Montserrat', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px 12px;
            overflow-x: hidden;
            position: relative;
        }

        .container {
            width: 100%;
            max-width: 420px;
            background-color: var(--card-bg);
            border-radius: 20px;
            box-shadow: 0 12px 35px rgba(0,0,0,0.06);
            padding: 25px 20px;
            text-align: center;
            z-index: 2;
        }

        /* Marcador estilo Polaroid */
        .polaroid {
            background: #ffffff;
            padding: 12px 12px 22px 12px;
            box-shadow: 0 6px 18px rgba(0,0,0,0.06);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            margin-bottom: 25px;
            transition: transform 0.3s ease;
        }

        .polaroid:hover {
            transform: translateY(-2px);
        }

        .polaroid img {
            width: 100%;
            height: 270px;
            object-fit: cover;
            border-radius: 4px;
        }

        .polaroid .names {
            font-family: 'Playfair Display', serif;
            font-size: 1.25rem;
            margin-top: 14px;
            color: var(--text-color);
            letter-spacing: 0.5px;
        }

        /* Sobre / Botón Interactivo */
        .envelope-wrapper {
            margin: 20px 0;
            cursor: pointer;
        }

        .envelope {
            background-color: #ebdcd0;
            border-radius: 12px;
            padding: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s ease;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.03);
            border: 1px dashed #d1bfb3;
        }

        .envelope:hover {
            background-color: #e3d2c5;
            transform: scale(1.02);
        }

        .envelope-seal {
            background-color: var(--accent-color);
            color: white;
            padding: 10px 22px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            box-shadow: 0 4px 12px rgba(163, 72, 94, 0.25);
        }

        .envelope-subtext {
            font-size: 0.8rem;
            color: var(--subtext-color);
            margin-top: 10px;
        }

        /* Contenido Oculto */
        .hidden-content {
            display: none;
            opacity: 0;
            transform: translateY(15px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .hidden-content.show {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }

        .letter {
            background: #faf6f0;
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 22px;
            text-align: left;
            font-size: 0.92rem;
            line-height: 1.75;
            margin-bottom: 25px;
            position: relative;
        }

        .letter::before {
            content: "“";
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            color: var(--accent-color);
            position: absolute;
            top: -10px;
            left: 12px;
            opacity: 0.25;
        }

        .letter p {
            margin-bottom: 14px;
        }

        .letter .signature {
            text-align: right;
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 1.05rem;
            margin-top: 15px;
            color: var(--accent-color);
        }

        /* Pregunta y Botón */
        .question-box {
            margin: 30px 0 20px 0;
            animation: fadeIn 1s ease;
        }

        .question-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.45rem;
            margin-bottom: 18px;
            color: var(--text-color);
            font-weight: 600;
        }

        .btn-yes {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 13px 34px;
            border-radius: 30px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(163, 72, 94, 0.3);
            transition: transform 0.2s ease, background-color 0.2s ease, box-shadow 0.2s ease;
        }

        .btn-yes:hover {
            transform: scale(1.05);
            background-color: var(--accent-hover);
            box-shadow: 0 7px 20px rgba(163, 72, 94, 0.4);
        }

        /* Contador de Tiempo */
        .counter-section {
            display: none;
            margin-top: 25px;
            border-top: 1px solid var(--border-color);
            padding-top: 25px;
            animation: fadeInUp 1s ease forwards;
        }

        .counter-title {
            font-size: 0.85rem;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            color: var(--subtext-color);
            margin-bottom: 18px;
            font-weight: 600;
        }

        .timer-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 8px;
            margin-bottom: 22px;
        }

        .time-box {
            background: #faf6f0;
            padding: 12px 4px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .time-value {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            font-weight: 600;
            color: var(--accent-color);
        }

        .time-label {
            font-size: 0.65rem;
            text-transform: uppercase;
            color: var(--subtext-color);
            margin-top: 3px;
        }

        .start-date {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 0.95rem;
            margin-bottom: 20px;
            color: var(--text-color);
        }

        .footer-text {
            font-size: 0.75rem;
            color: #b0a8a0;
            margin-top: 25px;
            letter-spacing: 1.5px;
            text-transform: uppercase;
        }

        /* Animación de Corazones Flotantes */
        .floating-heart {
            position: fixed;
            bottom: -20px;
            font-size: 20px;
            user-select: none;
            pointer-events: none;
            z-index: 999;
            animation: floatUp 3.5s linear forwards;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-105vh) rotate(360deg);
                opacity: 0;
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>

<div class="container">

    <!-- Foto Polaroid Superior -->
    <div class="polaroid">
        <img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?q=80&w=800&auto=format&fit=crop" alt="Foto Juntos">
        <div class="names">Greg & Cris</div>
    </div>

    <!-- Sobre / Botón Desplegable -->
    <div class="envelope-wrapper" id="envelopeWrapper" onclick="openEnvelope()">
        <div class="envelope">
            <div class="envelope-seal">Despliégate</div>
        </div>
        <div class="envelope-subtext">✦ Hay algo dentro para ti ✦</div>
    </div>

    <!-- Contenido Oculto -->
    <div class="hidden-content" id="hiddenLetter">
        
        <div class="letter">
            <p>Hay algo que todavía no te he confesado. Algo que mis ojos llevan tiempo intentando decirte cada vez que te miran, aunque mis palabras nunca hayan sabido cómo hacerlo.</p>
            <p>Porque contigo pasó algo diferente. Sin pedir permiso, te fuiste colando en mis pensamientos y en mis mejores días. Y entonces entendí que, desde el mismo día en que te vi, había una pregunta que no dejaba de rondarme la cabeza.</p>
            <p>Y hoy, por fin, quiero hacértela...</p>
            <div class="signature">— Greg</div>
        </div>

        <div class="question-box" id="questionBox">
            <div class="question-title">¿Quieres ser mi novia?</div>
            <button class="btn-yes" onclick="acceptProposal()">Sí, quiero ♥</button>
        </div>

    </div>

    <!-- Contador de Tiempo y Foto Final -->
    <div class="counter-section" id="counterSection">
        <div class="counter-title">Llevamos juntos</div>
        
        <div class="timer-grid">
            <div class="time-box">
                <div class="time-value" id="days">0</div>
                <div class="time-label">Días</div>
            </div>
            <div class="time-box">
                <div class="time-value" id="hours">0</div>
                <div class="time-label">Horas</div>
            </div>
            <div class="time-box">
                <div class="time-value" id="minutes">0</div>
                <div class="time-label">Minutos</div>
            </div>
            <div class="time-box">
                <div class="time-value" id="seconds">0</div>
                <div class="time-label">Segundos</div>
            </div>
        </div>

        <div class="start-date" id="startDateText">Desde el 19 de septiembre de 2026</div>

        <div class="polaroid">
            <img src="https://images.unsplash.com/photo-1522529599102-193c0d76b5b6?q=80&w=800&auto=format&fit=crop" alt="Foto Final">
            <div class="names" style="font-size:1.05rem; font-style:italic; margin-top:10px;">Hoy es el primer día de nuestra vida</div>
        </div>

        <div class="footer-text">HECHO CON AMOR</div>
    </div>

</div>

<script>
    // Fecha de inicio configurable (Año, Mes-1, Día)
    const startDate = new Date(2026, 8, 19, 0, 0, 0); // 19 de Septiembre de 2026

    function openEnvelope() {
        document.getElementById('envelopeWrapper').style.display = 'none';
        const hiddenLetter = document.getElementById('hiddenLetter');
        hiddenLetter.classList.add('show');
    }

    function acceptProposal() {
        // Ocultar la pregunta y el botón
        document.getElementById('questionBox').style.display = 'none';
        
        // Mostrar la sección del contador
        const counterSection = document.getElementById('counterSection');
        counterSection.style.display = 'block';

        // Lanzar animación de corazones
        launchHearts();

        // Iniciar el contador en vivo
        updateCounter();
        setInterval(updateCounter, 1000);
    }

    function updateCounter() {
        const now = new Date();
        const diff = now - startDate;

        const positiveDiff = diff < 0 ? 0 : diff;

        const days = Math.floor(positiveDiff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((positiveDiff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((positiveDiff % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((positiveDiff % (1000 * 60)) / 1000);

        document.getElementById('days').innerText = days;
        document.getElementById('hours').innerText = hours;
        document.getElementById('minutes').innerText = minutes;
        document.getElementById('seconds').innerText = seconds;
    }

    function launchHearts() {
        const heartIcons = ['♥', '💖', '💕', '💗', '✨'];
        const totalHearts = 35;

        for (let i = 0; i < totalHearts; i++) {
            setTimeout(() => {
                const heart = document.createElement('div');
                heart.classList.add('floating-heart');
                heart.innerText = heartIcons[Math.floor(Math.random() * heartIcons.length)];
                
                heart.style.left = Math.random() * 95 + 'vw';
                heart.style.animationDuration = (Math.random() * 2 + 2.5) + 's';
                heart.style.fontSize = (Math.random() * 15 + 16) + 'px';
                
                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 4000);
            }, i * 120);
        }
    }
</script>

</body>
</html>
