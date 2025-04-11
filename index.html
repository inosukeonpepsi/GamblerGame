<!DOCTYPE html>
<html>
<head>
  <title>Casino Guessing Game</title>
  <style>
    body {
      background: #1a1a1a;
      color: #fff;
      font-family: 'Arial', sans-serif;
      text-shadow: 0 0 10px rgba(255,255,255,0.3);
    }
    .container {
      display: flex;
      gap: 40px;
      padding: 20px;
    }
    button {
      background: #cc0000;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
      text-transform: uppercase;
      font-weight: bold;
      box-shadow: 0 0 15px rgba(204,0,0,0.3);
      transition: all 0.3s ease;
    }
    button:hover {
      background: #ff0000;
      transform: scale(1.05);
    }
    input {
      background: #333;
      color: white;
      border: 1px solid #666;
      padding: 8px;
      border-radius: 4px;
    }
    h1, h2, h3 {
      color: #ffcc00;
      text-transform: uppercase;
    }
    .game {
      flex: 1;
    }
    .slots {
      width: 200px;
      padding: 20px;
      border: 2px solid #ccc;
      border-radius: 10px;
      text-align: center;
    }
    .wheel {
      font-size: 40px;
      margin: 20px 0;
      font-family: monospace;
      display: flex;
      gap: 10px;
    }
    .reel {
      font-size: 30px;
    }
    #spinButton {
      background: #ff4444;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
    }
    #spinButton:disabled {
      background: #cccccc;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="game">
      <h1>Number Guessing Game</h1>
      <div id="ascensionContainer" style="margin-bottom: 15px;">
        <button onclick="ascend()" id="ascendButton" style="background: #ffcc00; font-size: 20px; display: none;">🌟 Ascend (Requires 1000 points)</button>
        <p id="multiplierDisplay" style="color: #ffcc00;">Wins Multiplier: 1x</p>
      </div>
      <p id="score">Total Score: 0 💰 | Numbers Guessed: 0</p>
      <p id="range">Guess a number between 1 and 100 (You have 10 guesses):</p>
      <input type="number" id="guessInput">
      <button onclick="guessNumber()">Guess</button>
      <p id="result"></p>
    </div>
    <div class="slots">
      <h3>Guess Gambler</h3>
      <input type="number" id="betAmount" min="10" placeholder="Bet amount (min 10)" style="width: 120px; margin-bottom: 10px;">
      <div class="wheel" id="wheel">
        <span class="reel"></span>
        <span class="reel"></span>
        <span class="reel"></span>
      </div>
      <button id="spinButton" onclick="spinWheel()" disabled>Spin</button>
    </div>
  </div>
  <div style="margin-top: 30px; border-top: 2px solid #ccc; padding-top: 20px; display: flex; gap: 20px;">
    <div style="flex: 3;">
      <h2>Blackjack Gambler</h2>
      <div style="display: flex; gap: 20px;">
        <div>
          <h3>Your Hand: <span id="playerCards"></span></h3>
          <p>Total: <span id="playerTotal">0</span></p>
        </div>
        <div>
          <h3>Dealer's Hand: <span id="dealerCards"></span></h3>
          <p>Total: <span id="dealerTotal">0</span></p>
        </div>
      </div>
      <input type="number" id="blackjackBet" min="10" placeholder="Bet amount (min 10)" style="width: 120px; margin-right: 10px;">
      <button id="dealButton" onclick="startBlackjack()">Deal</button>
      <button id="hitButton" onclick="hit()" style="display: none;">Hit</button>
      <button id="standButton" onclick="stand()" style="display: none;">Stand</button>
      <p id="blackjackResult"></p>
      <button onclick="resetGame()" style="margin-top: 10px;">Reset Game</button>
    </div>
    <div style="flex: 1; border-left: 2px solid #ccc; padding-left: 20px;">
      <h2>Shop</h2>
      <div style="display: flex; flex-direction: column; gap: 10px;">
        <button onclick="buyGuesses(1)" style="padding: 5px;">Buy 1 Guess (25 points)</button>
        <button onclick="buyGuesses(5)" style="padding: 5px;">Buy 5 Guesses (100 points)</button>
        <button onclick="buyGuesses(10)" style="padding: 5px;">Buy 10 Guesses (175 points)</button>
      </div>
    </div>
  </div>
  <script>
    // Blackjack game variables
    let deck = [];
    let playerHand = [];
    let dealerHand = [];
    let blackjackBet = 0;

    function getCardEmoji(card) {
      const suitEmojis = {
        '♠': '🂠',
        '♥': '🂱',
        '♦': '🃁',
        '♣': '🃑'
      };
      const faceCardEmojis = {
        'J': '🂫',
        'Q': '🂭',
        'K': '🂮',
        'A': '🂡'
      };

      if (faceCardEmojis[card.value]) {
        return faceCardEmojis[card.value];
      }
      return suitEmojis[card.suit];
    }

    function createDeck() {
      const suits = ['♠', '♥', '♦', '♣'];
      const values = ['2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K', 'A'];
      deck = [];
      for (let suit of suits) {
        for (let value of values) {
          deck.push({ suit, value });
        }
      }
      // Shuffle deck
      for (let i = deck.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [deck[i], deck[j]] = [deck[j], deck[i]];
      }
    }

    function getCardValue(card) {
      if (['J', 'Q', 'K'].includes(card.value)) return 10;
      if (card.value === 'A') return 11;
      return parseInt(card.value);
    }

    function calculateHand(hand) {
      let total = 0;
      let aces = 0;
      for (let card of hand) {
        if (card.value === 'A') aces++;
        total += getCardValue(card);
      }
      while (total > 21 && aces > 0) {
        total -= 10;
        aces--;
      }
      return total;
    }

    function startBlackjack() {
      blackjackBet = parseInt(document.getElementById('blackjackBet').value) || 0;
      if (blackjackBet < 10 || score < blackjackBet) {
        document.getElementById('blackjackResult').innerHTML = 'Invalid bet amount';
        return;
      }

      updateScore(-blackjackBet);
      createDeck();
      playerHand = [deck.pop(), deck.pop()];
      dealerHand = [deck.pop()];

      document.getElementById('playerCards').innerHTML = playerHand.map(card => getCardEmoji(card) + ' ' + card.value + card.suit).join(' ');
      document.getElementById('dealerCards').innerHTML = dealerHand.map(card => getCardEmoji(card) + ' ' + card.value + card.suit).join(' ') + ' 🂠';
      document.getElementById('playerTotal').innerHTML = calculateHand(playerHand);
      document.getElementById('dealerTotal').innerHTML = getCardValue(dealerHand[0]);

      document.getElementById('dealButton').style.display = 'none';
      document.getElementById('hitButton').style.display = 'inline';
      document.getElementById('standButton').style.display = 'inline';
      document.getElementById('blackjackResult').innerHTML = '';
    }

    function hit() {
      playerHand.push(deck.pop());
      document.getElementById('playerCards').innerHTML = playerHand.map(card => getCardEmoji(card) + ' ' + card.value + card.suit).join(' ');
      const total = calculateHand(playerHand);
      document.getElementById('playerTotal').innerHTML = total;

      if (total > 21) {
        endGame('Bust! You lose!');
      }
    }

    function stand() {
      while (calculateHand(dealerHand) < 17) {
        dealerHand.push(deck.pop());
      }

      document.getElementById('dealerCards').innerHTML = dealerHand.map(card => getCardEmoji(card) + ' ' + card.value + card.suit).join(' ');
      const playerTotal = calculateHand(playerHand);
      const dealerTotal = calculateHand(dealerHand);
      document.getElementById('dealerTotal').innerHTML = dealerTotal;

      if (dealerTotal > 21) {
        endGame('Dealer busts! You win!', true);
      } else if (playerTotal > dealerTotal) {
        endGame('You win!', true);
      } else if (dealerTotal > playerTotal) {
        endGame('Dealer wins!');
      } else {
        endGame('Push! Bet returned.', 'push');
      }
    }

    function endGame(message, win = false) {
      document.getElementById('hitButton').style.display = 'none';
      document.getElementById('standButton').style.display = 'none';
      document.getElementById('dealButton').style.display = 'inline';
      document.getElementById('blackjackResult').innerHTML = message;

      if (win === true) {
        const scoreReward = blackjackBet * 2;
        updateScore(scoreReward);
        document.getElementById('blackjackResult').innerHTML += ' +' + scoreReward + ' points!';
      } else if (win === 'push') {
        updateScore(blackjackBet);
      }
    }

    function buyGuesses(amount) {
      const costs = {
        1: 25,
        5: 100,
        10: 175
      };

      if (score >= costs[amount]) {
        updateScore(-costs[amount]);
        maxGuesses += amount;
        document.getElementById('range').innerHTML = 'Guess a number between 1 and ' + maxNumber + ' (You have ' + (maxGuesses - guesses) + ' guesses):';
        document.getElementById('result').innerHTML = 'Bought ' + amount + ' guesses for ' + costs[amount] + ' points!';
      } else {
        document.getElementById('result').innerHTML = 'Not enough points to buy guesses!';
      }
    }

    let actionPoints = 0;
    let winsMultiplier = 1;
    let ascensions = 0;

    function ascend() {
      if (actionPoints >= 1000) {
        ascensions++;
        winsMultiplier = 1 + (ascensions * 0.5);
        actionPoints = 0;
        document.getElementById('multiplierDisplay').textContent = 'Wins Multiplier: ' + winsMultiplier + 'x (Ascensions: ' + ascensions + ')';
        updateActionPointsDisplay();
        alert('Ascended! All future wins will be multiplied by ' + winsMultiplier + 'x');
      }
    }

    function checkAscensionAvailability() {
      document.getElementById('ascendButton').style.display = actionPoints >= 1000 ? 'block' : 'none';
    }

    function resetGame() {
      maxNumber = 100;
      randomNumber = Math.floor(Math.random() * maxNumber) + 1;
      guesses = 0;
      maxGuesses = 10;
      actionPoints = 0;
      startTime = Date.now();
      numbersGuessed = 0;
      updateActionPointsDisplay();
      document.getElementById('score').innerHTML = 'Total Score: ' + actionPoints + ' 💰 | Numbers Guessed: ' + numbersGuessed;
      document.getElementById('range').innerHTML = 'Guess a number between 1 and ' + maxNumber + ' (You have ' + (maxGuesses - guesses) + ' guesses):';
      document.getElementById('result').innerHTML = 'Game reset! Start guessing!';
      document.getElementById('guessInput').value = '';
      document.getElementById('spinButton').disabled = true;
    }

    let maxNumber = 100;
    let randomNumber = Math.floor(Math.random() * maxNumber) + 1;
    let guesses = 0;
    let maxGuesses = 10;
    let startTime = Date.now();
    let numbersGuessed = 0;

    function nextNumber() {
      maxNumber += 20;
      randomNumber = Math.floor(Math.random() * maxNumber) + 1;
      maxGuesses += 5;
      document.getElementById('range').innerHTML = 'Guess a number between 1 and ' + maxNumber + ' (You have ' + (maxGuesses - guesses) + ' guesses):';
      document.getElementById('result').innerHTML = 'New number generated! Keep guessing! (+5 guesses)';
      document.getElementById('guessInput').value = '';
    }

    function calculateTimeBonus() {
      const timeTaken = (Date.now() - startTime) / 1000; // Convert to seconds
      return Math.max(50 - Math.floor(timeTaken), 0);
    }

    function updateScore(points, guessBonusPoints = 0) {
      actionPoints += (points + guessBonusPoints) * winsMultiplier;
      updateActionPointsDisplay();
      document.getElementById('spinButton').disabled = actionPoints < 10;
      checkAscensionAvailability();
    }

    function updateActionPointsDisplay() {
      document.getElementById('score').innerHTML = 'Total Action Points: ' + actionPoints.toFixed(1) + ' 💰 | Numbers Guessed: ' + numbersGuessed;
    }

    const symbols = ['🍎', '🍊', '🍇', '🍒', '🍋', '🍉', '7️⃣'];
    let isSpinning = false;

    function spinWheel() {
      const betAmount = parseInt(document.getElementById('betAmount').value) || 0;
      if (isSpinning || betAmount < 10 || actionPoints < betAmount) return;
      isSpinning = true;
      updateScore(-betAmount);

      let spins = 0;
      const maxSpins = 30;
      const reels = document.getElementsByClassName('reel');
      let finalSymbols = [];

      // Create arrays for each reel's symbols
      const reelArrays = Array(3).fill().map(() =>
        Array(20).fill().map(() => symbols[Math.floor(Math.random() * symbols.length)])
      );

      let positions = [0, 0, 0];
      const speeds = [50, 60, 70]; // Different speeds for each reel

      const spinIntervals = reels.length;
      let completedReels = 0;

      // Spin each reel independently
      Array.from(reels).forEach((reel, i) => {
        const spinInterval = setInterval(() => {
          positions[i] = (positions[i] + 1) % reelArrays[i].length;
          reel.textContent = reelArrays[i][positions[i]];
          spins++;

          if (spins >= maxSpins + (i * 10)) {
            clearInterval(spinInterval);
            completedReels++;
            finalSymbols[i] = reelArrays[i][positions[i]];

            if (completedReels === spinIntervals) {
              isSpinning = false;
              checkWin(finalSymbols, betAmount);
            }
          }
        }, speeds[i]);
      });
    }

    function checkWin(symbols, betAmount) {
      const allSevens = symbols.every(s => s === '7️⃣');
      const allSame = symbols.every(s => s === symbols[0]);
      const twoSame = symbols[0] === symbols[1] || symbols[1] === symbols[2] || symbols[0] === symbols[2];

      if (allSevens) {
        const megaJackpot = betAmount * 50;
        updateScore(megaJackpot);
        document.getElementById('result').innerHTML = '🎰 MEGA JACKPOT! Triple Sevens! You won ' + megaJackpot + ' points! 🎰';
      } else if (allSame) {
        const jackpotScore = betAmount * 10;
        updateScore(jackpotScore);
        document.getElementById('result').innerHTML = '🎊 JACKPOT! All matching fruits! You won ' + jackpotScore + ' points! 🎊';
      } else if (twoSame) {
        const winScore = betAmount * 2;
        updateScore(winScore);
        document.getElementById('result').innerHTML = '🎉 Two matching fruits! You won ' + winScore + ' points! 🎉';
      } else {
        document.getElementById('result').innerHTML = '❌ Try again! ❌';
      }
    }

    function guessNumber() {
      let guess = parseInt(document.getElementById('guessInput').value);
      if (isNaN(guess)) {
        document.getElementById('result').innerHTML = 'Please enter a valid number.';
        return;
      }

      guesses++;

      if (guesses > maxGuesses) {
        document.getElementById('result').innerHTML = 'Game Over! Too many guesses. The number was ' + randomNumber + '. Your final score: ' + actionPoints;
        return;
      }

      if (guess < randomNumber) {
        document.getElementById('result').innerHTML = 'Too low! Guess again. ' + (maxGuesses - guesses) + ' guesses remaining.';
      } else if (guess > randomNumber) {
        document.getElementById('result').innerHTML = 'Too high! Guess again. ' + (maxGuesses - guesses) + ' guesses remaining.';
      } else {
        const timeBonus = calculateTimeBonus();
        const guessBonus = Math.max(0, 100 - (guesses * 10));
        const roundScore = guessBonus + timeBonus;
        numbersGuessed++;

        updateScore(roundScore, 5);
        document.getElementById('result').innerHTML = 'Correct! You got ' + (roundScore + 5) + ' points (' + guessBonus + ' for guesses + ' + timeBonus + ' time bonus + 5 for guess)! <button onclick="nextNumber()">Next Number</button>';
        startTime = Date.now();
      }
    }
    let score = 0;
  </script>
</body>
</html>
