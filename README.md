<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Kuesioner</title>
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

<h2>Tekan tombol "Mulai" di bawah ini untuk membuka kuesioner.</h2>

<!-- THIS TEXT SHOULD ONLY SHOW IF AUDIO IS ACTIVE -->
<h2 id="audioWarning">
Kuesioner tersebut akan mengeluarkan suara yang tidak bisa dihentikan selama Anda mengisi kuesioner.<br>Mohon untuk mengatur volume suara perangkat Anda agar suara tersebut dapat terdengar dengan jelas. Lalu, mohon tidak menurunkan volume atau mematikan suara perangkat Anda sampai Anda selesai mengisi kuesioner.<br>Bagian akhir kuesioner terkait dengan suara tersebut dan informasi yang terdapat di dalamn suara tersebut. Jika Anda tidak mendengarkan, maka Anda tidak akan dapat memberikan jawaban yang sesuai, dan Anda akan didiskualifikasi sebagai partisipan.</h2>

<h2 id ="kode">Pada bagian akhir kuesioner, anda juga akan diminta untuk memasukkan kode berikut: AUD25</h2>
<h2 id ="kodeno">Pada bagian akhir kuesioner, anda juga akan diminta untuk memasukkan kode berikut: NOA25</h2>

<button id="startBtn" style="padding: 10px 20px; font-size: 18px;">Mulai</button>

<div id="content">

  <!-- AUDIO -->
  <audio id="audio" autoplay>
    <source src="printaudio2.mp3" type="audio/mpeg">
  </audio>

  <!-- GOOGLE FORM -->
  <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdBdmzNpWii84Xi_LnOSHlbBbF3AFNewAZ6ZZkS7rt4FK48Bw/viewform?embedded=true" 
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
