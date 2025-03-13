# t-kla-kazan<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Troll Site</title>
    <style>
        body {
            text-align: center;
            padding: 50px;
            font-family: Arial, sans-serif;
            background-color: black;
            color: white;
        }
        #scary-img {
            display: none;
            width: 100vw;
            height: 100vh;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 9999;
        }
        #flash {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: white;
            opacity: 0;
            z-index: 10000;
        }
    </style>
</head>
<body>
    <h1>Bu siteye devam etmek için "Accept"e tıklayın</h1>
    <button id="accept-btn">Accept</button>

    <img id="scary-img" src="scary.jpg" alt="Jumpscare">
    <audio id="scary-audio" src="scream.mp3"></audio>
    <div id="flash"></div>

    <script>
        document.getElementById("accept-btn").addEventListener("click", function() {
            var image = document.getElementById("scary-img");
            var audio = document.getElementById("scary-audio");
            var flash = document.getElementById("flash");

            // Jumpscare resmi göster
            image.style.display = "block";

            // Korkutucu sesi oynat
            audio.play();

            // Beyaz ışık efekti (yanıp sönme)
            flash.style.display = "block";
            let opacity = 1;
            let interval = setInterval(() => {
                flash.style.opacity = opacity;
                opacity = opacity === 1 ? 0 : 1; // Beyaz yanıp sönsün
            }, 100);

            // 1.5 saniye sonra flaş efektini kapat
            setTimeout(() => {
                clearInterval(interval);
                flash.style.display = "none";
            }, 1500);
        });
    </script>
</body>
</html>
