# Dark-voice
https://yourname.github.io/dark-voice
<!DOCTYPE html>
<html>
<head>
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

h1 {
  color: #00ffcc;
}

textarea {
  width: 80%;
  height: 150px;
  padding: 10px;
  font-size: 16px;
  border-radius: 10px;
  border: none;
}

select, button {
  margin-top: 15px;
  padding: 10px;
  font-size: 16px;
  border-radius: 8px;
  border: none;
}

button {
  background: #00ffcc;
  cursor: pointer;
}

button:hover {
  background: #00ccaa;
}
</style>

</head>

<body>

<h1>🎤 Dark Voice Generator</h1>

<textarea id="text" placeholder="Type something..."></textarea>
<br>

<select id="voiceList"></select>
<br>

<button onclick="speak()">🔊 Convert to Voice</button>

<script>
let voices = [];

function loadVoices() {
  voices = speechSynthesis.getVoices();
  let voiceSelect = document.getElementById("voiceList");

  voiceSelect.innerHTML = "";

  voices.forEach((voice, index) => {
    let option = document.createElement("option");
    option.value = index;
    option.textContent = voice.name + " (" + voice.lang + ")";
    voiceSelect.appendChild(option);
  });
}

speechSynthesis.onvoiceschanged = loadVoices;

function speak() {
  let text = document.getElementById("text").value;
  let selectedVoiceIndex = document.getElementById("voiceList").value;

  let utterance = new SpeechSynthesisUtterance(text);
  utterance.voice = voices[selectedVoiceIndex];

  speechSynthesis.speak(utterance);
}
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Dark Voice AI</title>

<style>
body {
  margin: 0;
  display: flex;
  background: #0f0f0f;
  color: white;
  font-family: Arial;
}

/* Sidebar */
.sidebar {
  width: 200px;
  background: #1a1a1a;
  padding: 20px;
}

.sidebar h2 {
  color: #00ffcc;
}

.sidebar button {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}

.male {
  background: #0077ff;
}

.female {
  background: #ff0077;
}

/* Main */
.main {
  flex: 1;
  padding: 40px;
  text-align: center;
}

textarea {
  width: 80%;
  height: 150px;
  border-radius: 10px;
  padding: 10px;
  font-size: 16px;
}

button.speak {
  margin-top: 20px;
  padding: 15px;
  font-size: 18px;
  background: #00ffcc;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}
</style>
</head>

<body>

<div class="sidebar">
  <h2>Voice Type</h2>

  <button class="male" onclick="setVoice('male')">Male Voice</button>
  <button class="female" onclick="setVoice('female')">Female Voice</button>
</div>

<div class="main">
  <h1>🎤 Dark Voice AI</h1>

  <textarea id="text" placeholder="Type something...
