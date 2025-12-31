<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy New Year Mussu</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;400&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            width: 100%;
            overflow: hidden;
            font-family: 'Poppins', sans-serif;
            color: white;
            /* Background with Overlay */
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), 
                        url('https://uc.infoflow.live/uc?id=1JfgM-nznj93lDvBeUKZQWIm4eHGkbLd9');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

        .slide {
            height: 100vh;
            width: 100vw;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: absolute;
            transition: opacity 1s ease-in-out, transform 1s ease-in-out;
            opacity: 0;
            transform: scale(0.95);
            padding: 20px;
            box-sizing: border-box;
            backdrop-filter: blur(2px);
        }

        .active {
            opacity: 1;
            transform: scale(1);
            z-index: 10;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: clamp(2rem, 8vw, 3.5rem);
            margin-bottom: 20px;
            color: #ff4d6d;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.7);
        }

        p {
            font-size: 1.2rem;
            max-width: 600px;
            line-height: 1.6;
            text-shadow: 1px 1px 5px rgba(0,0,0,1);
        }

        .btn {
            margin-top: 30px;
            padding: 12px 25px;
            border: none;
            background: #ff4d6d;
            color: white;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.5);
            transition: 0.3s;
        }

        .btn:hover {
            background: #ff758f;
            transform: scale(1.05);
        }

        /* Music Toggle Button */
        #music-control {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 100;
            background: rgba(255, 77, 109, 0.8);
            border: none;
            border-radius: 50%;
            width: 45px;
            height: 45px;
            color: white;
            cursor: pointer;
            font-size: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .heart {
            position: fixed;
            color: rgba(255, 77, 109, 0.6);
            font-size: 20px;
            pointer-events: none;
            z-index: 1;
            animation: float 5s linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(110vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="PASTE_DIRECT_LINK_TO_MP3_HERE" type="audio/mpeg">
    </audio>

    <button id="music-control" onclick="toggleMusic()">🎵</button>

    <div class="slide active" id="slide1">
        <h1>Happy New Year my baccha mussu 🫂🫂💗</h1>
        <p>A new chapter begins, and I'm so happy it's with you.</p>
        <button class="btn" onclick="startExperience()">Click here, Mussu</button>
    </div>

    <div class="slide" id="slide2">
        <h1>You Made My Year Better ✨</h1>
        <p>Looking back at the past year, your presence was the brightest part of every single day. You turned ordinary moments into beautiful memories just by being there.</p>
        <button class="btn" onclick="nextSlide(3)">And one more thing...</button>
    </div>

    <div class="slide" id="slide3">
        <h1>Forever & Always ❤️</h1>
        <p>I love you more than words can express. As we step into this new year, my only wish is to keep holding your hand, chasing dreams together, and building a future where we never have to say goodbye.</p>
        <p style="font-size: 1rem; margin-top: 20px;">I want to be with you, today, tomorrow, and every year after. 💍</p>
        <button class="btn" onclick="nextSlide(1)">Restart ❤️</button>
    </div>

    <script>
        const music = document.getElementById('bgMusic');

        function startExperience() {
            // Start music on first click (browser requirement)
            music.play().catch(e => console.log("Music play blocked"));
            nextSlide(2);
        }

        function nextSlide(slideNumber) {
            document.querySelectorAll('.slide').forEach(slide => {
                slide.classList.remove('active');
            });
            document.getElementById('slide' + slideNumber).classList.add('active');
        }

        function toggleMusic() {
            if (music.paused) {
                music.play();
            } else {
                music.pause();
            }
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }

        setInterval(createHeart, 400);
    </script>
</body>
</html>
