<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Forced Audio Survey</title>
  <style>
    body { font-family: sans-serif; padding: 20px; text-align: center; }
    #content { display: none; }
  </style>
</head>
<body>

<h2>Click below to begin the survey.</h2>
<button id="startBtn" style="padding: 10px 20px; font-size: 18px;">Begin</button>

<div id="content">

  <h3>Please keep the audio playing while completing the survey.</h3>

  <!-- AUDIO -->
  <audio id="audio" autoplay>
    <source src="printaudio2.mp3" type="audio/mpeg">
  </audio>

  <script>
    const audio = document.getElementById("audio");
    audio.onpause = () => audio.play();
  </script>

  <!-- GOOGLE FORM -->
  <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdBdmzNpWii84Xi_LnOSHlbBbF3AFNewAZ6ZZkS7rt4FK48Bw/viewform?embedded=true" width="640" height="602" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>

</div>

<script>
  document.getElementById("startBtn").addEventListener("click", function() {
    document.getElementById("content").style.display = "block";
    this.style.display = "none";
    // Start audio after interaction
    const audio = document.getElementById("audio");
    audio.play();
  });
</script>

</body>
</html>
