<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<title>Popcat</title>
<style>
    body {
        background: #f8f8f8;
        text-align: center;
        font-family: Arial, sans-serif;
    }
    h1 {
        font-size: 2em;
    }
    img {
        width: 300px;
        cursor: pointer;
        user-select: none;
    }
    #score {
        font-size: 2em;
        margin-top: 20px;
    }
</style>
</head>
<body>

<h1>Popcat 🐱</h1>
<img id="popcat" src="https://i.ibb.co/6Yy3P0x/popcat-close.png" alt="Popcat">
<div id="score">0</div>

<audio id="popSound" src="https://www.myinstants.com/media/sounds/pop-cat.mp3"></audio>

<script>
    let score = 0;
    const popcat = document.getElementById("popcat");
    const scoreDisplay = document.getElementById("score");
    const popSound = document.getElementById("popSound");

    const openMouth = "https://i.ibb.co/NnR0gk9/popcat-open.png";
    const closeMouth = "https://i.ibb.co/6Yy3P0x/popcat-close.png";

    popcat.addEventListener("mousedown", () => {
        popcat.src = openMouth;
        popSound.currentTime = 0;
        popSound.play();
        score++;
        scoreDisplay.textContent = score;
    });

    popcat.addEventListener("mouseup", () => {
        popcat.src = closeMouth;
    });

    // รองรับมือถือ
    popcat.addEventListener("touchstart", () => {
        popcat.src = openMouth;
        popSound.currentTime = 0;
        popSound.play();
        score++;
        scoreDisplay.textContent = score;
    });

    popcat.addEventListener("touchend", () => {
        popcat.src = closeMouth;
    });
</script>

</body>
</html>
