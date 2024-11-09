<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hola Otra Vez</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            overflow: hidden;
            background-color: #f0f8ff;
            transition: background-color 0.3s;
        }

        .container {
            text-align: center;
        }

        .flower {
            position: absolute;
            width: 40px;
            height: 40px;
            background: radial-gradient(circle, purple, mediumorchid);
            border-radius: 50%;
            box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.2);
            animation: float 5s infinite linear;
        }

        .flower::after {
            content: "";
            position: absolute;
            width: 10px;
            height: 20px;
            background: limegreen;
            border-radius: 50%;
            bottom: -20px;
            left: 15px;
        }

        @keyframes float {
            0% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0); }
        }

        #errorMessage {
            display: none;
            color: red;
            font-size: 2em;
            font-weight: bold;
            margin-top: 20px;
        }

        #clickButton {
            padding: 10px 20px;
            font-size: 1.2em;
            cursor: pointer;
            background-color: lightgreen;
            border: none;
            border-radius: 5px;
            margin-top: 20px;
            transition: background-color 0.2s;
        }

        #clickButton:hover {
            background-color: limegreen;
        }

        #flowerBouquet {
            display: none;
            margin-top: 20px;
            width: 150px;
        }

        #card {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #fff;
            border: 2px solid #000;
            border-radius: 10px;
            text-align: center;
            padding: 50px;
            font-size: 3em;
            font-family: 'Ink Free', cursive;
            color: black;
            box-sizing: border-box;
        }

        #cardContent {
            margin-top: 20px;
            font-size: 2em;
        }

        #heart {
            color: limegreen;
            font-size: 2.5em;
            margin-top: 30px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>HOLA OTRA VEZ</h1>
        <p>This is for you my Marcianito... :3</p>
        <button id="clickButton" onclick="addFlower()">Haz clic otra vez tantas veces como me quieras</button>
        <div id="errorMessage">¡ERROR! ¿Dónde piensas que entrarán más flores?</div>
        <img id="flowerBouquet" src="https://www.pngmart.com/files/12/Rose-Bouquet-PNG-File.png" alt="Ramo de rosas" width="150">
    </div>

    <div id="card">
        Yo te quiero así pero muchísimo más
        <div id="heart">💚</div>
        <div id="cardContent">Atte: 👽</div>
    </div>

    <script>
        let flowerCount = 0;

        function addFlower() {
            if (flowerCount < 25) {
                const flower = document.createElement("div");
                flower.classList.add("flower");
                document.body.appendChild(flower);

                // Posiciona la flor en un lugar aleatorio
                flower.style.left = `${Math.random() * window.innerWidth - 20}px`;
                flower.style.top = `${Math.random() * window.innerHeight - 20}px`;
                flowerCount++;
            }

            // Mostrar mensaje de error y otros elementos cuando haya 25 flores
            if (flowerCount === 25) {
                document.querySelector(".container").style.display = "none";
                document.getElementById("errorMessage").style.display = "block";
                document.body.style.backgroundColor = "#ffb6c1";
                document.getElementById("flowerBouquet").style.display = "block";
                document.getElementById("card").style.display = "block";
                document.getElementById("clickButton").style.display = "none";
            }
        }
    </script>
</body>
</html>
