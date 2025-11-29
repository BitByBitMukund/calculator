# calculator
hi i made a calculator in javascript 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #f0f0f0;
        }

        .calculator {
            background: #fff;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            width: 260px;
        }

        input {
            width: 100%;
            height: 60px;
            font-size: 24px;
            margin-bottom: 10px;
            text-align: right;
            padding-right: 10px;
            border: 2px solid #ddd;
            border-radius: 8px;
        }

        .buttons button {
            width: 55px;
            height: 55px;
            font-size: 20px;
            margin: 5px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            background: #eee;
        }

        .buttons button:hover {
            background: #dcdcdc;
        }

        .equal {
            background: #4CAF50 !important;
            color: white;
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" id="display" disabled>

        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="deleteLast()">DEL</button>

            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('-')">-</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('+')">+</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button class="equal" onclick="calculate()">=</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
        </div>
    </div>

    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function deleteLast() {
            let current = document.getElementById('display').value;
            document.getElementById('display').value = current.slice(0, -1);
        }

        function calculate() {
            try {
                let result = eval(document.getElementById('display').value);
                document.getElementById('display').value = result;
            } catch {
                document.getElementById('display').value = "Error";
            }
        }
    </script>

</body>
</html>
