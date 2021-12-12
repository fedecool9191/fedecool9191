<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>Zahlen raten</title>
</head>

<body>
    <h2>Zahlen raten</h2>

    <p>Versuche, die Zahl zwischen 0 und 100 zu erraten!</p>

    <div style="height: 120px">
        <label>Dein Tipp:</label>
        <input type="number" id="inputGuess" style="width:100px" />
        <button onclick="checkNumber()">Überprüfen</button>

        <p id="outputResult"></p>
        <p id="outputCount"></p>
    </div>
</body>

<script type="text/javascript">
    var inputGuess = document.getElementById("inputGuess");
    var outputResult = document.getElementById("outputResult");
    var outputCount = document.getElementById("outputCount");

    var number, count;
    number = Math.floor(Math.random() * 100);
    count = 0;

    function checkNumber() {
        var guess = parseInt(inputGuess.value);
        if (guess < number)
            outputResult.innerHTML = "Dein Tipp war zu niedrig.";
        else if (guess > number)
            outputResult.innerHTML = "Dein Tipp war zu hoch.";
        else if (guess == number)
            outputResult.innerHTML = "Richtig!";
        count = count + 1;
        outputCount.innerHTML = "Du hast bisher " + count + " Versuche gebraucht.";
    }

    function newGame() {
        number = Math.floor(Math.random() * 100);
        count = 0;

        inputGuess.value = "";
        outputResult.innerHTML = "";
        outputCount.innerHTML = "";
    }
</script>
<button onclick="newGame()">Neu beginnen</button>

</html>
