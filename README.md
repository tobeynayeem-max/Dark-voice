# Dark-voice
https://yourname.github.io/dark-voice
<!DOCTYPE html>
<html>
<head>
    <!-- Page Title (Google search headline) -->
    <title>তোমার সাইটের নাম বা টপিক — Keyword</title>

   <!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Dark Voice - Text to Voice Converter</title>
    <style>
      body { font-family: Arial, sans-serif; background: #111; color: #fff; }
      textarea { width: 90%; height: 150px; margin-top: 20px; }
      button { padding: 10px 20px; margin-top: 15px; font-size: 18px; }
    </style>
</head>
<body>

  <h1>Dark Voice - Text to Speech 🔉</h1>

  <textarea id="textInput" placeholder="এখানে লিখে শুনুন..."></textarea><br>

  <button onclick="speakText()">Play Voice</button>

  <script>
    function speakText() {
      const text = document.getElementById("textInput").value;
      if (!text) { alert("দয়া করে text লিখুন।"); return; }

      const msg = new SpeechSynthesisUtterance(text);
      msg.lang = "bn-BD"; // বাংলা voice
      window.speechSynthesis.speak(msg);
    }
  </script>

</body>
</html> <!-- Meta Description (ছোট বর্ণনা Google search‑এ) -->
    <meta name="description" content="এটা তোমার পেজের সংক্ষিপ্ত বর্ণনা, search‑এ দেখানো হবে.">

    <!-- Robots Tag (Google‑কে বলবে index & follow কর) -->
    <meta name="robots" content="index, follow">
</head>
<body>
    <!-- তোমার content -->
    <h1>ওয়েলকাম!</h1>
    <p>এখানে তোমার ওয়েবসাইটের content লিখো...</p>
</body>
</html>
<script src="https://tts.ai/widget/tts.js"
      data-pk="pk-tts-YOUR_KEY"
      data-text="auto"
      data-voice="af_bella">
</script>জ
