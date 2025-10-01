<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Teens & Eletrônicos - Promoção</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
<style>
body {
  font-family: 'Arial', sans-serif;
  margin: 0; padding: 0;
  background-color: #f4f4f4;
  color: #333;
  text-align: center;
}
header {
  background-color: #002366;
  color: white;
  padding: 30px 15px;
  font-size: 2em;
  font-weight: bold;
  letter-spacing: 1px;
}
main {
  padding: 30px 20px;
  max-width: 1200px;
  margin: auto;
}
.intro-section {
  background: #fff;
  padding: 30px 20px;
  border-radius: 12px;
  margin-bottom: 25px;
  box-shadow: 0 6px 15px rgba(0,0,0,0.15);
}
.intro-section h2 {
  margin-bottom: 15px;
  font-size: 1.8em;
  color: #002366;
}
.intro-row {
  display:flex; gap:10px; flex-wrap:wrap; justify-content:center; align-items:center;
}
.intro-row input {
  padding:12px;
  border-radius:8px;
  border:1px solid #ccc;
  width:220px;
  max-width:90%;
  font-size:1em;
}
.intro-row .btn {
  background:#002366;
  color:white;
  border:none;
  padding:12px 20px;
  border-radius:8px;
  cursor:pointer;
  font-size:1em;
  transition: background 0.3s;
}
.intro-row .btn:hover { background:#1e3a8a; }

#caixa-surpresa { cursor:pointer; display:inline-block; margin-top:25px; }
#caixa-surpresa .caixa {
  width:160px;height:160px;
  background: conic-gradient(#1e3a8a,#2563eb,#3b82f6,#1e3a8a);
  border-radius:15px;
  display:flex; align-items:center; justify-content:center;
  color:#fff; font-size:1.5em; font-weight:bold;
  box-shadow:0 6px 15px rgba(0,0,0,0.2);
  user-select:none;
  transition: transform 0.3s ease;
}
#caixa-surpresa.spin .caixa { animation: spin 3s ease-in-out; }
@keyframes spin { from{transform:rotate(0)} to{transform:rotate(360deg)} }

#mensagem-desconto { display:none; font-size:1.2em; font-weight:bold; margin-top:18px; color:#388e3c; }
#temporizador { display:none; font-size:1.1em; margin-top:10px; color:#d32f2f; }

.produtos {
  display:none;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
  gap:20px;
  margin:30px 0;
}
.produto {
  background: #fff;
  border-radius:12px;
  padding:18px;
  display:flex;
  flex-direction:column;
  align-items:center;
  transition: transform .3s, box-shadow .3s;
  box-shadow: 0 4px 12px rgba(0,0,0,0.12);
  position: relative;
}
.produto:hover { transform: translateY(-8px); box-shadow:0 12px 22px rgba(0,0,0,0.18); }
.produto img {
  width: 100%;
  height: 220px;
  object-fit: contain;
  border-radius: 8px;
  margin-bottom: 12px;
  background:#fff;
  padding:6px;
}
.produto h3 { margin:6px 0; font-size:1.1em; color:#002366; }
.preco-original { text-decoration:line-through; color:#777; font-size:0.95em; margin:4px 0; }
.preco-desconto { color:#d32f2f; font-size:1.25em; font-weight:bold; margin:4px 0 10px; }
.produto button {
  background:#002366;
  color:#fff;
  border:none;
  padding:10px 16px;
  border-radius:8px;
  cursor:pointer;
  font-size:1em;
  width:100%;
  max-width:200px;
  transition: background 0.3s, transform 0.2s;
}
.produto button:hover:not(:disabled){ background:#1e3a8a; transform: scale(1.05); }
.produto button:disabled { background:#999; cursor:not-allowed; }

.toast {
  position: fixed; right:20px; bottom:20px;
  background:#ff9800; color:#fff; padding:14px 18px; border-radius:10px; font-weight:bold; z-index:9999;
  opacity:0; transform:translateY(20px); transition:opacity .35s, transform .35s;
  max-width:90vw; word-wrap:break-word; text-align:left;
}
.toast.show { opacity:1; transform:translateY(0); }

footer {
  background:#222; color:#eee; padding:30px 20px; text-align:center; margin-top:25px;
}
footer h3 { color:#002366; margin-bottom:12px; }
footer .selos { display:flex; justify-content:center; gap:25px; margin:12px 0; font-size:1.2em; }
footer p { margin-top:6px; font-size:1.1em; }

@media (max-width:700px){
  .produtos { grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); }
  header { font-size:1.4em; }
}
</style>
</head>
<body>
<header>🎉 Teens & Eletrônicos - GANHE ATÉ 50% DE DESCONTO! 🎉</header>

<main>
<div class="intro-section">
<h2>Participe da Surpresa</h2>
<div class="intro-row">
  <input id="nome-usuario" type="text" placeholder="Seu nome (ex.: João Silva)" />
  <button class="btn" onclick="habilitarCaixa()">Confirmar</button>
</div>
</div>

<div id="lista-produtos" class="produtos"></div>
</main>

<footer>
<h3>Confiança e Segurança</h3>
<div class="selos">
  <span title="Compra segura">🔒 Segurança</span>
  <span title="Entrega rápida">🚚 Entrega</span>
</div>
<p>🛍️ Teens & Eletrônicos • Since 2021</p>
</footer>

<div class="toast" id="toast"></div>

<script>
let descontoAtivo = false;
let tempoRestante = 600;
let nomeUsuario = "";
let timerInterval = null;

const produtos = [
{ nome: "Boneco Labubu", preco: 199.00, imagem:"https://down-br.img.susercontent.com/file/br-11134207-7r98o-m9zzn8o7e1q1aa", link:"https://app.ghostspaysv2.com/payment/checkout/2c42055d-f8ac-4b11-9da0-a14fc0750e65" },
{ nome: "Tablet Samsung", preco: 1499.00, imagem:"https://gazin-images.gazin.com.br/cNBvTxoXDdo6uT5Wqw3FkJ4nzl8=/1920x/filters:format(webp):quality(75)/https://gazin-marketplace.s3.amazonaws.com/midias/imagens/2024/07/tablet-samsung-galaxy-tab-s6-lite-104-64gb-4gb-android-14-sm-p620nzadzto-112407032345.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/ca1743be-4b5b-48a2-baf6-99ed38f5340c" },
{ nome: "Bola Copa de 2022", preco: 150.00, imagem:"https://img.odcdn.com.br/wp-content/uploads/2022/07/bola-copa-22.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/602f8975-1e9f-4497-89eb-a02d820d398d" },
{ nome: "Pista Skate", preco: 75.00, imagem:"https://a-static.mlcdn.com.br/800x600/pista-skate-dedo-profissional-rampa-e-corrimao-com-skate-dm-toys/fastvarejoloja/dmt6686-dellboard/53052402e90354dba997df19b78e5515.jpeg", link:"https://app.ghostspaysv2.com/payment/checkout/3683028e-c8c6-4d70-b1b0-898865564bbd" },
{ nome: "Quadro Neymar", preco: 299.90, imagem:"https://m.media-amazon.com/images/I/71YgRiaji1L._UF350,350_QL80_.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/bc79310c-c840-4866-ae97-56144631c598" },
{ nome: "Carro Controle Remoto", preco: 320.00, imagem:"https://i.zst.com.br/thumbs/12/c/3b/-1347048930.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/c2c623e5-78d1-4d2f-b307-ad5aab7c8451" },
{ nome: "Hoverboard Infantil", preco: 950.00, imagem:"https://m.media-amazon.com/images/I/51zpqiSLytL._UF894,1000_QL80_.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/3e97208a-6410-41a7-92af-60232a905a7c" },
{ nome: "Celular Samsung", preco: 2200.00, imagem:"https://t34114.vtexassets.com/arquivos/ids/244867/smartphone-samsung-galaxy-a16-lte-128gb-4gb-ram-tela-6-7-nfc-ip54-camera-de-ate-50mp-bateria-5000-mah-e-dual-chip-verde-claro-1.jpg?v=638708210592370000", link:"https://app.ghostspaysv2.com/payment/checkout/9e9fe3ff-9a6e-4373-839b-a2589fa95979" },
{ nome: "Patinete Eletrônico", preco: 680.00, imagem:"https://www.mymax.ind.br/wp-content/uploads/2020/02/009239_1.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/799e72fd-d15c-4f68-aafa-c1f7a34ac39b" },
{ nome: "Bobbie Goods", preco: 93.90, imagem:"https://images.tcdn.com.br/img/img_prod/1106500/kit_livro_de_colorir_bobbie_goods_80_canetinhas_duas_pontas_20600_1_b6882cd8eef0bc87e0e4ccd40606895e.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/4aeec8a5-d852-4c56-bc00-3ac0389614ca" },
{ nome: "Patins Inline", preco: 430.00, imagem:"https://freitasvarejo.vteximg.com.br/arquivos/ids/175986-440-500/16092876001_1.jpg?v=637993807985830000", link:"https://app.ghostspaysv2.com/payment/checkout/4990c25d-d243-4ba5-bd20-b0a732a6ab60" },
{ nome: "Mascara Batman", preco: 120.00, imagem:"https://superlegalbrinquedos.vtexassets.com/arquivos/ids/228056/Mascara-Eletronica---Batman-Armor-Up---15-Sons-e-Luzes---DC-Comics---Sunny-1.jpg?v=638422414673770000", link:"https://app.ghostspaysv2.com/payment/checkout/325591d3-60e4-4a46-bf71-1fb3dfbd3eec" },
{ nome: "Boneco Coringa", preco: 220.00, imagem:"https://http2.mlstatic.com/D_NQ_NP_949891-MLB89275608717_082025-O-boneco-coringa-estatua-de-resina-joker-23cm.webp", link:"https://app.ghostspaysv2.com/payment/checkout/16e2b936-697a-4ffe-a8e6-7a3afc78aef7" },
{ nome: "Caixa de Som JBL", preco: 560.00, imagem:"https://lojaibyte.vteximg.com.br/arquivos/ids/421409-540-540/caixa-de-som-jbl-boombox-3-180w-rms-01-min.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/250a08f0-b9f7-46df-a20b-5cef140f7d6f" },
{ nome: "Stitch Pelúcia", preco: 119.90, imagem:"https://www.americanas.com.br/_next/image?url=https%3A%2F%2Famericanas.vtexassets.com%2Farquivos%2Fids%2F31411475%2FPELUCIADISNEYSOFTSTITCH30CMF01808.jpg%3Fv%3D638836036964770000&w=768&q=90", link:"https://app.ghostspaysv2.com/payment/checkout/dba4e3a2-0cde-443a-87b5-277c95f7ddfc" },
{ nome: "Cozinha da Barbie", preco: 128.90, imagem:"https://http2.mlstatic.com/D_NQ_NP_779458-MLB52539244121_112022-O.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/1082e0d0-48bb-4f21-9b32-22170e9d51aa" },
{ nome: "Acampamento da Barbie", preco: 478.90, imagem:"https://http2.mlstatic.com/D_NQ_NP_980198-MLA91546267440_092025-O.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/58b66112-7aa4-4775-83c0-0e1b9b46bab0" },
{ nome: "Futebol de botão", preco: 254.90, imagem:"https://http2.mlstatic.com/D_NQ_NP_603090-MLB76004239711_042024-O-kit-futebol-de-boto-completo-campo-jogo-de-botoes-trave.webp", link:"https://app.ghostspaysv2.com/payment/checkout/420dd036-82d4-4dea-920e-5d5d154f7cfb" },
{ nome: "Playstation 5", preco: 3999.00, imagem:"https://cdn.awsli.com.br/600x450/241/241991/produto/302110171/71-wuld5s0x3a.png", link:"https://app.ghostspaysv2.com/payment/checkout/ad531c6b-9a81-480c-9a8e-fd8078734d9e" },
{ nome: "Notebook", preco: 2999.00, imagem:"https://m.media-amazon.com/images/I/71vvXGmdKWL.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/18431408-4370-47f4-b398-bc64dbb47a20" },
{ nome: "iPhone 14", preco: 5299.00, imagem:"https://m.media-amazon.com/images/I/61bK6PMOC3L._AC_SL1500_.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/3cdb45cf-0c00-40b7-89e7-ad2df6cc73ad" },
{ nome: "Bicicleta Aro 29", preco: 1800.00, imagem:"https://cdn.awsli.com.br/600x700/1259/1259538/produto/192827648/krw-bikes---out-20220079-yyfwirr7le.jpg", link:"https://app.ghostspaysv2.com/payment/checkout/c98c75ad-96c0-4f69-b77c-c0d20918a6fb" }
];

function formatMoneyBR(valor) { return 'R$ ' + valor.toFixed(2).replace('.', ','); }
function showToast(msg) { const t = document.getElementById('toast'); t.innerText=msg; t.classList.add('show'); setTimeout(()=>t.classList.remove('show'),2900); }

function habilitarCaixa() {
  const elNome = document.getElementById('nome-usuario');
  const nome = (elNome.value||'').trim();
  if(!nome){alert('Digite seu nome'); elNome.focus(); return;}
  nomeUsuario=nome;
  document.querySelector('.intro-section').innerHTML=`<div style="background:transparent;padding:8px;">
  <div style="font-weight:bold;margin-bottom:6px;">Olá, ${nomeUsuario}</div>
  <section id="caixa-surpresa" onclick="abrirCaixa()">
    <div class="caixa">🎁 Clique aqui!</div>
  </section>
  <div id="mensagem-desconto"></div>
  <div id="temporizador" style="display:none">⏰ Tempo restante: <span id="tempo">10:00</span></div>
  </div>`;
  document.getElementById('lista-produtos').innerHTML='';
}

function abrirCaixa() {
  if(descontoAtivo) return;
  descontoAtivo=true;
  const caixaWrapper = document.getElementById('caixa-surpresa');
  if(caixaWrapper) caixaWrapper.classList.add('spin');
  setTimeout(()=>{
    if(caixaWrapper) caixaWrapper.style.display='none';
    const msgEl=document.getElementById('mensagem-desconto');
    if(msgEl){
      msgEl.innerHTML=`🎉 <strong>PARABÉNS ${nomeUsuario.toUpperCase()}!</strong> DESCONTO DE 50% ATIVADO!`;
      msgEl.style.display='block';
    }
    document.getElementById('temporizador').style.display='block';
    carregarProdutos();
    iniciarTemporizador();
  },3000);
}

function carregarProdutos() {
  const lista=document.getElementById('lista-produtos');
  lista.innerHTML='';
  lista.style.display='grid';
  produtos.forEach((p,idx)=>{
    const precoDesc=(p.preco*0.5).toFixed(2);
    const div=document.createElement('div');
    div.className='produto';
    div.innerHTML=`
    <img src="${p.imagem}" alt="${p.nome}" loading="lazy"/>
    <h3>${p.nome}</h3>
    <p class="preco-original">${formatMoneyBR(p.preco)}</p>
    <p class="preco-desconto">${formatMoneyBR(parseFloat(precoDesc))}</p>
    <button onclick="comprarProduto(${idx})">Comprar</button>
    `;
    lista.appendChild(div);
  });
}

function iniciarTemporizador() {
  clearInterval(timerInterval);
  const el=document.getElementById('tempo');
  if(!el) return;
  el.textContent='10:00'; tempoRestante=600;
  timerInterval=setInterval(()=>{
    if(tempoRestante<=0){
      clearInterval(timerInterval);
      descontoAtivo=false;
      document.querySelectorAll('.produto button').forEach(btn=>{if(!btn.disabled){btn.disabled=true; btn.innerText='Tempo Esgotado';}});
      const msgEl=document.getElementById('mensagem-desconto');
      if(msgEl) msgEl.innerHTML+=`<br><small>❌ O desconto foi encerrado.</small>`;
      showToast('⛔ O desconto expirou!');
      return;
    }
    const m=String(Math.floor(tempoRestante/60)).padStart(2,'0');
    const s=String(tempoRestante%60).padStart(2,'0');
    el.textContent=`${m}:${s}`;
    tempoRestante--;
  },1000);
}

function comprarProduto(index){
  const produto=produtos[index];
  if(!produto) return;
  showToast(`✅ Produto ${produto.nome} adicionado ao carrinho com desconto de 50%!`);
  window.location.href = produto.link;
}
</script>
</body>
</html>
