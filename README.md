<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="apple-mobile-web-app-title" content="Calculadora UPSPRO">
<title>Calculadora UPSPRO</title>

<style>
body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, Arial;
    background: #f2f4f7;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    background: white;
    padding: 25px;
    border-radius: 15px;
    width: 90%;
    max-width: 400px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.15);
}

.header {
    background: #003366;
    color: white;
    padding: 15px;
    border-radius: 10px;
    text-align: center;
    font-weight: bold;
    font-size: 20px;
    margin-bottom: 20px;
}

input {
    width: 100%;
    padding: 12px;
    margin-top: 10px;
    margin-bottom: 15px;
    border-radius: 8px;
    border: 1px solid #ccc;
    font-size: 16px;
}

button {
    width: 100%;
    padding: 15px;
    background: #0056b3;
    color: white;
    border: none;
    border-radius: 10px;
    font-size: 18px;
    font-weight: bold;
}

button:active {
    background: #003f88;
}

.result {
    margin-top: 20px;
    padding: 15px;
    background: #e7f0ff;
    border-radius: 10px;
    text-align: center;
    font-weight: bold;
    color: #003366;
}
</style>
</head>

<body>

<div class="container">

<div class="header">
Calculadora UPSPRO
</div>

<label>Potência (Watts)</label>
<input type="number" id="potencia" placeholder="Ex: 300">

<label>Tensão do banco (Volts)</label>
<input type="number" id="tensao" placeholder="Ex: 24">

<label>Capacidade da bateria (Ah)</label>
<input type="number" id="ah" placeholder="Ex: 45">

<button onclick="calcular()">Calcular Autonomia</button>

<div class="result" id="resultado">
Insira os dados para calcular
</div>

</div>

<script>
function calcular() {

let potencia = parseFloat(document.getElementById("potencia").value);
let tensao = parseFloat(document.getElementById("tensao").value);
let ah = parseFloat(document.getElementById("ah").value);

if (!potencia || !tensao || !ah) {
document.getElementById("resultado").innerHTML = "Preencha todos os campos.";
return;
}

let wattsTotais = tensao * ah;
let autonomiaHoras = wattsTotais / potencia;

let horas = Math.floor(autonomiaHoras);
let minutos = Math.round((autonomiaHoras - horas) * 60);

document.getElementById("resultado").innerHTML =
"Autonomia estimada:<br>" +
horas + "h " + minutos + "min";
}
</script>

</body>
</html>
