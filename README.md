<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kenya Life Radio</title>

<!-- HLS Player -->
<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>

<style>
:root{
  --bg-image: url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e');
  --cover-image: url('https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4');
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  color: #fff;
  background: var(--bg-image) no-repeat center center fixed;
  background-size: cover;
}

.overlay {
  background: rgba(0,0,0,0.6);
  min-height: 100vh;
  padding: 20px;
}

.header {
  text-align: center;
  padding: 20px;
}

.logo {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #00d4ff;
}

.title {
  font-size: 28px;
  font-weight: bold;
  margin-top: 10px;
}

.cover {
  width: 100%;
  max-width: 500px;
  border-radius: 12px;
  margin: 20px auto;
  display: block;
}

.player-box {
  max-width: 500px;
  margin: auto;
  background: rgba(0,0,0,0.5);
  padding: 20px;
  border-radius: 12px;
}

button {
  background: #00d4ff;
  border: none;
  padding: 12px 18px;
  margin: 5px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background: #00a3c4;
}

.status {
  margin-top: 10px;
  color: #00ff99;
}

a {
  color: #00d4ff;
  text-decoration: none;
}
</style>
</head>

<body>
<div class="overlay">

<!-- HEADER -->
<div class="header">
  <!-- EDIT LOGO HERE -->
  <img src="https://via.placeholder.com/120" class="logo" alt="Logo">

  <div class="title">Kenya Life Radio</div>
  <p>Live Gospel • Talk • Music • News</p>
</div>

<!-- COVER PHOTO -->
<img src="https://via.placeholder.com/800x400" class="cover" alt="Cover">

<!-- PLAYER -->
<div class="player-box">

  <h2>🎧 Listen Live</h2>

  <video id="radio" controls autoplay style="width:100%;border-radius:10px;"></video>

  <div class="status" id="status">🔴 Connecting...</div>

  <button onclick="playRadio()">▶ Play</button>
  <button onclick="pauseRadio()">⏸ Pause</button>
  <button onclick="openStream()">🌐 Open Stream</button>
  <button onclick="openYouTube()">▶ Watch on YouTube</button>

  <p>
    🔗 Backup: <a href="https://goliveafrica.media/live/1/KENYALIFERADIO" target="_blank">GoLive Stream</a>
  </p>

</div>

</div>

<script>
const stream = "https://goliveafrica.media:9998/live/69fa1ca4e2dad/index.m3u8";
const video = document.getElementById('radio');
const status = document.getElementById('status');

function initStream() {
  if (Hls.isSupported()) {
    const hls = new Hls();
    hls.loadSource(stream);
    hls.attachMedia(video);
    hls.on(Hls.Events.MANIFEST_PARSED, function() {
      video.play();
      status.innerText = "🔴 LIVE - Streaming Now";
    });

    hls.on(Hls.Events.ERROR, function() {
      status.innerText = "⚠ Stream error - using fallback";
    });
  } else {
    video.src = stream;
    video.play();
  }
}

function playRadio(){
  video.play();
  status.innerText = "🔴 LIVE";
}

function pauseRadio(){
  video.pause();
  status.innerText = "⏸ Paused";
}

function openStream(){
  window.open("https://goliveafrica.media/live/1/KENYALIFERADIO", "_blank");
}

function openYouTube(){
  window.open("https://www.youtube.com/@kenyaliferadio", "_blank");
}

initStream();
</script>

</body>
</html>
