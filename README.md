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
  <source src="YOUR_AUDIO_FILE.mp3" type="audio/mpeg">
</audio>

<script>
  // Prevent pausing
  const audio = document.getElementById("audio");
  audio.onpause = () => audio.play();
</script>


<!-- GOOGLE FORM EMBED -->
<iframe 
  src="https://docs.google.com/forms/d/e/1FAIpQLSdpd2M0HGkUM9dLuYjxFOvTqHreGqKe0WIGFKCieSA54OQ9YA/viewform?usp=header"
  width="100%" 
  height="1200"
  frameborder="0" 
  marginheight="0" 
  marginwidth="0">
  Loading…
</iframe>

</body>
</html>
