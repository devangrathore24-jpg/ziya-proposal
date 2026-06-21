<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For Ziya ❤️</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      height: 100vh;
      overflow: hidden;
      background: linear-gradient(135deg, #ff9ecf, #ffd6e8, #ffeaf4);
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    .hearts {
      position: absolute;
      width: 100%;
      height: 100%;
      overflow: hidden;
      top: 0;
      left: 0;
      z-index: 0;
    }

    .heart {
      position: absolute;
      bottom: -20px;
      color: rgba(255, 255, 255, 0.7);
      font-size: 20px;
      animation: floatUp linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-110vh) scale(1.5);
        opacity: 0;
      }
    }

    .container {
      position: relative;
      z-index: 2;
      width: 90%;
      max-width: 420px;
      background: rgba(255, 255, 255, 0.25);
      backdrop-filter: blur(12px);
      border-radius: 25px;
      padding: 30px 20px;
      text-align: center;
      box-shadow: 0 10px 35px rgba(255, 105, 180, 0.3);
      border: 2px solid rgba(255,255,255,0.4);
    }

    .small {
      color: #b30059;
      font-size: 15px;
      margin-bottom: 8px;
      font-weight: bold;
    }

    h1 {
      color: #ff0066;
      font-size: 2rem;
      margin-bottom: 12px;
    }

    h2 {
      color: #cc0066;
      font-size: 1.2rem;
      margin-bottom: 18px;
      line-height: 1.5;
    }

    .names {
      color: #99004d;
      font-size: 1rem;
      margin-bottom: 18px;
      font-weight: bold;
    }

    .message {
      color: #7a003c;
      font-size: 1rem;
      line-height: 1.7;
      margin-bottom: 25px;
    }

    .buttons {
      position: relative;
      width: 100%;
      height: 120px;
      margin-top: 10px;
    }

    button {
      border: none;
      outline: none;
      cursor: pointer;
      padding: 14px 24px;
      font-size: 1rem;
      border-radius: 999px;
      font-weight: bold;
      transition: 0.3s;
      box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    }

    #yesBtn {
      background: #ff4d88;
      color: white;
      position: absolute;
      left: 20%;
      bottom: 20px;
    }

    #yesBtn:hover {
      transform: scale(1.08);
      background: #ff1a66;
    }

    #noBtn {
      background: white;
      color: #ff0066;
      position: absolute;
      right: 20%;
      bottom: 20px;
    }

    #result {
      margin-top: 20px;
      color: #cc0052;
      font-size: 1.2rem;
      font-weight: bold;
      min-height: 35px;
    }

    .music-note {
      margin-top: 15px;
      font-size: 14px;
      color: #99004d;
    }

    @media (max-width: 500px) {
      #yesBtn {
        left: 12%;
      }
      #noBtn {
        right: 12%;
      }
      h1 {
        font-size: 1.7rem;
      }
      h2 {
        font-size: 1.05rem;
      }
    }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>

  <div class="container">
    <div class="small">A special message from</div>
    <div class="names">Priyansh Rathore ❤️ Ziya Khan Phatan</div>

    <h1>For Ziya 💖</h1>
    <h2>Will you be my girlfriend?</h2>

    <div class="message">
      Ziya, you are very special to me.  
      Every moment with your thought makes my day better.  
      I made this little page just for you, with all my heart. 💕  
      Will you be my girlfriend? 🌸💗
    </div>

    <div class="buttons" id="buttonArea">
      <button id="yesBtn">Yes 💖</button>
      <button id="noBtn">No 🙈</button>
    </div>

    <div id="result"></div>
    <div class="music-note">🎵 Tap anywhere once to allow music on some phones</div>

    <!-- Replace this music link if you want -->
    <audio id="bgMusic" loop>
      <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>
  </div>

  <script>
    const heartsContainer = document.getElementById("hearts");
    for (let i = 0; i < 25; i++) {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (16 + Math.random() * 24) + "px";
      heart.style.animationDuration = (5 + Math.random() * 6) + "s";
      heart.style.animationDelay = Math.random() * 5 + "s";
      heartsContainer.appendChild(heart);
    }

    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const result = document.getElementById("result");
    const bgMusic = document.getElementById("bgMusic");

    function moveNoButton() {
      const area = document.getElementById("buttonArea");
      const maxX = area.clientWidth - noBtn.offsetWidth;
      const maxY = area.clientHeight - noBtn.offsetHeight;

      const randomX = Math.max(0, Math.floor(Math.random() * maxX));
      const randomY = Math.max(0, Math.floor(Math.random() * maxY));

      noBtn.style.left = randomX + "px";
      noBtn.style.top = randomY + "px";
      noBtn.style.right = "auto";
      noBtn.style.bottom = "auto";
      noBtn.style.position = "absolute";
    }

    noBtn.addEventListener("click", moveNoButton);
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
      result.innerHTML = "Yayyyy Ziya said Yes! 💖🌸✨";
      yesBtn.style.transform = "scale(1.1)";
      setTimeout(() => {
        alert("Awww 💕 Priyansh + Ziya forever 💖");
      }, 300);
    });

    document.body.addEventListener("click", () => {
      bgMusic.play().catch(() => {});
    }, { once: true });
  </script>
</body>
</html>
