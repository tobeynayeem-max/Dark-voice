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

