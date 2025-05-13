<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Счётчик строительства</title>
  <style>
    body { font-family: sans-serif; padding: 20px; background: #f0f0f0; }
    .timer { font-size: 22px; font-weight: bold; color: darkred; margin-top: 10px; }
    .section { margin-bottom: 12px; }
  </style>
</head>
<body>
  <h1>Информация о строительстве</h1>
  <div class="section"><strong>Объект:</strong> Жилой дом №1, ЖК «Солнечный»</div>
  <div class="section"><strong>Дата разрешения:</strong> 01.06.2023</div>
  <div class="section"><strong>Заказчик:</strong> ООО «СтройИнвест»</div>
  <div class="section"><strong>Проектировщик:</strong> ЗАО «АрхГрупп»</div>
  <div class="section"><strong>Подрядчик:</strong> ООО «МонолитСтрой»</div>
  <div class="section"><strong>Адрес:</strong> г. Москва, ул. Примерная, 10</div>
  <div class="section"><strong>Реестр:</strong> RU-123456-AB</div>
  <div class="section"><strong>До окончания:</strong> <div id="countdown" class="timer"></div></div>

  <script>
    const endDate = new Date("2025-12-31T23:59:59");
    function updateCountdown() {
      const now = new Date();
      const diff = endDate - now;
      if (diff <= 0) {
        document.getElementById("countdown").innerText = "Строительство завершено.";
        return;
      }
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);
      document.getElementById("countdown").innerText =
        `${days} дн. ${hours} ч. ${minutes} мин. ${seconds} сек.`;
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();
  </script>
</body>
</html>
