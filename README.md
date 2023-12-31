<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: black;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: white;
            background-image: url('thermometer-icon.png');
            background-repeat: no-repeat;
            background-size: 150px;
            background-position: right bottom;
        }

        .container {
            text-align: center;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
        }

        .input-container {
            margin-bottom: 20px;
        }

        input {
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            padding: 8px 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #0056b3;
        }

        .result {
            font-size: 24px;
            font-weight: bold;
            color: #a39393;
            opacity: 0;
            transform: translateY(-20px);
            transition: opacity 0.3s ease, transform 0.3s ease;
            margin-top: 20px;
        }

        .copyright {
            font-size: 12px;
            margin-top: 20px;
            opacity: 0;
            animation: fadeIn 1s forwards 3s;
        }

        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(10px); }
            100% { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Temperature Converter</h1>
        <div class="input-container">
            <input type="number" id="celsius" placeholder="Enter Celsius">
            <button id="convertBtn">Convert</button>
        </div>
        <div id="result" class="result"></div>
        <div class="copyright">MADE BY AAKASH PARBHANE</div>
    </div>
    <script>
        const convertBtn = document.getElementById('convertBtn');
        const celsiusInput = document.getElementById('celsius');
        const resultDiv = document.getElementById('result');

        convertBtn.addEventListener('click', () => {
            const celsiusValue = parseFloat(celsiusInput.value);
            if (!isNaN(celsiusValue)) {
                const fahrenheitValue = (celsiusValue * 9/5) + 32;
                resultDiv.textContent = `${celsiusValue}°C is ${fahrenheitValue.toFixed(2)}°F`;

                // Apply animation
                resultDiv.style.opacity = '1';
                resultDiv.style.transform = 'translateY(0)';
            } else {
                resultDiv.textContent = 'Invalid input. Please enter a valid number.';
                resultDiv.style.opacity = '0';
                resultDiv.style.transform = 'translateY(-20px)';
            }
        });
    </script>
</body>
</html>
