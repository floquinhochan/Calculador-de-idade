<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Idade em Dias</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom, #87cefa 0%, #00bfff 100%);
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            color: #333;
            overflow: hidden;
        }

        .container {
            background: #1e90ff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            padding: 20px;
            width: 350px;
            text-align: center;
            position: relative;
            z-index: 1; 
        }

        h1 {
            color: #ffffff;
            margin-bottom: 20px;
            font-size: 24px;
            font-weight: bold;
        }

        label {
            font-size: 16px;
            color: #ffffff;
            display: block;
            margin-bottom: 5px;
        }

        input[type="number"] {
            width: calc(100% - 20px);
            padding: 10px;
            border: 1px solid #ffffff;
            border-radius: 5px;
            font-size: 16px;
            margin-bottom: 15px;
            background: #f0f8ff;
            color: #333;
        }

        input[type="button"] {
            background-color: #4682b4;
            border: none;
            color: #ffffff;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        input[type="button"]:hover {
            background-color: #315f7a;
        }

        h2 {
            color: #00fa9a;
            font-size: 18px;
            margin-top: 20px;
        }

        .footer {
            margin-top: 20px;
            color: #ffffff;
            font-size: 14px;
        }

        .footer img {
            width: 24px;
            height: 24px;
            vertical-align: middle;
            margin: 0 5px;
        }

        .footer a {
            color: #ffffff;
            text-decoration: none;
            margin: 0 5px;
        }

        .footer a:hover {
            text-decoration: underline;
        }

        .clouds {
            position: absolute;
            top: 10%;
            left: 10%;
            width: 300px;
            height: 200px;
            z-index: 0;
        }

        .clock {
            position: absolute;
            top: 20%;
            right: 10%;
            width: 100px;
            height: 100px;
            z-index: 0;
        }

        .clouds svg, .clock svg {
            width: 100%;
            height: auto;
            fill: rgba(255, 255, 255, 0.7);
        }
    </style>
</head>
<body>
    <div class="clouds">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 60">
            <g fill="currentColor">
                <ellipse cx="30" cy="40" rx="30" ry="15"/>
                <ellipse cx="60" cy="40" rx="30" ry="15"/>
                <ellipse cx="45" cy="30" rx="30" ry="15"/>
            </g>
        </svg>
    </div>
    <div class="clock">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <circle cx="12" cy="12" r="10" fill="currentColor"/>
            <line x1="12" y1="6" x2="12" y2="12" stroke="#ffffff" stroke-width="2"/>
            <line x1="12" y1="12" x2="16" y2="12" stroke="#ffffff" stroke-width="2"/>
        </svg>
    </div>
    <div class="container">
        <h1>Calculadora de Idade em Dias</h1>
        <form id="idadeForm">
            <label for="anos">Anos:</label>
            <input type="number" id="anos" name="anos" min="0"><br>
            
            <label for="meses">Meses:</label>
            <input type="number" id="meses" name="meses" min="0" max="11"><br>
            
            <label for="dias">Dias:</label>
            <input type="number" id="dias" name="dias" min="0" max="29"><br>
            
            <input type="button" value="Calcular" onclick="calcularDias()">
        </form>
        
        <h2 id="resultado"></h2>
        
      
    </div>
    
    <script>
        function calcularDias() {
            const anos = parseInt(document.getElementById('anos').value) || 0;
            const meses = parseInt(document.getElementById('meses').value) || 0;
            const dias = parseInt(document.getElementById('dias').value) || 0;
            
                    const totalDias = (anos * 365) + (meses * 30) + dias;
            
            document.getElementById('resultado').textContent = `A idade expressa em dias é ${totalDias} dias.`;
        }
    </script>
</body>
</html>
