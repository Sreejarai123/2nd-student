---
toc: true
comments: true
layout: post
title: color wheel
description: color wheel
type: hacks
courses: { compsci: {week: 7} }
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Color Wheel</title>
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

        #colorWheel {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            border: 5px solid #fff;
            overflow: hidden; /* Ensure child divs are clipped to the circle */
        }

        .colorSegment {
            width: 1.40625%; /* 100% / 256 colors */
            height: 100%;
            float: left;
        }

        button {
            margin-top: 20px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="colorWheel"></div>
    <button onclick="toggleShift()">Toggle Shift Direction</button>
    <script>
        let shiftDirection = 1; // 1 for forward, -1 for backward

        function generateColorWheel() {
            const colorWheel = document.getElementById('colorWheel');
            const step = 360 / 256; // 256 colors in the wheel

            for (let i = 0; i < 256; i++) {
                const hue = i * step;
                const color = `hsl(${hue}, 100%, 50%)`;
                const div = document.createElement('div');
                div.className = 'colorSegment';
                div.style.backgroundColor = color;
                colorWheel.appendChild(div);
            }
        }

        function shiftColors() {
            const colorWheel = document.getElementById('colorWheel');
            const children = colorWheel.children;

            for (let i = 0; i < children.length; i++) {
                const hue = (i + shiftDirection) % 256; // Shift the colors
                const color = `hsl(${hue}, 100%, 50%)`;
                children[i].style.backgroundColor = color;
            }
        }

        function toggleShift() {
            shiftDirection *= -1; // Toggle between forward and backward
            shiftColors();
        }

        generateColorWheel();
    </script>
</body>
</html>
