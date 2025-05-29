<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Da Terra à Mesa</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        .game-container {
            max-width: 800px;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #4CAF50;
        }
        .message {
            margin-top: 20px;
            font-size: 1.2em;
        }
        .btn {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1.1em;
            cursor: pointer;
            margin: 10px;
            border-radius: 5px;
        }
        .btn:hover {
            background-color: #45a049;
        }
        .status {
            margin-top: 30px;
            font-size: 1.1em;
            background-color: #eee;
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>Da Terra à Mesa</h1>
        <p>Você vai acompanhar o ciclo de um alimento, desde o plantio até o consumo. Faça escolhas sábias!</p>
        
        <div class="message" id="message">Você é um agricultor. O que você quer plantar?</div>
        
        <button class="btn" id="plantButton">Plantar Alface</button>
        <button class="btn" id="plantButton2">Plantar Tomate</button>
        
        <div class="status" id="status">
            <p id="stage">Estágio: Plantio</p>
            <p id="foodStatus">Status: Nenhum alimento cultivado ainda.</p>
        </div>
    </div>

    <script>
        let currentStage = 'plantio';
        let food = '';
        let foodStatus = '';

        // Função que atualiza o texto de status
        function updateStatus() {
            document.getElementById('stage').innerText = `Estágio: ${currentStage.charAt(0).toUpperCase() + currentStage.slice(1)}`;
            document.getElementById('foodStatus').innerText = `Status: ${foodStatus}`;
        }

        // Função de plantio
        function plantFood(foodType) {
            food = foodType;
            foodStatus = `${foodType} plantado com sucesso! Agora, você pode processá-lo ou transportá-lo.`;
            currentStage = 'processamento';
            updateStatus();
            document.getElementById('message').innerText = `Você plantou ${food}. O que você quer fazer agora?`;
            document.getElementById('plantButton').style.display = 'none';
            document.getElementById('plantButton2').style.display = 'none';
            showProcessingButtons();
        }

        // Função de processamento
        function processFood() {
            foodStatus = `${food} processado com sucesso! Está pronto para ser transportado.`;
            currentStage = 'transporte';
            updateStatus();
            document.getElementById('message').innerText = `Seu ${food} foi processado. O que você quer fazer agora?`;
            showTransportButtons();
        }

        // Função de transporte
        function transportFood() {
            foodStatus = `${food} transportado com sucesso! Agora está disponível para o consumidor.`;
            currentStage = 'consumo';
            updateStatus();
            document.getElementById('message').innerText = `O ${food} chegou ao mercado. O que você quer fazer agora?`;
            showConsumptionButton();
        }

        // Função de consumo
        function consumeFood() {
            foodStatus = `${food} consumido com sucesso! Você completou o ciclo.`;
            currentStage = 'fim';
            updateStatus();
            document.getElementById('message').innerText = `Você consumiu o ${food}. Parabéns, você completou o ciclo de produção!`;
            hideButtons();
        }

        // Mostrar botões para a fase de processamento
        function showProcessingButtons() {
            let processButton = document.createElement('button');
            processButton.classList.add('btn');
            processButton.innerText = `Processar ${food}`;
            processButton.onclick = processFood;
            document.body.appendChild(processButton);
        }

        // Mostrar botões para a fase de transporte
        function showTransportButtons() {
            let transportButton = document.createElement('button');
            transportButton.classList.add('btn');
            transportButton.innerText = `Transportar ${food}`;
            transportButton.onclick = transportFood;
            document.body.appendChild(transportButton);
        }

        // Mostrar botões para a fase de consumo
        function showConsumptionButton() {
            let consumeButton = document.createElement('button');
            consumeButton.classList.add('btn');
            consumeButton.innerText = `Consumir ${food}`;
            consumeButton.onclick = consumeFood;
            document.body.appendChild(consumeButton);
        }

        // Ocultar todos os botões
        function hideButtons() {
            let buttons = document.querySelectorAll('.btn');
            buttons.forEach(button => button.style.display = 'none');
        }

        // Definir ações dos botões
        document.getElementById('plantButton').addEventListener('click', () => plantFood('Alface'));
        document.getElementById('plantButton2').addEventListener('click', () => plantFood('Tomate'));

        updateStatus(); // Inicializa o jogo
    </script>
</body>
</html>
