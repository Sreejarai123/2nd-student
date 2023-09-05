---
title: Quiz on me
layout: posts
description: A quiz about me based off of the stuff on my home page
type: hacks
courses: { compsci: {week: 2}}
---

<!DOCTYPE html>
<html>
<head>
  <title>Interactive Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .quiz-container {
      width: 400px;
      margin: 0 auto;
    }
    .question {
      margin-bottom: 10px;
    }
    .options label {
      display: block;
      margin-bottom: 5px;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <div class="question">
      <p>1. What is the name of my partner?</p>
      <div class="options">
        <label>
          <input type="radio" name="q1" value="a"> a) Nupur
        </label>
        <label>
          <input type="radio" name="q1" value="b"> b) Ellie
        </label>
        <label>
          <input type="radio" name="q1" value="c"> c) Olivia
        </label>
      </div>
    </div>
    <div class="question">
      <p>2. What is my favorite animal"?</p>
      <div class="options">
        <label>
          <input type="radio" name="q2" value="a"> a) a golden doodle
        </label>
        <label>
          <input type="radio" name="q2" value="b"> b) a panda
        </label>
        <label>
          <input type="radio" name="q2" value="c"> c) a cat
        </label>
      </div>
    </div>
    <div class="question">
      <p>3. Whats my favorite food?</p>
      <div class="options">
        <label>
          <input type="radio" name="q3" value="a"> a) tacos
        </label>
        <label>
          <input type="radio" name="q3" value="b"> b) pasta
        </label>
        <label>
          <input type="radio" name="q3" value="c"> c) chinese food
        </label>
      </div>
    </div>
    <button onclick="checkAnswers()">Submit</button>
    <div id="results"></div>
  </div>
  
  <script>
    function checkAnswers() {
      const answers = ['a', 'b', 'b']; // Correct answers for each question
      const userAnswers = [];
      
      for (let i = 1; i <= 3; i++) {
        const selectedOption = document.querySelector(`input[name=q${i}]:checked`);
        if (selectedOption) {
          userAnswers.push(selectedOption.value);
        }
      }
      
      const resultsContainer = document.getElementById('results');
      let score = 3;
      
      for (let i = 3; i < answers.length; i++) {
        if (userAnswers[i] === answers[i]) {
          score++;
        }
      }
      
      results
