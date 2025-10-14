#hello bae 
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bạn có thích tôi không?</title>
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
      left: 45%;
      top: 55%;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      left: 55%;
      top: 55%;
    }

    .heart-loader, .result-container {
      display: none;
      font






Bạn đã nói:
code v là hoàn chỉnh chưa


ChatGPT đã nói:
Gần hoàn rồi 😄 — chỉ thiếu phần cuối (một đoạn bị cắt dở) và cần sửa chỗ chuỗi template trong JavaScript.
Dưới đây là phiên bản hoàn chỉnh, copy là chạy ngay 👇

✅ Code HTML đầy đủ và hoạt động tốt
html
Sao chép mã
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bạn có thích tôi không?</title>
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
      left: 45%;
      top: 55%;
    }

    #noBtn {
      background-color: #f44336;
      color: white;
      left: 55%;
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
    <h2>Bạn có thích tôi không? 💖</h2>
    <button id="yesBtn">Có 🥰</button>
    <button id="noBtn">Không 😜</button>

    <div class="heart-loader">Đang suy nghĩ... 💞</div>
    <div class="result-container">Tôi biết mà 😍💘</div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const heartLoader = document.querySelector(".heart-loader");
    const resultContainer = document.querySelector(".result-container");

    // Khi rê chuột vào nút "Không" → nó chạy trốn
    noBtn.addEventListener("mouseover", () => {
      const newX = Math.floor(Math.random() * (window.innerWidth - 150));
      const newY = Math.floor(Math.random() * (window.innerHeight - 100));
      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    });

    // Khi bấm "Có" → hiện kết quả
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
