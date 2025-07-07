<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sorry Rukaya 💔</title>
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {
      background: url('https://res.cloudinary.com/dxjkbpmgm/image/upload/v1744658409/Picsart_25-04-14_00-56-51-907_ztwdk2.jpg') no-repeat center center fixed;
      background-size: cover;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      overflow: hidden;
      text-align: center;
    }
    .overlay {
      background: rgba(0,0,0,0.6);
      min-height: 100vh;
      padding: 40px 20px;
      position: relative;
      z-index: 2;
    }
    .animated-name {
      font-size: 3rem;
      color: #ff99cc;
      animation: glow 2s infinite alternate;
      font-weight: bold;
      margin-bottom: 10px;
    }
    @keyframes glow {
      from { text-shadow: 0 0 10px #ff99cc; }
      to   { text-shadow: 0 0 30px #ff66b2, 0 0 60px #ff66b2; }
    }
    .message {
      font-size: 1.3rem;
      margin: 20px auto;
      max-width: 600px;
      line-height: 1.8;
      text-shadow: 1px 1px 2px black;
    }
    .timer {
      margin-top: 10px;
      font-size: 1.1rem;
      color: #ffc0cb;
    }
    button {
      margin-top: 30px;
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 30px;
      background: #ff4d6d;
      color: white;
      cursor: pointer;
      box-shadow: 0 0 15px #ff4d6d;
      transition: 0.3s ease;
    }
    button:hover {
      background: #d6336c;
      transform: scale(1.1);
    }
    #secret {
      margin-top: 40px;
      font-size: 1.1rem;
      color: #fff;
      cursor: pointer;
      text-decoration: underline;
    }
    #secretMsg {
      display: none;
      margin-top: 15px;
      font-size: 1.3rem;
      color: #ffd1dc;
    }
    .firework {
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      border-radius: 50%;
      animation: explode 1s ease-out forwards;
    }
    @keyframes explode {
      0% { transform: scale(1); opacity: 1; }
      100% { transform: scale(5); opacity: 0; }
    }
    .rain {
      position: fixed;
      top: -50px;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      animation: fall linear infinite;
      z-index: 1;
      pointer-events: none;
    }
    @keyframes fall {
      0% { transform: translateY(-50px) rotate(0deg); }
      100% { transform: translateY(110vh) rotate(360deg); }
    }
    #popup {
      display: none;
      position: fixed;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: #ffb6c1;
      color: black;
      padding: 30px;
      border-radius: 20px;
      font-size: 1.2rem;
      box-shadow: 0 0 15px #ff69b4;
      z-index: 1000;
    }
  </style>
</head>
<body>
  <div class="overlay">
    <div class="animated-name">💖 Rukaya Jaan 💖</div>
    <div class="message">
      Tum ro rahi thi us waqt... aur main andar se toot gaya tha 😢<br><br>
      Galti meri thi, par dil se kabhi tujhe dukh dene ka iraada nahi tha...<br><br>
      Tere bina sab suna suna hai... khamosh hai dil...<br>
      Tu bas ek baar muskura de, main saari duniya bhool jaaun 💔<br><br>
      Mujhse maafi maangne ka tareeqa shayad perfect na ho...<br>
      Par jazbaat 100% dil se hain — <strong>please mujhe maaf kar do</strong> 🥺<br><br>
      — Tumhara apna <b>Muzamil</b>
    </div>
    <div class="timer">
      Main <span id="days">0</span> din <span id="hours">0</span> ghante 
      <span id="minutes">0</span> minute <span id="seconds">0</span> seconds se  
      tera intezaar kar raha hoon...
    </div>
    <button onclick="burstHeartAndPlay()">Click Here to Forgive 💘</button>
    <div id="secret" onclick="revealSecret()">Tap to Reveal Secret Message 💌</div>
    <div id="secretMsg">Tere bina sab khali hai… Bas ek baar gale lag ja… Main har din sirf tera hoon. 💖</div>
  </div>

  <!-- 🔊 Move audio ABOVE scripts -->
  <audio id="bgmusic" preload="auto">
    <source src="https://res.cloudinary.com/dxjkbpmgm/video/upload/v1751919519/Tu_Humsafar_Tu_Humkadam_Tu...._shorts__reels_360p_1_hj5w5a.mp3" type="audio/mpeg">
  </audio>

  <div id="popup">Jaan ❤️ maaf kar do please 😢</div>

  <script>
    const rukayaImg = "https://res.cloudinary.com/dxjkbpmgm/image/upload/v1744658409/Picsart_25-04-14_00-56-51-907_ztwdk2.jpg";
    function createRain() {
      const drop = document.createElement("img");
      drop.src = rukayaImg;
      drop.classList.add("rain");
      drop.style.left = Math.random() * 100 + "vw";
      drop.style.animationDuration = 3 + Math.random() * 3 + "s";
      document.body.appendChild(drop);
      setTimeout(() => drop.remove(), 8000);
    }
    setInterval(createRain, 300);
  </script>
  <script>
    const startTime = new Date("2025-07-06T20:00:00");
    function updateTimer() {
      const now = new Date();
      const diff = now - startTime;
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);
      document.getElementById("days").textContent = days;
      document.getElementById("hours").textContent = hours;
      document.getElementById("minutes").textContent = minutes;
      document.getElementById("seconds").textContent = seconds;
    }
    setInterval(updateTimer, 1000);
    updateTimer();
  </script>
  <script>
    const audio = document.getElementById("bgmusic");
    function burstHeartAndPlay() {
      for (let i = 0; i < 30; i++) {
        const fw = document.createElement('div');
        fw.classList.add('firework');
        fw.style.left = Math.random() * 100 + 'vw';
        fw.style.top = Math.random() * 100 + 'vh';
        fw.style.background = `hsl(${Math.random() * 360}, 100%, 60%)`;
        document.body.appendChild(fw);
        setTimeout(() => fw.remove(), 1000);
      }
      if (audio.paused) {
        audio.currentTime = 0;
        audio.play().then(() => {
          audio.loop = true;
        }).catch(err => {
          console.error("Audio play failed:", err);
        });
      }
      const popup = document.getElementById("popup");
      popup.style.display = "block";
      setTimeout(() => {
        popup.style.display = "none";
      }, 4000);
    }
    function revealSecret() {
      document.getElementById("secretMsg").style.display = "block";
    }
  </script>
</body>
</html>
