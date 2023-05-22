<!DOCTYPE html>

<html>

<head>

  <title>Tap Cookie Game</title>

  <style>

    button {

      padding: 10px 20px;

      font-size: 20px;

      margin-top: 10px;

    }

  </style>

</head>

<body>

  <h1>Tap Cookie Game</h1>

  <p>Click the cookie to earn points!</p>

  <button id="cookieButton" onclick="updateScore()">Tap Me!</button>

  <p id="score">Score: 0</p>

  <h2>Leaderboard</h2>

  <ol id="leaderboard"></ol>

  <script>

    // Mendapatkan data dari local storage atau membuat data baru jika belum ada

    var playerData = JSON.parse(localStorage.getItem('playerData')) || {};

    // Mengupdate skor pada tampilan dan data pemain

    function updateScore() {

      var currentScore = parseInt(playerData['score']) || 0;

      var newScore = currentScore + 1;

      document.getElementById('score').textContent = 'Score: ' + newScore;

      playerData['score'] = newScore;

      localStorage.setItem('playerData', JSON.stringify(playerData));

      updateLeaderboard();

    }

    // Memperbarui leaderboard pada tampilan

    function updateLeaderboard() {

      var leaderboard = document.getElementById('leaderboard');

      leaderboard.innerHTML = '';

      // Mengurutkan skor secara menurun

      var sortedScores = Object.keys(playerData).sort(function(a, b) {

        return playerData[b] - playerData[a];

      });

      // Menambahkan pemain dengan skor tertinggi ke leaderboard

      sortedScores.forEach(function(score) {

        var listItem = document.createElement('li');

        listItem.textContent = 'Score: ' + playerData[score];

        leaderboard.appendChild(listItem);

      });

    }

    // Memperbarui leaderboard saat halaman dimuat

    updateLeaderboard();

  </script>

</body>

</html>
