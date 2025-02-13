# Will-you-be-my-Valentine-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding-top: 50px;
            background-color: #f7f7f7;
            margin: 0;
            height: 100vh;
        }
        .button {
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            transition: transform 0.3s ease, font-size 0.3s ease;
            margin: 10px;
        }
        .yes {
            background-color: #ff5f5f;
            color: white;
            border: none;
            transition: transform 0.3s ease;
        }
        .no {
            background-color: #5f5fff;
            color: white;
            border: none;
        }
        .yes:hover, .no:hover {
            transform: scale(1.1);
        }
        /* Full-screen button effect */
        .yes.full-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            font-size: 50px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .message {
            margin-top: 20px;
            font-size: 20px;
            color: #333;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>Will you be my Valentine?</h1>
    <button class="button yes" id="yesButton">Yes</button>
    <button class="button no" id="noButton">No</button>

    <div id="message" class="message"></div>

    <script>
        let scale = 1; // Variable to track the size scaling of the Yes button
        const yesButton = document.getElementById("yesButton");
        const noButton = document.getElementById("noButton");
        const messageDiv = document.getElementById("message");

        // List of messages to show when No is clicked
        const messages = [
            "Why pookie, do you love me? Please say yes! 😔",
            "Come on, say yes! I’m waiting... 💕",
            "You’re my Valentine, right? Pretty please! 😍",
            "Why are you making me wait? Just say yes! ❤️",
            "I promise I'll make it worth it! Please say yes! 😘"
        ];

        let messageIndex = 0; // To keep track of the current message

        noButton.addEventListener("click", function() {
            // Show the next message in the list
            messageDiv.textContent = messages[messageIndex];
            messageIndex = (messageIndex + 1) % messages.length; // Cycle through the messages

            scale += 0.1; // Increase the size factor of the Yes button
            yesButton.style.transform = `scale(${scale})`; // Apply the scaling effect

            if (scale >= 10) { // When the scale is large enough, make the Yes button fullscreen
                yesButton.classList.add('full-screen');
                yesButton.innerText = 'YES! ❤️'; // Change the text when it's full-screen
            }
        });

        yesButton.addEventListener("click", function() {
            alert("Thank you pookie I love you so much🎀! ❤️");
        });
    </script>

</body>
</html>
