<!DOCTYPE html> 
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title></title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      background: #000;
      height: 100%;
      width: 100%;
      overflow: hidden;
    }

    video {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      background-color: #000;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <video id="video" autoplay muted playsinline></video>

  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <script>
    const video = document.getElementById('video');
[const src = "https://shlsakamai4.akamaized.net/hlsorigin/mountaineer_hd_fm_2200/chunklist.m3u8?streahttps://shlsakamai4.akamaized.net/hlsorigin/gulfstream_hd_fm_771/chunklist.m3u8?const src = "https://shlsakamai4.akamaized.net/hlsorigin/mountaineer_hd_fm_2200/chunklist.m3u8?stream=gulfstream_mbr&cust=TVG&user=&t=1745883258&h=891e8787b2d88706da2ceb9808542c78&type=live";(https://shlsakamai4.akamaized.net/hlsorigin/gulfstream_hd_fm_771/chunklist.m3u8?stream=gulfstream_mbr&cust=TVG&user=&t=1745883018&h=85a5cb26fba8c1aff516bac1be2a199b&type=live)

    if (Hls.isSupported()) {
      const hls = new Hls();
      hls.loadSource(src);
      hls.attachMedia(video);
      hls.on(Hls.Events.MANIFEST_PARSED, () => {
        video.play();
      });
    } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = src;
      video.addEventListener('loadedmetadata', () => {
        video.play();
      });
    }

    // Click para pantalla completa
    video.addEventListener('click', () => {
      if (video.requestFullscreen) {
        video.requestFullscreen();
      } else if (video.webkitRequestFullscreen) {
        video.webkitRequestFullscreen();
      } else if (video.msRequestFullscreen) {
        video.msRequestFullscreen();
      }
    });
  </script>
</body>
</html>
