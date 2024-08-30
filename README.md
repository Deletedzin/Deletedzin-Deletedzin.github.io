<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Imagem e Música</title>
    <style>
        body {
            font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
            overflow: hidden; /* Evita barras de rolagem indesejadas */
            height: 100vh;
            position: relative; /* Necessário para o posicionamento absoluto do vídeo */
        }

    
        <video id="power-poles-purple-sky-pixel-moewalls-com.mp4" autoplay muted loop>{
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover; /* Faz com que o vídeo cubra a área sem distorção */
            z-index: -1; /* Coloca o vídeo atrás do conteúdo */
        }

        .image-container {
            position: relative;
            margin-bottom: 30px;
        }

        .image-container img {
            max-width: 100%;
            height: 300px;
            border-radius: 0px;
            box-shadow: 0 8px 10px rgba(245, 247, 126, 0.829);
        }

        .arrow {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 2em;
            color: white;
            cursor: pointer;
        }

        .arrow.left {
            left: -50px;
        }

        .arrow.right {
            right: -50px;
        }

        audio {
            width: 100%;
            max-width: 600px;
            border: none;
            outline: yellow;
            margin-top: 10px;
        }
    </style>
</head>

<body>
    <!-- Vídeo de Plano de Fundo -->
    <video id="backgroundVideo" autoplay muted loop>
        <source src="power-poles-purple-sky-pixel-moewalls-com.mp4" type="video/mp4">
        Seu navegador não suporta vídeos HTML5.
    </video>

    <!-- Contêiner da Imagem com Setas -->
    <div class="image-container">
        <!-- Seta Esquerda -->
        <div class="arrow left" onclick="prevImage()">&#9664;</div>

        <!-- Imagem Central -->
        <img id="mainImage" src="jojo-anime.gif" alt="Imagem Centralizada">

        <!-- Seta Direita -->
        <div class="arrow right" onclick="nextImage()">&#9654;</div>
    </div>

    <!-- Player de Música -->
    <audio id="audioPlayer" controls style="opacity: 0.5;">
        <source id="audioSource" src="resonance - home (slowed & reverb).mp3" type="audio/mpeg">
    </audio>

    <script>
        // Array de imagens e músicas
        const media = [
            { img: "jojo-anime.gif", music: "resonance - home (slowed & reverb).mp3" },
            { img: "jjk-manga.gif", music: "the sylvers - remember the rain __SLOWED__.mp3" },
            { img: "imagem3.gif", music: "musica3.mp3" }
        ];

        let currentIndex = 0;

        function updateMedia() {
            document.getElementById("mainImage").src = media[currentIndex].img;
            const audioPlayer = document.getElementById("audioPlayer");
            document.getElementById("audioSource").src = media[currentIndex].music;
            audioPlayer.load(); // Recarrega o player para tocar a nova música
        }

        function nextImage() {
            currentIndex = (currentIndex + 1) % media.length;
            updateMedia();
        }

        function prevImage() {
            currentIndex = (currentIndex - 1 + media.length) % media.length;
            updateMedia();
        }
    </script>
</body>

</html>
