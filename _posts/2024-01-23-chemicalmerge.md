---
toc: true
comments: true
layout: post
title: chemical merge
description: chemical merge
type: hacks
courses: { compsci: {week: 7} }
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background-color: #F0F8FF; /* LightBlue background */
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
        }

        #game-container {
            text-align: center;
        }

        .element {
            display: inline-block;
            width: 80px;
            height: 80px;
            margin: 5px;
            background-color: #FFD700; /* Gold color */
            border-radius: 10px;
            line-height: 80px;
            font-size: 18px;
            font-weight: bold;
            position: relative;
            cursor: pointer;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .grid .cell {
            width: 80px;
            height: 80px;
            background-color: #87CEEB; /* SkyBlue color */
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
    <title>Periodic Element 2048 Game</title>
</head>
<body>
    <div id="game-container">
        <div id="score">Score: 0</div>
        <div id="elements-container"></div>
        <div class="grid" id="grid"></div>
    </div>
    <script>
        const elementsContainer = document.getElementById('elements-container');
        const gridContainer = document.getElementById('grid');
        const scoreElement = document.getElementById('score');
        let score = 0;
        let elements = [];
        let selectedElementIndex = 0;

        function initializeGame() {
            score = 0;
            updateScore();
            elements = generateInitialElements();

            // Display initial elements
            displayElements();
            displayGrid();

            // Listen for arrow key events
            window.addEventListener('keydown', handleKeyPress);
        }

        function generateInitialElements() {
            const initialElements = [];
            for (let i = 0; i < 2; i++) {
                initialElements.push(getRandomElement());
            }
            return initialElements;
        }

        function getRandomElement() {
            // For simplicity, using the first 10 elements in the periodic table
            const periodicTable = ['H', 'He', 'Li', 'Be', 'B', 'C', 'N', 'O', 'F', 'Ne'];
            const randomIndex = Math.floor(Math.random() * periodicTable.length);
            return periodicTable[randomIndex];
        }

        function displayElements() {
            elementsContainer.innerHTML = '';
            for (let i = 0; i < elements.length; i++) {
                const elementDiv = document.createElement('div');
                elementDiv.className = 'element';
                elementDiv.textContent = elements[i];
                elementDiv.draggable = true;
                elementDiv.addEventListener('dragstart', (event) => {
                    event.dataTransfer.setData('text/plain', elements[i]);
                });
                elementDiv.addEventListener('click', () => {
                    selectedElementIndex = i;
                });
                elementsContainer.appendChild(elementDiv);
            }
        }

        function displayGrid() {
            gridContainer.innerHTML = '';
            for (let i = 0; i < 16; i++) {
                const cell = document.createElement('div');
                cell.className = 'cell';
                cell.addEventListener('dragover', (event) => {
                    event.preventDefault();
                });
                cell.addEventListener('drop', (event) => {
                    event.preventDefault();
                    const draggedElement = event.dataTransfer.getData('text/plain');
                    mergeElementsInGrid(i, draggedElement);
                });
                gridContainer.appendChild(cell);
            }
        }

        function mergeElementsInGrid(index, draggedElement) {
            const cell = gridContainer.children[index];
            if (!cell.textContent) {
                // If the cell is empty, drop the selected element
                cell.textContent = elements[selectedElementIndex];
                checkMerge(index);
                elements.splice(selectedElementIndex, 1, getRandomElement());
                displayElements();
                updateScore();
            }
        }

        function checkMerge(index) {
            const cell = gridContainer.children[index];
            const neighborIndex = getNeighborIndex(index);

            if (neighborIndex !== -1) {
                const neighborCell = gridContainer.children[neighborIndex];
                if (cell.textContent === neighborCell.textContent) {
                    // If neighboring cells have the same element, merge them
                    const mergedElement = mergeElements(cell.textContent);
                    cell.textContent = mergedElement;
                    neighborCell.textContent = '';
                    updateScore();
                }
            }
        }

        function mergeElements(element) {
            // Define merging rules here
            const mergingRules = {
                'H': 'He',
                'He': 'Li',
                'Li': 'Be',
                'Be': 'B',
                'B': 'C',
                'C': 'N',
                'N': 'O',
                'O': 'F',
                'F': 'Ne',
                'Ne': 'Na',
                // Add more merging rules as needed
            };

            return mergingRules[element] || element;
        }

        function getNeighborIndex(index) {
            // Define the layout of the grid (4x4)
            const rows = 4;
            const cols = 4;

            // Convert 1D index to 2D row and column
            const row = Math.floor(index / cols);
            const col = index % cols;

            // Check left, right, up, down neighbors
            const neighbors = [
                [row, col - 1], // Left
                [row, col + 1], // Right
                [row - 1, col], // Up
                [row + 1, col], // Down
            ];

            for (const [r, c] of neighbors) {
                if (r >= 0 && r < rows && c >= 0 && c < cols) {
                    // Convert 2D row and column back to 1D index
                    const neighborIndex = r * cols + c;
                    return neighborIndex;
                }
            }

            return -1; // No valid neighbor
        }

        function updateScore() {
            scoreElement.textContent = 'Score: ' + score;
        }

        function handleKeyPress(event) {
            if (event.key === 'ArrowLeft' || event.key === 'ArrowRight') {
                moveSelectedElement(event.key);
            }
        }

        function moveSelectedElement(direction) {
            const currentIndex = selectedElementIndex;

            if (direction === 'ArrowLeft' && currentIndex > 0) {
                selectedElementIndex--;
            } else if (direction === 'ArrowRight' && currentIndex < elements.length - 1) {
                selectedElementIndex++;
            }

            displayElements();
        }

        // Initialize the game on page load
        initializeGame();
    </script>
</body>
