<!DOCTYPE html>

<html>

<head>

  <title>Multiplayer Shooter Game</title>

  <style>

    canvas {

      border: 1px solid black;

    }

  </style>

  <script src="https://www.gstatic.com/firebasejs/9.1.3/firebase-app.js"></script>

  <script src="https://www.gstatic.com/firebasejs/9.1.3/firebase-database.js"></script>

</head>

<body>

  <canvas id="gameCanvas" width="800" height="600"></canvas>

  <script>

    // Inisialisasi Firebase

    const firebaseConfig = {

      apiKey: "YOUR_API_KEY",

      authDomain: "YOUR_AUTH_DOMAIN",

      projectId: "YOUR_PROJECT_ID",

      databaseURL: "YOUR_DATABASE_URL",

    };

    

    firebase.initializeApp(firebaseConfig);

    const database = firebase.database();

    // Inisialisasi Game Canvas

    const canvas = document.getElementById("gameCanvas");

    const context = canvas.getContext("2d");

    // Menggambar pemain di canvas

    function drawPlayer(x, y) {

      context.fillStyle = "red";

      context.fillRect(x, y, 20, 20);

    }

    // Mendapatkan posisi pemain dari Firebase dan menggambar ulang canvas

    function updateGame() {

      database.ref("players").once("value").then((snapshot) => {

        context.clearRect(0, 0, canvas.width, canvas.height);

        snapshot.forEach((playerSnapshot) => {

          const player = playerSnapshot.val();

          drawPlayer(player.x, player.y);

        });

      });

    }

    // Mengirim posisi pemain ke Firebase

    function sendPosition(x, y) {

      const playerRef = database.ref("players/player1");

      playerRef.set({

        x: x,

        y: y

      });

    }

    // Menggerakkan pemain

    function movePlayer(event) {

      const canvasRect = canvas.getBoundingClientRect();

      const mouseX = event.clientX - canvasRect.left;

      const mouseY = event.clientY - canvasRect.top;

      sendPosition(mouseX, mouseY);

    }

    // Menghubungkan event mousemove ke fungsi movePlayer

    canvas.addEventListener("mousemove", movePlayer);

    // Mengupdate game secara periodik

    setInterval(updateGame, 100);

  </script>

</body>

</html>
