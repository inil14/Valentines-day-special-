# Valentines-day-special-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Valentine's Day Surprise</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial Rounded MT Bold', 'Arial', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }
        
        body {
            background: linear-gradient(135deg, #ffafbd, #ffc3a0);
            min-height: 100vh;
            min-height: -webkit-fill-available;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            touch-action: manipulation;
        }
        
        .container {
            text-align: center;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.92);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            width: 90%;
            max-width: 800px;
            margin: 15px;
            position: relative;
            z-index: 10;
            border: 8px solid #ff6b8b;
        }
        
        h1 {
            color: #d32f75;
            font-size: clamp(2.2rem, 5vw, 3.5rem);
            margin-bottom: 12px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            line-height: 1.2;
        }
        
        .subtitle {
            color: #ff4081;
            font-size: clamp(1.2rem, 3vw, 1.5rem);
            margin-bottom: 25px;
        }
        
        .buttons-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 35px 0;
            position: relative;
            min-height: 180px;
            width: 100%;
            overflow: hidden;
        }
        
        .valentine-button {
            padding: 18px 35px;
            font-size: clamp(1.5rem, 4vw, 1.8rem);
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: not-allowed;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            position: absolute;
            user-select: none;
            z-index: 5;
            -webkit-user-select: none;
            -webkit-touch-callout: none;
            touch-action: none;
            min-width: 140px;
            text-align: center;
        }
        
        .yes-button {
            background: linear-gradient(to right, #ff5e8e, #ff2e63);
            color: white;
            left: 50%;
            top: 30px;
            transform: translateX(-50%);
        }
        
        .no-button {
            background: linear-gradient(to right, #36d1dc, #5b86e5);
            color: white;
            left: 50%;
            top: 120px;
            transform: translateX(-50%);
        }
        
        .valentine-button:hover, .valentine-button:active {
            transform: scale(1.05);
        }
        
        .message {
            font-size: clamp(1rem, 2.5vw, 1.4rem);
            color: #333;
            margin: 20px 0;
            padding: 15px;
            background-color: rgba(255, 235, 238, 0.7);
            border-radius: 15px;
            border-left: 6px solid #ff4081;
            line-height: 1.5;
        }
        
        .instructions {
            background-color: rgba(255, 255, 255, 0.7);
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            color: #555;
            font-size: clamp(0.9rem, 2vw, 1.1rem);
            line-height: 1.4;
        }
        
        .hearts-container {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
        }
        
        .heart {
            position: absolute;
            color: #ff4081;
            font-size: clamp(18px, 4vw, 24px);
            animation: float 6s infinite ease-in-out;
        }
        
        .balloon {
            position: absolute;
            width: clamp(40px, 8vw, 60px);
            height: clamp(60px, 10vw, 80px);
            border-radius: 50%;
            animation: floatUp 15s infinite linear;
            z-index: 2;
        }
        
        .balloon:before {
            content: '';
            position: absolute;
            width: 2px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.7);
            top: 100%;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .balloon:nth-child(1) {
            background-color: #ff6b8b;
            left: 10%;
            top: 90%;
            animation-duration: 18s;
        }
        
        .balloon:nth-child(2) {
            background-color: #36d1dc;
            left: 20%;
            top: 85%;
            animation-duration: 22s;
        }
        
        .balloon:nth-child(3) {
            background-color: #5b86e5;
            left: 30%;
            top: 95%;
            animation-duration: 16s;
        }
        
        .balloon:nth-child(4) {
            background-color: #ffd166;
            left: 70%;
            top: 90%;
            animation-duration: 20s;
        }
        
        .balloon:nth-child(5) {
            background-color: #06d6a0;
            left: 80%;
            top: 85%;
            animation-duration: 25s;
        }
        
        .balloon:nth-child(6) {
            background-color: #ff9e6d;
            left: 90%;
            top: 95%;
            animation-duration: 19s;
        }
        
        .footer {
            margin-top: 15px;
            color: #fff;
            text-align: center;
            font-size: clamp(0.8rem, 2vw, 1rem);
            padding: 10px;
            z-index: 10;
            line-height: 1.4;
        }
        
        .footer i {
            color: #ff2e63;
            margin: 0 3px;
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
                opacity: 0.8;
            }
            50% {
                transform: translateY(-20px) rotate(10deg);
                opacity: 1;
            }
        }
        
        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0.8;
            }
            100% {
                transform: translateY(-100vh) rotate(20deg);
                opacity: 0;
            }
        }
        
        @keyframes moveButton {
            0% {
                transform: translate(-50%, 0);
            }
            25% {
                transform: translate(calc(-50% + 30px), 40px);
            }
            50% {
                transform: translate(calc(-50% - 20px), 60px);
            }
            75% {
                transform: translate(calc(-50% + 40px), -20px);
            }
            100% {
                transform: translate(-50%, 0);
            }
        }
        
        /* Mobile-specific adjustments */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
                margin: 10px;
            }
            
            .buttons-container {
                min-height: 220px;
            }
            
            .valentine-button {
                padding: 16px 30px;
                min-width: 120px;
            }
            
            .yes-button {
                top: 20px;
            }
            
            .no-button {
                top: 130px;
            }
            
            .balloon {
                width: 35px;
                height: 50px;
            }
            
            .balloon:before {
                height: 30px;
            }
        }
        
        @media (max-width: 480px) {
            .container {
                padding: 12px;
                border-width: 5px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .buttons-container {
                min-height: 200px;
            }
            
            .valentine-button {
                padding: 14px 25px;
                font-size: 1.3rem;
                min-width: 110px;
            }
            
            .message, .instructions {
                padding: 12px;
            }
            
            .footer {
                padding: 8px;
            }
        }
        
        /* Prevent text selection on buttons */
        .valentine-button {
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }
        
        /* Improve touch response */
        .valentine-button:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>
    <div class="hearts-container" id="hearts-container"></div>
    
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    
    <div class="container">
        <h1><i class="fas fa-heart"></i> Valentine's Day <i class="fas fa-heart"></i></h1>
        <div class="subtitle">Will you be my Valentine?</div>
        
        <div class="message">
            <i class="fas fa-quote-left"></i> 
            Love is not about how many days, months, or years you have been together. 
            Love is about how much you love each other every single day.
            <i class="fas fa-quote-right"></i>
        </div>
        
        <div class="buttons-container" id="buttonsContainer">
            <button class="valentine-button yes-button" id="yesButton">YES</button>
            <button class="valentine-button no-button" id="noButton">NO</button>
        </div>
        
        <div class="instructions">
            <i class="fas fa-info-circle"></i> 
            Try to tap the buttons! They're not clickable and will move around when you try to tap them! 
            The "NO" button is especially tricky!
        </div>
    </div>
    
    <div class="footer">
        Made with <i class="fas fa-heart"></i> for Valentine's Day | 
        <i class="fas fa-mobile-alt"></i> Mobile Friendly
    </div>

    <script>
        // Mobile detection
        const isMobile = /iPhone|iPad|iPod|Android/i.test(navigator.userAgent);
        
        // Create floating hearts
        const heartsContainer = document.getElementById('hearts-container');
        const heartCount = isMobile ? 15 : 25; // Fewer hearts on mobile for performance
        
        for (let i = 0; i < heartCount; i++) {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '<i class="fas fa-heart"></i>';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = Math.random() * 100 + 'vh';
            heart.style.fontSize = (Math.random() * 15 + 10) + 'px';
            heart.style.animationDelay = Math.random() * 5 + 's';
            heart.style.opacity = Math.random() * 0.5 + 0.3;
            heartsContainer.appendChild(heart);
        }
        
        // Get buttons and container
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const buttonsContainer = document.getElementById('buttonsContainer');
        
        // Function to generate random position within container
        function getRandomPosition(button) {
            const containerWidth = buttonsContainer.clientWidth;
            const containerHeight = buttonsContainer.clientHeight;
            const buttonWidth = button.clientWidth;
            const buttonHeight = button.clientHeight;
            
            const maxX = containerWidth - buttonWidth;
            const maxY = containerHeight - buttonHeight;
            
            // Ensure buttons stay within container bounds
            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);
            
            return { x: randomX, y: randomY };
        }
        
        // Function to move button to random position
        function moveButton(button) {
            const newPosition = getRandomPosition(button);
            
            if (button.id === 'yesButton') {
                button.style.left = newPosition.x + 'px';
                button.style.top = newPosition.y + 'px';
                button.style.transform = 'translate(0, 0)';
            } else {
                button.style.left = newPosition.x + 'px';
                button.style.top = newPosition.y + 'px';
                button.style.transform = 'translate(0, 0)';
            }
            
            // Add animation effect
            button.style.animation = 'moveButton 0.5s ease';
            setTimeout(() => {
                button.style.animation = '';
            }, 500);
        }
        
        // Set initial random positions
        window.addEventListener('load', () => {
            setTimeout(() => {
                moveButton(yesButton);
                moveButton(noButton);
            }, 500);
        });
        
        // Make buttons move on hover (for desktop)
        if (!isMobile) {
            yesButton.addEventListener('mouseover', () => {
                moveButton(yesButton);
            });
            
            noButton.addEventListener('mouseover', () => {
                moveButton(noButton);
            });
        }
        
        // Touch events for mobile
        yesButton.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveButton(yesButton);
            // Move the other button too for more fun
            setTimeout(() => moveButton(noButton), 100);
        });
        
        noButton.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveButton(noButton);
            // Move farther for the "NO" button
            setTimeout(() => moveButton(noButton), 50);
            setTimeout(() => moveButton(noButton), 150);
        });
        
        // Click events (for both mobile and desktop)
        yesButton.addEventListener('click', (e) => {
            e.preventDefault();
            moveButton(yesButton);
            // Show a cute message
            setTimeout(() => {
                alert("I knew you'd say YES! 💖 Happy Valentine's Day!");
            }, 300);
        });
        
        noButton.addEventListener('click', (e) => {
            e.preventDefault();
            moveButton(noButton);
            // Make it even harder to click by moving it again immediately
            setTimeout(() => moveButton(noButton), 50);
            setTimeout(() => moveButton(noButton), 150);
        });
        
        // Also move buttons randomly every 8-12 seconds
        setInterval(() => {
            moveButton(yesButton);
        }, 8000 + Math.random() * 4000);
        
        setInterval(() => {
            moveButton(noButton);
        }, 7000 + Math.random() * 3000);
        
        // Add keyboard interaction for fun (disabled on mobile virtual keyboard)
        if (!isMobile) {
            document.addEventListener('keydown', (e) => {
                if (e.key === 'y' || e.key === 'Y') {
                    moveButton(yesButton);
                    setTimeout(() => {
                        alert("Y for YES! You're so sweet! 💝");
                    }, 300);
                } else if (e.key === 'n' || e.key === 'N') {
                    moveButton(noButton);
                    setTimeout(() => moveButton(noButton), 100);
                }
            });
        }
        
        // Handle window resize
        let resizeTimeout;
        window.addEventListener('resize', () => {
            clearTimeout(resizeTimeout);
            resizeTimeout = setTimeout(() => {
                moveButton(yesButton);
                moveButton(noButton);
            }, 250);
        });
        
        // Prevent context menu on buttons for mobile
        yesButton.addEventListener('contextmenu', (e) => e.preventDefault());
        noButton.addEventListener('contextmenu', (e) => e.preventDefault());
        
        // Add vibration on mobile when button moves (if supported)
        if (isMobile && navigator.vibrate) {
            const originalMoveButton = moveButton;
            moveButton = function(button) {
                originalMoveButton(button);
                navigator.vibrate(50);
            };
        }
    </script>
</body>
</html>
