<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Cris</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #f7f1eb;
            --card-bg: #fffdfa;
            --accent-color: #a3485e;
            --text-color: #4a443f;
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
            padding: 20px 10px;
        }

        .container {
            width: 100%;
            max-width: 420px;
            background-color: var(--card-bg);
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            padding: 25px 20px;
            text-align: center;
        }

        /* Marcador de polaroid superior */
        .polaroid {
            background: #ffffff;
            padding: 12px 12px 25px 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.06);
            border: 1px solid var(--border-color);
            border-radius: 4px;
            margin-bottom: 25px;
        }

        .polaroid img {
            width: 100%;
            height: 260px;
            object-fit: cover;
            border-radius: 2px;
        }

        .polaroid .names {
            font-family: 'Playfair Display', serif;
            font-size: 1.2rem;
            margin-top: 12px;
            color: var(--text-color);
        }

        /* Sobre Interactivo */
        .envelope-wrapper {
            margin: 20px 0;
            cursor: pointer;
        }

        .envelope {
            background-color: #ebdcd0;
            border-radius: 8px;
            padding: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s ease;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.03);
        }

        .envelope-seal {
            background-color: var(--accent-color);
            color: white;
            padding: 8px 18px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            box-shadow: 0 2px 8px rgba(163, 72, 94, 0.3);
        }

        .envelope-subtext {
            font-size: 0.75rem;
            color: #8c827a;
            margin-top: 8px;
        }

        /* Contenido Oculto (Carta y Propuesta) */
        .hidden-content {
            display: none;
            opacity: 0;
            transition: opacity 0.6s ease;
        }

        .hidden-content.show {
            display: block;
            opacity: 1;
        }

        .letter {
            background: #faf6f0;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            text-align: left;
            font-size: 0.9rem;
            line-height: 1.6;
            margin-bottom: 25px;
            position: relative;
        }

        .letter::before {
            content: "“";
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            color: var(--accent-color);
            position: absolute;
            top: -10px;
            left: 10px;
            opacity: 0.3;
        }

        .letter p {
            margin-bottom: 12px;
        }

        .letter .signature {
            text-align: right;
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 1rem;
            margin-top: 15px;
        }

        /* Sección de Pregunta */
        .question-box {
            margin: 25px 0;
        }

        .question-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--text-color);
        }

        .btn-yes {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            box-shadow: 0 4px 12px rgba(163, 72, 94, 0.3);
            transition: transform 0.2s, background-color 0.2s;
        }

        .btn-yes:hover {
            transform: scale(1.05);
            background-color: #8f3e52;
        }

        /* Contador de Tiempo */
        .counter-section {
            display: none;
            margin-top: 30px;
            border-top: 1px border-solid var(--border-color);
            padding-top: 25px;
            animation: fadeIn 1s forwards;
        }

        .counter-title {
            font-size: 0.9rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            color: #8c827a;
            margin-bottom: 15px;
        }

        .timer-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 8px;
            margin-bottom: 20px;
        }

        .time-box {
            background: #faf6f0;
            padding: 10px 5px;
            border-radius: 6px;
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
            color: #8c827a;
            margin-top: 2px;
        }

        .start-date {
            font-family: 'Playfair Display', serif;
            font-style: italic;
            font-size: 0.95rem;
            margin-bottom: 15px;
            color: var(--text-color);
        }

        .second-polaroid {
            margin-top: 15px;
        }

        .footer-text {
            font-size: 0.75rem;
            color: #b0a8a0;
            margin-top: 20px;
            font-style: italic;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

<div class="container">

    <div class="polaroid">
        <img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?q=80&w=800&auto=format&fit=crop" alt="Greg y Cris">
        <div class="names">Greg & Cris</div>
    </div>

    <div class="envelope-wrapper" id="envelopeWrapper" onclick="openEnvelope()">
        <div class="envelope">
            <div class="envelope-seal">Despliega</div>
        </div>
        <div class="envelope-subtext">✦ Hay algo dentro para ti ✦</div>
    </div>

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

        <div class="start-date">Desde el 19 de septiembre de 2026</div>

        <div class="polaroid second-polaroid">
            <img src="https://images.unsplash.com/photo-1522529599102-193c0d76b5b6?q=80&w=800&auto=format&fit=crop" alt="Foto Juntos">
            <div class="names" style="font-size:0.95rem; font-style:italic; margin-top:8px;">Hoy es el primer día de nuestra vida</div>
        </div>

        <div class="footer-text">HECHO CON AMOR</div>
    </div>

</div>

<script>
    // Configura aquí la fecha de inicio deseada
    const startDate = new Date('2026-09-19T00:00:00');

    function openEnvelope() {
        document.getElementById('envelopeWrapper').style.display = 'none';
        document.getElementById('hiddenLetter').classList.add('show');
    }

    function acceptProposal() {
        document.getElementById('questionBox').style.display = 'none';
        document.getElementById('counterSection').style.display = 'block';
        
        // Iniciar el contador
        updateCounter();
        setInterval(updateCounter, 1000);
    }

    function updateCounter() {
        const now = new Date();
        const diff = now - startDate;

        // Si la fecha configurada es posterior a la actual, evita valores negativos
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
</script>

</body>
</html>
