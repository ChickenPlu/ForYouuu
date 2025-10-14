#hello bae 
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ebe có yêu tớ hongg..?</title>
  <style>
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
    }

    h2 {
      font-size: 28px;
      color: #333;
      margin-bottom: 40px;
    }

    .button-box {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 40px; /* khoảng cách giữa 2 nút */
    }

    button {
      padding: 12px 30px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      user-select: none;
      transition: 0.2s;
    }

    #yesBtn {
      background-color: #4caf50;
      color: white;
      z-index: 2;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      position: absolute;
      z-index: 3;
    }

    .heart-loader,
    .result-container {
      display: none;
      font-size: 22px;
      color: #ff0077;
      margin-top: 30px;
      animation: fadeIn 1s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>
  <h2>Ebe có yêu tớ hongg..? 💖</h2>

  <div class="button-box">
    <button id="yesBtn">Có 🥰</button>
    <button id="noBtn">Không 😜</button>
  </div>

  <div class="heart-loader">Anh cám ơn ebe 💞</div>
  <div class="result-container">Anh cũng yêu ebe nữaaa 😍💘</div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const heartLoader = document.querySelector(".heart-loader");
    const resultContainer = document.querySelector(".result-container");

    let dx = 4; // tốc độ chạy ngang
    let dy = 3; // tốc độ chạy dọc

    // Đặt vị trí ban đầu
    let x = window.innerWidth / 2 + 100;
    let y = window.innerHeight / 2;

    function moveNoBtn() {
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;

      x += dx;
      y += dy;

      // Va chạm rìa màn hình → bật ngược hướng
      if (x + btnWidth >= window.innerWidth || x <= 0) dx = -dx;
      if (y + btnHeight >= window.innerHeight || y <= 0) dy = -dy;

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";

      requestAnimationFrame(moveNoBtn);
    }

    // Bắt đầu chuyển động
    moveNoBtn();

    // Khi nhấn nút "Có"
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
