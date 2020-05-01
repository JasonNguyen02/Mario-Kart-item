# Mario-Kart-item
<!DOCTYPE html>
<html>

<head>
    <title>Mario Kart Item Box</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>

<body>

    <h1>Mario Kart Item Sim</h1>
    <div>

        <div class="special">
            <p><input id="input"><button id="butt4">GO!</button></p>
            <p><button id="butt">Generate Item</button> <button id="butt2">+5</button> <button id="butt3">+10</button>
            </p>
        </div>
        <p class="res">You got: <span id="result"></span></p>
        <p>
            <ul>Banana: <span id="B"></span></ul>
            <ul>Green Shell: <span id="G"></span></ul>
            <ul>Star: <span id="S"></span></ul>
            <ul>Gold Mushroom: <span id="D"></span></ul>
            <ul>Bullet Bill: <span id="K"></span></ul>
        </p>
    </div>

    <script src="main.js"></script>
</body>


body {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 20px;
    width: 800px;
    background-color: rgba(212, 212, 212, 0.5);
    margin: auto;
    padding-top: 10px;
    padding-bottom: 800px;
}

html {
    background-image: url(Pics/ditem.jpg);
    background-repeat: no-repeat;
    background-size: 1100px 1000px;
    margin-left: 150px;
}
h1 {
    text-align: center;
}

div {
    width: 300px;
    margin: auto;
}

.res {
    border: 1px solid black;
    text-align: center;
}

input {
    width: 40px;
}

.special {
    text-align: center;
}


document.getElementById("butt").addEventListener("click", main);
document.getElementById("butt2").addEventListener("click", plusFive);
document.getElementById("butt3").addEventListener("click", plusTen);
document.getElementById("butt4").addEventListener("click", any);

let banana = 0;
let greenshell = 0;
let star = 0;
let golden = 0;
let black = 0;

function main() {
    randNum = Math.round(Math.random() * 100);
    if (randNum <= 25) {
        document.getElementById("result").innerHTML = "banana";
        banana += 1;
        document.getElementById("B").innerHTML = banana;
    } else if (randNum > 25 && randNum <= 50) {
        document.getElementById("result").innerHTML = "green shell";
        greenshell += 1;
        document.getElementById("G").innerHTML = greenshell;
    } else if (randNum > 50 && randNum <= 65) {
        document.getElementById("result").innerHTML = "star";
        star += 1;
        document.getElementById("S").innerHTML = star;
    } else if (randNum > 65 && randNum <= 80) {
        document.getElementById("result").innerHTML = "golden mushrooms";
        golden += 1;
        document.getElementById("D").innerHTML = golden;
    } else {
        document.getElementById("result").innerHTML = "black-bill";
        black += 1;
        document.getElementById("K").innerHTML = black;
    }
}
function plusFive() {
    for (let n = 0; n < 5; n++) {
        main();
    }
}

function plusTen() {
    for (let n = 0; n < 10; n++) {
        main();
    }
}

function any() {
    let run = document.getElementById("input").value;
    for (let n = 0; n < run; n++) {
        main();
    }
}
