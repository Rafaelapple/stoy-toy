<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Promoção Dia das Crianças</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    body {
      font-family: 'Comic Sans MS', Arial, sans-serif;
      margin: 0;
      padding: 0;
      background:
        linear-gradient(rgba(255,255,255,0.9), rgba(255,255,255,0.9)),
        url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ2B46wPHBfP57ZeknvVn6k6YtI7F2IdD_uZw&s')
        no-repeat center center fixed;
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
      max-width: 1100px;
      margin: auto;
    }

    .intro-section {
      background: rgba(255,255,255,0.9);
      padding: 40px 20px;
      border-radius: 15px;
      margin-bottom: 20px;
    }

    #caixa-surpresa {
      cursor: pointer;
      display: inline-block;
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
      user-select: none;
    }
    #caixa-surpresa.spin .caixa {
      animation: spin 3s ease-in-out;
    }
    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    #mensagem-desconto {
      display: none;
      font-size: 1.4em;
      font-weight: bold;
      margin-top: 15px;
      color: #388e3c;
    }

    #temporizador {
      display: none;
      font-size: 1.2em;
      font-weight: bold;
      margin-top: 10px;
      color: #d32f2f;
    }

    .produtos {
      display: none;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      margin: 30px 0;
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
      color: #fff;
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
      color: #fff;
      font-size: 0.95em;
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

    .depoimentos {
      margin: 40px 0;
      text-align: left;
    }
    .depoimento {
      background: rgba(255,255,255,0.9);
      border-left: 4px solid #388e3c;
      padding: 15px;
      margin-bottom: 15px;
      border-radius: 5px;
    }
    .depoimento p {
      margin: 5px 0;
    }
    .depoimento .cliente {
      font-weight: bold;
      color: #555;
    }

    footer {
      background: #222;
      color: #eee;
      padding: 30px 20px;
      text-align: center;
    }
    footer h3 {
      margin-bottom: 15px;
      font-size: 1.2em;
      color: #ff9800;
    }
    .footer-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 20px;
      margin-bottom: 20px;
    }
    .footer-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      font-size: 0.95em;
    }
    .footer-item i {
      font-size: 1.8em;
      margin-bottom: 8px;
      color: #ff9800;
    }
    .footer-bottom {
      border-top: 1px solid #444;
      padding-top: 15px;
      font-size: 0.85em;
      color: #aaa;
    }

    @media (max-width: 600px) {
      header { font-size: 1.4em; }
      .produto img { max-height: 200px; }
      .footer-container { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>
  <header>🎉 GANHE ATÉ 50% DE DESCONTO! 🎉</header>

  <main>
    <div class="intro-section">
      <div id="entrada-nome">
        <p>Digite seu nome para participar da surpresa:</p>
        <input type="text" id="nome-usuario" placeholder="Seu nome" style="padding: 10px; border-radius: 8px; border: 1px solid #ccc; width: 80%; max-width: 300px;" />
        <br><br>
        <button onclick="habilitarCaixa()" style="background: #ff6f00; color: white; border: none; padding: 10px 20px; border-radius: 8px; cursor: pointer; font-size: 1em;">Confirmar</button>
      </div>

      <section id="caixa-surpresa" onclick="abrirCaixa()" role="button" tabindex="0"
        onkeypress="if(event.key==='Enter') abrirCaixa();" aria-label="Clique para abrir a caixa surpresa"
        style="display: none;">
        <div class="caixa">🎁 Clique aqui!</div>
      </section>

      <div id="mensagem-desconto"></div>
      <div id="temporizador">⏰ Tempo restante: <span id="tempo">10:00</span></div>
    </div>

    <div class="produtos" id="lista-produtos"></div>

    <div class="depoimentos">
      <h2>Clientes Satisfeitos:</h2>
      <div class="depoimento">
        <p>"Chegou rapidinho e tudo certinho. Meu filho ama o Labubu!"</p>
        <p class="cliente">— Mariana, SP</p>
      </div>
      <div class="depoimento">
        <p>"Patinete excelente, entrega segura. Super recomendo!"</p>
        <p class="cliente">— Carlos, RJ</p>
      </div>
      <div class="depoimento">
        <p>"Patins incrível. Atendimento nota 10 e entrega rápida."</p>
        <p class="cliente">— Juliana, SP</p>
      </div>
    </div>
  </main>

  <footer>
    <h3>Confiança e Segurança</h3>
    <div class="footer-container">
      <!-- Ícones -->
    </div>
    <div class="footer-bottom">
      © 2025 Teens & Eletronicos. Todos os direitos reservados.
    </div>
  </footer>

  <div class="carrinho" id="carrinho">Carrinho: 0 itens – R$ 0,00</div>
  <div class="toast" id="toast"></div>

  <script>
    let totalItens = 0, totalValor = 0, descontoAtivo = false, tempoRestante = 600;
    let nomeUsuario = "";

    const produtos = [/*...mesma lista de produtos...*/];

    function habilitarCaixa() {
      const nomeInput = document.getElementById("nome-usuario");
      nomeUsuario = nomeInput.value.trim();
      if (!nomeUsuario) {
        alert("Por favor, digite seu nome para continuar.");
        return;
      }
      document.getElementById("entrada-nome").style.display = "none";
      document.getElementById("caixa-surpresa").style.display = "inline-block";
    }

    function abrirCaixa() {
      if (descontoAtivo || !nomeUsuario) return;
      descontoAtivo = true;
      const caixa = document.getElementById("caixa-surpresa");
      caixa.classList.add("spin");
      setTimeout(() => {
        caixa.style.display = "none";
        const msg = document.getElementById("mensagem-desconto");
        msg.innerHTML = `🎉 <strong>PARABÉNS ${nomeUsuario.toUpperCase()}!</strong> VOCÊ GANHOU O DESCONTO DE 50%! 🎉`;
        msg.style.display = "block";
        document.getElementById("temporizador").style.display = "block";
        carregarProdutos();
        iniciarTemporizador();
      }, 3000);
    }

    function carregarProdutos() {
      const lista = document.getElementById("lista-produtos");
      lista.style.display = "grid";
      produtos.forEach(p => {
        const precoDesc = (p.preco * 0.5).toFixed(2);
        const card = document.createElement("div");
        card.className = "produto";
        card.innerHTML = `
          <img src="${p.imagem}" alt="${p.nome}" loading="lazy" />
          <h3>${p.nome}</h3>
          <p class="preco-original">R$ ${p.preco.toFixed(2).replace('.', ',')}</p>
          <p class="preco-desconto">R$ ${precoDesc.replace('.', ',')}</p>
          <button onclick="adicionarAoCarrinho('${p.nome}', ${precoDesc}, event)">Comprar</button>
        `;
        lista.appendChild(card);
      });
    }

    function iniciarTemporizador() {
      const el = document.getElementById("tempo");
      const msg = document.getElementById("mensagem-desconto");
      const interval = setInterval(() => {
        if (tempoRestante <= 0) {
          clearInterval(interval);
          document.querySelectorAll(".produto button").forEach(b => {
            b.disabled = true;
            b.innerText = "Tempo Esgotado";
          });
          msg.innerHTML += "<br><small>❌ O desconto foi encerrado.</small>";
          mostrarToast("⛔ O desconto expirou!");
          return;
        }
        const m = String(Math.floor(tempoRestante / 60)).padStart(2, '0');
        const s = String(tempoRestante % 60).padStart(2, '0');
        el.textContent = `${m}:${s}`;
        tempoRestante--;
      }, 1000);
    }

    function adicionarAoCarrinho(nome, preco, event) {
      totalItens++;
      totalValor += preco;
      atualizarCarrinho();
      mostrarToast(`✅ ${nome} adicionado ao carrinho!`);
      const btn = event.target;
      btn.disabled = true;
      btn.innerText = "Adicionado!";
    }

    function atualizarCarrinho() {
      document.getElementById("carrinho").innerText = 
        `Carrinho: ${totalItens} item(s) – R$ ${totalValor.toFixed(2).replace('.', ',')}`;
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
