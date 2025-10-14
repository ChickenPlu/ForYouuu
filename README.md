#hello bae
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ebe có yêu anh hongg..?</title>
  <style>
    * { box-sizing: border-box; }
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
      touch-action: none;
    }

    h2 {
      font-size: 6vw;
      color: #333;
      margin-bottom: 40px;
    }

    .question-container {
      position: relative;
      width: 100%;
      height: 60vh;
    }

    button {
      position: absolute;
      padding: 12px 30px;
      font-size: 5vw;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.2s;
      user-select: none;
    }

    /* Nút "Có" bên trái giữa */
    #yesBtn {
      background-color: #4caf50;
      color: white;
      left: 35%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    /* Nút "Không" bên phải giữa */
    #noBtn {
      background-color: #f44336;
      color: white;
      left: 65%;
      top: 50%;
      transform: translate(-50%, -50%);
      z-index: 10;
    }

    .heart-loader, .result-container {
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
      h2 { font-size: 28px; }
      button { font-size: 18px; }
      .heart-loader, .result-container { font-size: 24px; }
    }
  </style>
</head>
<body>
  <div class="question-container">
    <h2>Ebe có yêu anh hongg..?💖</h2>
    <button id="yesBtn">Dạ Có 🥰</button>
    <button id="noBtn">Không thèmm 😜</button>
    <div class="heart-loader">Cám ơn bé nhaaa 💞</div>
    <div class="result-container">Anh cũng yêu béeee 😍💘</div>
  </div>

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
      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    // Né chuột trên PC
    noBtn.addEventListener("mouseover", moveNoBtn);

    // Né tay trên điện thoại
    noBtn.addEventListener("touchstart", (e) => {
      e.preventDefault();
      moveNoBtn();
    });

    // Dự phòng nếu click
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
