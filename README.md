<!DOCTYPE html>
<html>
<head>
  <title>Happy New Year!</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      background: radial-gradient(circle, #001f3f, #000814);
      font-family: "Comic Sans MS", cursive;
      color: white;
    }

    h1 {
      text-align: center;
      margin-top: 20px;
      font-size: 3.5rem;
      animation: bounce 2s infinite;
      text-shadow: 3px 3px #ffcc00;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-20px); }
    }

    /* Countdown */
    #countdown {
      text-align: center;
      font-size: 2rem;
      margin-top: 10px;
      color: #ffcc00;
    }

    /* Car */
    .car {
      position: absolute;
      bottom: 80px;
      left: -300px;
      width: 300px;
      animation: drive 6s linear infinite;
    }

    @keyframes drive {
      from { left: -300px; }
      to { left: 110%; }
    }

    /* Wheels */
    .wheel {
      position: absolute;
      width: 45px;
      animation: spin 1s linear infinite;
    }

    .wheel1 { bottom: 95px; left: 75px; }
    .wheel2 { bottom: 95px; left: 200px; }

    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    /* Fireworks */
    .firework {
      position: absolute;
      width: 8px;
      height: 8px;
      background: yellow;
      border-radius: 50%;
      animation: explode 2s infinite;
    }

    @keyframes explode {
      0% { transform: scale(0); opacity: 1; }
      100% { transform: scale(4); opacity: 0; }
    }
  </style>
</head>

<body>

<h1>🎉 Happy New Year! 🎉</h1>
<div id="countdown"></div>

<!-- Car body -->
<img class="car" src="https://i.imgur.com/O7MZ2xD.png">

<!-- Wheels -->
<img class="wheel wheel1" src="https://i.imgur.com/7QbK0wK.png">
<img class="wheel wheel2" src="https://i.imgur.com/7QbK0wK.png">

<!-- Fireworks -->
<div class="firework" style="top:150px; left:300px;"></div>
<div class="firework" style="top:200px; left:600px;"></div>
<div class="firework" style="top:120px; left:900px;"></div>

<script>
  // Countdown timer
  const countdownEl = document.getElementById("countdown");
  let seconds = 10;

  const timer = setInterval(() => {
    countdownEl.textContent = "New Year in: " + seconds;
    seconds--;

    if (seconds < 0) {
      clearInterval(timer);
      countdownEl.textContent = "🎆 Welcome to the New Year! 🎆";
    }
  }, 1000);
</script>

</body>
</html>
