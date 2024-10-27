# Criando-um-Jogo-de-Cartas-do-Yu-Gi-Oh-com-JavaScript-e-CSS
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo de Cartas Yu-Gi-Oh!</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="game-container">
        <div class="player-hand" id="player-hand"></div>
        <div class="opponent-hand" id="opponent-hand"></div>
        <button id="draw-card">Comprar Carta</button>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.game-container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.player-hand, .opponent-hand {
    display: flex;
    width: 100%;
    justify-content: center;
    margin: 10px 0;
}

.card {
    width: 100px;
    height: 150px;
    border: 1px solid #333;
    border-radius: 5px;
    margin: 0 5px;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.2em;
}
const playerHand = document.getElementById('player-hand');
const opponentHand = document.getElementById('opponent-hand');
const drawButton = document.getElementById('draw-card');

const cards = ['Dragão Negro', 'Mago do Feitiço', 'Cavaleiro da Luz', 'Golem de Pedra'];

function createCard(cardName) {
    const card = document.createElement('div');
    card.className = 'card';
    card.textContent = cardName;
    return card;
}

function drawCard() {
    const randomCard = cards[Math.floor(Math.random() * cards.length)];
    const cardElement = createCard(randomCard);
    playerHand.appendChild(cardElement);
}
