<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Loja Dia das Crianças - Descontos Especiais</title>
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

    #temporizador {
      font-size: 1.2em;
      background: #d32f2f;
      color: #fff;
      padding: 10px;
      font-weight: bold;
      display: none;
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
      margin: 50px auto;
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
      margin: auto;
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
  </style>
</head>
<body>

<header>🎉 Promoção Dia das Crianças 🎉</header>
<div id="temporizador">⏰ Tempo restante com desconto: <span id="tempo">10:00</span></div>

<main>
  <!-- Caixa Surpresa -->
  <section id="caixa-surpresa" onclick="abrirCaixa()" aria-label="Abrir caixa surpresa de desconto">
    <div class="caixa">🎁 Clique aqui!</div>
  </section>

  <div id="mensagem-desconto" role="alert">🎈 Desconto de 45% ativado! Aproveite por tempo limitado!</div>

  <!-- Lista de Produtos (oculta inicialmente) -->
  <section class="produtos" id="lista-produtos" style="display: none;"></section>
</main>

<!-- Carrinho e Toast -->
<div class="carrinho" id="carrinho">Carrinho: 0 itens – R$ 0,00</div>
<div class="toast" id="toast"></div>

<script>
  const produtos = [
    { nome: "Boneco Labubu", preco: 199.00 },
    { nome: "Tablet Samsung", preco: 1499.00 },
    { nome: "Carrinho de Controle Remoto", preco: 299.00 },
    { nome: "Bola da Copa 2022", preco: 120.00 },
    { nome: "Hoverboard Infantil", preco: 999.00 },
    { nome: "Pista de Skate de Dedo", preco: 75.00 },
    { nome: "Celular Samsung", preco: 2199.00 },
    { nome: "Patinete Eletrônico", preco: 1490.00 },
    { nome: "Caixa de Som JBL", preco: 699.00 },
    { nome: "Patins", preco: 359.00 },
    { nome: "Quadro do Neymar", preco: 89.00 },
    { nome: "Máscara do Batman", preco: 49.00 },
    { nome: "Boobie Goods", preco: 39.00 },
    { nome: "Boneco do Coringa", preco: 89.90 },
  ];

  const lista = document.getElementById("lista-produtos");
  const desconto = 0.45;
  let totalItens = 0;
  let totalValor = 0;
  let descontoAtivo = false;
  let tempoRestante = 600; // 10 minutos

  function abrirCaixa() {
    if (descontoAtivo) return;
    descontoAtivo = true;

    const caixa = document.querySelector("#caixa-surpresa .caixa");
    const mensagem = document.getElementById("mensagem-desconto");

    caixa.innerText = "Abrindo...";
    caixa.style.transform = "rotate(360deg) scale(1.1)";
    
    setTimeout(() => {
      caixa.style.display = "none";
      mensagem.style.display = "block";
      document.getElementById("lista-produtos").style.display = "grid";
      document.getElementById("temporizador").style.display = "block";
      renderizarProdutos();
      iniciarTemporizador();
    }, 1000);
  }

  function renderizarProdutos() {
    produtos.forEach(p => {
      const precoComDesconto = (p.preco * (1 - desconto)).toFixed(2);
      const produtoEl = document.createElement("article");
      produtoEl.className = "produto";
      produtoEl.innerHTML = `
        <img src="https://via.placeholder.com/280x180?text=${encodeURIComponent(p.nome)}" alt="${p.nome}">
        <h2>${p.nome}</h2>
        <p class="preco-original">R$ ${p.preco.toFixed(2).replace('.', ',')}</p>
        <p class="preco-desconto">R$ ${precoComDesconto.replace('.', ',')}</p>
        <button onclick="adicionarAoCarrinho('${p.nome}', ${precoComDesconto})">Comprar</button>
      `;
      lista.appendChild(produtoEl);
    });
  }

  function iniciarTemporizador() {
    const timerEl = document.getElementById("tempo");
    const interval = setInterval(() => {
      if (tempoRestante <= 0) {
        clearInterval(interval);
        timerEl.innerText = "00:00";
        encerrarDesconto();
        return;
      }

      const minutos = Math.floor(tempoRestante / 60);
      const segundos = tempoRestante % 60;
      timerEl.innerText = `${String(minutos).padStart(2, '0')}:${String(segundos).padStart(2, '0')}`;
      tempoRestante--;
    }, 1000);
  }

  function encerrarDesconto() {
    document.querySelectorAll(".produto button").forEach(btn => {
      btn.disabled = true;
      btn.innerText = "Tempo Esgotado";
      btn.style.background = "#aaa";
      btn.style.cursor = "not-allowed";
    });
    mostrarToast("⛔ Tempo esgotado! O desconto foi encerrado.");
  }

  function adicionarAoCarrinho(produto, preco) {
    totalItens++;
    totalValor += preco;
    atualizarCarrinho();
    mostrarToast(`✅ ${produto} adicionado ao carrinho!`);
  }

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
</script>

</body>
</html>
