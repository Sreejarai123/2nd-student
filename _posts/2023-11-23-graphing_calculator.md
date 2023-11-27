---
toc: true
comments: true
layout: post
title: binary translator
description: binary translator
type: hacks
courses: { compsci: {week: 7} }
---

<!DOCTYPE html>
<html lang="en">
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

       .switch-container {
           display: flex;
           justify-content: center;
           margin-top: 10px;
       }

       .switch-label {
           margin-right: 5px;
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
       <div class="switch-container">
           <span class="switch-label">Left Shift</span>
           <label class="switch">
               <input type="checkbox" id="shiftSwitch">
               <span class="slider round"></span>
           </label>
           <span class="switch-label">Right Shift</span>
       </div>
       <br>
       <label for="binary">Binary:</label>
       <br>
       <input type="text" id="binary" placeholder="Enter binary">
       <br>
       <button onclick="binaryToText()">To Text</button>
   </div>
   <script>
       function textToBinary() {
           const textInput = document.getElementById('text').value;
           const shiftDirection = document.getElementById('shiftSwitch').checked ? '<<' : '>>';
           const binaryOutput = textInput.split('').map(char => (char.charCodeAt(0) << 1).toString(2)).join(' ');
           document.getElementById('binary').value = binaryOutput;
       }

       function binaryToText() {
           const binaryInput = document.getElementById('binary').value;
           const shiftDirection = document.getElementById('shiftSwitch').checked ? '>>' : '<<';
           const textOutput = binaryInput.split(' ').map(bin => String.fromCharCode(parseInt(bin, 2) >> 1)).join('');
           document.getElementById('text').value = textOutput;
       }
   </script>
</body>
</html>

