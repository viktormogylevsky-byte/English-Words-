# English-Words-
Learn new words through quizzes 
<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<title>Вивчення слів</title>
<style>
  body { font-family: Arial; text-align: center; margin-top: 50px; }
  .card { font-size: 30px; margin: 20px; }
  button { padding: 10px 20px; margin: 5px; }
</style>
</head>

<body>

<h1>Вчимо слова</h1>

<div class="card" id="word"></div>
<div class="card" id="translation" style="display:none;"></div>

<button onclick="speak()">🔊 Вимова</button>
<button onclick="showTranslation()">Показати переклад</button>
<button onclick="nextWord()">Далі</button>

<script>
let words = [
  {en: "apple", uk: "яблуко"},
  {en: "dog", uk: "собака"},
  {en: "house", uk: "будинок"}
];

let index = 0;

function showWord() {
  document.getElementById("word").innerText = words[index].en;
  document.getElementById("translation").style.display = "none";
}

function showTranslation() {
  document.getElementById("translation").innerText = words[index].uk;
  document.getElementById("translation").style.display = "block";
}

function nextWord() {
  index = (index + 1) % words.length;
  showWord();
}

function speak() {
  let msg = new SpeechSynthesisUtterance(words[index].en);
  msg.lang = "en-US";
  speechSynthesis.speak(msg);
}

showWord();
</script>

</body>
</html>
