<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Casa del Sole – Guida per gli Ospiti / Guest Guide</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
  :root { --cream:#F7F4EE;--warm-white:#FDFBF6;--sun:#D4880A;--sun-light:#F2B84B;--ocean:#2A6B8A;--ocean-light:#5BA3C4;--dark:#1C1A14;--mid:#4A4030;--border:rgba(70,55,30,0.13);--shadow:0 6px 30px rgba(28,26,20,0.07); }
  *{margin:0;padding:0;box-sizing:border-box}
  body{background:var(--cream);color:var(--dark);font-family:'DM Sans',sans-serif;font-weight:300}
  .lang-bar{background:var(--dark);display:flex;justify-content:center;gap:4px;padding:10px;position:sticky;top:0;z-index:200}
  .lang-btn{background:transparent;border:1px solid rgba(255,255,255,0.2);color:rgba(255,255,255,0.5);font-family:'DM Sans',sans-serif;font-size:10px;letter-spacing:2px;text-transform:uppercase;padding:7px 18px;border-radius:2px;cursor:pointer;transition:all .2s}
  .lang-btn.active{background:var(--sun);border-color:var(--sun);color:#fff}
  .hero{background:var(--dark);position:relative;overflow:hidden;padding:70px 40px 60px;text-align:center}
  .hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 90% 60% at 50% 110%,rgba(212,136,10,0.3) 0%,transparent 65%),radial-gradient(ellipse 60% 40% at 80% 20%,rgba(42,107,138,0.2) 0%,transparent 60%)}
  .hero-eyebrow{font-size:10px;letter-spacing:5px;text-transform:uppercase;color:var(--sun-light);margin-bottom:18px;position:relative}
  .hero h1{font-family:'Cormorant Garamond',serif;font-size:clamp(44px,9vw,88px);font-weight:300;color:var(--warm-white);line-height:0.95;position:relative;letter-spacing:-2px}
  .hero h1 em{font-style:italic;color:var(--sun-light)}
  .hero-location{margin-top:20px;font-size:13px;color:rgba(253,251,246,0.5);letter-spacing:1.5px;position:relative}
  .hero-divider{width:36px;height:1px;background:var(--sun);margin:26px auto 0;position:relative}
  nav{background:var(--warm-white);border-bottom:1px solid var(--border);display:flex;justify-content:center;overflow-x:auto;z-index:100;scrollbar-width:none}
  nav::-webkit-scrollbar{display:none}
  nav a{text-decoration:none;color:var(--mid);font-size:10px;letter-spacing:2px;text-transform:uppercase;padding:15px 14px;border-bottom:2px solid transparent;transition:all .2s;white-space:nowrap;font-weight:400}
  nav a:hover{color:var(--sun);border-bottom-color:var(--sun)}
  main{max-width:800px;margin:0 auto;padding:0 24px 80px}
  section{margin-top:68px}
  .section-label{font-size:10px;letter-spacing:3px;text-transform:uppercase;color:var(--sun);margin-bottom:10px}
  .section-title{font-family:'Cormorant Garamond',serif;font-size:clamp(28px,5vw,44px);font-weight:300;color:var(--dark);line-height:1.05;margin-bottom:28px;padding-bottom:18px;border-bottom:1px solid var(--border)}
  .card{background:var(--warm-white);border:1px solid var(--border);border-radius:3px;padding:26px 30px;margin-bottom:14px;box-shadow:var(--shadow)}
  .card-icon{font-size:20px;margin-bottom:10px;display:block}
  .card h3{font-family:'Cormorant Garamond',serif;font-size:21px;font-weight:400;color:var(--dark);margin-bottom:12px}
  .card p{font-size:14px;line-height:1.85;color:var(--mid)}
  .card ul{padding-left:18px}
  .card li{font-size:14px;line-height:2;color:var(--mid)}
  .steps{list-style:none;padding:0;counter-reset:step}
  .steps li{counter-increment:step;display:flex;align-items:flex-start;gap:14px;padding:13px 0;border-bottom:1px solid var(--border)}
  .steps li:last-child{border-bottom:none}
  .steps li::before{content:counter(step);min-width:26px;height:26px;background:var(--sun);color:#fff;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:500;flex-shrink:0;margin-top:3px}
  .steps li > div > div.it,.steps li > div > div.en{font-size:14px;line-height:1.75;color:var(--mid)}
  .steps li > div > div.en{margin-top:4px;color:rgba(74,64,48,0.55);font-style:italic;font-size:13px}
  body.lang-en .steps li > div > div.it{display:none}
  body.lang-en .steps li > div > div.en{color:var(--mid);font-style:normal;font-size:14px;margin-top:0}
  body.lang-it .steps li > div > div.en{display:none}
  .code-display{font-family:'Cormorant Garamond',serif;font-size:56px;font-weight:600;letter-spacing:16px;color:var(--sun);background:rgba(212,136,10,0.08);border:2px solid rgba(212,136,10,0.3);border-radius:4px;padding:12px 28px;margin-top:10px;display:inline-block}
  .keys-list{list-style:none;padding:0}
  .keys-list li{display:flex;align-items:flex-start;gap:12px;padding:13px 0;border-bottom:1px solid var(--border)}
  .keys-list li:last-child{border-bottom:none}
  .key-emoji{font-size:20px;flex-shrink:0;margin-top:2px}
  .keys-list li > div > div.it,.keys-list li > div > div.en{font-size:14px;line-height:1.7;color:var(--mid)}
  .keys-list li > div > div.en{margin-top:3px;color:rgba(74,64,48,0.55);font-style:italic;font-size:13px}
  body.lang-en .keys-list li > div > div.it{display:none}
  body.lang-en .keys-list li > div > div.en{color:var(--mid);font-style:normal;font-size:14px;margin-top:0}
  body.lang-it .keys-list li > div > div.en{display:none}
  .time-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
  .time-card{background:var(--dark);border-radius:3px;padding:26px 20px;color:var(--warm-white);text-align:center}
  .time-card .t-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--sun-light);margin-bottom:10px}
  .time-card .t-time{font-family:'Cormorant Garamond',serif;font-size:50px;font-weight:300;line-height:1}
  .time-card .t-desc{font-size:11px;color:rgba(253,251,246,0.45);margin-top:7px}
  .wifi-box{background:linear-gradient(135deg,#0d2a3a 0%,#163d54 100%);border-radius:3px;padding:30px 32px;color:var(--warm-white);display:flex;align-items:center;justify-content:space-between;gap:24px;flex-wrap:wrap}
  .wifi-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--ocean-light);opacity:.8;margin-bottom:5px}
  .wifi-name{font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:300;margin-bottom:4px}
  .wifi-sub{font-size:12px;color:rgba(255,255,255,0.4)}
  .wifi-password-block{text-align:right}
  .wifi-pass-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--ocean-light);opacity:.8;margin-bottom:5px}
  .wifi-pass{font-family:'Cormorant Garamond',serif;font-size:30px;font-weight:300;letter-spacing:3px;color:#89cce8}
  .wifi-copy-btn{display:inline-block;margin-top:9px;background:rgba(255,255,255,0.08);color:rgba(255,255,255,0.65);border:1px solid rgba(255,255,255,0.13);border-radius:2px;font-size:9px;letter-spacing:2px;text-transform:uppercase;padding:7px 14px;cursor:pointer;transition:background .2s;font-family:'DM Sans',sans-serif}
  .rules-list{list-style:none;padding:0}
  .rules-list li{display:flex;align-items:flex-start;gap:13px;padding:15px 0;border-bottom:1px solid var(--border);font-size:14px;line-height:1.7;color:var(--mid)}
  .rules-list li:last-child{border-bottom:none}
  .rule-icon{width:27px;height:27px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:13px;flex-shrink:0;margin-top:1px}
  .rule-ok{background:rgba(42,107,138,0.1)}
  .rule-no{background:rgba(212,136,10,0.1)}
  .place-category{margin-bottom:26px}
  .place-category h3{font-family:'Cormorant Garamond',serif;font-size:21px;font-weight:400;margin-bottom:12px;color:var(--dark)}
  .place-item{background:var(--warm-white);border:1px solid var(--border);border-radius:3px;padding:16px 20px;margin-bottom:9px;display:flex;justify-content:space-between;align-items:center;gap:14px;box-shadow:var(--shadow)}
  .place-info strong{display:block;font-size:14px;font-weight:500;margin-bottom:2px}
  .place-info span{font-size:12px;color:var(--mid)}
  .place-tag{font-size:9px;letter-spacing:1.5px;text-transform:uppercase;background:rgba(212,136,10,0.1);color:var(--sun);padding:4px 9px;border-radius:20px;white-space:nowrap;font-weight:500}
  .parking-box{background:linear-gradient(135deg,var(--dark) 0%,#2d2510 100%);border-radius:3px;padding:34px;color:var(--warm-white);position:relative;overflow:hidden}
  .parking-box::after{content:'P';position:absolute;right:28px;bottom:-14px;font-family:'Cormorant Garamond',serif;font-size:130px;font-weight:300;color:rgba(255,255,255,0.03);line-height:1}
  .parking-box h3{font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:300;margin-bottom:12px;color:var(--sun-light)}
  .parking-box p{font-size:14px;line-height:1.85;color:rgba(253,251,246,0.72);margin-bottom:10px}
  .highlight{display:inline-flex;align-items:center;gap:8px;background:rgba(212,136,10,0.12);border:1px solid rgba(212,136,10,0.25);border-radius:3px;padding:10px 16px;margin-top:14px;font-size:13px;color:var(--sun);font-weight:500}
  .warning-banner{background:#7a1515;border-radius:3px;padding:22px 26px;display:flex;align-items:flex-start;gap:16px;margin-bottom:18px}
  .warning-banner .warn-icon{font-size:28px;flex-shrink:0}
  .warning-banner h4{font-family:'Cormorant Garamond',serif;font-size:20px;font-weight:600;color:#fff;margin-bottom:7px}
  .warning-banner p{font-size:13px;line-height:1.8;color:rgba(255,210,210,0.88)}
  .secco-rule{background:linear-gradient(135deg,#3a2000 0%,#5c3800 100%);border-radius:3px;padding:26px 30px;margin-bottom:18px;border-left:4px solid var(--sun);position:relative;overflow:hidden}
  .secco-rule h4{font-family:'Cormorant Garamond',serif;font-size:21px;font-weight:400;color:var(--sun-light);margin-bottom:12px}
  .secco-rule p{font-size:14px;line-height:1.85;color:rgba(253,240,200,0.85)}
  .waste-grid{display:grid;grid-template-columns:1fr 1fr;gap:11px;margin-bottom:14px}
  .waste-card{background:var(--warm-white);border:1px solid var(--border);border-radius:3px;padding:16px 18px;box-shadow:var(--shadow);border-left:4px solid #ccc}
  .waste-card.plastica{border-left-color:#1565C0}.waste-card.carta{border-left-color:#F9A825}.waste-card.vetro{border-left-color:#2E7D32}.waste-card.secco{border-left-color:#616161}.waste-card.organico{border-left-color:#6D4C41}
  .waste-day{font-size:9px;letter-spacing:2px;text-transform:uppercase;font-weight:600;margin-bottom:4px}
  .plastica .waste-day{color:#1565C0}.carta .waste-day{color:#F9A825}.vetro .waste-day{color:#2E7D32}.secco .waste-day{color:#616161}.organico .waste-day{color:#6D4C41}
  .waste-type{font-size:15px;font-weight:500;color:var(--dark);margin-bottom:4px}
  .waste-container{font-size:12px;color:var(--mid);line-height:1.5}
  .qr-section{background:var(--dark);border-radius:3px;padding:36px 32px;text-align:center;margin-bottom:14px}
  .qr-section h3{font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:300;color:var(--warm-white);margin-bottom:8px}
  .qr-section p{font-size:13px;color:rgba(253,251,246,0.5);margin-bottom:24px}
  #qrcode{display:inline-block;background:white;padding:14px;border-radius:4px;margin-bottom:20px}
  .qr-url{font-size:12px;color:rgba(253,251,246,0.4);letter-spacing:1px;word-break:break-all;margin-bottom:20px}
  .copy-link-btn{display:inline-block;background:var(--sun);color:#fff;border:none;font-family:'DM Sans',sans-serif;font-size:11px;letter-spacing:2px;text-transform:uppercase;font-weight:500;padding:12px 24px;border-radius:2px;cursor:pointer;transition:opacity .2s}
  .contact-bar{background:var(--sun);border-radius:3px;padding:26px 30px;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:14px;margin-top:14px}
  .contact-text{font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:300;color:var(--warm-white)}
  .contact-number{font-size:14px;color:rgba(253,251,246,0.82);margin-top:3px}
  .contact-btn{display:inline-block;background:var(--warm-white);color:var(--sun);text-decoration:none;font-size:10px;letter-spacing:2px;text-transform:uppercase;font-weight:500;padding:11px 20px;border-radius:2px;transition:opacity .2s}
  footer{text-align:center;padding:40px 24px;font-size:10px;color:rgba(70,55,30,0.38);letter-spacing:2px;text-transform:uppercase;border-top:1px solid var(--border)}
  body.lang-en .it{display:none}body.lang-it .en{display:none}
  span.it,span.en{display:inline}
  body.lang-en span.it{display:none}body.lang-it span.en{display:none}body.lang-en span.en{display:inline}
  @media(max-width:520px){
    .time-grid,.waste-grid{grid-template-columns:1fr}.hero{padding:56px 20px 46px}
    nav a{padding:13px 10px;font-size:9px}.wifi-box{flex-direction:column}
    .wifi-password-block{text-align:left}.parking-box{padding:24px 20px}
    .card{padding:20px 18px}.contact-bar{flex-direction:column}
    .warning-banner{flex-direction:column;gap:10px}.waste-card.organico{grid-column:span 1}
    .code-display{font-size:40px;letter-spacing:10px}}
</style>
</head>
<body class="lang-it">
<div class="lang-bar">
  <button class="lang-btn active" onclick="setLang('it')">🇮🇹 Italiano</button>
  <button class="lang-btn" onclick="setLang('en')">🇬🇧 English</button>
</div>
<div class="hero">
  <p class="hero-eyebrow it">Benvenuti</p><p class="hero-eyebrow en">Welcome</p>
  <h1>Casa del <em>Sole</em></h1>
  <p class="hero-location">📍 Via delle Rondini 12 · Cagliari · Spiaggia del Poetto</p>
  <div class="hero-divider"></div>
</div>
<nav>
  <a href="#checkin">Check-in</a>
  <a href="#checkout">Check-out</a>
  <a href="#wifi">Wi-Fi</a>
  <a href="#regole"><span class="it">Regole</span><span class="en">Rules</span></a>
  <a href="#luoghi"><span class="it">Spiagge</span><span class="en">Beaches</span></a>
  <a href="#trasporti"><span class="it">Trasporti</span><span class="en">Transport</span></a>
  <a href="#parcheggio"><span class="it">Parcheggio</span><span class="en">Parking</span></a>
  <a href="#rifiuti"><span class="it">Rifiuti</span><span class="en">Recycling</span></a>
  <a href="#condividi"><span class="it">Condividi</span><span class="en">Share</span></a>
  <a href="#contatti"><span class="it">Contatti</span><span class="en">Contacts</span></a>
</nav>
<main>

  <section id="checkin">
    <p class="section-label it">Arrivo</p><p class="section-label en">Arrival</p>
    <h2 class="section-title it">Istruzioni Self Check-in</h2>
    <h2 class="section-title en">Self Check-in Instructions</h2>
    <div class="time-grid">
      <div class="time-card">
        <p class="t-label it">Check-in dalle</p><p class="t-label en">Check-in from</p>
        <p class="t-time">15:00</p>
        <p class="t-desc it">Contattaci per arrivi tardivi</p><p class="t-desc en">Contact us for late arrivals</p>
      </div>
      <div class="time-card">
        <p class="t-label it">Indirizzo</p><p class="t-label en">Address</p>
        <p class="t-time" style="font-size:26px;margin-top:6px;line-height:1.2;">Via delle<br>Rondini 12</p>
        <p class="t-desc">Cagliari</p>
      </div>
    </div>
    <div class="card">
      <span class="card-icon">🔑</span>
      <h3 class="it">Come trovare le chiavi</h3><h3 class="en">How to find the keys</h3>
      <ol class="steps">
        <li><div><div class="it">Raggiungi il cancello di ingresso in <strong>Via delle Rondini 12</strong>.</div><div class="en">Reach the entrance gate at <strong>Via delle Rondini 12</strong>.</div></div></li>
        <li><div><div class="it">Sotto la cassetta della posta, accanto al cancello, troverai la <strong>cassetta di sicurezza</strong> per le chiavi.</div><div class="en">Under the letterbox, next to the gate, you'll find the <strong>key safe</strong>.</div></div></li>
        <li><div><div class="it">Solleva il pannello di plastica e componi il codice:</div><div class="en">Lift the plastic panel and enter the code:</div><div class="code-display">0860</div></div></li>
        <li><div><div class="it">Premi i <strong>due pulsanti laterali</strong> contemporaneamente per aprire la cassaforte.</div><div class="en">Press the <strong>two side buttons</strong> simultaneously to open the safe.</div></div></li>
        <li><div><div class="it">Prendi le <strong>chiavi di ingresso</strong> e il <strong>badge</strong> di accesso alla casa.</div><div class="en">Take the <strong>entrance keys</strong> and the <strong>access badge</strong>.</div></div></li>
        <li><div><div class="it">Richiudi accuratamente la cassetta <strong>mescolando i numeri</strong> della combinazione.</div><div class="en">Close the safe carefully, <strong>scrambling the digits</strong> of the combination.</div></div></li>
      </ol>
    </div>
    <div class="card">
      <span class="card-icon">🗝️</span>
      <h3 class="it">A cosa serve ogni chiave</h3><h3 class="en">What each key is for</h3>
      <ul class="keys-list">
        <li><span class="key-emoji">🟢</span><div><div class="it"><strong>Chiave verde</strong> → cancello di ingresso condominiale</div><div class="en"><strong>Green key</strong> → building entrance gate</div></div></li>
        <li><span class="key-emoji">🟠</span><div><div class="it"><strong>Chiave arancione</strong> → portoncino del palazzo</div><div class="en"><strong>Orange key</strong> → building front door</div></div></li>
        <li><span class="key-emoji">🔹</span><div><div class="it"><strong>Chiave piccola</strong> → cancello automatico del posto auto</div><div class="en"><strong>Small key</strong> → automatic gate of the parking area</div></div></li>
        <li><span class="key-emoji">💳</span><div><div class="it"><strong>Badge</strong> → apre la porta dell'appartamento e attiva l'elettricità</div><div class="en"><strong>Badge</strong> → opens the apartment door and activates electricity</div></div></li>
      </ul>
      <div class="highlight">🏠 <span class="it">Casa del Sole si trova al <strong>3° piano</strong></span><span class="en">Casa del Sole is on the <strong>3rd floor</strong></span></div>
    </div>
  </section>

  <section id="checkout">
    <p class="section-label it">Partenza</p><p class="section-label en">Departure</p>
    <h2 class="section-title it">Istruzioni Self Check-out</h2>
    <h2 class="section-title en">Self Check-out Instructions</h2>
    <div class="time-grid">
      <div class="time-card">
        <p class="t-label it">Check-out entro le</p><p class="t-label en">Check-out by</p>
        <p class="t-time">11:00</p>
        <p class="t-desc it">Del mattino del giorno di partenza</p><p class="t-desc en">On the morning of your departure</p>
      </div>
      <div class="time-card">
        <p class="t-label it">Late check-out</p><p class="t-label en">Late check-out</p>
        <p class="t-time" style="font-size:36px;margin-top:8px;">📩</p>
        <p class="t-desc it">Solo su richiesta e disponibilità</p><p class="t-desc en">On request, subject to availability</p>
      </div>
    </div>
    <div class="card">
      <span class="card-icon">✅</span>
      <h3 class="it">Lista prima di partire</h3><h3 class="en">Departure checklist</h3>
      <ol class="steps">
        <li><div><div class="it">Se hai l'auto nel cortile, <strong>portala fuori prima di lasciare la casa</strong>.</div><div class="en">If your car is in the courtyard, <strong>take it out before leaving the apartment</strong>.</div></div></li>
        <li><div><div class="it">Spegni <strong>luci, TV, aria condizionata</strong> e tutti gli elettrodomestici.</div><div class="en">Turn off <strong>lights, TV, air conditioning</strong> and all appliances.</div></div></li>
        <li><div><div class="it">Chiudi bene tutte le <strong>finestre</strong>.</div><div class="en">Close all <strong>windows</strong> securely.</div></div></li>
        <li><div><div class="it">Lascia le <strong>chiavi all'interno dell'appartamento</strong> e chiudi la porta uscendo.</div><div class="en">Leave the <strong>keys inside the apartment</strong> and close the door as you leave.</div></div></li>
      </ol>
      <p class="it" style="margin-top:18px;font-size:14px;color:var(--mid);line-height:1.8;">Grazie della tua collaborazione e felice permanenza! Per qualsiasi esigenza non esitare a contattarmi. — <strong>Ignazio</strong></p>
      <p class="en" style="margin-top:18px;font-size:14px;color:var(--mid);line-height:1.8;">Thank you for your cooperation and enjoy your stay! Don't hesitate to get in touch for anything you need. — <strong>Ignazio</strong></p>
    </div>
  </section>

  <section id="wifi">
    <p class="section-label it">Connessione</p><p class="section-label en">Internet</p>
    <h2 class="section-title">Wi-Fi</h2>
    <div class="wifi-box">
      <div>
        <p class="wifi-label it">Nome rete</p><p class="wifi-label en">Network name</p>
        <p class="wifi-name">CasadelSole_Guest</p>
        <p class="wifi-sub it">Copertura in tutto l'appartamento</p><p class="wifi-sub en">Full apartment coverage</p>
      </div>
      <div class="wifi-password-block">
        <p class="wifi-pass-label">Password</p>
        <p class="wifi-pass" id="wifi-pass">Da aggiungere</p>
        <button class="wifi-copy-btn" onclick="copyWifi()">📋 <span class="it">Copia</span><span class="en">Copy</span></button>
      </div>
    </div>
    <div class="card" style="margin-top:14px">
      <span class="card-icon">💡</span>
      <h3 class="it">Problemi di connessione?</h3><h3 class="en">Connection issues?</h3>
      <p class="it">Se la connessione è instabile, prova a spegnere e riaccendere il router. Se il problema persiste, contatta Ignazio al <strong>+39 327 095 7224</strong>.</p>
      <p class="en">If the connection is unstable, try switching the router off and on again. If the problem persists, contact Ignazio at <strong>+39 327 095 7224</strong>.</p>
    </div>
  </section>

  <section id="regole">
    <p class="section-label it">Da sapere</p><p class="section-label en">House Rules</p>
    <h2 class="section-title it">Regole della Casa</h2><h2 class="section-title en">House Rules</h2>
    <div class="card">
      <ul class="rules-list">
        <li><span class="rule-icon rule-no">🚭</span><div class="it">Vietato fumare all'interno dell'appartamento.</div><div class="en">No smoking inside the apartment.</div></li>
        <li><span class="rule-icon rule-no">🔊</span><div class="it"><strong>Silenzio dopo le 22:30.</strong> Rispettiamo i vicini.</div><div class="en"><strong>Quiet hours after 10:30 PM.</strong> Please respect the neighbours.</div></li>
        <li><span class="rule-icon rule-no">🐾</span><div class="it">Animali domestici non ammessi senza autorizzazione.</div><div class="en">Pets not allowed without prior authorisation.</div></li>
        <li><span class="rule-icon rule-no">👥</span><div class="it">Il numero massimo di ospiti è quello indicato nella prenotazione.</div><div class="en">Maximum number of guests as stated in the booking.</div></li>
        <li><span class="rule-icon rule-ok">🧹</span><div class="it">Lasciare la casa nelle stesse condizioni di arrivo.</div><div class="en">Please leave the apartment as you found it.</div></li>
        <li><span class="rule-icon rule-ok">🛏️</span><div class="it">La biancheria è inclusa. Non portarla fuori dall'alloggio.</div><div class="en">Bed linen is included. Please do not take it outside the apartment.</div></li>
      </ul>
    </div>
  </section>

  <section id="luoghi">
    <p class="section-label it">Cagliari e dintorni</p><p class="section-label en">Cagliari & surroundings</p>
    <h2 class="section-title it">Spiagge da non perdere</h2><h2 class="section-title en">Best Beaches</h2>
    <div class="place-category">
      <h3 class="it">🏖️ Vicino a casa</h3><h3 class="en">🏖️ Close to home</h3>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia del Poetto</strong><span class="it">Pochi minuti a piedi · sabbia bianca · 8 km di spiaggia</span><span class="en">A few minutes on foot · white sand · 8 km of beach</span></div>
        <span class="place-tag it">Vicinissima</span><span class="place-tag en">Closest</span>
      </div>
      <div class="place-item">
        <div class="place-info"><strong>Laguna di Molentargius</strong><span class="it">Parco naturale con fenicotteri rosa · accanto al Poetto</span><span class="en">Natural park with pink flamingos · next to Poetto beach</span></div>
        <span class="place-tag it">Natura</span><span class="place-tag en">Nature</span>
      </div>
    </div>
    <div class="place-category">
      <h3 class="it">🌊 Gita a Chia — Domus de Maria (~60 km)</h3><h3 class="en">🌊 Day trip to Chia — Domus de Maria (~60 km)</h3>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia di Chia</strong><span class="it">Acque cristalline e dune di sabbia bianca · una delle più belle della Sardegna</span><span class="en">Crystal clear waters and white sand dunes · one of Sardinia's finest</span></div>
        <span class="place-tag it">Imperdibile</span><span class="place-tag en">Must visit</span>
      </div>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia di Su Giudeu</strong><span class="it">Domus de Maria · acque turchesi · spiaggia selvaggia e naturale</span><span class="en">Domus de Maria · turquoise waters · wild and unspoilt</span></div>
        <span class="place-tag it">Selvaggia</span><span class="place-tag en">Wild</span>
      </div>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia di Tuerredda</strong><span class="it">Domus de Maria · laguna color smeraldo · tra le più belle d'Italia</span><span class="en">Domus de Maria · emerald lagoon · among Italy's most beautiful</span></div>
        <span class="place-tag it">Top</span><span class="place-tag en">Top</span>
      </div>
    </div>
    <div class="place-category">
      <h3 class="it">🌅 Gita a Villasimius (~50 km)</h3><h3 class="en">🌅 Day trip to Villasimius (~50 km)</h3>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia di Simius</strong><span class="it">La più famosa di Villasimius · sabbia bianchissima · mare da sogno</span><span class="en">Villasimius's most famous beach · white sand · dream-like sea</span></div>
        <span class="place-tag it">Iconica</span><span class="place-tag en">Iconic</span>
      </div>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia del Riso</strong><span class="it">Sabbia finissima bianca · acque trasparenti e poco profonde</span><span class="en">Fine white sand · transparent shallow waters</span></div>
        <span class="place-tag it">Consigliata</span><span class="place-tag en">Recommended</span>
      </div>
      <div class="place-item">
        <div class="place-info"><strong>Spiaggia di Campus</strong><span class="it">Acque azzurre · ottima per lo snorkeling</span><span class="en">Blue waters · great for snorkelling</span></div>
        <span class="place-tag it">Snorkeling</span><span class="place-tag en">Snorkelling</span>
      </div>
    </div>
    <div class="place-category">
      <h3 class="it">🗺️ Da non perdere in città</h3><h3 class="en">🗺️ Must see in the city</h3>
      <div class="place-item">
        <div class="place-info"><strong>Castello di Cagliari</strong><span class="it">Il quartiere storico sul colle — panorama mozzafiato</span><span class="en">Historic hilltop quarter — breathtaking panoramic views</span></div>
        <span class="place-tag it">Centro storico</span><span class="place-tag en">Old town</span>
      </div>
    </div>
  </section>

  <section id="trasporti">
    <p class="section-label it">Muoversi</p><p class="section-label en">Getting around</p>
    <h2 class="section-title it">Trasporti</h2><h2 class="section-title en">Transport</h2>
    <div class="card">
      <span class="card-icon">🚕</span>
      <h3 class="it">Taxi</h3><h3 class="en">Taxi</h3>
      <ul class="keys-list">
        <li><span class="key-emoji">🔴</span><div>
          <div class="it"><strong>Rossoblù Taxi</strong> — <a href="tel:0706655" style="color:var(--sun);font-weight:500;">070 6655</a></div>
          <div class="en"><strong>Rossoblù Taxi</strong> — <a href="tel:0706655" style="color:var(--sun);font-weight:500;">070 6655</a></div>
        </div></li>
        <li><span class="key-emoji">📻</span><div>
          <div class="it"><strong>Radio Taxi</strong> — <a href="tel:0707055" style="color:var(--sun);font-weight:500;">070 7055</a></div>
          <div class="en"><strong>Radio Taxi</strong> — <a href="tel:0707055" style="color:var(--sun);font-weight:500;">070 7055</a></div>
        </div></li>
      </ul>
    </div>
    <div class="card">
      <span class="card-icon">🚌</span>
      <h3 class="it">Autobus CTM — dal Poetto verso il centro</h3>
      <h3 class="en">CTM Bus — from Poetto to the city centre</h3>
      <ul class="keys-list">
        <li><span class="key-emoji">🔵</span><div>
          <div class="it"><strong>Linea PF</strong> → Viale Poetto · centro città · porto di Cagliari</div>
          <div class="en"><strong>Line PF</strong> → Viale Poetto · city centre · Cagliari port</div>
        </div></li>
        <li><span class="key-emoji">🟣</span><div>
          <div class="it"><strong>Linea PQ</strong> → Viale Poetto · centro città · porto di Cagliari</div>
          <div class="en"><strong>Line PQ</strong> → Viale Poetto · city centre · Cagliari port</div>
        </div></li>
      </ul>
      <div style="margin-top:16px;padding:14px 16px;background:rgba(42,107,138,0.08);border-radius:3px;border-left:3px solid var(--ocean);">
        <p class="it" style="font-size:13px;color:var(--mid);">📱 Orari aggiornati su <a href="https://www.ctmcagliari.it" target="_blank" style="color:var(--ocean);font-weight:500;">ctmcagliari.it</a></p>
        <p class="en" style="font-size:13px;color:var(--mid);">📱 Updated timetables at <a href="https://www.ctmcagliari.it" target="_blank" style="color:var(--ocean);font-weight:500;">ctmcagliari.it</a></p>
      </div>
    </div>
  </section>

  <section id="parcheggio">
    <p class="section-label it">Auto</p><p class="section-label en">Car</p>
    <h2 class="section-title it">Parcheggio</h2><h2 class="section-title en">Parking</h2>
    <div class="parking-box">
      <h3 class="it">Posto auto riservato n° 1</h3><h3 class="en">Reserved parking spot n° 1</h3>
      <p class="it">All'interno del cortile condominiale di <strong>Via delle Rondini 12</strong> troverai il tuo posto auto riservato, <strong>contrassegnato con il numero 1</strong> sul suolo, proprio di fronte al cancello automatico.</p>
      <p class="en">Inside the building courtyard at <strong>Via delle Rondini 12</strong> you will find your reserved parking spot, <strong>marked with the number 1</strong> on the ground, right in front of the automatic gate.</p>
      <p class="it">Usa la <strong>chiave piccola</strong> per aprire il cancello automatico. Ti chiediamo di portare fuori la macchina <strong>prima di lasciare l'appartamento</strong> al check-out.</p>
      <p class="en">Use the <strong>small key</strong> to open the automatic gate. Please take your car out <strong>before leaving the apartment</strong> at check-out.</p>
    </div>
  </section>

  <section id="rifiuti">
    <p class="section-label it">Obbligatorio</p><p class="section-label en">Mandatory</p>
    <h2 class="section-title it">Raccolta Differenziata</h2><h2 class="section-title en">Waste Recycling</h2>
    <div class="warning-banner">
      <div class="warn-icon">🚨</div>
      <div>
        <h4 class="it">Regole soggette a sanzione della Polizia Locale</h4>
        <h4 class="en">Rules enforceable by Local Police fine</h4>
        <p class="it">Il Comune di Cagliari effettua controlli regolari. Il mancato rispetto è soggetto a <strong>sanzione amministrativa della Polizia Locale</strong>. Seguire scrupolosamente le istruzioni.</p>
        <p class="en">The Municipality of Cagliari carries out regular checks. Failure to comply is subject to <strong>administrative fines by the Local Police</strong>. Please follow the instructions carefully.</p>
      </div>
    </div>
    <div class="card">
      <span class="card-icon">🗑️</span>
      <h3 class="it">Dove conferire i rifiuti</h3><h3 class="en">Where to dispose of waste</h3>
      <p class="it">Tutti i rifiuti devono essere conferiti negli <strong>appositi mastelli condominiali nel parcheggio interno</strong>. La chiave per accedere ai bidoni è appesa alla <strong>lavagna in cucina</strong>.</p>
      <p class="en">All waste must be placed in the <strong>designated condominium bins in the internal car park</strong>. The key to access the bins hangs on the <strong>kitchen board</strong>.</p>
    </div>
    <div class="secco-rule">
      <h4 class="it">⚠️ Regola speciale — Secco Indifferenziato (contenitore grigio)</h4>
      <h4 class="en">⚠️ Special rule — General Waste (grey bin)</h4>
      <p class="it">Il mastello grigio è <strong>l'unico</strong> da esporre in strada. Va posizionato <strong>a fianco del cancello condominiale il giovedì sera dopo le 20:00</strong> e ritirato <strong>immancabilmente il venerdì mattina</strong>. Tutti gli altri mastelli restano sempre nel parcheggio interno.</p>
      <p class="en">The grey bin is <strong>the only one</strong> to be placed on the public road. Put it <strong>next to the building gate on Thursday evening after 8:00 PM</strong> and bring it back in <strong>without fail on Friday morning</strong>. All other bins stay in the internal car park.</p>
    </div>
    <div class="it"><p style="font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--sun);margin-bottom:12px;">Calendario di raccolta</p></div>
    <div class="en"><p style="font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--sun);margin-bottom:12px;">Collection schedule</p></div>
    <div class="waste-grid">
      <div class="waste-card plastica"><p class="waste-day it">Sabato</p><p class="waste-day en">Saturday</p><p class="waste-type it">♻️ Plastica</p><p class="waste-type en">♻️ Plastic</p><p class="waste-container it">Contenitore BLU · sacchi semitrasparenti</p><p class="waste-container en">BLUE bin · semi-transparent bags</p></div>
      <div class="waste-card carta"><p class="waste-day it">Giovedì</p><p class="waste-day en">Thursday</p><p class="waste-type it">📄 Carta e Cartone</p><p class="waste-type en">📄 Paper & Cardboard</p><p class="waste-container it">Contenitore GIALLO · cartoni piegati accanto al contenitore</p><p class="waste-container en">YELLOW bin · flatten cardboard next to bin</p></div>
      <div class="waste-card vetro"><p class="waste-day it">Mercoledì</p><p class="waste-day en">Wednesday</p><p class="waste-type it">🍾 Vetro, Latta & Lattine</p><p class="waste-type en">🍾 Glass, Tins & Cans</p><p class="waste-container it">Contenitore VERDE · risciacquare bottiglie e barattoli</p><p class="waste-container en">GREEN bin · rinse bottles and jars</p></div>
      <div class="waste-card secco"><p class="waste-day it">Martedì · esporre giovedì sera</p><p class="waste-day en">Tuesday · put out Thursday evening</p><p class="waste-type it">🗑️ Secco Indifferenziato</p><p class="waste-type en">🗑️ General Waste</p><p class="waste-container it">Contenitore GRIGIO · unico da esporre in strada</p><p class="waste-container en">GREY bin · only bin placed on road</p></div>
      <div class="waste-card organico" style="grid-column:span 2"><p class="waste-day it">Lunedì · Mercoledì · Venerdì</p><p class="waste-day en">Monday · Wednesday · Friday</p><p class="waste-type it">🍌 Umido Organico</p><p class="waste-type en">🍌 Organic Waste</p><p class="waste-container it">Contenitore MARRONE · sacchetti biodegradabili obbligatori</p><p class="waste-container en">BROWN bin · biodegradable bags required</p></div>
    </div>
  </section>

  <section id="condividi">
    <p class="section-label it">Condividi</p><p class="section-label en">Share</p>
    <h2 class="section-title it">Condividi questa Guida</h2><h2 class="section-title en">Share this Guide</h2>
    <div class="qr-section">
      <h3 class="it">📲 Invia agli ospiti</h3><h3 class="en">📲 Send to guests</h3>
      <p class="it">Scansiona il QR code o copia il link qui sotto</p><p class="en">Scan the QR code or copy the link below</p>
      <div id="qrcode"></div>
      <p class="qr-url" id="page-url"></p>
      <button class="copy-link-btn" onclick="copyPageLink()"><span class="it">🔗 Copia link</span><span class="en">🔗 Copy link</span></button>
    </div>
    <div class="card">
      <span class="card-icon">💡</span>
      <h3 class="it">Come condividere</h3><h3 class="en">How to share</h3>
      <ul>
        <li class="it">📱 Invia il link via <strong>WhatsApp</strong> o <strong>email</strong> agli ospiti prima dell'arrivo</li>
        <li class="en">📱 Send the link via <strong>WhatsApp</strong> or <strong>email</strong> to guests before arrival</li>
        <li class="it">🖨️ Stampa il <strong>QR code</strong> e appendilo in casa</li>
        <li class="en">🖨️ Print the <strong>QR code</strong> and display it in the apartment</li>
        <li class="it">📋 Inserisci il link nel messaggio di conferma su Airbnb o Booking</li>
        <li class="en">📋 Add the link to your booking confirmation on Airbnb or Booking</li>
      </ul>
    </div>
  </section>

  <section id="contatti">
    <p class="section-label it">Aiuto</p><p class="section-label en">Help</p>
    <h2 class="section-title it">Contatti</h2><h2 class="section-title en">Contacts</h2>
    <div class="card">
      <span class="card-icon">💬</span>
      <h3 class="it">Sempre disponibile</h3><h3 class="en">Always available</h3>
      <p class="it">Per qualsiasi necessità durante il tuo soggiorno, contattami via WhatsApp o telefono. Rispondo di solito nel giro di pochi minuti.</p>
      <p class="en">For anything you need during your stay, contact me via WhatsApp or phone. I usually reply within a few minutes.</p>
    </div>
    <div class="contact-bar">
      <div><p class="contact-text">Ignazio</p><p class="contact-number">📱 +39 327 095 7224</p></div>
      <a href="https://wa.me/393270957224" class="contact-btn">WhatsApp</a>
    </div>
    <div class="card" style="margin-top:14px">
      <span class="card-icon">🚨</span>
      <h3 class="it">Numeri di emergenza</h3><h3 class="en">Emergency numbers</h3>
      <ul>
        <li><strong>112</strong> — <span class="it">Emergenze generali / Carabinieri</span><span class="en">General emergencies / Police</span></li>
        <li><strong>118</strong> — <span class="it">Pronto soccorso</span><span class="en">Ambulance</span></li>
        <li><strong>115</strong> — <span class="it">Vigili del fuoco</span><span class="en">Fire brigade</span></li>
        <li><strong>113</strong> — <span class="it">Polizia di Stato</span><span class="en">State Police</span></li>
      </ul>
    </div>
  </section>

</main>
<footer>
  <span class="it">© Casa del Sole · Cagliari · Buona vacanza! ☀️</span>
  <span class="en">© Casa del Sole · Cagliari · Enjoy your stay! ☀️</span>
</footer>
<script>
  function setLang(lang){document.body.className='lang-'+lang;document.querySelectorAll('.lang-btn').forEach(b=>b.classList.remove('active'));document.querySelector('.lang-btn[onclick="setLang(\''+lang+'\')"]').classList.add('active');document.documentElement.lang=lang;}
  function copyWifi(){const pass=document.getElementById('wifi-pass').textContent;navigator.clipboard.writeText(pass).then(()=>{const btn=document.querySelector('.wifi-copy-btn');const orig=btn.innerHTML;btn.textContent='✅ OK!';setTimeout(()=>btn.innerHTML=orig,2000);});}
  function copyPageLink(){navigator.clipboard.writeText(window.location.href).then(()=>{const btn=document.querySelector('.copy-link-btn');const orig=btn.innerHTML;btn.innerHTML='✅ Copiato!';setTimeout(()=>btn.innerHTML=orig,2000);});}
  window.addEventListener('load',function(){const url=window.location.href;document.getElementById('page-url').textContent=url;new QRCode(document.getElementById('qrcode'),{text:url,width:180,height:180,colorDark:'#1C1A14',colorLight:'#ffffff',correctLevel:QRCode.CorrectLevel.M});});
  document.querySelectorAll('nav a').forEach(a=>{a.addEventListener('click',e=>{e.preventDefault();const t=document.querySelector(a.getAttribute('href'));if(t)t.scrollIntoView({behavior:'smooth'});});});
</script>
</body>
</html>
