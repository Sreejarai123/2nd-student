---
title: Classic Pizza Game
layout: base
description: This is an interactive game in which you can create your own pizza using your own toppings that you choose 
categories: [C4.9]
type: hacks
courses: { compsci: {week: 1}}
---

<!DOCTYPE html>
<html>
<head>
  <title>Pizza Making Game</title>
  <style>
    .pizza-container {
      text-align: center;
    }
    .pizza {
      width: 200px;
      height: 200px;
      background-color: tomato;
      position: relative;
      margin: 20px auto;
    }
    .topping {
      width: 50px;
      height: 50px;
      position: absolute;
    }
  </style>
</head>
<body>
  <div class="pizza-container">
    <h1>Pizza Making Game</h1>
    <div class="pizza" id="pizza">
      <!-- Initial pizza base -->
    </div>
    <h3>Toppings:</h3>
    <input type="checkbox" id="pepperoni" class="topping-checkbox">
    <label for="pepperoni">Pepperoni</label><br>
    <input type="checkbox" id="mushrooms" class="topping-checkbox">
    <label for="mushrooms">Mushrooms</label><br>
    <input type="checkbox" id="olives" class="topping-checkbox">
    <label for="olives">Olives</label><br>
    <h3>Crust:</h3>
    <select id="crust-type">
      <option value="thin">Thin</option>
      <option value="thick">Thick</option>
    </select><br>
    <button onclick="makePizza
    Make Pizza</button>
  </div>

  <script>
    function makePizza() {
      const pizza = document.getElementById("pizza");
      pizza.innerHTML = ""; // Clear previous toppings

      const toppings = document.querySelectorAll(".topping-checkbox");
      toppings.forEach(topping => {
        if (topping.checked) {
          const toppingName = topping.id;
          const toppingElement = document.createElement("div");
          toppingElement.className = "topping " + toppingName;
          pizza.appendChild(toppingElement);
        }
      });

      const crustType = document.getElementById("crust-type").value;
      pizza.style.border = crustType ===
