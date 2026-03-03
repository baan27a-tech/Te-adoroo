# Te-adoroo
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Galaxia para ti</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body, html {
      height: 100%;
      overflow: hidden;
      background: #000;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: #fff;
    }
    #particles-js {
      position: absolute;
      width: 100%;
      height: 100%;
      background: radial-gradient(ellipse at bottom, #0b001f 0%, #000 100%);
    }
    .content {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      z-index: 10;
      pointer-events: none;
    }
    h1 {
      font-size: 4.5rem;
      margin-bottom: 1rem;
      text-shadow: 0 0 20px rgba(255, 215, 0, 0.8), 0 0 40px rgba(255, 165, 0, 0.6);
      animation: glow 3s ease-in-out infinite alternate;
    }
    p {
      font-size: 1.8rem;
      opacity: 0.9;
      text-shadow: 0 0 15px rgba(173, 216, 230, 0.7);
      animation: float 6s ease-in-out infinite;
    }
    @keyframes glow {
      from { text-shadow: 0 0 10px #fff, 0 0 20px #ffd700, 0 0 30px #ff8c00; }
      to   { text-shadow: 0 0 20px #fff, 0 0 40px #ffd700, 0 0 60px #ff4500; }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50%      { transform: translateY(-20px); }
    }
    /* Reproductor simple (opcional) */
    .music-player {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 20;
      pointer-events: auto;
    }
    button {
      padding: 12px 24px;
      font-size: 1.1rem;
      background: rgba(255, 255, 255, 0.15);
      border: 1px solid rgba(255, 255, 255, 0.3);
      color: white;
      border-radius: 30px;
      cursor: pointer;
      backdrop-filter: blur(5px);
      transition: all 0.3s;
    }
    button:hover {
      background: rgba(255, 215, 0, 0.3);
      box-shadow: 0 0 20px gold;
    }
  </style>
</head>
<body>

  <div id="particles-js"></div>

  <div class="content">
    <h1>Galaxia para ti</h1>
    <p>Donde cada estrella brilla por ti ✨💫</p>
  </div>

  <!-- Reproductor de música opcional -->
  <div class="music-player">
    <audio id="bgMusic" loop>
      <source src="tu-cancion.mp3" type="audio/mpeg">
      Tu navegador no soporta audio.
    </audio>
    <button onclick="toggleMusic()">Reproducir / Pausar música 🎶</button>
  </div>

  <!-- Particles.js CDN -->
  <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>

  <script>
    // Configuración de particles.js para efecto galaxia/estrellas
    particlesJS("particles-js", {
      "particles": {
        "number": { "value": 120, "density": { "enable": true, "value_area": 800 } },
        "color": { "value": ["#ffffff", "#ffd700", "#00ffff", "#ff69b4"] }, // colores estelares
        "shape": { "type": "circle" },
        "opacity": { "value": 0.8, "random": true, "anim": { "enable": true, "speed": 1, "opacity_min": 0.1 } },
        "size": { "value": 2.5, "random": true, "anim": { "enable": true, "speed": 2, "size_min": 0.3 } },
        "line_linked": { "enable": false },
        "move": {
          "enable": true,
          "speed": 0.8,
          "direction": "none",
          "random": true,
          "straight": false,
          "out_mode": "out",
          "bounce": false,
          "attract": { "enable": false }
        }
      },
      "interactivity": {
        "detect_on": "canvas",
        "events": {
          "onhover": { "enable": true, "mode": "bubble" },
          "onclick": { "enable": true, "mode": "repulse" },
          "resize": true
        },
        "modes": {
          "bubble": { "distance": 200, "size": 4, "duration": 2, "opacity": 0.8 },
          "repulse": { "distance": 150, "duration": 0.4 }
        }
      },
      "retina_detect": true
    });

    // Control de música
    const music = document.getElementById("bgMusic");
    function toggleMusic() {
      if (music.paused) {
        music.play();
      } else {
        music.pause();
      }
    }
  </script>

</body>
</html>
