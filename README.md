<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Loja Dia das Crianças - Labubu & Tablets</title>
  <style>
    body {
      font-family: 'Comic Sans MS', Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom, #fff8e1, #ffe0b2);
      color: #333;
      text-align: center;
    }

    header {
      background: #ff6f00;
      color: #fff;
      padding: 25px 15px;
      font-size: 1.8em;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }

    .produtos {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 30px 10px;
    }

    .produto {
      background: #fff;
      border: 3px dashed #ff6f00;
      border-radius: 15px;
      padding: 20px;
      width: 280px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .produto img {
      width: 100%;
      border-radius: 10px;
    }

    .preco-original {
      text-decoration: line-through;
      color: #888;
      font-size: 0.9em;
    }

    .preco-desconto {
      color: #d32f2f;
      font-size: 1.4em;
      font-weight: bold;
    }

    .produto button {
      background: #d32f2f;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1em;
      margin-top: 10px;
      transition: background 0.3s;
    }

    .produto button:hover {
      background: #b71c1c;
    }

    /* Caixinha surpresa */
    #caixa-surpresa {
      cursor: pointer;
      display: inline-block;
      margin: 30px 0;
    }

    #caixa-surpresa .caixa {
      width: 160px;
      height: 160px;
      background: conic-gradient(#ffca28, #ff8f00, #f4511e, #ffca28);
      border-radius: 15px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 1.2em;
      font-weight: bold;
      box-shadow: 0 6px 15px rgba(0,0,0,0.2);
      transition: transform 0.5s;
    }

    #mensagem-desconto {
      display: none;
      font-size: 1.2em;
      color: #388e3c;
      font-weight: bold;
      margin-top: 15px;
    }

    .carrinho {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #388e3c;
      color: white;
      padding: 12px 18px;
      border-radius: 12px;
      font-weight: bold;
      font-size: 0.95em;
      z-index: 999;
    }

    /* Responsividade para celulares */
    @media (max-width: 600px) {
      header {
        font-size: 1.4em;
        padding: 20px 10px;
      }

      .produto {
        width: 90%;
      }

      #caixa-surpresa .caixa {
        width: 140px;
        height: 140px;
        font-size: 1em;
      }

      .carrinho {
        bottom: 10px;
        right: 10px;
        font-size: 0.85em;
        padding: 10px 14px;
      }
    }
  </style>
</head>
<body>

<header>🎉 Promoção Dia das Crianças! Tudo com 45% OFF! 🎉</header>

<!-- Caixa Surpresa -->
<section id="caixa-surpresa" onclick="abrirCaixa()">
  <div class="caixa">🎁 Clique aqui!</div>
</section>
<div id="mensagem-desconto">🎈 Você desbloqueou o <strong>Desconto do Dia das Crianças</strong>! 45% OFF aplicado!</div>

<!-- Lista de Produtos -->
<section class="produtos">
  <div class="produto">
    <img src="https://via.placeholder.com/280x180?text=Labubu" alt="Boneco Labubu"/>
    <h2>Boneco Labubu</h2>
    <p class="preco-original">R$ 199,00</p>
    <p class="preco-desconto">R$ 109,45</p>
    <button onclick="adicionarAoCarrinho('Labubu', 109.45)">Comprar</button>
  </div>

  <div class="produto">
    <img src="https://via.placeholder.com/280x180?text=Tablet+Samsung" alt="Tablet Samsung"/>
    <h2>Tablet Samsung</h2>
    <p class="preco-original">R$ 1.499,00</p>
    <p class="preco-desconto">R$ 824,45</p>
    <button onclick="adicionarAoCarrinho('Tablet Samsung', 824.45)">Comprar</button>
  </div>
</section>

<!-- Carrinho -->
<div class="carrinho" id="carrinho">Carrinho: 0 itens – R$ 0,00</div>

<!-- Scripts -->
<script>
  let totalItens = 0;
  let totalValor = 0;
  let descontoMostrado = false;

  function adicionarAoCarrinho(produto, preco) {
    totalItens++;
    totalValor += preco;
    document.getElementById("carrinho").innerText =
      `Carrinho: ${totalItens} item(s) – R$ ${totalValor.toFixed(2)}`;
    alert(`✅ ${produto} adicionado ao carrinho!`);
  }

  function abrirCaixa() {
    if (descontoMostrado) return;
    descontoMostrado = true;
    const caixa = document.querySelector("#caixa-surpresa .caixa");
    const mensagem = document.getElementById("mensagem-desconto");

    caixa.innerText = "Abrindo...";
    caixa.style.transform = "rotate(360deg) scale(1.1)";

    setTimeout(() => {
      mensagem.style.display = "block";
      caixa.innerText = "🎉 Desconto Ativado!";
      caixa.style.background = "linear-gradient(to right, #8bc34a, #558b2f)";
    }, 1000);
  }
</script>

</body>
</html>
