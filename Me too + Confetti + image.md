<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For Malak 💖</title>
  <style>
    body {
      background-color: #ffc0cb;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      position: relative;
    }

    .card {
      background: white;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      z-index: 1;
    }

    h1 {
      color: #ff4d6d;
      margin-bottom: 10px;
    }

    p {
      font-size: 22px;
      margin-bottom: 30px;
    }

    button {
      padding: 12px 25px;
      font-size: 18px;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      margin: 10px;
    }

    #yes {
      background-color: #ff4d6d;
      color: white;
    }

    #no {
      background-color: #ddd;
      position: absolute;
    }

    #imagePopup {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      max-width: 80%;
      max-height: 80%;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.5);
      z-index: 10;
      animation: fadeIn 0.5s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translate(-50%, -60%) scale(0.8); }
      to { opacity: 1; transform: translate(-50%, -50%) scale(1); }
    }

    /* Canvas for confetti */
    #confettiCanvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 20;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Malak 💕</h1>
    <p>I like you 💖</p>
    <button id="yes">Me too</button>
    <button id="no">No</button>
  </div>

  <!-- الصورة -->
  <img id="imagePopup" src="" alt="Popup Image">

  <!-- Canvas للـ confetti -->
  <canvas id="confettiCanvas"></canvas>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const imagePopup = document.getElementById("imagePopup");

    // زرار No بيهرب
    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });

    // زرار Yes يظهر الصورة ويشغل Confetti
    yesBtn.addEventListener("click", () => {
      imagePopup.src = "your-image-name.jpg"; // غير الاسم بعد رفع الصورة
      imagePopup.style.display = "block";
      startConfetti();
    });

    // اضغط على الصورة لإخفائها
    imagePopup.addEventListener("click", () => {
      imagePopup.style.display = "none";
    });

    // ========== Confetti ==========
    const canvas = document.getElementById("confettiCanvas");
    const ctx = canvas.getContext("2d");
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const confettiCount = 150;
    const confetti = [];

    function randomColor() {
      const colors = ["#ff4d6d", "#ffe066", "#6a4c93", "#4dabf7", "#ff922b"];
      return colors[Math.floor(Math.random() * colors.length)];
    }

    for(let i = 0; i < confettiCount; i++) {
      confetti.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height - canvas.height,
        r: Math.random() * 6 + 4,
        d: Math.random() * confettiCount,
        color: randomColor(),
        tilt: Math.random() * 10 - 10,
        tiltAngleIncrement: Math.random() * 0.07 + 0.05,
        tiltAngle: 0
      });
    }

    let confettiActive = false;

    function drawConfetti() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      confetti.forEach(c => {
        ctx.beginPath();
        ctx.lineWidth = c.r / 2;
        ctx.strokeStyle = c.color;
        ctx.moveTo(c.x + c.tilt + c.r / 4, c.y);
        ctx.lineTo(c.x + c.tilt, c.y + c.tilt + c.r / 4);
        ctx.stroke();
      });
      updateConfetti();
    }

    function updateConfetti() {
      confetti.forEach((c, i) => {
        c.tiltAngle += c.tiltAngleIncrement;
        c.y += (Math.cos(c.d) + 3 + c.r / 2) / 2;
        c.tilt = Math.sin(c.tiltAngle) * 15;

        if (c.y > canvas.height) {
          c.y = -10;
          c.x = Math.random() * canvas.width;
        }
      });
    }

    function startConfetti() {
      confettiActive = true;
      function animate() {
        if (!confettiActive) return;
        drawConfetti();
        requestAnimationFrame(animate);
      }
      animate();
      // يوقف Confetti بعد 5 ثواني
      setTimeout(() => { confettiActive = false; ctx.clearRect(0,0,canvas.width,canvas.height); }, 5000);
    }

    // تحديث حجم canvas عند تغيير حجم الشاشة
    window.addEventListener("resize", () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    });
  </script>

</body>
</html>      margin-bottom: 30px;
    }

    button {
      padding: 12px 25px;
      font-size: 18px;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      margin: 10px;
    }

    #yes {
      background-color: #ff4d6d;
      color: white;
    }

    #no {
      background-color: #ddd;
      position: absolute;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Malk 💕</h1>
    <p>I like you 💖</p>
    <button id="yes" onclick="alert('You just made me smile 😊💗')">Yes</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById("no");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    });
  </script>

</body>
</html>
