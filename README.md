<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Angga Maula Insani</title>
  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@500;700&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 1rem;
      background: #ffc0cb;
      font-family: 'Quicksand', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .card {
      background: white;
      padding: 2rem;
      border-radius: 20px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
      text-align: center;
      width: 100%;
      max-width: 400px;
    }

    .image-row {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 1rem;
      margin-bottom: 1rem;
    }

    .cake-image {
      width: 100px;
      height: auto;
    }

    h1 {
      color: #ff1493;
      font-size: 2rem;
      margin-top: 0.5rem;
    }

    p {
      color: #888;
      font-size: 1rem;
    }

    .btn {
      background: linear-gradient(to right, #ff69b4, #ff1493);
      color: white;
      padding: 0.8rem 1.5rem;
      border: none;
      border-radius: 50px;
      margin-top: 1.5rem;
      font-size: 1rem;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .btn:hover {
      transform: scale(1.05);
    }

    .balloons, .fireworks, .confetti {
      position: absolute;
      width: 100%;
      left: 0;
      display: flex;
      justify-content: space-around;
      pointer-events: none;
    }

    .balloons {
      top: -30px;
      animation: float 3s infinite ease-in-out;
    }

    .fireworks {
      bottom: -30px;
      animation: burst 2s infinite;
    }

    .confetti {
      top: 0;
      animation: fall 5s infinite linear;
    }

    .balloon, .firework, .confetto {
      width: 20px;
      height: 30px;
      background: #ff69b4;
      border-radius: 50%;
    }

    .firework {
      width: 10px;
      height: 10px;
    }

    .confetto {
      width: 8px;
      height: 8px;
      background: #fff;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0); }
    }

    @keyframes burst {
      0% { transform: scale(1); opacity: 1; }
      100% { transform: scale(1.5); opacity: 0; }
    }

    @keyframes fall {
      0% { transform: translateY(-100px); }
      100% { transform: translateY(500px); }
    }

    .animated-text {
      margin-top: 2rem;
      font-size: 1.2rem;
      color: #ff1493;
      animation: fadein 3s ease-in-out infinite;
    }

    @keyframes fadein {
      0% { opacity: 0; }
      50% { opacity: 1; }
      100% { opacity: 0; }
    }

    .video-popup {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .video-popup video {
      max-width: 90%;
      max-height: 80%;
      border-radius: 20px;
    }

    .video-popup.show {
      display: flex;
    }
  </style>
</head>
<body onload="bgMusic.play()">
  <div class="card">
    <div class="balloons">
      <div class="balloon"></div>
      <div class="balloon"></div>
      <div class="balloon"></div>
    </div>
    <div class="fireworks">
      <div class="firework" style="background:#ff1493"></div>
      <div class="firework" style="background:#ffa07a"></div>
    </div>
    <div class="confetti">
      <div class="confetto"></div>
      <div class="confetto"></div>
      <div class="confetto"></div>
    </div>
    <div class="image-row">
      <img src="birthday_cake.png.png" alt="Birthday Cake" class="cake-image" />
    </div>
    <h1>Happy 20th Birthday, Sayang! 🎉</h1>
    <p>Selamat ulang tahun yang ke-20 ya, cintaku! 🥰 Semoga semua impian sayang makin dekat dan hari-hari sayang selalu penuh tawa dan peluk hangat dari akuu!</p>
    <button class="btn" onclick="showVideo()">Tonton video ini yah sayang 🎥</button>
    <div class="animated-text">Semoga hari sayangg penuh cinta dan kejutan manis 💖</div>
    <div style="margin-top: 2rem; font-weight: bold; color: #ff1493;">From : Angga Maula Insani</div>
  </div>

  <div class="video-popup" id="videoPopup" onclick="hideVideo()">
    <video id="birthdayVideo" controls>
      <source src="lv_0_20250419212416.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>

  <audio id="openSound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_958e53b6b1.mp3"></audio>
  <audio id="bgMusic" src="(Synthesia) Romantic Happy Birthday (arr. Miranda Wong)  Piano Cover by Seander Alfonsus.mp3" loop></audio>

  <script>
    const bgMusic = document.getElementById('bgMusic');
    const birthdayVideo = document.getElementById('birthdayVideo');

    function showVideo() {
      document.getElementById('videoPopup').classList.add('show');
      document.getElementById('openSound').play();
      bgMusic.pause();
    }

    function hideVideo() {
      const popup = document.getElementById('videoPopup');
      popup.classList.remove('show');
      birthdayVideo.pause();
      bgMusic.play();
    }
  </script>
</body>
</html>
