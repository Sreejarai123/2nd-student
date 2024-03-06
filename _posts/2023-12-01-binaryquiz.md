---
toc: true
comments: true
layout: post
title: binary quiz
description: A little quiz to test your binary knowledge. 
type: hacks
courses: { compsci: {week: 7} }
---
<html>
<head>
    <style>
        /* Global styles for the entire page */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f2e6ff;
            display: grid;
            place-items: center;
            min-height: 100vh;
        }

        /* Style for the question containers */
        .question-container {
            background-color: #9cf; /* Light Blue background color for question containers */
            border-radius: 10px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
            max-width: 400px;
            margin: 10px;
            padding: 20px;
            text-align: left;
        }

        /* Style for question titles */
        .question h2 {
            font-size: 18px;
            color: #000; /* Black color for question titles */
        }

        /* Style for the question text */
        .question p {
            color: #000; /* Black color for question text */
        }

        /* Style for answer choices */
        .question ul {
            list-style-type: none;
            padding: 0;
        }

        .question li {
            padding: 8px 0;
            color: #000; /* Black color for answer choices */
        }

        /* Style for the correct answer reveal */
        .question details {
            margin-top: 15px;
            cursor: pointer;
        }

        .question summary {
            font-weight: bold;
            color: #666; /* Dark Gray color for summary text */
        }

        /* Style for the correct answer */
        .question details p {
            margin: 0;
            color: #009900; /* Green color for correct answer */
        }

        /* Arrange questions in two rows using grid layout */
        .questions-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
    </style>
</head>
<body>
    <div class="questions-grid">
        <!-- First Question Container -->
        <div class="question-container">
            <div class="question">
                <h2>Binary Question 1</h2>
                <p>How many bits are in binary colors?</p>
                <ul>
                    <li>A) 24</li>
                    <li>B) 16</li>
                    <li>C) 8</li>
                    <li>D) 5</li>
                </ul>
                <details>
                    <summary>Click to reveal the correct answer</summary>
                    <p>The correct answer is A) 24 bits, as there is 8 bits of data for 3 color channels</p>
                </details>
            </div>
        </div>

        <!-- Second Question Container -->
        <div class="question-container">
            <div class="question">
                <h2>Binary Question 2</h2>
                <p>Convert 30 into a binary number?</p>
                <ul>
                    <li>A) 00011001</li>
                    <li>B) 00011011</li>
                    <li>C) 00011110</li>
                    <li>D) 00111111</li>
                </ul>
                <details>
                    <summary>Click to reveal the correct answer</summary>
                    <p>The correct answer is C) 00011110, solve the problem out. We recommend using a paper and pencil.</p>
                </details>
            </div>
        </div>

        <!-- Third Question Container -->
        <div class="question-container">
            <div class="question">
                <h2> Binary Question</h2>
                <p>What is a bit?</p>
                <ul>
                    <li>A) a bit piece of something</li>
                    <li>B) Basic Unit of information and computing and digital communications</li>
                    <li>C) Computer science</li>
                </ul>
                <details>
                    <summary>Click to reveal the correct answer</summary>
                    <p>The correct answer is B) Basic Unit of information and computing and digital communications</p>
                </details>
            </div>
        </div>
    </div>
</body>
</html>

