<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Interactive Love Note</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #f3e5f5;
    color: #4a148c;
    text-align: center;
    padding: 50px;
  }
  .question {
    display: none;
    margin-bottom: 20px;
  }
  .answer {
    display: none;
    font-size: 1.2em;
    font-weight: bold;
    margin-top: 10px;
    animation: boom 0.5s ease-out;
  }
  @keyframes boom {
    0% { transform: scale(0); opacity: 0; }
    50% { transform: scale(1.2); opacity: 1; }
    100% { transform: scale(1); opacity: 1; }
  }
  button {
    background-color: #7b1fa2;
    color: white;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    cursor: pointer;
    border-radius: 8px;
    font-size: 1em;
  }
  button:hover {
    background-color: #4a148c;
  }
</style>
</head>
<body>

<h1>Happy Birthday, Hope! 💖</h1>

<div id="quiz">
  <div class="question" id="q0">
    <p>Do you love me?</p>
    <button onclick="showAnswer(0)">Yes ❤️</button>
    <button onclick="showAnswer(0)">No 😢</button>
    <div class="answer" id="a0">Boom! I love you too! 💗</div>
  </div>

  <div class="question" id="q1">
    <p>Who is always mysterious?</p>
    <button onclick="showAnswer(1)">You 😏</button>
    <button onclick="showAnswer(1)">Someone else</button>
    <div class="answer" id="a1">Boom! That’s you, my mysterious queen 😘</div>
  </div>

  <div class="question" id="q2">
    <p>Who is the boss?</p>
    <button onclick="showAnswer(2)">You 🏆</button>
    <button onclick="showAnswer(2)">Me 😎</button>
    <div class="answer" id="a2">Boom! Always you, the boss! 💜</div>
  </div>
</div>

<div>
  <button onclick="prevQuestion()">Previous</button>
  <button onclick="nextQuestion()">Next</button>
</div>

<script>
  let currentQuestion = 0;
  const questions = document.querySelectorAll('.question');
  questions[currentQuestion].style.display = 'block';

  function showAnswer(index) {
    const answer = document.getElementById('a' + index);
    answer.style.display = 'block';
  }

  function nextQuestion() {
    if (currentQuestion < questions.length - 1) {
      questions[currentQuestion].style.display = 'none';
      currentQuestion++;
      questions[currentQuestion].style.display = 'block';
    }
  }

  function prevQuestion() {
    if (currentQuestion > 0) {
      questions[currentQuestion].style.display = 'none';
      currentQuestion--;
      questions[currentQuestion].style.display = 'block';
    }
  }
</script>

</body>
</html>
