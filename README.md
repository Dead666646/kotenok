[index.html](https://github.com/user-attachments/files/33980396/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Для моей любимой ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&family=Montserrat:wght@400;600;700&display=swap');

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: #070205;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
            padding: 20px;
        }

        .bg-orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(90px);
            opacity: 0.4;
            z-index: 0;
            animation: floatOrb 12s infinite alternate ease-in-out;
        }
        .orb-1 {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, #ff4d6d, transparent);
            top: -10%;
            left: -10%;
        }
        .orb-2 {
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, #7b2cbf, transparent);
            bottom: -15%;
            right: -10%;
            animation-delay: -6s;
        }
        @keyframes floatOrb {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(40px, 60px) scale(1.1); }
        }

        .hearts-bg {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
        }

        .heart-particle {
            position: absolute;
            color: rgba(255, 117, 143, 0.15);
            animation: floatUp 9s linear infinite;
            bottom: -50px;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg) scale(0.6); opacity: 0; }
            20% { opacity: 0.8; }
            100% { transform: translateY(-120vh) rotate(360deg) scale(1.2); opacity: 0; }
        }

        .wrapper {
            position: relative;
            width: 100%;
            max-width: 580px;
            z-index: 10;
        }

        .progress-dots {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-bottom: 25px;
        }
        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            transition: all 0.4s ease;
        }
        .dot.active {
            background: #ff4d6d;
            box-shadow: 0 0 12px #ff4d6d;
            transform: scale(1.3);
        }

        .step-page {
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 50px 45px;
            border-radius: 40px;
            text-align: center;
            box-shadow: 0 30px 70px rgba(0, 0, 0, 0.5), inset 0 0 30px rgba(255, 77, 109, 0.05);
            width: 100%;
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.6s ease;
        }

        .step-page.active {
            display: flex;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            color: #fff;
            font-size: 2.1rem;
            line-height: 1.3;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(255, 77, 109, 0.5);
        }

        p {
            color: rgba(255, 255, 255, 0.85);
            font-size: 1.15rem;
            line-height: 1.7;
            margin-bottom: 40px;
            max-width: 460px;
        }

        .buttons-wrapper {
            display: flex;
            justify-content: center;
            gap: 25px;
            width: 100%;
            flex-wrap: wrap;
        }

        .nav-btn, .final-btn {
            padding: 18px 45px;
            font-size: 1.1rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            outline: none;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .nav-btn, #yesBtn {
            background: linear-gradient(45deg, #ff4d6d, #ff758f);
            color: white;
            box-shadow: 0 0 25px rgba(255, 77, 109, 0.4);
        }

        .nav-btn:active, #yesBtn:active {
            transform: scale(0.95);
        }

        #noBtn {
            background: rgba(255, 255, 255, 0.08);
            color: rgba(255, 255, 255, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(5px);
        }

        .success-gif {
            display: none;
            font-size: 110px;
            animation: heartBeat 1.2s infinite;
            margin-top: 10px;
            filter: drop-shadow(0 0 20px rgba(255, 77, 109, 0.6));
        }

        @keyframes heartBeat {
            0%, 40%, 80%, 100% { transform: scale(1); }
            20%, 60% { transform: scale(1.15); }
        }

        #confetti-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 100;
        }

        @media (max-width: 480px) {
            .step-page { padding: 40px 25px; border-radius: 30px; }
            h1 { font-size: 1.7rem; }
            p { font-size: 1rem; }
            .nav-btn, .final-btn { padding: 16px 35px; font-size: 1rem; }
            .orb-1 { width: 250px; height: 250px; }
            .orb-2 { width: 300px; height: 300px; }
        }
    </style>
