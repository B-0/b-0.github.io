<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Forced Audio Survey</title>
  <style>
    body { font-family: sans-serif; padding: 20px; }
  </style>
</head>
<body>

<h2>Please keep the audio playing while completing the survey.</h2>
<p>The audio starts automatically and cannot be paused.</p>

<!-- AUDIO PLAYER -->
<audio id="audio" autoplay>
  <source src="https://github.com/B-0/b-0.github.io/blob/main/printaudio2.mp3" type="audio/mpeg">
</audio>

<script>
  // Prevent pausing
  const audio = document.getElementById("audio");
  audio.onpause = () => audio.play();
</script>


<!-- GOOGLE FORM EMBED -->
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdBdmzNpWii84Xi_LnOSHlbBbF3AFNewAZ6ZZkS7rt4FK48Bw/viewform?embedded=true" width="640" height="602" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>

</body>
</html>
