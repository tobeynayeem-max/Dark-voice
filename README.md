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
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Dark Voice</title>
  <style>
    body {
      background: #0f172a;
      color: white;
      font-family: Arial;
      text-align: center;
      padding: 50px;
    }

    textarea {
      width: 80%;
      height: 120px;
      border-radius: 10px;
      padding: 10px;
      font-size: 16px;
    }

    button {
      margin-top: 20px;
      padding: 12px 25px;
      font-size: 16px;
      border: none;
      border-radius: 10px;
      background: #22c55e;
      color: white;
      cursor: pointer;
    }

    select {
      margin-top: 10px;
      padding: 10px;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <h1>🎤 Dark Voice</h1>
  <p>Write anything and convert to voice</p>

  <textarea id="text" placeholder="Type something..."></textarea><br>

  <select id="voiceSelect"></select><br>

  <button onclick="speak()">🔊 Convert to Voice</button>

  <script src="script.js"></script>
</body>
</html>let voices = [];

function loadVoices() {
  voices = speechSynthesis.getVoices();
  let voiceSelect = document.getElementById("voiceSelect");

  voiceSelect.innerHTML = "";

  voices.forEach((voice, i) => {
    let option = document.createElement("option");
    option.value = i;
    option.textContent = voice.name + " (" + voice.lang + ")";
    voiceSelect.appendChild(option);
  });
}

speechSynthesis.onvoiceschanged = loadVoices;

function speak() {
  let text = document.getElementById("text").value;
  let selectedVoice = document.getElementById("voiceSelect").value;

  let msg = new SpeechSynthesisUtterance();
  msg.text = text;
  msg.voice = voices[selectedVoice];
  msg.rate = 1;
  msg.pitch = 1;

  speechSynthesis.speak(msg);
}
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Dark Voice</title>

<style>
body {
  background: #0f0f0f;
  color: white;
  font-family: Arial;
  text-align: center;
  padding: 50px;
}

textarea {
  width: 80%;
  height: 150px;
  border-radius: 10px;
  padding: 10px;
  font-size: 16px;
  border: none;
}

button {
  padding: 12px 20px;
  margin-top: 15px;
  border: none;
  border-radius: 10px;
  background: #00ffcc;
  font-size: 16px;
  cursor: pointer;
}

select {
  padding: 10px;
  border-radius: 10px;
  margin-top: 10px;
}
</style>

</head>
<body>

<h1>🎤 Dark Voice</h1>
<p>Write anything → Hear voice</p>

<textarea id="text" placeholder="Type something..."></textarea><br>

<select id="voiceSelect"></select><br>

<button onclick="speak()">🔊 Speak</button>

<script>
const synth = window.speechSynthesis;
const voiceSelect = document.getElementById("voiceSelect");

let voices = [];

function loadVoices() {
  voices = synth.getVoices();
  voiceSelect.innerHTML = "";

  voices.forEach((voice, i) => {
    const option = document.createElement("option");
    option.value = i;
    option.textContent = voice.name + " (" + voice.lang + ")";
    voiceSelect.appendChild(option);
  });
}

speechSynthesis.onvoiceschanged = loadVoices;

function speak() {
  const text = document.getElementById("text").value;
  const utterance = new SpeechSynthesisUtterance(text);

  const selectedVoice = voices[voiceSelect.value];
  utterance.voice = selectedVoice;

  utterance.rate = 1;
  utterance.pitch = 1;

  synth.speak(utterance);
}
</script>

</body>
</html>
