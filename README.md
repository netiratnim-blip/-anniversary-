<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Anniversary ❤️</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    }
    body {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ffd1dc, #ffe6eb, #e0c3fc);
      overflow-x: hidden;
      padding: 20px;
      position: relative;
    }
    .card {
      background: rgba(255, 255, 255, 0.9);
      backdrop-filter: blur(10px);
      border-radius: 24px;
      padding: 32px 24px;
      max-width: 420px;
      width: 100%;
      text-align: center;
      box-shadow: 0 15px 35px rgba(230, 80, 110, 0.2);
      z-index: 10;
    }
    h1 {
      color: #e63946;
      font-size: 26px;
      margin-bottom: 8px;
    }
    .subtitle {
      color: #666;
      font-size: 14px;
      margin-bottom: 24px;
    }
    .timer-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      margin-bottom: 24px;
    }
    .timer-box {
      background: #fff0f3;
      border: 1px solid #ffccd5;
      border-radius: 14px;
      padding: 12px 6px;
    }
    .timer-num {
      color: #d90429;
      font-size: 22px;
      font-weight: 700;
    }
    .timer-label {
      font-size: 11px;
      color: #888;
      margin-top: 4px;
    }
    .message-btn {
      background: linear-gradient(135deg, #ff4d6d, #ff758f);
      color: white;
      border: none;
      border-radius: 50px;
      padding: 12px 28px;
      font-size: 15px;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 6px 16px rgba(255, 77, 109, 0.35);
      transition: transform 0.2s;
    }
    .message-btn:active {
      transform: scale(0.96);
    }
    .message-box {
      display: none;
      margin-top: 20px;
      padding: 16px;
      background: #fff8f9;
      border-radius: 16px;
      border: 1px dashed #ff758f;
      color: #444;
      font-size: 14px;
      line-height: 1.6;
    }
    .heart {
      position: absolute;
      color: #ff4d6d;
      font-size: 18px;
      animation: floatUp 4s linear infinite;
      opacity: 0.7;
      z-index: 1;
      pointer-events: none;
    }
    @keyframes floatUp {
      0% { transform: translateY(100vh) scale(0.5); opacity: 0; }
      20% { opacity: 0.8; }
      100% { transform: translateY(-10vh) scale(1.2); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Happy Anniversary ❤️</h1>
    <p class="subtitle">เราเดินข้างกันมานานแค่ไหนแล้วนะ</p>

    <div class="timer-grid">
      <div class="timer-box">
        <div class="timer-num" id="days">0</div>
        <div class="timer-label">วัน</div>
      </div>
      <div class="timer-box">
        <div class="timer-num" id="hours">0</div>
        <div class="timer-label">ชั่วโมง</div>
      </div>
      <div class="timer-box">
        <div class="timer-num" id="minutes">0</div>
        <div class="timer-label">นาที</div>
      </div>
      <div class="timer-box">
        <div class="timer-num" id="seconds">0</div>
        <div class="timer-label">วินาที</div>
      </div>
    </div>

    <button class="message-btn" onclick="toggleMessage()">กดเปิดการ์ดตรงนี้ 💌</button>

    <div class="message-box" id="message">
      ขอบคุณที่เข้ามาเป็นรอยยิ้มและความสุขให้กันเสมอในทุกๆ วันนะ<br/>
      รักและอยากอยู่ฉลองวันครบรอบด้วยกันแบบนี้ไปเรื่อยๆ เลยนะคับ ✨
    </div>
  </div>

  <script>
    // เปลี่ยนใส่วันที่เริ่มคบกันตรงนี้ (รูปแบบ: ปี-เดือน-วัน)
    const startDate = new Date("2024-02-14T00:00:00");

    function updateTimer() {
      const now = new Date();
      const diff = now - startDate;

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      document.getElementById("days").innerText = days;
      document.getElementById("hours").innerText = hours;
      document.getElementById("minutes").innerText = minutes;
      document.getElementById("seconds").innerText = seconds;
    }
    setInterval(updateTimer, 1000);
    updateTimer();

    function toggleMessage() {
      const box = document.getElementById("message");
      box.style.display = box.style.display === "block" ? "none" : "block";
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 2 + 3 + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 4000);
    }
    setInterval(createHeart, 450);
  </script>
</body>
</html>
