<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fumée Omniscient, Mirage Onirique - Résidence de création, janvier 2025, Bain Mathieu</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 16px;
        }
        video {
            width: 100%;
            max-width: 2000px;
        }
        button {
            margin: 30px;
            padding: 20px;
            font-size: 12px;
        }
    </style>
</head>
<body>

    <h1>Contrôle du spectacle</h1>

    <!-- Vidéo divisée en deux (les deux salles) -->
    <video id="video" controls autoplay>
        <source src="[votre_video.mp4](https://www.dropbox.com/scl/fi/2ytjemo9md4sk6nyq8mtk/felix-antoine-coutu_Fum-e-Omnisciente-Mirage-Onirique-V4.m4v?rlkey=1nztikpgekcljvgn4obcnpdfw&st=zygs89un&draw=1)" type="video/m4v">
        
        Votre navigateur ne prend pas en charge la vidéo HTML5.
    </video>

    <!-- Pistes audio -->
    <audio id="audioSalle1" loop>
        <source src="audio_salle1.mp3" type="audio/mp3">
        Votre navigateur ne prend pas en charge l'audio.
    </audio>
    <audio id="audioSalle2" loop>
        <source src="audio_salle2.mp3" type="audio/mp3">
        Votre navigateur ne prend pas en charge l'audio.
    </audio>

    <!-- Boutons de contrôle -->
    <button id="btnBascule">Basculer l'audio</button>

    <!-- Script JavaScript intégré -->
    <script>
        document.getElementById("video").addEventListener("play", function() {
            // Lors du démarrage de la vidéo, les deux pistes audio sont lancées et non muettes
            var audioSalle1 = document.getElementById("audioSalle1");
            var audioSalle2 = document.getElementById("audioSalle2");

            audioSalle1.play();
            audioSalle2.play();
            audioSalle2.muted = true;  // D'abord, on mute l'audio de la salle 2, donc seul l'audio de la salle 1 est audible
        });

        document.getElementById("btnBascule").addEventListener("click", function() {
            var audioSalle1 = document.getElementById("audioSalle1");
            var audioSalle2 = document.getElementById("audioSalle2");

            // Bascule entre l'audio de la première et de la deuxième salle
            if (audioSalle1.muted) {
                // Si l'audio de la salle 1 est muet, on le rend audible et on mute celui de la salle 2
                audioSalle1.muted = false;
                audioSalle2.muted = true;
            } else {
                // Si l'audio de la salle 2 est muet, on le rend audible et on mute celui de la salle 1
                audioSalle1.muted = true;
                audioSalle2.muted = false;
            }
        });
    </script>
</body>
</html>
