<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>إزيك يا كبدة</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #fbeedb;
      font-family: 'Arial', sans-serif;
      overflow-x: hidden;
    }
    h1, h2, p {
      text-align: center;
      color: #b30000;
    }
    .button, .heart-button {
      display: block;
      margin: 40px auto;
      padding: 15px 30px;
      font-size: 20px;
      background-color: #ff6699;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .hidden {
      display: none;
    }
    .heart {
      width: 10px;
      height: 10px;
      background-color: red;
      position: absolute;
      top: -10px;
      left: 50%;
      animation: float 6s linear infinite;
      opacity: 0.7;
      transform: rotate(45deg);
    }
    .heart:before, .heart:after {
      content: '';
      width: 10px;
      height: 10px;
      background-color: red;
      position: absolute;
      border-radius: 50%;
    }
    .heart:before {
      top: -5px;
      left: 0;
    }
    .heart:after {
      left: -5px;
      top: 0;
    }
    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 0.7;
      }
      100% {
        transform: translateY(-800px) rotate(45deg);
        opacity: 0;
      }
    }
    .love-page {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background-color: #fff0f5;
      display: none;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 10;
    }
    .big-heart {
      font-size: 100px;
      color: red;
    }
    .love-message {
      font-size: 20px;
      margin-top: 20px;
      color: #b30000;
      max-width: 80%;
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>إزيك يا كبدة وحشتني</h1>
  <button class="button" onclick="startCelebration()">لو خلصت الـ10 ساعات أو أكتر اضغط هنا</button>

  <div id="celebration" class="hidden">
    <h2>والله وعملوها الرجالة</h2>
    <audio autoplay>
      <source src="https://dl.sndup.net/k3gq/%D8%AD%D9%84%D9%85%20%D8%A7%D9%84%D8%B9%D9%85%D8%B1.mp3" type="audio/mpeg">
    </audio>
    <button class="heart-button" onclick="showLove()">Y</button>
  </div>

  <div class="love-page" id="lovePage">
    <div class="big-heart">❤️</div>
    <div class="love-message">
      فخورة بيك جدا لأبعد الحدود وبتمنى تستمر على ده، بحبك وهفضل أحبك لآخر العمر.
    </div>
  </div>

  <script>
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.backgroundColor = Math.random() > 0.5 ? "#ff4d4d" : "#ff66b3";
      document.body.appendChild(heart);
      setTimeout(() => { heart.remove(); }, 6000);
    }
    setInterval(createHeart, 200);

    function startCelebration() {
      document.getElementById("celebration").classList.remove("hidden");
    }

    function showLove() {
      document.getElementById("lovePage").style.display = "flex";
    }
  </script>
</body>
</html>
