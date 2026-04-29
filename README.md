<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Kuesioner Persepsi Sosial WNI</title>
  <style>
    body { font-family: sans-serif; padding: 20px; text-align: center; }
    #content { display: none; }
    #audioWarning { display: none; }
    #kode { display: none; }
    #kodeno { display: none; }
    #audio { display: none; }
  </style>
</head>

<script>
  // RANDOMIZE CONDITION: true = audio ON, false = audio OFF
  const audioCondition = Math.random() < 0.5;
</script>

<body>

<h1>Kuesioner Persepsi Sosial WNI</h1>
<h2>Tekan tombol "Mulai" di bawah ini untuk membuka kuesioner.</h2>

<!-- THIS TEXT SHOULD ONLY SHOW IF AUDIO IS ACTIVE -->
<h2 id="audioWarning">
Suara yang keluar dari kuesioner ini sangat penting. Anda dilarang untuk mematikan suara perangkat Anda selama mengerjakan kuesioner.</h2>

<h2 id ="kode">Kode verifikasi: AUD25</h2>
<h2 id ="kodeno">Kode verifikasi: NOA25</h2>

<button id="startBtn" style="padding: 10px 20px; font-size: 18px;">Mulai</button>

<div id="content">

  <!-- AUDIO -->
  <audio id="audio" autoplay>
    <source src="printaudio2.mp3" type="audio/mpeg">
  </audio>

  <!-- GOOGLE FORM -->
  <iframe src="https://forms.gle/toh7g9q2BFgm14zh8" 
          width="640" height="602" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>

</div>

<script>
  // SHOW/HIDE ELEMENTS BASED ON RANDOMIZATION
  if (audioCondition) {
    document.getElementById("audioWarning").style.display = "block"; // show the warning
    document.getElementById("kode").style.display = "block";
    document.getElementById("audio").style.display = "block";        // show the audio element
  } else {
     document.getElementById("kodeno").style.display = "block";
  }

  // START BUTTON
  document.getElementById("startBtn").addEventListener("click", function() {
    document.getElementById("content").style.display = "block";
    this.style.display = "none";

    // ONLY PLAY AUDIO IF IN AUDIO CONDITION
    if (audioCondition) {
      const audio = document.getElementById("audio");
      audio.play();
      audio.onpause = () => audio.play(); // prevent pausing
    }
  });
</script>

</body>
</html>
