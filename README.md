<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Like, Subscribe & Download</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #f0f0f0;
      padding: 30px;
    }
    input {
      width: 80%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    button {
      padding: 12px 20px;
      margin: 10px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }
    .like-btn, .sub-btn {
      background-color: #ff0000;
      color: white;
    }
    .download-btn {
      background-color: #4CAF50;
      color: white;
    }
    .download-btn:disabled {
      background-color: #aaa;
      cursor: not-allowed;
    }
  </style>
</head>
<body>

  <h2>Like, Subscribe, lalu Download</h2>

  <input type="url" id="videoUrl" placeholder="Masukkan URL Video YouTube (Like)">
  <br>
  <input type="url" id="channelUrl" placeholder="Masukkan URL Channel YouTube (Subscribe)">
  <br>
  <input type="url" id="downloadUrl" placeholder="Masukkan URL Mediafire (Download)">
  <br><br>

  <button class="like-btn" onclick="openLike()">👍 Like Video</button>
  <button class="sub-btn" onclick="openSubscribe()">🔔 Subscribe Channel</button>
  <br><br>

  <button class="download-btn" id="downloadBtn" disabled onclick="startDownload()">📥 Download Sekarang</button>

  <script>
    let liked = false;
    let subscribed = false;

    function openLike() {
      const url = document.getElementById("videoUrl").value;
      if (url) {
        liked = true;
        window.open(url, "_blank");
        checkDownloadReady();
      } else {
        alert("Masukkan URL video YouTube dulu.");
      }
    }

    function openSubscribe() {
      const url = document.getElementById("channelUrl").value;
      if (url) {
        subscribed = true;
        window.open(url, "_blank");
        checkDownloadReady();
      } else {
        alert("Masukkan URL channel YouTube dulu.");
      }
    }

    function checkDownloadReady() {
      if (liked && subscribed) {
        document.getElementById("downloadBtn").disabled = false;
      }
    }

    function startDownload() {
      const url = document.getElementById("downloadUrl").value;
      if (url) {
        window.open(url, "_blank");
      } else {
        alert("Masukkan URL download Mediafire dulu.");
      }
    }
  </script>

</body>
</html>
