<!-- digital_clock.html -->
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>⏰ ساعت دیجیتال</title>
  <style>
    body {
      font-family: sans-serif;
      background: linear-gradient(135deg, #667eea, #764ba2);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      color: white;
      text-align: center;
    }
    .clock {
      font-size: 60px;
      font-weight: bold;
      background: rgba(255, 255, 255, 0.1);
      padding: 20px 40px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    }
    .date {
      margin-top: 15px;
      font-size: 22px;
      opacity: 0.8;
    }
  </style>
</head>
<body>
  <div>
    <div class="clock" id="clock">00:00:00</div>
    <div class="date" id="date"></div>
  </div>

  <script>
    function updateClock() {
      const now = new Date();
      const hours = String(now.getHours()).padStart(2, "0");
      const minutes = String(now.getMinutes()).padStart(2, "0");
      const seconds = String(now.getSeconds()).padStart(2, "0");

      document.getElementById("clock").textContent = `${hours}:${minutes}:${seconds}`;

      const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
      document.getElementById("date").textContent = now.toLocaleDateString('fa-IR', options);
    }

    setInterval(updateClock, 1000);
    updateClock();
  </script>
</body>
</html>
