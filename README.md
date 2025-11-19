<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Kuesioner</title>
  <style>
    body { font-family: sans-serif; padding: 20px; text-align: center; }
    #content { display: none; }
  </style>
</head>
<script>
  const audioCondition = Math.random() < 0.5;
</script>
<body>
  
<h2>Tekan tombol "Mulai" di bawah ini untuk membuka kuesioner.</h2>
<h2 id="audioWarning">Kuesioner tersebut akan mengeluarkan suara yang tidak bisa dihentikan selama Anda mengisi kuesioner.<br>Mohon untuk mengatur volume suara perangkat Anda agar suara tersebut dapat terdengar dengan jelas. Lalu, mohon tidak menurunkan volume ataupun mematikan suara perangkat Anda sampai Anda selesai mengisi kuesioner.<br>Audio tersebut mengandung informasi yang diperlukan untuk bagian akhir kuesioner. Jika Anda tidak mendengarkan, maka Anda tidak akan dapat memberikan jawaban yang sesuai, dan Anda akan didiskualifikasi sebagai partisipan.</h2>
<button id="startBtn" style="padding: 10px 20px; font-size: 18px;">Mulai</button>

<div id="content">
  
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
