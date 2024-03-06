---
toc: true
comments: true
layout: post
title: binary translator
description: transforms words to binary
type: hacks
courses: { compsci: {week: 7} }
---

<DOCYPE HTML>
<html lang="en">
<link href="styles.css">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Binary Translator</title>
   <style>
       body {
           display: flex;
           justify-content: center;
           align-items: center;
           height: 100vh;
           margin: 0;
           background-color: #f4f4f4;
           font-family: Arial, sans-serif;
       }
       .translator-container {
           text-align: center;
           border: 2px solid #333;
           padding: 20px;
           border-radius: 10px;
           background-color: white;
       }
       input {
           margin: 5px;
           padding: 8px;
           font-size: 16px;
       }
       button {
           margin: 5px;
           padding: 10px;
           font-size: 16px;
           cursor: pointer;
       }
        #colorShift {
            background-color: #123; 
        }
   </style>
</head>
<body>
   <div class="translator-container">
       <label for="text">Text:</label>
       <br>
       <input type="text" id="text" placeholder="Enter text">
       <br>
       <button onclick="textToBinary()">To Binary</button>
       <br>
       <label for="binary">Binary:</label>
       <br>
       <input type="text" id="binary" placeholder="Enter binary">
       <br>
       <button onclick="binaryToText()">To Text</button>
   </div>
    <div class="translator-container" id="colorShift">
       <p id="currentColor" style="background-color: purple;">Current Color: #123</p>
       <p id="currentBinary" style="background-color: purple;">Current Binary: 01111011</p>
       <button onclick="shiftLeft()">shift left</button>
       <br>
       <button onclick="shiftRight()">shift Right</button>
       <br>
   </div>
   <script>
       function textToBinary() {
           const textInput = document.getElementById('text').value;
           const binaryOutput = textInput.split('').map(char => char.charCodeAt(0).toString(2)).join(' ');
           document.getElementById('binary').value = binaryOutput;
       }
       function binaryToText() {
           const binaryInput = document.getElementById('binary').value;
           const textOutput = binaryInput.split(' ').map(bin => String.fromCharCode(parseInt(bin, 2))).join('');
           document.getElementById('text').value = textOutput;
       }
        var backgroundColor = '123';
        var backgroundColorBinary;
        function shiftLeft() {
            backgroundColorBinary = Number(backgroundColor).toString(2);
            backgroundColorBinary = backgroundColorBinary + "0";
            backgroundColor = parseInt(backgroundColorBinary, 2);
            document.getElementById("currentColor").textContent = "Current Color: #" + backgroundColor;
            document.getElementById("currentBinary").textContent = "Current Binary: " + backgroundColorBinary;
            document.getElementById("colorShift").style.background = "#" + backgroundColor;
       }
       function shiftRight() {
            backgroundColorBinary = Number(backgroundColor).toString(2);
            backgroundColorBinary = backgroundColorBinary.substring(0, backgroundColorBinary.length-1);
            backgroundColor = parseInt(backgroundColorBinary, 2);
            document.getElementById("currentColor").textContent = "Current Color: #" + backgroundColor;
            document.getElementById("currentBinary").textContent = "Current Binary: " + backgroundColorBinary;
            document.getElementById("colorShift").style.background = "#" + backgroundColor;
       }
   </script>
</body>
</html>