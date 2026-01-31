<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For Malk 💖</title>
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
    }

    .card {
      background: white;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
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