</head>
<body>

    <div class="bg-orb orb-1"></div>
    <div class="bg-orb orb-2"></div>
    <div class="hearts-bg" id="heartsBg"></div>
    <canvas id="confetti-canvas"></canvas>

    <div class="wrapper">
        <div class="progress-dots">
            <span class="dot active" id="dot1"></span>
            <span class="dot" id="dot2"></span>
            <span class="dot" id="dot3"></span>
        </div>

        <div class="step-page active" id="step1">
            <h1>Привет, моя хорошая... ✨</h1>
            <p>Я создал эту страницу специально для тебя. Кое-что очень хочу тебе сказать. Пойдем дальше?</p>
            <div class="buttons-wrapper">
                <button class="nav-btn" onclick="goToStep(2)">Давай 🥺</button>
            </div>
        </div>

        <div class="step-page" id="step2">
            <h1>Ты самое лучшее в моей жизни ❤️</h1>
            <p>Каждый миг, проведенный вместе с тобой — особенный. Спасибо за твою улыбку, заботу и твое невероятное тепло.</p>
            <div class="buttons-wrapper">
                <button class="nav-btn" onclick="goToStep(3)">Дальше 👉</button>
            </div>
        </div>

        <!-- ИСПРАВЛЕНО: id="finalPage" заменён на id="step3" -->
        <div class="step-page" id="step3">
            <h1 id="question">Ты меня любишь? </h1>
            <div class="buttons-wrapper" id="finalButtons">
                <button id="yesBtn" class="final-btn" onclick="sayYesFinal()">Да!</button>
                <button id="noBtn" class="final-btn">Нет</button>
            </div>
            <div id="heartIcon" class="success-gif">❤️</div>
        </div>
    </div>

    <script>
        let currentStep = 1;

        function goToStep(step) {
            document.getElementById('step' + currentStep).classList.remove('active');
            document.getElementById('dot' + currentStep).classList.remove('active');
            
            currentStep = step;
            document.getElementById('step' + currentStep).classList.add('active');
            document.getElementById('dot' + currentStep).classList.add('active');
        }

        function sayYesFinal() {
            document.getElementById('question').innerHTML = 'Урааа! Я тебя тоже очень сильно люблю! 🥰✨';
            document.getElementById('question').style.color = '#ff758f';
            document.getElementById('finalButtons').style.display = 'none';
            document.getElementById('heartIcon').style.display = 'block';
            
            document.querySelector('.orb-1').style.opacity = '0.7';
            document.querySelector('.orb-2').style.opacity = '0.7';
            // ИСПРАВЛЕНО: finalPage → step3
            document.getElementById('step3').style.boxShadow = '0 30px 70px rgba(255, 77, 109, 0.3), inset 0 0 40px rgba(255, 77, 109, 0.1)';
            
            startConfetti();
        }

        document.addEventListener('DOMContentLoaded', () => {
            const noButton = document.getElementById('noBtn');

            const moveNoButton = (e) => {
                if (e) {
                    e.preventDefault();
                    e.stopPropagation();
                }
                const padding = 40;
                const maxX = window.innerWidth - noButton.offsetWidth - padding;
                const maxY = window.innerHeight - noButton.offsetHeight - padding;
                
                const randomX = Math.max(padding, Math.random() * maxX);
                const randomY = Math.max(padding, Math.random() * maxY);
                
                noButton.style.position = 'fixed';
                noButton.style.left = randomX + 'px';
                noButton.style.top = randomY + 'px';
                noButton.style.zIndex = '1000';
            };

            noButton.addEventListener('mouseover', moveNoButton);
            noButton.addEventListener('touchstart', moveNoButton, { passive: false });
            noButton.addEventListener('click', moveNoButton);

            const heartsBg = document.getElementById('heartsBg');
            const heartSymbols = ['❤️', '💖', '💝', '💕', '✨'];
            
            for (let i = 0; i < 25; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart-particle');
                heart.innerText = heartSymbols[Math.floor(Math.random() * heartSymbols.length)];
                heart.style.left = (Math.random() * 100) + 'vw';
                heart.style.animationDelay = (Math.random() * 6) + 's';
                heart.style.fontSize = (Math.random() * 15 + 12) + 'px';
                heartsBg.appendChild(heart);
            }
        });

        function startConfetti() {
            const canvas = document.getElementById('confetti-canvas');
            const ctx = canvas.getContext('2d');
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;

            const pieces = [];
            const colors = ['#ff4d6d', '#ff758f', '#ffb3c1', '#fff', '#ffd166', '#06d6a0'];

            for (let i = 0; i < 150; i++) {
                pieces.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * canvas.height - canvas.height,
                    w: Math.random() * 10 + 5,
                    h: Math.random() * 10 + 5,
                    color: colors[Math.floor(Math.random() * colors.length)],
                    speed: Math.random() * 3 + 2,
                    angle: Math.random() * 360,
                    spin: Math.random() * 0.2 - 0.1
                });
            }

            function draw() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                pieces.forEach(p => {
                    ctx.save();
                    ctx.translate(p.x + p.w / 2, p.y + p.h / 2);
                    ctx.rotate(p.angle);
                    ctx.fillStyle = p.color;
                    ctx.fillRect(-p.w / 2, -p.h / 2, p.w, p.h);
                    ctx.restore();

                    p.y += p.speed;
                    p.angle += p.spin;

                    if (p.y > canvas.height) {
                        p.y = -20;
                        p.x = Math.random() * canvas.width;
                    }
                });
                requestAnimationFrame(draw);
            }
            draw();
            
            window.addEventListener('resize', () => {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
            });
        }
    </script>
</body>
</html>
