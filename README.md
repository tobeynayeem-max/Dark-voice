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


<script>
let voices = [];
let selectedType = "male";

function loadVoices() {
  voices = speechSynthesis.getVoices();
}
speechSynthesis.onvoiceschanged = loadVoices;

function setVoice(type) {
  selectedType = type;
}

function speak() {
  let text = document.getElementById("text").value;

  // 🔥 Text improve (pause + smooth voice)
  text = text.replace(/\./g, ". ").replace(/,/g, ", ");

  let utterance = new SpeechSynthesisUtterance(text);

  // 🎛️ Voice settings (IMPORTANT)
  utterance.rate = 0.9;   // slow = smooth
  utterance.pitch = selectedType === "male" ? 0.7 : 1.2;
  utterance.volume = 1;

  // 🔊 Best voice select logic
  let bestVoice = voices.find(v =>
    selectedType === "male"
      ? v.name.toLowerCase().includes("male") || v.lang.includes("en")
      : v.name.toLowerCase().includes("female")
  );

  if (!bestVoice) bestVoice = voices[0];

  utterance.voice = bestVoice;

  speechSynthesis.cancel(); // old voice stop
  speechSynthesis.speak(utterance);
}
</script>
<script>
let voices = [];

function loadVoices() {
  voices = speechSynthesis.getVoices();
}
speechSynthesis.onvoiceschanged = loadVoices;

function speak() {
  let text = document.getElementById("text").value;

  let utterance = new SpeechSynthesisUtterance(text);

  // 🔥 BEST SETTINGS
  utterance.rate = 0.85;   // slow = smooth
  utterance.pitch = 1;
  utterance.volume = 1;

  // 🔥 BEST VOICE PICK (IMPORTANT)
  let bestVoice =
    voices.find(v => v.lang === "en-US") ||
    voices.find(v => v.lang.includes("en")) ||
    voices[0];

  utterance.voice = bestVoice;

  speechSynthesis.cancel();
  speechSynthesis.speak(utterance);
}
</script>
<!-- SEO META TAG -->
<title>Dark Voice AI - Bangla Voice Generator</title>

<meta name="description" content="Dark Voice AI website যেখানে আপনি লেখা দিলে voice হয়ে যাবে। Bangla deep voice generator.">

<meta name="keywords" content="dark voice, bangla voice generator, text to speech bangla, AI voice">

<meta name="author" content="Dark Voice">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Google indexing -->
<meta name="robots" content="index, follow">
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://yourwebsite.com/</loc>
    <priority>1.0</priority>
  </url>
</urlset><h1>Dark Voice AI - Bangla Voice Generator</h1>
<p>Write anything and convert it into realistic voice.</p>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Dark Voice AI Pro</title>

<style>
body {
  background: #0f0f0f;
  color: white;
  text-align: center;
  font-family: Arial;
  padding: 50px;
}

textarea {
  width: 80%;
  height: 150px;
  border-radius: 10px;
  padding: 10px;
}

button {
  padding: 15px;
  margin-top: 20px;
  background: #00ffcc;
  border: none;
  cursor: pointer;
}
</style>
</head>

<body>

<h1>🔥 Dark Voice AI (11Labs Style)</h1>

<textarea id="text" placeholder="Write something..."></textarea>
<br>

<button onclick="generateVoice()">🎤 Generate Voice</button>

<audio id="audio" controls></audio>

<script>
async function generateVoice() {
  let text = document.getElementById("text").value;

  const response = await fetch("https://api.elevenlabs.io/v1/text-to-speech/YOUR_VOICE_ID", {
    method: "POST",
    headers: {
      "xi-api-key": "YOUR_API_KEY",
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
      text: text,
      model_id: "eleven_multilingual_v2",
      voice_settings: {
        stability: 0.5,
        similarity_boost: 0.8
      }
    })
  });

  const audioBlob = await response.blob();
  const audioUrl = URL.createObjectURL(audioBlob);

  document.getElementById("audio").src = audioUrl;
}
</script>

</body>
</html>
