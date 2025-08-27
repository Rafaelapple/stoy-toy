<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Promoção Dia das Crianças</title>
  <style>
    body {
      font-family: 'Comic Sans MS', Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: 
        linear-gradient(rgba(255,255,255,0.85), rgba(255,255,255,0.85)),
        url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ2B46wPHBfP57ZeknvVn6k6YtI7F2IdD_uZw&s') no-repeat center center fixed;
      background-size: cover;
      color: #333;
      text-align: center;
      min-height: 100vh;
    }

    header {
      background: #ff6f00cc;
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
      box-sizing: border-box;
      max-width: 1200px;
      margin: auto;
    }

    /* Caixa com fundo infantil */
    .intro-section {
      background: rgba(255,255,255,0.9);
      padding: 40px 20px;
      border-radius: 15px;
      margin-bottom: 30px;
    }

    .intro-section .caixa {
      width: 160px;
      height: 160px;
      background: conic-gradient(#ffca28, #ff8f00, #f4511e, #ffca28);
      border-radius: 15px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 1.2em;
      font-weight: bold;
      box-shadow: 0 6px 15px rgba(0,0,0,0.2);
      transition: transform 0.5s, background 0.5s;
      cursor: pointer;
      user-select: none;
    }

    #mensagem-desconto {
      display: none;
      font-size: 1.2em;
      color: #388e3c;
      font-weight: bold;
      margin-top: 15px;
    }

    #temporizador {
      display: none;
      font-size: 1.3em;
      font-weight: bold;
      margin: 20px 0;
      color: #d32f2f;
    }

    .produtos {
      display: none;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      margin-bottom: 40px;
    }

    .produto {
      background: rgba(255,255,255,0.9);
      border: 3px dashed #ff6f00;
      border-radius: 15px;
      padding: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .produto:hover {
      transform: translateY(-5px);
      box-shadow: 0 6px 15px rgba(0,0,0,0.15);
    }

    .produto img {
      width: 100%;
      height: auto;
      max-height: 220px;
      object-fit: contain;
      border-radius: 10px;
      margin-bottom: 15px;
      background: #fff;
      padding: 5px;
      box-sizing: border-box;
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
      margin-top: auto;
      width: 100%;
      max-width: 200px;
      transition: background 0.3s;
    }

    .produto button:hover:not(:disabled) {
      background: #b71c1c;
    }

    .produto button:disabled {
      background: #aaa;
      cursor: not-allowed;
    }

    .carrinho, .toast {
      position: fixed;
      right: 20px;
      padding: 12px 18px;
      border-radius: 12px;
      font-weight: bold;
      z-index: 999;
      max-width: 90vw;
      word-wrap: break-word;
    }

    .carrinho {
      bottom: 20px;
      background: #388e3c;
      color: white;
      font-size: 0.95em;
      box-shadow: 0 4px 12px rgba(0,0,0,0.25);
    }

    .toast {
      bottom: 70px;
      background: #ff9800;
      color: #fff;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s, transform 0.5s;
    }

    .toast.show {
      opacity: 1;
      transform: translateY(0);
    }

    /* Depoimentos */
    .depoimentos {
      margin: 40px 0;
      text-align: left;
    }
    .depoamento {
      background: rgba(255,255,255,0.9);
      border-left: 4px solid #388e3c;
      padding: 15px;
      margin-bottom: 15px;
      border-radius: 5px;
    }
    .depoamento p {
      margin: 5px 0;
    }
    .depoamento .cliente {
      font-weight: bold;
      color: #555;
    }

    @media (max-width: 600px) {
      header { font-size: 1.4em; padding: 20px 10px; }
      .produto img { max-height: 200px; }
    }
  </style>
</head>
<body>

<header>🎉 GANHE ATÉ 50% DE DESCONTO! 🎉</header>

<main>
  <!-- Intro com fundo infantil e caixinha -->
  <div class="intro-section">
    <section id="caixa-surpresa" onclick="abrirCaixa()" role="button" tabindex="0"
             onkeypress="if(event.key==='Enter') abrirCaixa();">
      <div class="caixa">🎁 Clique aqui!</div>
    </section>
    <div id="mensagem-desconto">🎈 Desconto de 50% desbloqueado!</div>
    <div id="temporizador">⏰ Tempo restante: <span id="tempo">10:00</span></div>
  </div>

  <!-- Produtos -->
  <div class="produtos" id="lista-produtos"></div>

  <!-- Depoimentos de clientes -->
  <div class="depoimentos" id="depoimentos">
    <h2>O que dizem nossos clientes:</h2>
    <div class="depoamento">
      <p>“Chegou antes do esperado e a qualidade é excelente. Meu filho adorou o Labubu!”</p>
      <p class="cliente">— Mariana, SP</p>
    </div>
    <div class="depoamento">
      <p>“O patinete chegou bem embalado e super seguro. Recomendo muito!”</p>
      <p class="cliente">— Carlos, RJ</p>
    </div>
    <div class="depoamento">
      <p>“O carrinho de controle remoto é incrível! Entrega rápida e atendimento excelente.”</p>
      <p class="cliente">— Juliana, MG</p>
    </div>
  </div>
</main>

<div class="carrinho" id="carrinho">Carrinho: 0 itens – R$ 0,00</div>
<div class="toast" id="toast"></div>

<script>
  let totalItens = 0, totalValor = 0, descontoAtivo = false, tempoRestante = 600;
  const produtos = [
    { nome:"Boneco Labubu", preco:199.00, imagem:"https://down-br.img.susercontent.com/file/br-11134207-7r98o-m9zzn8o7e1q1aa" },
    { nome:"Tablet Samsung", preco:1499.00, imagem:"https://gazin-images.gazin.com.br/...jpg" },
    { nome:"Bola da Copa 2022", preco:150.00, imagem:"https://img.odcdn.com.br/...jpg" },
    { nome:"Pista de Skate de Dedo", preco:75.00, imagem:"https://a-static.mlcdn.com.br/...jpeg" },
    { nome:"Quadro do Neymar", preco:299.90, imagem:"https://m.media-amazon.com/...jpg" },
    { nome:"Carrinho de Controle Remoto", preco:320.00, imagem:"https://i.zst.com.br/...jpg" },
    { nome:"Hoverboard Infantil", preco:950.00, imagem:"https://m.media-amazon.com/...jpg" },
    { nome:"Celular Samsung", preco:2200.00, imagem:"https://planoscelular.claro.com.br/...jpg" },
    { nome:"Patinete Eletrônico", preco:680.00, imagem:"https://www.mymax.ind.br/...jpg" },
    { nome:"Boobie Goods", preco:80.00, imagem:"https://a-static.mlcdn.com.br/...jpeg" },
    { nome:"Patins", preco:430.00, imagem:"https://freitasvarejo.vteximg.com.br/...jpg" },
    { nome:"Máscara do Batman", preco:120.00, imagem:"https://superlegalbrinquedos.vtexassets.com/...jpg" },
    { nome:"Boneco do Coringa", preco:220.00, imagem:"https://http2.mlstatic.com/...webp" },
    { nome:"Caixa de Som JBL", preco:560.00, imagem:"https://d3alv7ekdacjys.cloudfront.net/...webp" },
  ];

  function abrirCaixa() {
    if (descontoAtivo) return;
    descontoAtivo = true;
    document.getElementById("caixa-surpresa").style.display = "none";
    document.getElementById("mensagem-desconto").style.display = "block";
    document.getElementById("temporizador").style.display = "block";
    carregarProdutos();
    iniciarTemporizador();
  }

  function carregarProdutos() {
    const lista = document.getElementById("lista-produtos");
    lista.style.display = "grid";
    produtos.forEach(p => {
      const precoDesc = (p.preco * 0.5).toFixed(2);
      const card = document.createElement("div");
      card.className = "produto";
      card.innerHTML = `
        <img src="${p.imagem}" alt="${p.nome}">
        <h3>${p.nome}</h3>
        <p class="preco-original">R$ ${p.preco.toFixed(2).replace('.', ',')}</p>
        <p class="preco-desconto">R$ ${precoDesc.replace('.', ',')}</p>
        <button onclick="adicionarAoCarrinho('${p.nome}', ${precoDesc})">Comprar</button>`;
      lista.appendChild(card);
    });
  }

  function iniciarTemporizador() {
    const el = document.getElementById("tempo");
    const int = setInterval(() => {
      if (tempoRestante <= 0) {
        clearInterval(int);
        encerrarDesconto();
        return;
      }
      const m = String(Math.floor(tempoRestante/60)).padStart(2,'0'),
            s = String(tempoRestante%60).padStart(2,'0');
      el.textContent = `${m}:${s}`;
      tempoRestante--;
    }, 1000);
  }

  function encerrarDesconto() {
    document.querySelectorAll(".produto button").forEach(b => {
      b.disabled = true;
      b.innerText = "Tempo Esgotado";
    });
    mostrarToast("⛔ O desconto expirou!");
  }

  function adicionarAoCarrinho(nome, preco) {
    totalItens++;
    totalValor += preco;
    atualizarCarrinho();
    mostrarToast(`✅ ${nome} adicionado ao carrinho!`);
  }

  function atualizarCarrinho() {
    document.getElementById("carrinho").innerText = `Carrinho: ${totalItens} item(s) – R$ ${totalValor.toFixed(2).replace('.', ',')}`;
  }

  function mostrarToast(msg) {
    const t = document.getElementById("toast");
    t.innerText = msg;
    t.classList.add("show");
    setTimeout(() => t.classList.remove("show"), 2500);
  }
</script>

</body>
</html>
