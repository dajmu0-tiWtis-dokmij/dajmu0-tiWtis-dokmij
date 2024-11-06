<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kick Animation</title>
  <style>
    /* Основные стили */
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f0f0;
      overflow: hidden;
    }

    .character {
      font-size: 50px;
      position: absolute;
      bottom: 50px;
      left: 50px;
      cursor: pointer;
    }

    .icon {
      font-size: 40px;
      position: absolute;
      bottom: 50px;
      left: 150px;
      transition: transform 0.3s;
    }

    /* Анимация для "пинка" */
    @keyframes kickAnimation {
      0% {
        transform: translateX(0) translateY(0) rotate(0deg);
      }
      50% {
        transform: translateX(200px) translateY(-100px) rotate(180deg);
      }
      100% {
        transform: translateX(400px) translateY(0) rotate(360deg);
      }
    }

    .icon.kicked {
      animation: kickAnimation 0.8s ease-out forwards;
    }
  </style>
</head>
<body>
  <div class="character" id="character">👟</div>
  <div class="icon" id="icon">
    <img src="https://cdn-icons-png.flaticon.com/512/8281/8281819.png" alt="icon" width="50">
  </div>

  <script>
    document.addEventListener("DOMContentLoaded", function() {
      const character = document.getElementById("character");
      const icon = document.getElementById("icon");

      if (character && icon) {
        character.addEventListener("click", () => {
          icon.classList.add("kicked");
          setTimeout(() => {
            icon.classList.remove("kicked");
          }, 800);
        });
      }
    });
  </script>
</body>
</html>
