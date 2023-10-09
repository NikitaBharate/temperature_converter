# temperature_converter

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <title>Temperature Converter</title>
</head>
<body>
    <div class="container">
        <h1>Temperature Converter</h1>
        <input type="number" id="temperature" placeholder="Enter temperature..." required>
        <select id="unit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
            <option value="kelvin">Kelvin</option>
        </select>
        <button onclick="convertTemperature()">Convert</button>
        <div id="result"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>

css:

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    font-family: Arial, sans-serif;
}

.container {
    text-align: center;
}

input, select, button {
    margin: 10px;
    padding: 8px;
    font-size: 16px;
}

#result {
    font-size: 18px;
    margin-top: 20px;
}

Javascript:

function convertTemperature() {
    let temperature = parseFloat(document.getElementById("temperature").value);
    let unit = document.getElementById("unit").value;
    let result = document.getElementById("result");

    if (isNaN(temperature)) {
        result.textContent = "Please enter a valid number.";
        return;
    }

    if (unit === "celsius") {
        result.textContent = `Converted Temperature: ${temperature * 9/5 + 32}°F / ${temperature + 273.15}K`;
    } else if (unit === "fahrenheit") {
        result.textContent = `Converted Temperature: ${(temperature - 32) * 5/9}°C / ${(temperature - 32) * 5/9 + 273.15}K`;
    } else if (unit === "kelvin") {
        result.textContent = `Converted Temperature: ${temperature - 273.15}°C / ${(temperature - 273.15) * 9/5 + 32}°F`;
    }
}
