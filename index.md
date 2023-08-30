---
layout: default
title: Student Blog
---


## Sreeja's Page 2023-2024 (CSP)


## Free Form Image about me
- I like driving and making money
- my favorite food is ice cream and tacos (ecspecially from the Taco stand)
-I like playing golf, ping pong, tennis and swimming


 <img src="https://github.com/Sreejarai123/Sreeja/assets/142522690/6804836b-c7c9-4397-be02-78e32833334a" width="100" height="200">

## About Me
- Hi my name is Sreeja Rai and I am a current Junior at Del Norte High school



<img src="https://github.com/Sreejarai123/Sreeja/assets/142522690/85adc0f4-6c68-4495-b327-8f005efb5fe8" width="200" height="100">
- I like going to concerts this past year I went to the Harry styles, The Weeknd, SZA, and Olivia rodrigo. I like going to the beach and hanging out with my friends. My favorite animal is a dog and I really want a mini golden doodle. I like playing tennis and am on the varsity team as well as the track team and I do dance outside of school. 

<img src="https://cdn.wallpapersafari.com/79/85/BRV5GC.jpg" width="200" height="100">
- Homework requirments: I have about 2 hours of homework every day about 30 minutes from each class sometimes the homework is collaborative but mainly it is meant to be done solo.

<img src="https://wagbrag.com/wp-content/uploads/2018/04/MiniGoldenDoodle.png" width="200" height="100">

## Challenges We Faced:
- Making the make command work: the command was periodically working and not that reliable to use so instead we started using bundle exec jekyll serve but after reinstalling the new make command it started working again
- Also another challenge we faced was making sure that all the commands were installed because a lot of times the commands kept showing errors despite being continously installed 
- to fix this we rebooted the computer and cleaned up our vs code and it ended up working after that
- Another issue was that my partner was on windows and I was using a mac which made it difficult for us to help each other but we became more familiar with each other's laptops.
- BUT with an AGILE MINDSET and the idea that nothing is too difficult to achieve we persevered through all the issues we faced. 

<html>|
<table>
  <tr>
    <th>period</th>
    <th> class</th> 
    <th>teacher</th>
  </tr>
  <tr>
    <td>1</td>
    <td>AP CSP</td> 
    <td>Mr. Mortenson</td>
  </tr>
  <tr>
    <td>2</td>
    <td>AP STATS</td> 
    <td>Mr. Deputron</td>
  </tr>
  <tr>
    <td>3</td>
    <td>APUSH</td> 
    <td>Mr. Swanson</td>
  </tr>
  <tr>
    <td>4</td>
    <td>APEL</td> 
    <td>Mrs. Dafoe</td>
  </tr>
  <tr>
    <td>5</td>
    <td>APES</td> 
    <td>Mr. Hendricks</td>
  </tr>
</table>
</html>



## Python Calculator
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Calculator</title>
<style>
  /* Add your CSS styling here */
  body {
    font-family: Arial, sans-serif;
  }
  .calculator {
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  input[type="text"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  button {
    width: 50px;
    height: 50px;
    font-size: 18px;
    margin: 5px;
  }
</style>
</head>
<body>
<div class="calculator">
  <input type="text" id="result" readonly>
  <button onclick="appendToResult('7')">7</button>
  <button onclick="appendToResult('8')">8</button>
  <button onclick="appendToResult('9')">9</button>
  <button onclick="appendToResult('+')">+</button>
  <br>
  <button onclick="appendToResult('4')">4</button>
  <button onclick="appendToResult('5')">5</button>
  <button onclick="appendToResult('6')">6</button>
  <button onclick="appendToResult('-')">-</button>
  <br>
  <button onclick="appendToResult('1')">1</button>
  <button onclick="appendToResult('2')">2</button>
  <button onclick="appendToResult('3')">3</button>
  <button onclick="appendToResult('*')">*</button>
  <br>
  <button onclick="appendToResult('0')">0</button>
  <button onclick="calculateResult()">=</button>
  <button onclick="clearResult()">C</button>
  <button onclick="appendToResult('/')">/</button>
</div>

<script>
  function appendToResult(value) {
    document.getElementById("result").value += value;
  }

  function calculateResult() {
    const resultField = document.getElementById("result");
    try {
      resultField.value = eval(resultField.value);
    } catch (error) {
      resultField.value = "Error";
    }
  }

  function clearResult() {
    document.getElementById("result").value = "";
  }
</script>
</body>
</html>


<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Graphing Calculator</title>
<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<style>
  /* Add your CSS styling here */
  body {
    font-family: Arial, sans-serif;
  }
  #calculator {
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  input[type="text"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  button {
    width: 50px;
    height: 50px;
    font-size: 18px;
    margin: 5px;
  }
  #graph {
    margin-top: 20px;
  }
</style>
</head>
<body>
<div id="calculator">
  <input type="text" id="expression" placeholder="Enter an expression">
  <button onclick="plotGraph()">Plot</button>
</div>
<div id="graph"></div>
<script>
  function plotGraph() {
    const expression = document.getElementById("expression").value;
    const graphDiv = document.getElementById("graph");
    
    try {
      const x = [];
      const y = [];
      for (let i = -10; i <= 10; i += 0.5) {
        x.push(i);
        y.push(eval(expression.replace("x", i)));
      }

      const data = [{ x, y, type: 'scatter', mode: 'lines' }];
      const layout = { title: 'Graph', xaxis: { title: 'x' }, yaxis: { title: 'y' } };
      Plotly.newPlot(graphDiv, data, layout);
    } catch (error) {
      graphDiv.innerHTML = "<p>Error: Invalid expression</p>";
    }
  }
</script>
</body>
</html>





   
    



 