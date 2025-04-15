<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #8a2be2, #ff69b4);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3);
            animation: bounce 2s infinite;
        }
        
        .message {
            font-size: 1.5rem;
            margin-bottom: 30px;
            line-height: 1.6;
        }
        
        .cake {
            font-size: 100px;
            margin: 30px 0;
            text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.3);
            animation: rotate 4s infinite alternate;
        }
        
        .balloons {
            display: flex;
            justify-content: space-around;
            width: 100%;
            margin: 20px 0;
        }
        
        .balloon {
            font-size: 40px;
            animation: float 3s infinite alternate;
            animation-delay: calc(var(--i) * 0.5s);
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #fff;
            opacity: 0.7;
            animation: confetti-fall 5s linear infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-20px); }
        }
        
        @keyframes rotate {
            0% { transform: rotate(-5deg); }
            100% { transform: rotate(5deg); }
        }
        
        @keyframes confetti-fall {
            0% { transform: translateY(-100vh) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }
        
        @media (max-width: 600px) {
            h1 {
                font-size: 2rem;
            }
            
            .message {
                font-size: 1.2rem;
            }
            
            .cake {
                font-size: 70px;
            }
            
            .balloon {
                font-size: 30px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="balloons">
            <div class="balloon" style="--i:0;">🎈</div>
            <div class="balloon" style="--i:1;">🎈</div>
            <div class="balloon" style="--i:2;">🎈</div>
            <div class="balloon" style="--i:3;">🎈</div>
            <div class="balloon" style="--i:4;">🎈</div>
        </div>
        
        <h1>Happy Birthday, Wonderful Friend!</h1>
        
        <div class="cake">🎂</div>
        
        <div class="message">
            On your special day, I wanted to wish you the happiest of birthdays! May this year bring you joy, success, and all the amazing things you deserve.
        </div>
        
        <div class="balloons">
            <div class="balloon" style="--i:2;">🎉</div>
            <div class="balloon" style="--i:3;">🎁</div>
            <div class="balloon" style="--i:4;">✨</div>
            <div class="balloon" style="--i:5;">🎊</div>
            <div class="balloon" style="--i:6;">🎉</div>
        </div>
    </div>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Create confetti
            for (let i = 0; i < 100; i++) {
                createConfetti();
            }
            
            // Continue creating confetti
            setInterval(function() {
                createConfetti();
            }, 300);
        });
        
        function createConfetti() {
            const confetti = document.createElement('div');
            confetti.classList.add('confetti');
            
            // Random position, color and animation duration
            const colors = ['#ff69b4', '#ff1493', '#8a2be2', '#1e90ff', '#ffff00', '#ff8c00'];
            const left = Math.random() * 100;
            const color = colors[Math.floor(Math.random() * colors.length)];
            const duration = 5 + Math.random() * 5;
            
            confetti.style.left = left + 'vw';
            confetti.style.backgroundColor = color;
            confetti.style.animationDuration = duration + 's';
            confetti.style.width = (5 + Math.random() * 10) + 'px';
            confetti.style.height = (5 + Math.random() * 10) + 'px';
            confetti.style.opacity = 0.5 + Math.random() * 0.5;
            
            document.body.appendChild(confetti);
            
            // Remove confetti after animation completes
            setTimeout(function() {
                confetti.remove();
            }, duration * 1000);
        }
    </script>
</body>
</html>
