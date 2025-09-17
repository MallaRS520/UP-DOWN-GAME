<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Up-Down Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #f2f2f2;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    #game {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      display: inline-block;
    }
    input, button {
      padding: 10px;
      margin: 5px;
      font-size: 16px;
    }
    #result {
      font-weight: bold;
      margin-top: 15px;
    }
    a {
      display: block;
      margin-top: 20px;
      font-size: 18px;
      color: blue;
    }
  </style>
</head>
<body>
  <h1>🎮 Up-Down Number Guessing Game 🎮</h1>
  
  <div id="game">
    <p>Guess a number between <b>1</b> and <b>100</b>.</p>
    <input type="number" id="guess" placeholder="Enter your guess">
    <button onclick="checkGuess()">Guess</button>
    <p id="result"></p>
  </div>

  <!-- ChatGPT history link -->
  <a href="https://chat.openai.com/share/YOUR_CHAT_LINK" target="_blank">
    🔗 View My ChatGPT History
  </a>

  <script>
    let randomNumber = Math.floor(Math.random() * 100) + 1;

    function checkGuess() {
      const guess = parseInt(document.getElementById("guess").value);
      const result = document.getElementById("result");

      if (isNaN(guess)) {
        result.textContent = "❌ Please enter a valid number!";
        return;
      }

      if (guess < randomNumber) {
        result.textContent = "⬆️ Up! Try a higher number.";
      } else if (guess > randomNumber) {
        result.textContent = "⬇️ Down! Try a lower number.";
      } else {
        result.textContent = "🎉 Correct! You guessed the number!";
      }
    }
  </script>
</body>
</html>
