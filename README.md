#hello bae
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ebe có yêu tớ hongg..?</title>
  <style>
    body {
      font-family: "Segoe UI", sans-serif;
      background: linear-gradient(135deg, #ffd6e7, #d6f0ff);
      height: 100vh;
      overflow: hidden;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }

    h2 {
      font-size: 28px;
      color: #333;
    }

    .question-container {
      position: relative;
      width: 100%;
      height: 80vh;
    }

    button {
      position: absolute;
      padding: 10px 25px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.2s;
    }

    #yesBtn {
      background-color: #4caf50;
      color: white;
      left: 40%;
      top: 55%;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      left: calc(40% + 120px); /* cách nút xanh khoảng 45px */
      top: 55%;
    }

    .heart-loader, .result-container {
      display: none;
      font-size: 24px;
      color: #ff0077;
      margin-top: 20px;
      animation: fadeIn 1s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>
  <div class="question-container">
    <h2>Ebe có yêu tớ hongg..? 💖</h2>
    <button id="yesBtn">Có 🥰</button>
    <button id="noBtn">Không 😜</button>

    <div class="heart-loader">Anh cám ơn ebe 💞</div>
    <div class="result-container">Anh cũng yêu ebe nữaaa 😍💘</div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const heartLoader = document.querySelector(".heart-loader");
    const resultContainer = document.querySelector(".result-container");

    function moveButton() {
      const padding = 10; // ~1cm cách rìa màn hình
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;

      const maxX = window.innerWidth - btnWidth - padding;
      const maxY = window.innerHeight - btnHeight - padding;

      const newX = Math.floor(Math.random() * (maxX - padding) + padding);
      const newY = Math.floor(Math.random() * (maxY - padding) + padding);

      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    // Chỉ chạy khi ấn vào nút đỏ (dù PC hay điện thoại)
    noBtn.addEventListener("click", (e) => {
      e.preventDefault();
      moveButton();
    });

    noBtn.addEventListener("touchstart", (e) => {
      e.preventDefault();
      moveButton();
    });

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
