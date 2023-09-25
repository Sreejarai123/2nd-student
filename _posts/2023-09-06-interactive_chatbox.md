---
toc: true
comments: false
layout: post
title: chat box
description: an interactive chat box
type: hacks
courses: { compsci: {week: 3} }
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Static Chatbot</title>
    <style>
        /* Add your CSS styles here */
        body {
            font-family: Arial, sans-serif;
        }
        .chat-container {
            width: 300px;
            margin: 0 auto;
            border: 1px solid #ccc;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
        }
        .chat-header {
            background-color: #0074e4;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .chat-messages {
            padding: 10px;
            max-height: 300px;
            overflow-y: auto;
        }
        .message {
            margin-bottom: 10px;
        }
        .user-message {
            text-align: right;
            background-color: #0074e4;
            color: white;
            border-radius: 5px;
            padding: 5px 10px;
            display: inline-block;
        }
        .bot-message {
            text-align: left;
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 5px 10px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-header">
            Chatbot
        </div>
        <div class="chat-messages">
            <div class="bot-message">Hello! How can I assist you today?</div>
            <div class="user-message">Hi! I have a question.</div>
            <div class="bot-message">Sure, go ahead and ask.</div>
        </div>
    </div>
</body>
</html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Chatbox</title>
    <style>
        /* Add your CSS styles here */
        .chat-container {
            width: 300px;
            margin: 0 auto;
            border: 1px solid #ccc;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
        }
        .chat-header {
            background-color: #0074e4;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .chat-messages {
            padding: 10px;
            max-height: 300px;
            overflow-y: auto;
        }
        .message {
            margin-bottom: 10px;
        }
        .user-message {
            text-align: right;
            background-color: #0074e4;
            color: white;
            border-radius: 5px;
            padding: 5px 10px;
            display: inline-block;
        }
        .bot-message {
            text-align: left;
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 5px 10px;
            display: inline-block;
        }
        .chat-input {
            display: flex;
            justify-content: space-between;
            padding: 10px;
            background-color: #f9f9f9;
        }
        #user-input {
            flex-grow: 1;
            padding: 5px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        #send-button {
            background-color: #0074e4;
            color: white;
            border: none;
            border-radius: 3px;
            padding: 5px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-header">
            Chatbox
        </div>
        <div class="chat-messages" id="chat-messages">
            <!-- Chat messages will be displayed here -->
        </div>
        <div class="chat-input">
            <input type="text" id="user-input" placeholder="Type your message...">
            <button id="send-button">Send</button>
        </div>
    </div>

    <script>
        // JavaScript code for the interactive chatbox
        document.addEventListener("DOMContentLoaded", function () {
            const chatMessages = document.getElementById("chat-messages");
            const userInput = document.getElementById("user-input");
            const sendButton = document.getElementById("send-button");

            sendButton.addEventListener("click", function () {
                const userMessage = userInput.value.trim();
                if (userMessage !== "") {
                    appendMessage("You", userMessage);
                    userInput.value = ""; // Clear the input field
                }
            });

            function appendMessage(sender, message) {
                const messageElement = document.createElement("div");
                messageElement.classList.add("message");

                if (sender === "You") {
                    messageElement.innerHTML = `<div class="user-message">${sender}: ${message}</div>`;
                } else {
                    messageElement.innerHTML = `<div class="bot-message">${sender}: ${message}</div>`;
                }

                chatMessages.appendChild(messageElement);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
        });
    </script>
</body>
</html>
<html>
<head>
    <style>
        body {
            background-color: #e5c3d1; /* Light Purple color */
        }
    </style>
</head>
<body>
    
</body>
</html>
