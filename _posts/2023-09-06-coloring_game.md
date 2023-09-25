---
toc: true
comments: false
layout: post
title: Coloring Game
description: an interactive coloring game
type: hacks
courses: { compsci: {week: 3} }
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Coloring Game</title>
    <style>
        /* Add some basic styling */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        
        .color-palette {
            margin-top: 20px;
        }

        .color {
            width: 30px;
            height: 30px;
            border: 2px solid #000;
            display: inline-block;
            margin: 5px;
            cursor: pointer;
        }

        .canvas {
            display: flex;
            flex-wrap: wrap;
            max-width: 300px;
            margin: 20px auto;
        }

        .canvas-square {
            width: 30px;
            height: 30px;
            border: 1px solid #ccc;
            background-color: white;
        }
    </style>
</head>
<body>
    <h1>HTML Coloring Game</h1>
    <div class="color-palette">
        <div class="color" style="background-color: red;"></div>
        <div class="color" style="background-color: blue;"></div>
        <div class="color" style="background-color: green;"></div>
        <div class="color" style="background-color: yellow;"></div>
    </div>
    <div class="canvas">
        <!-- Create a 10x10 grid of coloring squares -->
        <div class="canvas-square"></div>
        <!-- Add more canvas squares here as needed -->
    </div>
    <script>
        // JavaScript can be added here for interactivity, but it's very limited in this case
    </script>
</body>
</html>

<html>
<head>
    <style>
        body {
            background-color: green; /* Green color */
        }
    </style>
</head>
<body>
    
</body>
</html>
