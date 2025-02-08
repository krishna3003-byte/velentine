# velentine
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine, Humera?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffcccb;
            text-align: center;
            padding: 50px;
            position: relative;
            overflow: hidden;
        }
        h1 {
            color: #d63447;
            font-size: 1.6em;
        }
        p {
            color: #333;
            font-size: 1.5em;
        }
        .button {
            background-color: #d63447;
            color: white;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 1.2em;
            margin: 20px 10px;
            cursor: pointer;
            border: none;
            border-radius: 12px;
            transition: all 0.3s ease;
        }
        .button:hover {
            background-color: #ff6f61;
        }
        .heart {
            color: #d63447;
            font-size: 2em;
        }
        .cute-message {
            color: #d63447;
            font-size: 1.2em;
            margin-top: 15px;
            display: none;
        }
        /* Hide the audio controls */
        audio {
            display: none;
        }
    </style>
</head>
<body>
    <h1>Will You Be My Valentine, Humera?</h1>
    <p>Hey Humera,</p>
    <p>I know this might be a little cheesy, but I couldn't resist creating this website just for you.</p>
    <p>You mean so much to me, and I was wondering...</p>
    <p>Will you be my Valentine?</p>
    <p class="heart">❤️</p>
    <button class="button" id="yesButton" onclick="alert('Yay! I\'m so happy! ❤️')">Yes!</button>
    <button class="button" id="noButton">Maybe Later</button>
    <p id="cuteMessage" class="cute-message"></p>

    <!-- Romantic Song: "Perfect" by Ed Sheeran -->
    <audio autoplay loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <script>
        const noButton = document.getElementById('noButton');
        const cuteMessage = document.getElementById('cuteMessage');
        const messages = [
            "Are you sure? 😢",
            "Pretty please? 🥺",
            "I'll make it worth your while! 😘",
            "Just say yes! 😍",
            "You're breaking my heart! 💔",
            "I won't give up! ❤️",
            "Okay, last chance... say yes! 😊"
        ];
        let messageIndex = 0;

        noButton.addEventListener('click', () => {
            // Display cute messages
            cuteMessage.textContent = messages[messageIndex];
            cuteMessage.style.display = 'block';
            messageIndex = (messageIndex + 1) % messages.length;

            // Move the button around
            const x = Math.random() * (window.innerWidth - noButton.offsetWidth);
            const y = Math.random() * (window.innerHeight - noButton.offsetHeight);
            noButton.style.position = 'absolute';
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;

            // Remove the "Maybe Later" button after a few tries
            if (messageIndex === messages.length - 1) {
                noButton.style.display = 'none';
                cuteMessage.textContent = "You have no choice now... it's a YES! ❤️";
            }
        });
    </script>
</body>
</html>
