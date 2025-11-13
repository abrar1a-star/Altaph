<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Althaf Bau Belum Mandi</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #004d00; /* Dark green background */
            font-family: Arial, sans-serif;
            overflow: hidden; /* Prevent scrolling */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            position: relative;
        }
        .bathtub {
            position: absolute;
            font-size: 20em; /* Large bathtub emoji */
            color: rgba(255, 255, 255, 0.1); /* Faint white for subtle background effect */
            z-index: 1; /* Behind text but above nothing else */
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            pointer-events: none;
        }
        .text {
            font-size: 3em;
            color: #fff; /* White text for contrast on dark background */
            text-align: center;
            z-index: 10; /* Keep text above falling emojis and bathtub */
            background: rgba(0, 0, 0, 0.5); /* Semi-transparent dark background for readability */
            padding: 20px;
            border-radius: 10px;
        }
        .emoji {
            position: absolute;
            font-size: 2em;
            animation: fall linear infinite;
            pointer-events: none; /* So they don't interfere with clicks */
        }
        @keyframes fall {
            0% {
                top: -50px;
                opacity: 1;
            }
            100% {
                top: 100vh;
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="bathtub">🛁</div>
    <div class="text">Althaf Bau Belum Mandi</div>
    
    <script>
        const emojis = ['💩', '🤢', '😷', '🗑️', '🤮', '👃', '🚽', '🧴']; // Disgust-themed emojis
        const container = document.body;

        function createFallingEmoji() {
            const emoji = document.createElement('div');
            emoji.className = 'emoji';
            emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
            emoji.style.left = Math.random() * 100 + 'vw'; // Random horizontal position
            emoji.style.animationDuration = (Math.random() * 3 + 2) + 's'; // Random fall speed (2-5 seconds)
            container.appendChild(emoji);

            // Remove emoji after animation to avoid buildup
            setTimeout(() => {
                container.removeChild(emoji);
            }, 5000);
        }

        // Create new emojis every 200ms for a steady "rain"
        setInterval(createFallingEmoji, 200);
    </script>
</body>
</html>
