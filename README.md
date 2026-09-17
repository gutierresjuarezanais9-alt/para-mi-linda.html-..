# para-mi-linda.html-..
Flores para la novia más linda del mundo 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para ti 🌻</title>
  <style>
    * {
      box-sizing: border-box;
    }
    body, html {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at center, #1a1a3a 0%, #050510 100%);
      color: #ffffff;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    /* GALAXIA CAYENDO DE FONDO */
    .galaxy-container {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: 1;
      pointer-events: none;
    }

    .flower {
      position: absolute;
      top: -50px;
      font-size: 24px;
      animation: fall linear infinite;
      opacity: 0.8;
      filter: drop-shadow(0 0 6px rgba(255, 215, 0, 0.8));
    }

    .flower:nth-child(1) { left: 5%; animation-duration: 6s; animation-delay: 0s; font-size: 20px; }
    .flower:nth-child(2) { left: 15%; animation-duration: 9s; animation-delay: 2s; font-size: 32px; }
    .flower:nth-child(3) { left: 25%; animation-duration: 7s; animation-delay: 4s; font-size: 18px; }
    .flower:nth-child(4) { left: 35%; animation-duration: 11s; animation-delay: 1s; font-size: 28px; }
    .flower:nth-child(5) { left: 45%; animation-duration: 8s; animation-delay: 3s; font-size: 22px; }
    .flower:nth-child(6) { left: 55%; animation-duration: 10s; animation-delay: 5s; font-size: 30px; }
    .flower:nth-child(7) { left: 65%; animation-duration: 6s; animation-delay: 2s; font-size: 16px; }
    .flower:nth-child(8) { left: 75%; animation-duration: 12s; animation-delay: 0s; font-size: 34px; }
    .flower:nth-child(9) { left: 85%; animation-duration: 7s; animation-delay: 3s; font-size: 24px; }
    .flower:nth-child(10){ left: 95%; animation-duration: 9s; animation-delay: 1s; font-size: 20px; }

    @keyframes fall {
      0% {
        transform: translateY(-50px) rotate(0deg);
        opacity: 0;
      }
      20% {
        opacity: 1;
      }
      100% {
        transform: translateY(105vh) rotate(360deg);
        opacity: 0.2;
      }
    }

    /* TARJETA CENTRAL */
    .card {
      position: relative;
      z-index: 10;
      background: rgba(15, 15, 35, 0.85);
      padding: 30px 20px;
      border-radius: 20px;
      border: 1px solid rgba(255, 215, 0, 0.6);
      box-shadow: 0 0 30px rgba(255, 215, 0, 0.4);
      max-width: 90%;
      width: 380px;
      backdrop-filter: blur(8px);
    }

    h1 {
      color: #ffd700;
      font-size: 1.5rem;
      margin-bottom: 20px;
      text-shadow: 0 0 12px rgba(255, 215, 0, 0.7);
      line-height: 1.3;
    }

    .quote-box {
      font-size: 1.1rem;
      min-height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-style: italic;
      color: #fff8dc;
      margin: 20px 0;
      transition: opacity 0.4s ease-in-out;
    }

    .btn {
      background: linear-gradient(135deg, #ffd700, #ffae00);
      border: none;
      padding: 14px 24px;
      font-size: 1.1rem;
      font-weight: bold;
      color: #0b0b1a;
      border-radius: 30px;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(255, 215, 0, 0.4);
      transition: transform 0.2s;
    }

    .btn:active {
      transform: scale(0.95);
    }

    /* BOTÓN FLOTANTE PARA PAUSAR/REPRODUCIR MÚSICA */
    .music-btn {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: rgba(255, 215, 0, 0.2);
      border: 1px solid #ffd700;
      color: #ffd700;
      font-size: 1.2rem;
      padding: 10px 15px;
      border-radius: 50px;
      cursor: pointer;
      z-index: 100;
      backdrop-filter: blur(5px);
    }

    .hidden {
      display: none !important;
    }
  </style>
</head>
<body>

  <!-- REPRODUCTOR DE AUDIO (Música de fondo) -->
  <audio id="bg-music" loop>
    <!-- Enlace directo a la música -->
    <source src="https://ia801503.us.archive.org/15/items/flores-amarillas-floricienta/Flores%20Amarillas.mp3" type="audio/mpeg">
  </audio>

  <!-- BOTÓN PARA SILENCIAR/ACTIVAR MÚSICA -->
  <button class="music-btn hidden" id="music-control" onclick="toggleMusic()">🎵 Música: ON</button>

  <!-- GALAXIA CAYENDO DE FONDO -->
  <div class="galaxy-container">
    <div class="flower">🌻</div>
    <div class="flower">✨</div>
    <div class="flower">🌼</div>
    <div class="flower">⭐</div>
    <div class="flower">🌻</div>
    <div class="flower">✨</div>
    <div class="flower">🌼</div>
    <div class="flower">🌻</div>
    <div class="flower">⭐</div>
    <div class="flower">✨</div>
  </div>

  <!-- PANTALLA INICIAL -->
  <div class="card" id="start-screen">
    <button class="btn" onclick="iniciarExperiencia()">toca para iniciar mi linda 🌻</button>
  </div>

  <!-- PANTALLA PRINCIPAL -->
  <div class="card hidden" id="main-screen">
    <h1>🌻 feliz día de la flores amarillas mi linda hermocha 🌻</h1>
    
    <div class="quote-box" id="quote">"Toca el botón de abajo para ver tus frases..."</div>

    <button class="btn" onclick="nextQuote()">Ver otra frase ✨</button>
  </div>

  <script>
    const frases = [
      "«Eres mi flor amarilla favorita en todo el universo.»",
      "«Gracias por llenar mi vida de tanta luz y alegría. ✨»",
      "«Donde sea, pero que sea contigo. 🌻»",
      "«Te mereces todas las flores del mundo hoy y siempre.»"
    ];

    let index = 0;
    const music = document.getElementById('bg-music');
    const musicBtn = document.getElementById('music-control');

    function iniciarExperiencia() {
      // Oculta inicio y muestra pantalla principal
      document.getElementById('start-screen').classList.add('hidden');
      document.getElementById('main-screen').classList.remove('hidden');
      musicBtn.classList.remove('hidden');

      // Inicia la reproducción de la canción
      music.play().catch(e => console.log("Audio reproducido tras interacción"));
    }

    function toggleMusic() {
      if (music.paused) {
        music.play();
        musicBtn.innerText = "🎵 Música: ON";
      } else {
        music.pause();
        musicBtn.innerText = "🔇 Música: OFF";
      }
    }

    function nextQuote() {
      const quoteElement = document.getElementById("quote");
      quoteElement.style.opacity = 0;
      setTimeout(() => {
        quoteElement.innerText = frases[index];
        quoteElement.style.opacity = 1;
        index = (index + 1) % frases.length;
      }, 300);
    }
  </script>
</body>
</html>
