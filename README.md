<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Temperature Converter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #7bcef5ff;
      padding: 40px;
      max-width: 400px;
      margin: auto;
    }
    h2 {
      text-align: center;
      margin-bottom: 30px;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
    }
    .radio-group {
      display: flex;
      justify-content: space-between;
      margin: 15px 0;
    }
    .result {
      background: #f04f4fff;
      padding: 15px;
      border-radius: 5px;
      text-align: center;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>🌡️ Temperature Converter</h2>

  <label for="temp">Enter Temperature:</label>
  <input type="number" id="temp" placeholder="Enter a number" />

  <div class="radio-group">
    <label><input type="radio" name="unit" value="C" checked> Celsius</label>
    <label><input type="radio" name="unit" value="F"> Fahrenheit</label>
    <label><input type="radio" name="unit" value="K"> Kelvin</label>
  </div>

  <button onclick="convertTemp()">Convert</button>

  <div id="output" class="result">Converted temperature will appear here</div>

  <script>
    function convertTemp() {
      const tempInput = document.getElementById("temp").value;
      const unit = document.querySelector('input[name="unit"]:checked').value;
      const output = document.getElementById("output");

      if (tempInput === '' || isNaN(tempInput)) {
        output.textContent = "Please enter a valid number!";
        return;
      }

      const temp = parseFloat(tempInput);
      let c, f, k;

      switch (unit) {
        case 'C':
          f = (temp * 9 / 5) + 32;
          k = temp + 273.15;
          output.textContent = Fahrenheit; {f.toFixed(2)} F | Kelvin; {k.toFixed(2)} K;
          break;
        case 'F':
          c = (temp - 32) * 5 / 9;
          k = c + 273.15;
          output.textContent = Celsius; {c.toFixed(2)} C | Kelvin; {k.toFixed(2)} K;
          break;
        case 'K':
          c = temp - 273.15;
          f = (c * 9 / 5) + 32;
          output.textContent = Celsius; {c.toFixed(2)} C | Fahrenheit; {f.toFixed(2)} F;
          break;
      }
    }
  </script>

</body>
</html>
