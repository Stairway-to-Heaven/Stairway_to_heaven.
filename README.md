<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tambola Game</title>
    <style>
        /* Add your CSS styling here */
        /* For example, you can style the board and numbers */
    </style>
</head>
<body>
    <h1>Tambola Game</h1>
    
    <div id="board">
        <!-- The tambola board will be dynamically generated here -->
    </div>

    <button onclick="generateBoard()">Generate Board</button>
    <button onclick="drawNumber()">Draw Number</button>

    <script>
        function generateBoard() {
            // Implement logic to generate a random Tambola board
            // You may want to represent the board as a 2D array

            // Example: Generating a 3x3 board with numbers 1 to 9
            const boardSize = 3;
            const board = [];

            for (let i = 1; i <= boardSize; i++) {
                const row = [];
                for (let j = 1; j <= boardSize; j++) {
                    row.push(i * boardSize + j);
                }
                board.push(row);
            }

            displayBoard(board);
        }

        function displayBoard(board) {
            // Implement logic to display the board on the HTML page
            // You can use HTML elements like <table> and <td>

            const boardContainer = document.getElementById("board");
            boardContainer.innerHTML = ""; // Clear previous content

            const table = document.createElement("table");

            for (let i = 0; i < board.length; i++) {
                const row = document.createElement("tr");

                for (let j = 0; j < board[i].length; j++) {
                    const cell = document.createElement("td");
                    cell.textContent = board[i][j];
                    row.appendChild(cell);
                }

                table.appendChild(row);
            }

            boardContainer.appendChild(table);
        }

        function drawNumber() {
            // Implement logic to draw a random number
            // and update the display accordingly

            const drawnNumber = Math.floor(Math.random() * 90) + 1;
            alert(`Number Drawn: ${drawnNumber}`);
        }
    </script>
</body>
</html>
