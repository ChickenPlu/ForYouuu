#hello bae  <!DOCTYPE html>
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
      margin-bottom: 50px;
    }

    .button-area {
      position: relative;
      width: 100%;
      height: 150px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    button {
      padding: 16px 40px;
      font-size: 5vw;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      transition: 0.2s;
      user-select: none;
      min-width: 150px;
    }

    #yesBtn {
      background-color: #4caf50;
      color: white;
      z-index: 5;
      position: relative;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      position: absolute;
      top: 50%;
      left: 60%;
      transform: translate(-50%, -50%);
      z-index: 10;
    }

    .heart-loader,
    .result-container {
      display: none;
      font-size: 6vw;
      color: #ff0077;
      margin-top: 40px;
      animation: fadeIn 1s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @media (min-width: 768px) {
      h2 { font-size: 28px; }
      button { font-size: 20px; padding: 12px 30px; }
      .heart-loader, .result-container { font-size: 24px; }
    }
  </style>
</head>
<body>
  <h2>Ebe có yêu anh hongg..?💖</h2>

  <div class="button-area" id="buttonArea">
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
    const area = document.getElementById("buttonArea");

    function moveNoBtn() {
      const areaRect = area.getBoundingClientRect();
      const btnW = noBtn.offsetWidth;
      const btnH = noBtn.offsetHeight;

      // Giới hạn di chuyển trong vùng hiển thị
      const maxX = areaRect.width - btnW - 10;
      const maxY = areaRect.height - btnH - 10;

      // Random vị trí mới (tránh quá gần nút xanh)
      let newX = Math.random() * maxX;
      let newY = Math.random() * maxY;

      // Giữ nút trong vùng an toàn giữa màn hình
      newX = Math.max(0, Math.min(newX, areaRect.width - btnW));
      newY = Math.max(0, Math.min(newY, areaRect.height - btnH));

      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    // Né chuột (PC)
    noBtn.addEventListener("mouseover", moveNoBtn);

    // Né tay (điện thoại)
    noBtn.addEventListener("touchstart", (e) => {
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
