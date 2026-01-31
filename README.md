<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Justin's Valentine Challenge 💖</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            user-select: none;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            min-height: 100vh;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
        }

        .container {
            max-width: 800px;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 25px;
            padding: 40px 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            position: relative;
            z-index: 10;
            border: 8px solid #ff4d6d;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        h1 {
            color: #d63384;
            font-size: 3.2rem;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        h1:after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            height: 4px;
            background: linear-gradient(to right, #ff4d6d, #ff8fab);
            border-radius: 2px;
        }

        .subtitle {
            font-size: 1.5rem;
            color: #a61e4d;
            margin-bottom: 25px;
            font-weight: 600;
        }

        .jelena-signature {
            font-family: 'Dancing Script', cursive;
            font-size: 2.2rem;
            color: #ff4d6d;
            margin: 10px 0 30px;
            display: block;
        }

        #timer {
            background: linear-gradient(to right, #ff4d6d, #ff8fab);
            color: white;
            font-size: 2rem;
            font-weight: bold;
            padding: 15px 30px;
            border-radius: 15px;
            margin: 25px auto;
            width: fit-content;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .buttons-container {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
            flex-wrap: wrap;
            position: relative;
            min-height: 120px;
        }

        button {
            font-size: 1.8rem;
            padding: 20px 45px;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            min-width: 180px;
        }

        #yes {
            background: linear-gradient(to right, #ff4d6d, #ff8fab);
            color: white;
            position: relative;
            z-index: 5;
        }

        #yes:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 20px rgba(255, 77, 109, 0.5);
        }

        #no {
            background: linear-gradient(to right, #6c757d, #adb5bd);
            color: white;
            position: absolute;
        }

        #no:hover {
            background: linear-gradient(to right, #495057, #868e96);
        }

        /* Shake animation */
        .shake {
            animation: shake 0.5s ease;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            10%, 30%, 50%, 70%, 90% { transform: translateX(-8px); }
            20%, 40%, 60%, 80% { transform: translateX(8px); }
        }

        /* Floating hearts */
        .heart {
            position: absolute;
            font-size: 24px;
            color: #ff4d6d;
            z-index: 1;
            opacity: 0.7;
            animation: floatAround 20s linear infinite;
        }

        @keyframes floatAround {
            0% {
                transform: translate(0, 0) rotate(0deg);
                opacity: 0.7;
            }
            25% {
                transform: translate(100px, 100px) rotate(90deg);
                opacity: 1;
            }
            50% {
                transform: translate(50px, 200px) rotate(180deg);
                opacity: 0.7;
            }
            75% {
                transform: translate(-50px, 150px) rotate(270deg);
                opacity: 0.9;
            }
            100% {
                transform: translate(0, 0) rotate(360deg);
                opacity: 0.7;
            }
        }

        /* Falling hearts for celebration */
        .falling-heart {
            position: fixed;
            top: -50px;
            font-size: 28px;
            color: #ff4d6d;
            z-index: 100;
            pointer-events: none;
            animation: fall linear forwards;
        }

        @keyframes fall {
            to {
                transform: translateY(110vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Instructions */
        .instructions {
            margin-top: 30px;
            font-size: 1.1rem;
            color: #6c757d;
            font-style: italic;
            background-color: rgba(255, 255, 255, 0.7);
            padding: 15px;
            border-radius: 10px;
            max-width: 600px;
        }

        /* Music controls */
        .music-controls {
            position: absolute;
            top: 20px;
            right: 20px;
            background: white;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            z-index: 100;
            transition: all 0.3s ease;
        }

        .music-controls:hover {
            transform: scale(1.1);
            background-color: #ffeef2;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.3rem;
            }
            
            .jelena-signature {
                font-size: 1.8rem;
            }
            
            button {
                font-size: 1.5rem;
                padding: 18px 35px;
                min-width: 150px;
            }
            
            #timer {
                font-size: 1.8rem;
                padding: 12px 25px;
            }
            
            .buttons-container {
                gap: 20px;
            }
            
            .container {
                padding: 30px 20px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 2rem;
            }
            
            button {
                font-size: 1.3rem;
                padding: 15px 25px;
            }
            
            .buttons-container {
                flex-direction: column;
                align-items: center;
            }
            
            #no {
                position: relative;
                margin-top: 20px;
            }
        }

        /* Confetti effect */
        .confetti {
            position: fixed;
            width: 15px;
            height: 15px;
            background-color: #ff4d6d;
            top: -10px;
            z-index: 99;
            pointer-events: none;
            animation: confettiFall 5s linear forwards;
        }

        @keyframes confettiFall {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }

        /* Couch warning */
        .couch-warning {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 10px 20px;
            border-radius: 10px;
            font-size: 1rem;
            opacity: 0;
            transition: opacity 0.5s;
            z-index: 20;
        }

        .couch-warning.show {
            opacity: 1;
        }
        
        /* Deployment info */
        .deployment-info {
            position: fixed;
            bottom: 10px;
            left: 10px;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 8px 12px;
            border-radius: 8px;
            font-size: 0.8rem;
            z-index: 100;
        }
        
        .deployment-info a {
            color: #ff8fab;
            text-decoration: none;
        }
        
        .deployment-info a:hover {
            text-decoration: underline;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
</head>
<body>

    <div class="music-controls" id="musicToggle">
        <i class="fas fa-music" id="musicIcon"></i>
    </div>

    <div class="container">
        <h1>Hey Justin 😏</h1>
        <p class="subtitle">Will you be Jelena's Valentine? 💘</p>
        <span class="jelena-signature">~ Jelena ~</span>
        
        <div id="timer">
            <i class="fas fa-hourglass-half"></i>
            <span id="timeLeft">10</span> seconds left
        </div>
        
        <div class="buttons-container">
            <button id="yes" onclick="yesClicked()">
                <i class="fas fa-heart"></i> YES ❤️
            </button>
            <button id="no" onmouseover="shakeAndRun()" ontouchstart="shakeAndRun()">
                <i class="fas fa-heart-broken"></i> NO 💔
            </button>
        </div>
        
        <p class="instructions">
            Hint: The "NO" button might be tricky to catch! Choose wisely... 😉
        </p>
    </div>

    <div class="couch-warning" id="couchWarning">
        <i class="fas fa-couch"></i> Choosing NO means sleeping on the couch! <i class="fas fa-couch"></i>
    </div>

    <audio id="bgMusic" loop>
        <source src="https://assets.mixkit.co/music/preview/mixkit-clear-love-739.mp3" type="audio/mpeg">
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <div class="deployment-info">
        Share this link: <span id="pageUrl">Loading...</span>
    </div>

    <script>
        // Initialize variables
        let timeLeft = 10;
        let musicStarted = false;
        let countdown;
        let heartsInterval;
        let isYesClicked = false;
        
        // Create floating hearts background
        function createFloatingHearts() {
            for (let i = 0; i < 20; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.innerHTML = '❤️';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.top = Math.random() * 100 + 'vh';
                heart.style.fontSize = (20 + Math.random() * 30) + 'px';
                heart.style.animationDuration = (15 + Math.random() * 20) + 's';
                document.body.appendChild(heart);
            }
        }
        
        // Start the countdown timer
        function startTimer() {
            const timerElement = document.getElementById('timeLeft');
            countdown = setInterval(() => {
                timeLeft--;
                timerElement.textContent = timeLeft;
                
                // Change color when time is running out
                if (timeLeft <= 5) {
                    document.getElementById('timer').style.background = 'linear-gradient(to right, #dc3545, #ff6b6b)';
                }
                
                if (timeLeft <= 0) {
                    clearInterval(countdown);
                    if (!isYesClicked) {
                        autoSelectYes();
                    }
                }
            }, 1000);
        }
        
        // Auto-select YES when time runs out
        function autoSelectYes() {
            isYesClicked = true;
            document.getElementById('timer').innerHTML = '<i class="fas fa-heart"></i> Time\'s up! Auto-selecting YES!';
            document.getElementById('timer').style.background = 'linear-gradient(to right, #28a745, #20c997)';
            
            setTimeout(() => {
                celebrateYes();
            }, 1000);
        }
        
        // Handle YES button click
        function yesClicked() {
            if (isYesClicked) return;
            
            isYesClicked = true;
            clearInterval(countdown);
            document.getElementById('timer').innerHTML = '<i class="fas fa-heart"></i> You made the right choice!';
            document.getElementById('timer').style.background = 'linear-gradient(to right, #28a745, #20c997)';
            
            // Show celebration
            celebrateYes();
        }
        
        // Celebration when YES is selected
        function celebrateYes() {
            // Launch falling hearts
            launchHearts();
            
            // Create confetti
            createConfetti();
            
            // Show success message
            setTimeout(() => {
                const messages = [
                    "Yay! You're Jelena's Valentine! 😘❤️",
                    "Perfect choice! Now get ready for an amazing Valentine's Day! 💝",
                    "Wise decision! You just avoided couch sleeping 😌🛋️"
                ];
                
                const randomMessage = messages[Math.floor(Math.random() * messages.length)];
                alert(randomMessage);
                
                // Keep celebrating with hearts
                heartsInterval = setInterval(launchHearts, 500);
                
                // Stop after 10 seconds
                setTimeout(() => {
                    clearInterval(heartsInterval);
                }, 10000);
            }, 800);
        }
        
        // Create falling hearts for celebration
        function launchHearts() {
            for (let i = 0; i < 15; i++) {
                const heart = document.createElement('div');
                heart.classList.add('falling-heart');
                heart.innerHTML = ['❤️', '💖', '💘', '💝', '💗', '💓'][Math.floor(Math.random() * 6)];
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.fontSize = (20 + Math.random() * 25) + 'px';
                heart.style.animationDuration = (3 + Math.random() * 4) + 's';
                document.body.appendChild(heart);
                
                // Remove heart after animation
                setTimeout(() => {
                    if (heart.parentNode) {
                        heart.parentNode.removeChild(heart);
                    }
                }, 5000);
            }
        }
        
        // Create confetti effect
        function createConfetti() {
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.backgroundColor = ['#ff4d6d', '#ff8fab', '#ffb3c1', '#ffccd5', '#c9184a'][Math.floor(Math.random() * 5)];
                confetti.style.width = (10 + Math.random() * 15) + 'px';
                confetti.style.height = (10 + Math.random() * 15) + 'px';
                confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                confetti.style.animationDuration = (2 + Math.random() * 3) + 's';
                document.body.appendChild(confetti);
                
                // Remove confetti after animation
                setTimeout(() => {
                    if (confetti.parentNode) {
                        confetti.parentNode.removeChild(confetti);
                    }
                }, 5000);
            }
        }
        
        // Handle NO button hover/touch
        function shakeAndRun() {
            if (isYesClicked) return;
            
            const noBtn = document.getElementById('no');
            
            // Show couch warning
            document.getElementById('couchWarning').classList.add('show');
            setTimeout(() => {
                document.getElementById('couchWarning').classList.remove('show');
            }, 2000);
            
            // Shake animation
            noBtn.classList.add('shake');
            
            setTimeout(() => {
                noBtn.classList.remove('shake');
                
                // Move button to random position
                runAway();
            }, 500);
        }
        
        // Move NO button to random position
        function runAway() {
            const noBtn = document.getElementById('no');
            const container = document.querySelector('.buttons-container');
            const containerRect = container.getBoundingClientRect();
            
            // Calculate random position within container
            const maxX = containerRect.width - noBtn.offsetWidth;
            const maxY = containerRect.height - noBtn.offsetHeight;
            
            const randomX = Math.random() * maxX;
            const randomY = Math.random() * maxY;
            
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        }
        
        // Music controls
        document.getElementById('musicToggle').addEventListener('click', function() {
            const music = document.getElementById('bgMusic');
            const icon = document.getElementById('musicIcon');
            
            if (music.paused) {
                music.play();
                icon.classList.remove('fa-music');
                icon.classList.add('fa-volume-up');
            } else {
                music.pause();
                icon.classList.remove('fa-volume-up');
                icon.classList.add('fa-music');
            }
        });
        
        // Auto-start music on first interaction
        function startMusicOnInteraction() {
            if (!musicStarted) {
                document.getElementById('bgMusic').play().catch(e => {
                    console.log("Autoplay prevented. User interaction required.");
                });
                musicStarted = true;
                document.getElementById('musicIcon').classList.remove('fa-music');
                document.getElementById('musicIcon').classList.add('fa-volume-up');
            }
        }
        
        // Show current URL for sharing
        function showCurrentUrl() {
            const urlElement = document.getElementById('pageUrl');
            urlElement.textContent = window.location.href;
            
            // Make it clickable to copy
            urlElement.style.cursor = 'pointer';
            urlElement.title = 'Click to copy URL';
            urlElement.addEventListener('click', function() {
                navigator.clipboard.writeText(window.location.href).then(() => {
                    const originalText = urlElement.textContent;
                    urlElement.textContent = 'URL copied!';
                    setTimeout(() => {
                        urlElement.textContent = originalText;
                    }, 2000);
                });
            });
        }
        
        // Initialize the page
        function init() {
            createFloatingHearts();
            startTimer();
            showCurrentUrl();
            
            // Start music on any user interaction
            document.addEventListener('click', startMusicOnInteraction);
            document.addEventListener('touchstart', startMusicOnInteraction);
            document.addEventListener('keydown', startMusicOnInteraction);
            
            // Set initial position for NO button
            document.getElementById('no').style.position = 'absolute';
        }
        
        // Start everything when page loads
        window.onload = init;
    </script>
</body>
</html>
