<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ebe có yêu anh hongg..?</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      font-family: "Segoe UI", sans-serif;
      background: linear-gradient(135deg, #ffd6e7, #d6f0ff);
      height: 100vh;
      margin: 0;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      touch-action: none; /* Ngăn zoom/kéo trang khi chạm */
    }

    h2 {
      font-size: 6vw;
      color: #333;
      margin-bottom: 30px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 40px; /* khoảng cách giữa 2 nút */
      margin-top: 40px;
      position: relative;
    }

    button {
      padding: 12px 30px;
      font-size: 5vw;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.2s;
      user-select: none;
      position: relative;
    }

    #yesBtn {
      background-color: #4caf50;
      color: white;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      z-index: 10;
    }

    .heart-loader,
    .result-container {
      display: none;
      font-size: 6vw;
      color: #ff0077;
      margin-top: 30px;
      animation: fadeIn 1s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @media (min-width: 768px) {
      h2 {
        font-size: 28px;
      }
      button {
        font-size: 18px;
      }
      .heart-loader,
      .result-container {
        font-size: 24px;
      }
    }
  </style>
</head>
<body>
  <h2>Ebe có yêu anh hongg..? 💖</h2>

  <div class="buttons">
    <button id="yesBtn">Dạ Có 🥰</button>
    <button id="noBtn">Không thèm 😜</button>
  </div>

  <div class="heart-loader">Cám ơn bé nhaaa 💞</div>
  <div class="result-container">Anh cũng yêu béeee 😍💘</div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const heartLoader = document.querySelector(".heart-loader");
    const resultContainer = document.querySelector(".result-container");

    function moveNoBtn() {
      const maxX = window.innerWidth - noBtn.offsetWidth - 20;
      const maxY = window.innerHeight - noBtn.offsetHeight - 20;
      const newX = Math.random() * maxX;
      const newY = Math.random() * maxY;
      noBtn.style.position = "absolute";
      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    // Khi rê hoặc chạm vào nút "Không" → chạy trốn
    noBtn.addEventListener("mouseover", moveNoBtn);
    noBtn.addEventListener("touchstart", (e) => {
      e.preventDefault();
      moveNoBtn();
    });
    noBtn.addEventListener("click", (e) => {
      e.preventDefault();
      moveNoBtn();
    });

    // Khi bấm "Có"
    yesBtn.addEventListener("click", () => {
      heartLoader.style.display = "block";
      setTimeout(() => {
        heartLoader.style.display = "none";
        resultContainer.style.display = "block";
      }, 2000);
    });
  </script>
</body>
</html>
