<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Small Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f5f5f7;
        }
        .calculator {
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            max-width: 300px;
            width: 100%;
            background-color: #fff;
        }
        .display {
            padding: 20px;
            background-color: rgb(12, 12, 12);
            color: #fff;
            font-size: 2em;
            text-align: right;
            border-bottom: 1px solid #ddd;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1px;
        }
        .button {
            padding: 20px;
            text-align: center;
            font-size: 1.5em;
            cursor: pointer;
            background-color: hsl(130, 3%, 44%);
            border: 1px solid #ddd;
        }
        .button.operator {
            background-color: #ff9500;
            color: #fff;
        }
        .button.equal {
            background-color: hsl(122, 83%, 49%);
            color: #fff;
            grid-column: span 4;
        }
        .button:hover {
            background-color: #ddd;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <div class="button" onclick="clearDisplay()">C</div>
            <div class="button" onclick="appendCharacter('/')">/</div>
            <div class="button" onclick="appendCharacter('7')">7</div>
             <div class="button operator" onclick="appendCharacter('-')">-</div>
            <div class="button" onclick="appendCharacter('8')">8</div>
            <div class="button" onclick="appendCharacter('9')">9</div>
            <div class="button" onclick="appendCharacter('4')">4</div>
            <div class="button operator" onclick="appendCharacter('+')">+</div>
            <div class="button" onclick="appendCharacter('5')">5</div>
            <div class="button" onclick="appendCharacter('6')">6</div>
            <div class="button" onclick="appendCharacter('1')">1</div>
              <div class="button operator" onclick="appendCharacter('.')">.</div>
            <div class="button" onclick="appendCharacter('2')">2</div>
            <div class="button" onclick="appendCharacter('3')">3</div>
             <div class="button" onclick="appendCharacter('0')">0</div>
             <div class="button operator" onclick="appendCharacter('*')">x</div>
            <div class="button equal" onclick="calculate()">=</div>
        </div>
    </div>

    <script>
        function clearDisplay() {
            document.getElementById('display').textContent = '0';
        }

        function appendCharacter(character) {
            const display = document.getElementById('display');
            if (display.textContent === '0') {
                display.textContent = character;
            } else {
                display.textContent += character;
            }
        }

        function calculate() {
            const display = document.getElementById('display');
            try {
                display.textContent = eval(display.textContent);
            } catch {
                display.textContent = 'Error';
            }
        }
    </script>
</body>
</html>
