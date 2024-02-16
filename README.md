<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Adivinhe o Número</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
    }
    #guessInput {
        width: 50px;
    }
</style>
</head>
<body>
<h1>Adivinhe o Número</h1>
<p>Tente adivinhar o número entre 1 e 100:</p>
<input type="text" id="guessInput">
<button onclick="checkGuess()">Verificar</button>
<p id="message"></p>

<script>
    // Gerar um número aleatório entre 1 e 100
    const numeroAleatorio = Math.floor(Math.random() * 100) + 1;
    let tentativas = 0;

    function checkGuess() {
        const palpite = parseInt(document.getElementById('guessInput').value);
        if (isNaN(palpite) || palpite < 1 || palpite > 100) {
            setMessage('Por favor, insira um número válido entre 1 e 100.');
            return;
        }
        tentativas++;
        if (palpite === numeroAleatorio) {
            setMessage(`Parabéns! Você acertou em ${tentativas} tentativa(s)!`);
            disableInputAndButton();
        } else if (palpite < numeroAleatorio) {
            setMessage('Tente um número maior.');
        } else {
</body>
</body>
            setMessage('Tente um número menor.');
        }
    }

    function setMessage(msg) {
        document.getElementById('message').textContent = msg;
    }

    function disableInputAndButton() {
        document.getElementById('guessInput').disabled = true;
        document.querySelector('button').disabled = true;
    }
</script>
</body>
</html>
