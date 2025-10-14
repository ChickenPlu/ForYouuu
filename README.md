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
      left: 45%;
      top: 55%;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      left: calc(45% + 120px); /* cách nút xanh 120px, không đè nhau */
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

    <div class="heart-loader">anh cám ơn ebe 💞</div>
    <div class="result-container">anh cũng yêu ebe nữaaa 😍💘</div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const heartLoader = document.querySelector(".heart-loader");
    const resultContainer = document.querySelector(".result-container");

    // Hàm random vị trí, tránh ra ngoài
    function moveButton() {
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;
      const maxX = window.innerWidth - btnWidth - 10;
      const maxY = window.innerHeight - btnHeight - 10;
      const newX = Math.floor(Math.random() * maxX);
      const newY = Math.floor(Math.random() * maxY);
      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    // Khi rê chuột (PC)
    noBtn.addEventListener("mouseover", moveButton);

    // Khi chạm (điện thoại)
    noBtn.addEventListener("touchstart", moveButton);

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
