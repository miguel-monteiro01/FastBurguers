# FastBurguers
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fast Burguers</title>
<style>
body {
    font-family: Arial;
    margin: 0;
    background: #111;
    color: #fff;
}
header {
    background: red;
    padding: 20px;
    text-align: center;
    font-size: 24px;
    font-weight: bold;
}
.container {
    padding: 15px;
}
.card {
    background: #1c1c1c;
    margin-bottom: 10px;
    padding: 15px;
    border-radius: 10px;
}
button {
    background: red;
    color: white;
    border: none;
    padding: 10px;
    border-radius: 5px;
    width: 100%;
    margin-top: 10px;
}
.total {
    position: fixed;
    bottom: 0;
    width: 100%;
    background: red;
    padding: 15px;
    text-align: center;
}
</style>
</head>

<body>

<header>🍔 Fast Burguers</header>

<div class="container">

<div class="card">
<h3>X-Burguer</h3>
<p>R$ 18,90</p>
<button onclick="add(18.9,'X-Burguer')">Adicionar</button>
</div>

<div class="card">
<h3>X-Bacon</h3>
<p>R$ 23,90</p>
<button onclick="add(23.9,'X-Bacon')">Adicionar</button>
</div>

<div class="card">
<h3>Combo Completo</h3>
<p>R$ 32,90</p>
<button onclick="add(32.9,'Combo')">Adicionar</button>
</div>

</div>

<div class="total" onclick="finalizar()">
Finalizar Pedido | R$ <span id="total">0</span>
</div>

<script>
let total = 0;
let pedidos = [];

function add(valor, nome){
    total += valor;
    pedidos.push(nome);
    document.getElementById('total').innerText = total.toFixed(2);
}

function finalizar(){
    let msg = "Pedido:%0A";
    pedidos.forEach(p => msg += "- " + p + "%0A");
    msg += "%0ATotal: R$ " + total.toFixed(2);
    msg += "%0A%0APagar via PIX: 589a5b52-c86a-4df2-9fde-1fd86498695f";
    msg += "%0ATempo de entrega: 40 a 60 minutos";

    window.open("https://wa.me/5547996575888?text=" + msg);
}
</script>

</body>
</html>
