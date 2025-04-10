<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Кохаю тебе, моє сонечко</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(120deg, #ffecd2, #fcb69f);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      overflow: auto;
    }

    .container {
      text-align: center;
      color: #fff;
      padding: 20px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 20px;
      box-shadow: 0 0 20px rgba(0,0,0,0.2);
      backdrop-filter: blur(10px);
      margin-bottom: 20px;
      max-width: 90%;
    }

    h1 {
      font-size: 5vw; /* Замінили на vw для адаптивності */
      margin-bottom: 10px;
    }

    p {
      font-size: 3vw; /* Замінили на vw для адаптивності */
      margin-top: 0;
    }

    .photos {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
      margin-bottom: 20px;
      max-width: 90%;
    }

    .photos img {
      width: 100%;
      max-width: 300px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }

    .audio {
      margin-bottom: 20px;
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .hearts {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 0;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 8s linear infinite;
    }

    .heart::before, .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }

    /* Медіа-запити для мобільних пристроїв */
    @media (max-width: 600px) {
      h1 {
        font-size: 8vw;
      }

      p {
        font-size: 5vw;
      }

      .photos img {
        max-width: 100%;
      }

      .container {
        padding: 15px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Кохаю тебе, моє сонечко 🌞</h1>
    <p>Ти — найкраще, що зі мною траплялося 💛</p>
  </div>

  <div class="photos">
    <img src="https://i.postimg.cc/HsNYrsQ0/photo2-jpg.jpg" alt="Наша пара">
    <img src="https://i.postimg.cc/52Z2RNy9/photo1-jpg.jpg" alt="Photo 2">
    <img src="https://i.postimg.cc/L6qtYDqJ/photo3-jpg.jpg" alt="Photo 3">
  </div>

  <div class="audio">
    <audio controls autoplay loop>
      <source src="https://muzka.cc/uploads/files/2023-03/1679586978_tik-bez-tebe.mp3" type="audio/mpeg">
      Ваш браузер не підтримує аудіо.
    </audio>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    const heartsContainer = document.getElementById('hearts');

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (5 + Math.random() * 5) + 's';
      heartsContainer.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 10000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>
