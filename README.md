<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            text-align: center;
            padding: 50px;
            overflow: hidden;
        }
        .container {
            position: relative;
            display: inline-block;
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
        }
        h1 {
            color: #ff4757;
            font-size: 3em;
            margin-bottom: 20px;
        }
        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        .buttons button {
            padding: 10px 20px;
            font-size: 1.5em;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        #yesButton {
            background-color: #ff6b81;
            color: white;
        }
        #noButton {
            background-color: #ff4757;
            color: white;
        }
        .hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .hearts img {
            position: absolute;
            width: 50px;
            animation: float 5s infinite ease-in-out;
        }
        .hearts img:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; }
        .hearts img:nth-child(2) { top: 20%; left: 80%; animation-delay: 1s; }
        .hearts img:nth-child(3) { top: 50%; left: 30%; animation-delay: 2s; }
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        .teddy-bear {
            position: absolute;
            bottom: 10px;
            right: 10px;
            width: 100px;
            z-index: -1; /* Ensure it stays in the background */
        }
        .congrats {
            display: none;
            font-size: 2em;
            color: #ff4757;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Dear Zuu,Be My Valentine?</h1>
        <h3>If you say no, you will experience certain effects. If you can see them, then there's no problem.</h3>
        <div class="buttons">
            <button id="yesButton">Yes</button>
            <button id="noButton">No</button>
        </div>
        <div class="hearts">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">
            <img src="https://img.icons8.com/color/48/000000/hearts.png" alt="heart">

        </div>
        <img class="teddy-bear" src="https://img.icons8.com/color/48/000000/teddy-bear.png" alt="teddy bear">
        <div class="congrats" id="congratsMessage">
            Congratulations! You are mine! & always Waisa batana ki kiya zarorat thi hehe :D ap hain hi mera.
        </div>
    </div>

    <script>
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const congratsMessage = document.getElementById('congratsMessage');
        const noTexts = ["No", "Kiu nhi ji?", "Itne buri hun kia?", "Buht buri hun kia?", "Nahi na na karo, say yeshh"];
        let step = 0;

        noButton.addEventListener('click', () => {
            step = (step + 1) % noTexts.length;
            noButton.textContent = noTexts[step];
            const currentSize = parseFloat(window.getComputedStyle(yesButton).fontSize);
            yesButton.style.fontSize = `${currentSize + 10}px`;
        });

        yesButton.addEventListener('click', () => {
            congratsMessage.style.display = 'block';
            yesButton.style.display = 'none';
            noButton.style.display = 'none';
        });
    </script>
</body>
</html>
