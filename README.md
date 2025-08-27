<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8"/>
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

    main {
      padding: 20px;
    }

    .produtos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      padding: 30px 10px;
      max-width: 1200px;
      margin: auto;
    }

    .produto {
      background: #fff;
      border: 3px dashed #ff6f00;
      border-radius: 15px;
      padding: 20px;
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .produto:hover {
      transform: translateY(-5px);
      box-shadow: 0 6px 15px rgba(0,0,0,0.15);
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
      transition: transform 0.5s, background 0.5s;
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
      box-shadow: 0 4px 12px rgba(0,0,0,0.25);
    }

    .toast {
      position: fixed;
      bottom: 70px;
      right: 20px;
      background: #ff9800;
      color: #fff;
      padding: 12px 18px;
      border-radius: 10px;
      font-weight: bold;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s, transform 0.5s;
      z-index: 1000;
    }

    .toast.show {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 600px) {
      header { font-size: 1.4em; padding: 20px 10px; }
      .carrinho { bottom: 10px; right: 10px; font-size: 0.85em; }
      #caixa-surpresa .caixa { width: 140px; height: 140px; font-size: 1em; }
    }
  </style>
</head>
<body>

<header>🎉 Promoção Dia das Crianças! Tudo com 45% OFF! 🎉</header>

<main>

  <!-- Caixa Surpresa -->
  <section id="caixa-surpresa" onclick="abrirCaixa()" aria-label="Abrir caixa surpresa de desconto">
    <div class="caixa">🎁 Clique aqui!</div>
  </section>
  <div id="mensagem-desconto" role="alert">🎈 Você desbloqueou o <strong>Desconto do Dia das Crianças</strong>! 45% OFF aplicado!</div>

  <!-- Produtos -->
  <section class="produtos" id="lista-produtos">
    <!-- Produtos serão inseridos aqui via JavaScript -->
  </section>
</main>

<!-- Carrinho -->
<div class="carrinho" id="carrinho">Carrinho: 0 itens – R$ 0,00</div>
<div class="toast" id="toast"></div>

<script>
  const produtos = [
    { nome: "Boneco Labubu", preco: 199.00, imagem: "https://via.placeholder.com/280x180?text=Labubu" },
    { nome: "Tablet Samsung", preco: 1499.00, imagem: "https://via.placeholder.com/280x180?text=Tablet+Samsung" },
    { nome: "Carrinho de Controle Remoto", preco: 299.00, imagem: "https://via.placeholder.com/280x180?text=Carrinho+RC" },
    { nome: "Bola da Copa 2022", preco: 120.00, imagem: "https://via.placeholder.com/280x180?text=Bola+Copa+2022" },
    { nome: "Hoverboard Infantil", preco: 999.00, imagem: "https://via.placeholder.com/280x180?text=Hoverboard" },
    { nome: "Pista de Skate de Dedo", preco: 75.00, imagem: "https://via.placeholder.com/280x180?text=Skate+de+Dedo" },
    { nome: "Celular Samsung", preco: 2199.00, imagem: "https://via.placeholder.com/280x180?text=Celular+Samsung" },
    { nome: "Patinete Eletrônico", preco: 1490.00, imagem: "https://via.placeholder.com/280x180?text=Patinete+Elétrico" },
    { nome: "Caixa de Som JBL", preco: 699.00, imagem: "https://via.placeholder.com/280x180?text=Caixa+JBL" },
    { nome: "Patins", preco: 359.00, imagem: "https://via.placeholder.com/280x180?text=Patins" },
    { nome: "Quadro do Neymar", preco: 89.00, imagem: "https://via.placeholder.com/280x180?text=Quadro+Neymar" },
    { nome: "Máscara do Batman", preco: 49.00, imagem: "https://via.placeholder.com/280x180?text=Máscara+Batman" },
    { nome: "Boobie Goods", preco: 39.00, imagem: "https://via.placeholder.com/280x180?text=Boobie+Goods" },
    { nome: "Boneco do Coringa", preco: 89.90, imagem: "https://via.placeholder.com/280x180?text=Coringa" },
  ];

  const lista = document.getElementById("lista-produtos");

  const desconto = 0.45;
  let totalItens = 0;
  let totalValor = 0;
  let descontoMostrado = false;

  produtos.forEach(p => {
    const precoDesconto = (p.preco * (1 - desconto)).toFixed(2);
    const card = document.createElement("article");
    card.className = "produto";
    card.innerHTML = `
      <img src="${p.imagem}" alt="${p.nome}"/>
      <h2>${p.nome}</h2>
      <p class="preco-original">R$ ${p.preco.toFixed(2).replace('.', ',')}</p>
      <p class="preco-desconto">R$ ${precoDesconto.replace('.', ',')}</p>
      <button onclick="adicionarAoCarrinho('${p.nome}', ${precoDesconto})">Comprar</button>
    `;
    lista.appendChild(card);
  });

  function atualizarCarrinho() {
    document.getElementById("carrinho").innerText =
      `Carrinho: ${totalItens} item(s) – R$ ${totalValor.toFixed(2).replace('.', ',')}`;
  }

  function mostrarToast(mensagem) {
    const toast = document.getElementById("toast");
    toast.textContent = mensagem;
    toast.classList.add("show");
    setTimeout(() => toast.classList.remove("show"), 2500);
  }

  function adicionarAoCarrinho(produto, preco) {
    totalItens++;
    totalValor += preco;
    atualizarCarrinho();
    mostrarToast(`✅ ${produto} adicionado ao carrinho!`);
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
