<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bio Page</title>
<style>
  /* Сброс стилей */
  * { margin: 0; padding: 0; box-sizing: border-box; }

  /* Видео-фон */
  body, html {
    height: 100%;
    font-family: Arial, sans-serif;
    color: #fff;
    overflow: hidden;
  }

  .video-bg {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    object-fit: cover;
    z-index: -1;
  }

  /* Полупрозрачный градиент */
  .overlay {
    position: fixed;
    top:0; left:0;
    width:100%; height:100%;
    background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5));
    z-index: 0;
  }

  /* Контент */
  .content {
    position: relative;
    z-index: 1;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    gap: 20px;
  }

  h1 {
    font-size: 3em;
    animation: fadeIn 2s ease-in;
  }

  .links {
    display: flex;
    flex-direction: column;
    gap: 15px;
    animation: fadeIn 3s ease-in;
  }

  .links a {
    text-decoration: none;
    color: #fff;
    padding: 10px 25px;
    background: rgba(255,255,255,0.2);
    border-radius: 25px;
    transition: 0.3s;
  }

  .links a:hover {
    background: rgba(255,255,255,0.5);
  }

  /* Анимация */
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px);}
    to { opacity: 1; transform: translateY(0);}
  }

  /* Музыка */
  #musicButton {
    padding: 10px 20px;
    border-radius: 20px;
    background: rgba(255,255,255,0.2);
    border: none;
    color: white;
    cursor: pointer;
    font-size: 16px;
    transition: 0.3s;
  }

  #musicButton:hover {
    background: rgba(255,255,255,0.5);
  }
</style>
</head>
<body>

<!-- Видео фон -->
<video class="video-bg" autoplay muted loop>
  <source src="assets/video.mp4" type="video/mp4">
</video>

<!-- Градиент -->
<div class="overlay"></div>

<!-- Контент -->
<div class="content">
  <h1>Привет, это мое био!</h1>
  <div class="links">
    <a href="https://instagram.com/" target="_blank">Instagram</a>
    <a href="https://t.me/" target="_blank">Telegram</a>
    <a href="https://youtube.com/" target="_blank">YouTube</a>
  </div>
  <button id="musicButton">Включить музыку</button>
  <audio id="bgMusic" loop>
    <source src="assets/music.mp3" type="audio/mpeg">
  </audio>
</div>

<script>
  const music = document.getElementById("bgMusic");
  const btn = document.getElementById("musicButton");

  btn.addEventListener("click", () => {
    if (music.paused) {
      music.play();
      btn.textContent = "Выключить музыку";
    } else {
      music.pause();
      btn.textContent = "Включить музыку";
    }
  });
</script>

</body>
</html>
