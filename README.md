<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
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

  #countdown {
    text-align: center;
    font-size: 2rem;
    color: #ffcc00;
  }

  /* CAR */
  .car {
    position: absolute;
    bottom: 90px;
    left: -220px;
    width: 220px;
    height: 60px;
    animation: drive 6s linear infinite;
  }

  @keyframes drive {
    from { left: -240px; }
    to { left: 110%; }
  }

  .car-body {
    width: 220px;
    height: 50px;
    background: #ff4136;
    border-radius: 25px;
    position: absolute;
    top: 0;
  }

  .car-top {
    width: 120px;
    height: 35px;
    background: #ff725c;
    border-radius: 20px 20px 0 0;
    position: absolute;
    top: -30px;
    left: 50px;
  }

  .wheel {
    width: 36px;
    height: 36px;
    background: black;
    border-radius: 50%;
    position: absolute;
    bottom: -18px;
    animation: spin 1s linear infinite;
  }

  .wheel.left { left: 35px; }
  .wheel.right { right: 35px; }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  /* FIREWORKS */
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

<!-- CAR -->
<div class="car">
  <div class="car-top"></div>
  <div class="car-body"></div>
  <div class="wheel left"></div>
  <div class="wheel right"></div>
</div>

<!-- FIREWORKS -->
<div class="firework" style="top:150px; left:200px;"></div>
<div class="firework" style="top:200px; left:500px;"></div>
<div class="firework" style="top:120px; left:800px;"></div>
<div class="firework" style="top:180px; left:1000px;"></div>

<script>
  let seconds = 10;
  const countdown = document.getElementById("countdown");

  const timer = setInterval(() => {
    countdown.textContent = "New Year in: " + seconds;
    seconds--;

    if (seconds < 0) {
      clearInterval(timer);
      countdown.textContent = "🎆 Welcome to the New Year! 🎆";
    }
  }, 1000);
</script>

</body>
</html>
