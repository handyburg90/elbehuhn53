<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Elbehuhn 53 — Bestellung</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Archivo:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  /* ========== الأنماط الأساسية (كما هي مع تعديلات بسيطة) ========== */
  :root{
    --char:#1c1410;
    --char-2:#241a14;
    --flame:#e25822;
    --flame-2:#ff6b35;
    --turmeric:#f4b400;
    --turmeric-2:#ffd166;
    --poultry-red:#b3261a;
    --cream:#fbf2e3;
    --cream-dim:#d8c9ad;
    --line: rgba(244,180,0,0.22);
    --green: #6b8f3e;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--char);
    color:var(--cream);
    font-family:'Archivo', sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;text-decoration:none;}
  body::before{
    content:"";
    position:fixed;
    inset:0;
    background-image: radial-gradient(circle at 15% 8%, rgba(226,88,34,0.10), transparent 45%), radial-gradient(circle at 90% 75%, rgba(244,180,0,0.07), transparent 50%);
    pointer-events:none;
    z-index:0;
  }

  /* HEADER */
  header{
    position:relative;
    padding:40px 24px 32px;
    text-align:center;
    border-bottom:1px solid var(--line);
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:8px;
  }
  .header-top{
    display:flex;
    align-items:center;
    justify-content:center;
    gap:24px;
    flex-wrap:wrap;
  }
  .logo-img img{
    width:85px;height:85px;
    border-radius:50%;
    object-fit:cover;
    border:2px solid var(--turmeric);
    background:var(--char-2);
  }
  .eyebrow{
    font-family:'DM Mono', monospace;
    font-size:12px;
    letter-spacing:0.32em;
    text-transform:uppercase;
    color:var(--turmeric);
    display:inline-flex;
    align-items:center;
    gap:10px;
  }
  .eyebrow .dot{width:6px;height:6px;border-radius:50%;background:var(--flame-2);display:inline-block;}
  h1.brand{
    font-family:'Archivo Black', sans-serif;
    font-size:clamp(46px, 12vw, 110px);
    line-height:0.88;
    letter-spacing:-0.01em;
    color:var(--cream);
    text-transform:uppercase;
  }
  h1.brand .num{ color:var(--flame-2); -webkit-text-stroke: 2px var(--turmeric); }
  .tagline-row{
    margin-top:14px;
    display:flex;
    justify-content:center;
    gap:18px;
    flex-wrap:wrap;
    font-family:'DM Mono', monospace;
    font-size:13px;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--cream-dim);
  }
  .tagline-row span{position:relative; padding:0 18px;}
  .tagline-row span:not(:last-child)::after{ content:"·"; position:absolute; right:-2px; color:var(--flame); }
  .addr-bar{
    margin-top:18px;
    display:inline-flex;
    flex-wrap:wrap;
    gap:14px 28px;
    justify-content:center;
    font-size:14px;
    color:var(--cream-dim);
  }
  .addr-bar strong{color:var(--cream); font-weight:600;}

  /* HERO */
  .hero-banner{
    max-width:1100px;
    margin:20px auto 0;
    padding:0 24px;
  }
  .hero-banner img{
    width:100%;
    height:auto;
    max-height:380px;
    object-fit:cover;
    border-radius:24px;
    border:1px solid var(--line);
    background:var(--char-2);
    display:block;
  }

  /* SPIT */
  .spit{
    position:relative;
    height:34px;
    margin:0 auto;
    max-width:1100px;
    display:flex;
    align-items:center;
  }
  .spit::before{
    content:"";
    position:absolute;
    left:0; right:0; top:50%;
    height:3px;
    transform:translateY(-50%);
    background:linear-gradient(90deg, transparent, var(--turmeric) 8%, var(--turmeric) 92%, transparent);
    opacity:0.55;
  }
  .spit .skewer-cap{
    position:absolute;
    width:10px;height:10px;border-radius:50%;
    background:var(--cream-dim);
    top:50%;transform:translateY(-50%);
  }
  .spit .skewer-cap.left{left:-2px;}
  .spit .skewer-cap.right{right:-2px;}
  .spit-meats{
    position:relative;
    display:flex;
    width:100%;
    justify-content:space-evenly;
    z-index:1;
  }
  .meat{
    width:26px;height:26px;
    border-radius:46% 54% 50% 50%/55% 50% 50% 45%;
    background: linear-gradient(155deg, var(--flame-2), var(--poultry-red) 60%, #7a160e);
    box-shadow: inset -3px -3px 6px rgba(0,0,0,0.35), inset 2px 2px 4px rgba(255,209,102,0.25);
  }
  .meat:nth-child(3n){background: linear-gradient(155deg, var(--turmeric-2), var(--turmeric) 55%, #b9810a);}
  .meat:nth-child(4n+1){width:20px;height:20px;}

  /* NAV */
  nav{
    position:sticky;
    top:0;
    z-index:30;
    background:rgba(28,20,16,0.92);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line);
    overflow-x:auto;
    white-space:nowrap;
    scrollbar-width:none;
  }
  nav::-webkit-scrollbar{display:none;}
  nav .inner{
    display:inline-flex;
    gap:6px;
    padding:14px 20px;
  }
  nav a{
    font-family:'DM Mono', monospace;
    font-size:12px;
    letter-spacing:0.06em;
    text-transform:uppercase;
    color:var(--cream-dim);
    padding:8px 14px;
    border-radius:999px;
    border:1px solid transparent;
    transition: color .2s, border-color .2s, background .2s;
  }
  nav a:hover, nav a:focus-visible{
    color:var(--turmeric-2);
    border-color:var(--line);
    background:rgba(244,180,0,0.06);
    outline:none;
  }

  /* MAIN */
  main{
    position:relative;
    z-index:1;
    max-width:1100px;
    margin:0 auto;
    padding:48px 24px 40px;
  }
  section{margin-bottom:68px; scroll-margin-top:64px;}

  .section-head{
    display:flex;
    align-items:center;
    gap:18px;
    margin-bottom:28px;
    flex-wrap:wrap;
  }
  .section-num{
    font-family:'DM Mono', monospace;
    font-size:14px;
    color:var(--flame-2);
    letter-spacing:0.1em;
  }
  .section-head h2{
    font-family:'Archivo Black', sans-serif;
    font-size:clamp(28px, 4.5vw, 42px);
    text-transform:uppercase;
    color:var(--cream);
    letter-spacing:-0.01em;
  }
  .section-sub{
    font-size:14px;
    color:var(--cream-dim);
    font-style:italic;
    flex-basis:100%;
  }
  .section-icon{
    width:48px;height:48px;
    border-radius:50%;
    overflow:hidden;
    border:1px solid var(--line);
    flex-shrink:0;
    background:var(--char-2);
  }
  .section-icon img{
    width:100%;height:100%;
    object-fit:cover;
    display:block;
  }

  /* MENU GRID */
  .menu-grid{
    display:grid;
    grid-template-columns:repeat(2, 1fr);
    gap:0;
    border-top:1px solid var(--line);
  }
  @media (max-width:720px){ .menu-grid{grid-template-columns:1fr;} }

  .item{
    padding:16px 18px;
    border-bottom:1px solid var(--line);
    display:flex;
    align-items:center;
    gap:16px;
    position:relative;
  }
  .menu-grid .item:nth-child(odd){border-right:1px solid var(--line);}
  @media (max-width:720px){ .menu-grid .item:nth-child(odd){border-right:none;} }

  .item-img{
    width:72px;height:72px;
    flex-shrink:0;
    border-radius:14px;
    overflow:hidden;
    border:1px solid var(--line);
    background:var(--char-2);
  }
  .item-img img{
    width:100%;height:100%;
    object-fit:cover;
    display:block;
  }

  .item-content{
    flex:1;
    display:flex;
    flex-direction:column;
    gap:4px;
    min-width:0;
  }

  .item-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
  }
  .item-name{
    font-weight:700;
    font-size:16px;
    color:var(--cream);
    line-height:1.3;
  }
  .item-name .badge-num{
    color:var(--turmeric);
    font-family:'DM Mono', monospace;
    font-weight:500;
    font-size:13px;
    margin-right:6px;
  }
  .item-price{
    font-family:'DM Mono', monospace;
    font-size:15px;
    font-weight:500;
    color:var(--flame-2);
    white-space:nowrap;
  }
  .item-price .price-alt{
    display:block;
    font-size:12px;
    color:var(--cream-dim);
    text-align:right;
  }
  .item-desc{
    font-size:13px;
    color:var(--cream-dim);
    line-height:1.5;
  }
  .item-tags{
    font-family:'DM Mono', monospace;
    font-size:10px;
    color:rgba(216,201,173,0.55);
    letter-spacing:0.04em;
  }

  /* ===== زر الإضافة ===== */
  .add-btn{
    background: var(--flame-2);
    color: var(--char);
    border: none;
    border-radius: 50%;
    width: 34px;
    height: 34px;
    font-size: 22px;
    font-weight: 700;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: 0.2s;
    flex-shrink: 0;
    line-height: 1;
    box-shadow: 0 2px 8px rgba(226, 88, 34, 0.4);
  }
  .add-btn:hover{
    transform: scale(1.1);
    background: var(--turmeric-2);
  }
  .add-btn:active{ transform: scale(0.95); }

  /* DRINKS */
  .drinks-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(220px, 1fr));
    gap:14px;
    border-top:none;
  }
  .drink-card{
    background:var(--char-2);
    border:1px solid var(--line);
    border-radius:14px;
    padding:14px 18px;
    display:flex;
    align-items:center;
    gap:14px;
  }
  .drink-card .item-name{font-size:15px;}
  .drink-card .item-price{font-size:14px;}
  .drink-card .item-img{
    width:48px;height:48px;
    border-radius:50%;
  }
  .drink-card .add-btn{
    width: 30px;
    height: 30px;
    font-size: 18px;
  }

  /* WEEKEND */
  .weekend-banner{
    margin-top:46px;
    border:1px solid var(--line);
    border-radius:18px;
    background:linear-gradient(135deg, rgba(226,88,34,0.14), rgba(244,180,0,0.08));
    padding:34px 30px;
    text-align:center;
  }
  .weekend-banner .eyebrow{justify-content:center; width:100%;}
  .weekend-banner h3{
    font-family:'Archivo Black', sans-serif;
    font-size:clamp(24px, 4vw, 34px);
    text-transform:uppercase;
    margin-top:10px;
    color:var(--turmeric-2);
  }
  .weekend-banner p{
    margin-top:8px;
    color:var(--cream-dim);
    font-size:14px;
  }

  /* ===== سلة التسوق (Floating Cart) ===== */
  .cart-toggle{
    position: fixed;
    bottom: 28px;
    right: 28px;
    background: var(--flame-2);
    color: var(--char);
    border: none;
    border-radius: 60px;
    padding: 14px 24px;
    font-family: 'Archivo', sans-serif;
    font-weight: 700;
    font-size: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
    cursor: pointer;
    box-shadow: 0 6px 24px rgba(226, 88, 34, 0.5);
    z-index: 100;
    transition: 0.2s;
    border: 1px solid rgba(255,255,255,0.1);
  }
  .cart-toggle:hover{ transform: scale(1.05); background: var(--turmeric-2); }
  .cart-toggle .badge{
    background: var(--char);
    color: var(--cream);
    border-radius: 50%;
    padding: 2px 10px;
    font-size: 14px;
  }

  /* السلة الجانبية */
  .cart-sidebar{
    position: fixed;
    top: 0;
    right: -480px;
    width: 440px;
    max-width: 92vw;
    height: 100%;
    background: var(--char-2);
    border-left: 2px solid var(--line);
    z-index: 200;
    padding: 28px 24px;
    transition: right 0.35s cubic-bezier(0.22, 1, 0.36, 1);
    display: flex;
    flex-direction: column;
    box-shadow: -8px 0 40px rgba(0,0,0,0.7);
    overflow-y: auto;
  }
  .cart-sidebar.open{ right: 0; }

  .cart-sidebar .close-btn{
    background: none;
    border: none;
    color: var(--cream-dim);
    font-size: 32px;
    cursor: pointer;
    align-self: flex-end;
    transition: 0.2s;
  }
  .cart-sidebar .close-btn:hover{ color: var(--flame-2); transform: rotate(90deg); }

  .cart-sidebar h3{
    font-family: 'Archivo Black', sans-serif;
    font-size: 28px;
    margin: 8px 0 24px;
    color: var(--turmeric-2);
  }

  .cart-items-list{
    flex: 1;
    overflow-y: auto;
    padding-right: 6px;
  }
  .cart-item{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px 0;
    border-bottom: 1px solid var(--line);
  }
  .cart-item .name{ font-weight: 500; }
  .cart-item .qty-control{
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .cart-item .qty-control button{
    background: var(--char);
    color: var(--cream);
    border: 1px solid var(--line);
    border-radius: 50%;
    width: 28px; height: 28px;
    cursor: pointer;
    font-weight: 700;
    transition: 0.2s;
  }
  .cart-item .qty-control button:hover{ background: var(--flame); color: #fff; }
  .cart-item .qty-control span{ min-width: 20px; text-align: center; font-weight: 600; }
  .cart-item .price{ color: var(--flame-2); font-family: 'DM Mono', monospace; }

  .cart-total{
    border-top: 2px solid var(--turmeric);
    padding: 20px 0 16px;
    display: flex;
    justify-content: space-between;
    font-size: 20px;
    font-weight: 700;
    color: var(--cream);
  }
  .cart-total span:last-child{ color: var(--turmeric-2); }

  .checkout-btn{
    background: var(--turmeric);
    color: var(--char);
    border: none;
    padding: 16px;
    border-radius: 60px;
    font-weight: 700;
    font-size: 18px;
    cursor: pointer;
    width: 100%;
    transition: 0.2s;
    margin-top: 8px;
    font-family: 'Archivo', sans-serif;
  }
  .checkout-btn:hover{ background: var(--turmeric-2); transform: scale(1.02); }
  .empty-cart-msg{
    color: var(--cream-dim);
    text-align: center;
    margin-top: 60px;
    font-size: 18px;
  }

  /* FOOTER */
  footer{
    border-top:1px solid var(--line);
    padding:48px 24px 64px;
    position:relative;
    z-index:1;
  }
  .footer-inner{
    max-width:1100px;
    margin:0 auto;
    display:grid;
    grid-template-columns:1.1fr 1fr;
    gap:40px;
  }
  @media (max-width:760px){ .footer-inner{grid-template-columns:1fr;} }
  .footer-block h4{
    font-family:'DM Mono', monospace;
    font-size:12px;
    letter-spacing:0.18em;
    text-transform:uppercase;
    color:var(--turmeric);
    margin-bottom:14px;
  }
  .allergen-list{
    font-size:12.5px;
    color:var(--cream-dim);
    line-height:1.9;
  }
  .allergen-list .row{display:flex; gap:8px;}
  .allergen-list .key{
    font-family:'DM Mono', monospace;
    color:var(--flame-2);
    flex-shrink:0;
    width:1.4em;
  }
  .hours-table{font-size:14px;}
  .hours-table .row{
    display:flex;
    justify-content:space-between;
    padding:8px 0;
    border-bottom:1px dashed var(--line);
  }
  .hours-table .row:last-child{border-bottom:none;}
  .hours-table .day{color:var(--cream-dim);}
  .hours-table .time{font-family:'DM Mono', monospace; color:var(--cream);}
  .contact-row{
    margin-top:22px;
    display:flex;
    gap:14px;
    flex-wrap:wrap;
  }
  .contact-row a{
    border:1px solid var(--line);
    border-radius:999px;
    padding:10px 18px;
    font-size:13px;
    font-family:'DM Mono', monospace;
    display:inline-flex;
    align-items:center;
    gap:8px;
    transition: border-color .2s, color .2s;
  }
  .contact-row a:hover, .contact-row a:focus-visible{
    border-color:var(--turmeric);
    color:var(--turmeric-2);
    outline:none;
  }
  .delivery-row{
    margin-top:18px;
    display:flex;
    gap:10px;
    flex-wrap:wrap;
  }
  .delivery-row span{
    font-size:12px;
    font-family:'DM Mono', monospace;
    color:var(--cream-dim);
    border:1px solid var(--line);
    padding:6px 12px;
    border-radius:999px;
  }
  .fine-print{
    max-width:1100px;
    margin:40px auto 0;
    font-size:11px;
    color:rgba(216,201,173,0.45);
    text-align:center;
  }
  .skip-link{
    position:absolute;
    left:-9999px;
  }
  .skip-link:focus{
    left:16px;
    top:16px;
    background:var(--turmeric);
    color:var(--char);
    padding:10px 16px;
    border-radius:8px;
    z-index:100;
  }
</style>
</head>
<body>

<a class="skip-link" href="#main">Zum Inhalt springen</a>

<header>
  <div class="header-top">
    <div class="logo-img">
      <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='85' height='85'%3E%3Crect width='85' height='85' fill='%23241a14'/%3E%3Ccircle cx='42' cy='42' r='30' fill='%23e25822'/%3E%3Ctext x='18' y='50' font-family='sans-serif' font-size='28' fill='%23fff'%3E🐔%3C/text%3E%3C/svg%3E" alt="شعار المطعم">
    </div>
    <div>
      <span class="eyebrow"><span class="dot"></span>Otto-von-Guericke-Str. 53 · Magdeburg</span>
      <h1 class="brand">ELBE<span class="num">HUHN</span> 53</h1>
    </div>
  </div>
  <div class="tagline-row">
    <span>Knusprig</span>
    <span>Lecker</span>
    <span>Zum Reinbeißen</span>
  </div>
  <div class="addr-bar">
    <span><strong>Vorbestellung:</strong> 0176 411 32 807</span>
    <span><strong>Mo–Fr:</strong> 10:00–00:00</span>
    <span><strong>Sa–So:</strong> 10:00–02:00</span>
  </div>
</header>

<section class="hero-banner">
  <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='1100' height='380'%3E%3Crect width='1100' height='380' fill='%23241a14'/%3E%3Ctext x='380' y='190' font-family='sans-serif' font-size='38' fill='%23f4b400'%3E🍗 Grill &amp; Döner %3C/text%3E%3C/svg%3E" alt="صورة الأطباق الرئيسية">
</section>

<div class="spit">
  <span class="skewer-cap left"></span>
  <span class="skewer-cap right"></span>
  <div class="spit-meats">
    <div class="meat"></div><div class="meat"></div><div class="meat"></div><div class="meat"></div>
    <div class="meat"></div><div class="meat"></div><div class="meat"></div><div class="meat"></div>
    <div class="meat"></div><div class="meat"></div><div class="meat"></div><div class="meat"></div>
  </div>
</div>

<nav>
  <div class="inner">
    <a href="#spezialitaeten">Elbe-Spezialitäten</a>
    <a href="#schawarma">Schawarma</a>
    <a href="#haehnchen">Hähnchen</a>
    <a href="#verschiedenes">Verschiedene Gerichte</a>
    <a href="#scheiben">Scheiben Döner</a>
    <a href="#toschka">Toschka</a>
    <a href="#getraenke">Getränke</a>
  </div>
</nav>

<main id="main">

  <!-- ============================================================ -->
  <!-- 01 ELBE SPEZIALITÄTEN -->
  <!-- ============================================================ -->
  <section id="spezialitaeten">
    <div class="section-head">
      <span class="section-num">01</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥙%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Elbe&nbsp;Spezialitäten</h2>
      <span class="section-sub">nach Döner Kebab Art gewürzt</span>
    </div>
    <div class="menu-grid" data-section="spezialitaeten">
      <!-- 1 -->
      <div class="item" data-name="Elbe Kebab" data-price="7.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🌯%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">1</span>Elbe Kebab</span>
            <span class="item-price">7,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J,K</span>
        </div>
      </div>
      <!-- 2 -->
      <div class="item" data-name="Elbe Kebab Extra" data-price="7.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥩%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">2</span>Elbe Kebab Extra</span>
            <span class="item-price">7,50&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, extra Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J,K</span>
        </div>
      </div>
      <!-- 3 -->
      <div class="item" data-name="Elbe Kebab – Käse" data-price="7.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧀%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">3</span>Elbe Kebab – Käse</span>
            <span class="item-price">7,50&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, Fleisch, Schafskäse, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J,K</span>
        </div>
      </div>
      <!-- 4 -->
      <div class="item" data-name="Kinder Elbe Kebab" data-price="6.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👦%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">4</span>Kinder Elbe Kebab</span>
            <span class="item-price">6,50&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J,K</span>
        </div>
      </div>
      <!-- 5 -->
      <div class="item" data-name="Elbe Kebabteller" data-price="11.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">5</span>Elbe Kebabteller</span>
            <span class="item-price">11,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fleisch, Salat, Pommes &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
      <!-- 6 -->
      <div class="item" data-name="Elbe Kebabteller Extra" data-price="12.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">6</span>Elbe Kebabteller Extra</span>
            <span class="item-price">12,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Extra Fleisch, Salat, Pommes &amp; Soße</p>
          <span class="item-tags">A,F,G,I,J,4,7</span>
        </div>
      </div>
      <!-- 7 -->
      <div class="item" data-name="Elbe Vegetarisch" data-price="5.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥗%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">7</span>Elbe Vegetarisch</span>
            <span class="item-price">5,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, Salat &amp; Soße</p>
          <span class="item-tags">A,K</span>
        </div>
      </div>
      <!-- 8 -->
      <div class="item" data-name="Elbe Dürüm Kebab" data-price="8.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🌮%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">8</span>Elbe Dürüm Kebab</span>
            <span class="item-price">8,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Teig, Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
      <!-- 9 -->
      <div class="item" data-name="Mega Elbe Dürüm" data-price="8.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E💪%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">9</span>Mega Elbe Dürüm</span>
            <span class="item-price">8,50&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Teig, Extra Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
      <!-- 10 -->
      <div class="item" data-name="Lahmacun" data-price="9.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥙%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">10</span>Lahmacun</span>
            <span class="item-price">9,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Teig, Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
      <!-- 11 -->
      <div class="item" data-name="Gemischter Elbe Kebab" data-price="7.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍖%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">11</span>Gemischter Elbe Kebab</span>
            <span class="item-price">7,50&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fladenbrot, Fleisch, Hähnchen, Salat &amp; Soße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 12 -->
      <div class="item" data-name="Elbe Kebab Salat" data-price="9.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥬%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">12</span>Elbe Kebab Salat</span>
            <span class="item-price">9,00&nbsp;€</span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fleisch, Schafskäse, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
      <!-- 13 (سعران) نأخذ السعر الأول للتبسيط -->
      <div class="item" data-name="Elbe Kebab Box (Klein)" data-price="6.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E📦%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top">
            <span class="item-name"><span class="badge-num">13</span>Elbe Kebab Box</span>
            <span class="item-price">Klein 6,00&nbsp;€<span class="price-alt">Groß 7,00&nbsp;€</span></span>
            <button class="add-btn" aria-label="Add to cart">+</button>
          </div>
          <p class="item-desc">Fleisch, Salat &amp; Soße</p>
          <span class="item-tags">4,7,A,F,G,I,J</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 02 SCHAWARMA (مختصراً لتوفير المساحة ولكن بنفس الهيكل) -->
  <!-- ============================================================ -->
  <section id="schawarma">
    <div class="section-head">
      <span class="section-num">02</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🌯%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Schawarma</h2>
    </div>
    <div class="menu-grid" data-section="schawarma">
      <!-- 14 -->
      <div class="item" data-name="Schawarma Klassisch" data-price="5.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🌯%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">14</span>Schawarma Klassisch</span><span class="item-price">5,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Brot, Hähnchenfleisch, Saure Gurken &amp; Knoblauchsoße</p>
          <span class="item-tags">A</span>
        </div>
      </div>
      <!-- 14a -->
      <div class="item" data-name="Mini Schawarma" data-price="4.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👶%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">14a</span>Mini Schawarma</span><span class="item-price">4,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Brot, Hähnchenfleisch, Saure Gurken &amp; Knoblauchsoße</p>
          <span class="item-tags">A</span>
        </div>
      </div>
      <!-- 15 -->
      <div class="item" data-name="Chicken Döner" data-price="7.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🐓%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">15</span>Chicken Döner</span><span class="item-price">7,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Fladenbrot, Hähnchenfleisch, Salat, Kräutersoße &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 16 -->
      <div class="item" data-name="Arabische Schawarma" data-price="10.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🇸🇦%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">16</span>Arabische Schawarma</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, Saure Gurken, Brot, Pommes &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 17 -->
      <div class="item" data-name="Schawarma Teller" data-price="11.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">17</span>Schawarma Teller</span><span class="item-price">11,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, Pommes, Saure Gurken &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 18 -->
      <div class="item" data-name="Schawarma mit Käse" data-price="6.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧀%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">18</span>Schawarma mit Käse</span><span class="item-price">6,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Brot, Hähnchenfleisch, Schafskäse, Saure Gurken &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 19 -->
      <div class="item" data-name="Schawarma 4 Pers." data-price="28.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👨‍👩‍👧‍👦%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">19</span>Schawarma 4 Pers.</span><span class="item-price">28,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, Pommes, verschiedene Salate &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 20 -->
      <div class="item" data-name="Schawarma 2 Pers." data-price="15.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👫%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">20</span>Schawarma 2 Pers.</span><span class="item-price">15,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, Pommes, verschiedene Salate &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 21 -->
      <div class="item" data-name="Humus Schawarma" data-price="9.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🫘%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">21</span>Humus Schawarma</span><span class="item-price">9,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, verschiedene Salate &amp; Knoblauchsoße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
      <!-- 22 -->
      <div class="item" data-name="Fathat Schawarma" data-price="10.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍚%3C/text%3E%3C/svg%3E" alt=""></div>
        <div class="item-content">
          <div class="item-top"><span class="item-name"><span class="badge-num">22</span>Fathat Schawarma</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div>
          <p class="item-desc">Hähnchenfleisch, Reis &amp; Soße</p>
          <span class="item-tags">A,F,G,I,J</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 03 HÄHNCHEN (مختصر) -->
  <!-- ============================================================ -->
  <section id="haehnchen">
    <div class="section-head">
      <span class="section-num">03</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Hähnchen&nbsp;Gerichte</h2>
    </div>
    <div class="menu-grid" data-section="haehnchen">
      <div class="item" data-name="Gegrilltes Hähnchen (mit Beilage)" data-price="12.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">23</span>Gegrilltes Hähnchen</span><span class="item-price">12,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes, Salat &amp; Knoblauchsoße</p></div></div>
      <div class="item" data-name="Gegrilltes Hähnchen (ohne Beilage)" data-price="10.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">24</span>Gegrilltes Hähnchen</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Ohne Beilage</p></div></div>
      <div class="item" data-name="½ gegrilltes Hähnchen (mit Beilage)" data-price="7.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E½%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">25</span>½ gegrilltes Hähnchen</span><span class="item-price">7,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes, Salat &amp; Knoblauchsoße</p></div></div>
      <div class="item" data-name="½ gegrilltes Hähnchen (ohne Beilage)" data-price="5.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E½%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">26</span>½ gegrilltes Hähnchen</span><span class="item-price">5,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Ohne Beilage</p></div></div>
      <div class="item" data-name="Familien Fried Chicken" data-price="18.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👨‍👩‍👦%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">27</span>Familien Fried Chicken</span><span class="item-price">18,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes oder Reis, Salat &amp; Soße</p><span class="item-tags">4,A,C,G</span></div></div>
      <div class="item" data-name="Fried Chicken 4 Stk." data-price="9.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">28</span>Fried Chicken 4 Stk.</span><span class="item-price">9,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes, Salat &amp; Knoblauchsoße</p><span class="item-tags">4,A,C,G</span></div></div>
      <div class="item" data-name="Hähnchenschnitzel" data-price="10.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">29</span>Hähnchenschnitzel</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes oder Reis, Salat &amp; Soße</p><span class="item-tags">A,C,G,F,J</span></div></div>
      <div class="item" data-name="Crispy (3 Stk.)" data-price="8.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍔%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">30</span>Crispy</span><span class="item-price">3 Stk. 8,00&nbsp;€<span class="price-alt">5 Stk. 10,00&nbsp;€</span></span><button class="add-btn">+</button></div><p class="item-desc">mit Pommes oder Reis, Salat &amp; Soße</p><span class="item-tags">4,A,C,G</span></div></div>
      <div class="item" data-name="Crispy Sandwich" data-price="7.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥪%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">30a</span>Crispy Sandwich</span><span class="item-price">7,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">4,A,C,G</span></div></div>
      <div class="item" data-name="Chicken Nuggets 12 Stk." data-price="8.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">31</span>Chicken Nuggets 12 Stk.</span><span class="item-price">8,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,K</span></div></div>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 04 VERSCHIEDENES (مختصر) -->
  <!-- ============================================================ -->
  <section id="verschiedenes">
    <div class="section-head">
      <span class="section-num">04</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Verschiedene&nbsp;Gerichte</h2>
    </div>
    <div class="menu-grid" data-section="verschiedenes">
      <div class="item" data-name="Fladenbrot mit Soße" data-price="3.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍞%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">32</span>Fladenbrot mit Soße</span><span class="item-price">3,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A</span></div></div>
      <div class="item" data-name="Falafel Fladenbrot" data-price="5.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧆%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">33</span>Falafel Fladenbrot</span><span class="item-price">5,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Falafel, Fladenbrot, Salat &amp; Soße</p><span class="item-tags">A,K</span></div></div>
      <div class="item" data-name="Falafel Rolle" data-price="4.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧆%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">34</span>Falafel Rolle</span><span class="item-price">4,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Falafel, Brot, Salat &amp; Soße</p><span class="item-tags">A,K</span></div></div>
      <div class="item" data-name="Falafel Teller 6 Stk." data-price="6.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧆%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">35</span>Falafel Teller 6 Stk.</span><span class="item-price">6,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Falafel, Salat &amp; Soße</p><span class="item-tags">A,K</span></div></div>
      <div class="item" data-name="Humus Teller" data-price="3.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🫘%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">36</span>Humus Teller</span><span class="item-price">3,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,K</span></div></div>
      <div class="item" data-name="Döner Auflauf" data-price="10.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍲%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">37</span>Döner Auflauf</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Pommes, Dönerfleisch, Schafskäse &amp; Soße</p><span class="item-tags">4,A,F,I,J,G</span></div></div>
      <div class="item" data-name="Brokkoli Auflauf" data-price="10.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥦%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">38</span>Brokkoli Auflauf</span><span class="item-price">10,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Brokkoli, Käse &amp; Soße</p></div></div>
      <div class="item" data-name="Halloumi" data-price="5.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧀%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">39</span>Halloumi</span><span class="item-price">5,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,G</span></div></div>
      <div class="item" data-name="Halloumi Teller" data-price="9.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🧀%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">40</span>Halloumi Teller</span><span class="item-price">9,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">G</span></div></div>
      <div class="item" data-name="Hamburger" data-price="6.50"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍔%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">41</span>Hamburger</span><span class="item-price">6,50&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Fleisch, Brot, Salat &amp; Soße</p><span class="item-tags">2,6,A,I,J,K</span></div></div>
      <div class="item" data-name="Cheesburger" data-price="7.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍔%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">42</span>Cheesburger</span><span class="item-price">7,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Fleisch, Käse, Salat &amp; Soße</p><span class="item-tags">2,A,I,G,J,K</span></div></div>
      <div class="item" data-name="Lammhaxe mit Reis Mandy" data-price="15.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🐑%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">43</span>Lammhaxe mit Reis Mandy</span><span class="item-price">15,00&nbsp;€</span><button class="add-btn">+</button></div></div></div>
      <div class="item" data-name="Pommes (Klein)" data-price="4.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍟%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">44</span>Pommes</span><span class="item-price">Klein 4,00&nbsp;€<span class="price-alt">Groß 5,00&nbsp;€</span></span><button class="add-btn">+</button></div></div></div>
      <div class="item" data-name="Arabischer Salat" data-price="6.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">45</span>Arabischer Salat</span><span class="item-price">6,00&nbsp;€</span><button class="add-btn">+</button></div></div></div>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 05 SCHEIBEN (YAPRAK) DÖNER -->
  <!-- ============================================================ -->
  <section id="scheiben">
    <div class="section-head">
      <span class="section-num">05</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥩%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Scheiben&nbsp;(Yaprak)&nbsp;Döner</h2>
    </div>
    <div class="menu-grid" data-section="scheiben">
      <div class="item" data-name="Scheiben Döner" data-price="9.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥩%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">46</span>Scheiben Döner</span><span class="item-price">9,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,I,J</span></div></div>
      <div class="item" data-name="Scheiben Dürüm" data-price="7.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🌮%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">47</span>Scheiben Dürüm</span><span class="item-price">7,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,I,J</span></div></div>
      <div class="item" data-name="Mini Scheiben Dürüm" data-price="4.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E👶%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">47a</span>Mini Scheiben Dürüm</span><span class="item-price">4,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,I,J</span></div></div>
      <div class="item" data-name="Scheiben Dürüm mit Salat" data-price="9.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥗%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">47b</span>Scheiben Dürüm mit Salat</span><span class="item-price">9,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,I,J</span></div></div>
      <div class="item" data-name="Scheiben Teller" data-price="15.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">48</span>Scheiben Teller</span><span class="item-price">15,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">I,J</span></div></div>
      <div class="item" data-name="Arabische Scheiben Döner" data-price="12.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🇸🇦%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">49</span>Arabische Scheiben Döner</span><span class="item-price">12,00&nbsp;€</span><button class="add-btn">+</button></div><span class="item-tags">A,I,J</span></div></div>
    </div>
    <div class="weekend-banner">
      <span class="eyebrow"><span class="dot"></span>Nur bei Elbehuhn 53</span>
      <h3>Jedes Wochenende: Fr · Sa · So<br>Scheiben Döner statt „Elbe Kebab"</h3>
      <p>Freitag, Samstag &amp; Sonntag — frag einfach an der Theke danach.</p>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 06 TOSCHKA -->
  <!-- ============================================================ -->
  <section id="toschka">
    <div class="section-head">
      <span class="section-num">06</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🌯%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Toschka</h2>
    </div>
    <div class="menu-grid" data-section="toschka">
      <div class="item" data-name="Toschka Hähnchen" data-price="8.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🐓%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">55</span>Toschka Hähnchen</span><span class="item-price">8,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">Dürüm mit Fleisch, Käse, Mais &amp; Champignon</p></div></div>
      <div class="item" data-name="Toschka Normal Döner" data-price="8.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🥩%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">56</span>Toschka Normal Döner</span><span class="item-price">8,00&nbsp;€</span><button class="add-btn">+</button></div></div></div>
      <div class="item" data-name="Toschka Hähnchen Teller" data-price="13.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">57</span>Toschka Hähnchen Teller</span><span class="item-price">13,00&nbsp;€</span><button class="add-btn">+</button></div></div></div>
      <div class="item" data-name="Toschka Normal Döner Teller" data-price="13.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍽️%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">58</span>Toschka Normal Döner Teller</span><span class="item-price">13,00&nbsp;€</span><button class="add-btn">+</button></div></div></div>
      <div class="item" data-name="Toschka Menü" data-price="15.00"><div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='72' height='72'%3E%3Crect width='72' height='72' fill='%23241a14'/%3E%3Ctext x='12' y='44' font-size='30'%3E🍔%3C/text%3E%3C/svg%3E" alt=""></div><div class="item-content"><div class="item-top"><span class="item-name"><span class="badge-num">58</span>Toschka Menü</span><span class="item-price">15,00&nbsp;€</span><button class="add-btn">+</button></div><p class="item-desc">+ Cola &amp; Pommes</p></div></div>
    </div>
  </section>

  <!-- ============================================================ -->
  <!-- 07 GETRÄNKE -->
  <!-- ============================================================ -->
  <section id="getraenke">
    <div class="section-head">
      <span class="section-num">07</span>
      <div class="section-icon"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥤%3C/text%3E%3C/svg%3E" alt=""></div>
      <h2>Getränke</h2>
    </div>
    <div class="drinks-grid">
      <div class="drink-card" data-name="Cola (0.33l)" data-price="2.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥤%3C/text%3E%3C/svg%3E" alt=""></div>
        <span class="item-name"><span class="badge-num">50</span>Cola <span class="item-tags">(1)</span></span>
        <span class="item-price">0,33l 2,50&nbsp;€<span class="price-alt">1,5l 3,00&nbsp;€</span></span>
        <button class="add-btn" aria-label="Add to cart">+</button>
      </div>
      <div class="drink-card" data-name="Fritz (0.33l)" data-price="2.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥤%3C/text%3E%3C/svg%3E" alt=""></div>
        <span class="item-name"><span class="badge-num">51</span>Fritz</span>
        <span class="item-price">0,33l 2,50&nbsp;€</span>
        <button class="add-btn" aria-label="Add to cart">+</button>
      </div>
      <div class="drink-card" data-name="Mineralwasser" data-price="1.50">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E💧%3C/text%3E%3C/svg%3E" alt=""></div>
        <span class="item-name"><span class="badge-num">52</span>Mineralwasser</span>
        <span class="item-price">1,50&nbsp;€</span>
        <button class="add-btn" aria-label="Add to cart">+</button>
      </div>
      <div class="drink-card" data-name="Ayran" data-price="2.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E🥛%3C/text%3E%3C/svg%3E" alt=""></div>
        <span class="item-name"><span class="badge-num">53</span>Ayran <span class="item-tags">(G)</span></span>
        <span class="item-price">2,00&nbsp;€</span>
        <button class="add-btn" aria-label="Add to cart">+</button>
      </div>
      <div class="drink-card" data-name="Energy Drink" data-price="3.00">
        <div class="item-img"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='48' height='48'%3E%3Crect width='48' height='48' fill='%23241a14'/%3E%3Ctext x='8' y='32' font-size='28'%3E⚡%3C/text%3E%3C/svg%3E" alt=""></div>
        <span class="item-name"><span class="badge-num">54</span>Energy Drink</span>
        <span class="item-price">3,00&nbsp;€</span>
        <button class="add-btn" aria-label="Add to cart">+</button>
      </div>
    </div>
  </section>

</main>

<!-- ======== زر فتح السلة ======== -->
<button class="cart-toggle" id="cartToggle" aria-label="Open cart">
  🛒 سلة الطلب <span class="badge" id="cartCount">0</span>
</button>

<!-- ======== السلة الجانبية ======== -->
<div class="cart-sidebar" id="cartSidebar">
  <button class="close-btn" id="closeCart">✕</button>
  <h3>🛒 طلبك</h3>
  <div class="cart-items-list" id="cartItemsList">
    <div class="empty-cart-msg">السلة فارغة</div>
  </div>
  <div class="cart-total">
    <span>المجموع</span>
    <span id="cartTotalPrice">0.00 €</span>
  </div>
  <button class="checkout-btn" id="checkoutBtn">📲 إرسال الطلب عبر واتساب</button>
</div>

<footer>
  <div class="footer-inner">
    <div class="footer-block">
      <h4>Zusatzstoffe &amp; Allergene</h4>
      <div class="allergen-list">
        <div class="row"><span class="key">1</span><span>mit Coffein</span></div>
        <div class="row"><span class="key">2</span><span>mit Farbstoff</span></div>
        <div class="row"><span class="key">3</span><span>mit Süßungsmittel</span></div>
        <div class="row"><span class="key">4</span><span>mit Geschmacksverstärker</span></div>
        <div class="row"><span class="key">5</span><span>mit Antioxidationsmittel</span></div>
        <div class="row"><span class="key">6</span><span>mit Konservierungsstoff</span></div>
        <div class="row"><span class="key">7</span><span>mit Phosphat</span></div>
        <div class="row"><span class="key">A</span><span>Enthält glutenhaltiges Getreide (Weizen)</span></div>
        <div class="row"><span class="key">C</span><span>Enthält Eier und -erzeugnisse</span></div>
        <div class="row"><span class="key">D</span><span>Enthält Fisch und -erzeugnisse</span></div>
        <div class="row"><span class="key">F</span><span>Enthält Soja und -erzeugnisse</span></div>
        <div class="row"><span class="key">G</span><span>Enthält Milch und -erzeugnisse</span></div>
        <div class="row"><span class="key">H</span><span>Enthält Schalenfrüchte</span></div>
        <div class="row"><span class="key">H1</span><span>Enthält Mandeln</span></div>
        <div class="row"><span class="key">I</span><span>Enthält Sellerie und -erzeugnisse</span></div>
        <div class="row"><span class="key">J</span><span>Enthält Senf und -erzeugnisse</span></div>
        <div class="row"><span class="key">K</span><span>Enthält Sesam und -erzeugnisse</span></div>
      </div>
      <p style="margin-top:14px; font-size:12px; color:var(--cream-dim);">Kräuter- &amp; Knoblauchsoßen: C, G, J &nbsp;·&nbsp; Chilisoße: 3, 5, 6</p>
    </div>
    <div class="footer-block">
      <h4>Öffnungszeiten &amp; Kontakt</h4>
      <div class="hours-table">
        <div class="row"><span class="day">Montag – Freitag</span><span class="time">10:00 – 00:00</span></div>
        <div class="row"><span class="day">Samstag – Sonntag</span><span class="time">10:00 – 02:00</span></div>
      </div>
      <div class="contact-row"><a href="tel:+4917641132807">📞 0176 411 32 807</a></div>
      <p style="margin-top:18px; font-size:13px; color:var(--cream-dim);">Otto-von-Guericke-Str. 53 · 39104 Magdeburg</p>
      <div class="delivery-row">
        <span>Uber Eats</span><span>Lieferando</span><span>Instagram</span><span>Facebook</span><span>WhatsApp</span>
      </div>
    </div>
  </div>
  <p class="fine-print">Alle Preise verstehen sich in Euro (€) inkl. gesetzlicher MwSt. · Änderungen vorbehalten · Elbehuhn 53, Magdeburg</p>
</footer>

<script>
  // ============================================================
  //  جافا سكريبت السلة
  // ============================================================
  (function() {
    const STORAGE_KEY = 'elbehuhn_cart';
    let cart = JSON.parse(localStorage.getItem(STORAGE_KEY)) || [];

    // عناصر DOM
    const cartSidebar = document.getElementById('cartSidebar');
    const cartToggle = document.getElementById('cartToggle');
    const closeCart = document.getElementById('closeCart');
    const cartItemsList = document.getElementById('cartItemsList');
    const cartTotalPrice = document.getElementById('cartTotalPrice');
    const cartCount = document.getElementById('cartCount');
    const checkoutBtn = document.getElementById('checkoutBtn');

    // حفظ السلة
    function saveCart() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(cart));
    }

    // عرض السلة
    function renderCart() {
      const totalItems = cart.reduce((acc, item) => acc + item.qty, 0);
      cartCount.textContent = totalItems;

      if (cart.length === 0) {
        cartItemsList.innerHTML = '<div class="empty-cart-msg">🛒 السلة فارغة</div>';
        cartTotalPrice.textContent = '0.00 €';
        return;
      }

      let html = '';
      let total = 0;
      cart.forEach((item, index) => {
        const price = parseFloat(item.price);
        const subtotal = price * item.qty;
        total += subtotal;
        html += `
          <div class="cart-item">
            <span class="name">${item.name}</span>
            <div class="qty-control">
              <button data-index="${index}" data-action="decr">−</button>
              <span>${item.qty}</span>
              <button data-index="${index}" data-action="incr">+</button>
              <button data-index="${index}" data-action="remove" style="background:transparent; border:none; color:#b3261a; font-weight:bold; margin-left:4px;">✕</button>
            </div>
            <span class="price">${subtotal.toFixed(2)} €</span>
          </div>
        `;
      });

      cartItemsList.innerHTML = html;
      cartTotalPrice.textContent = total.toFixed(2) + ' €';

      // ربط أزرار التحكم
      document.querySelectorAll('.cart-item .qty-control button').forEach(btn => {
        btn.addEventListener('click', function(e) {
          e.stopPropagation();
          const index = parseInt(this.dataset.index);
          const action = this.dataset.action;
          if (isNaN(index)) return;

          if (action === 'incr') {
            cart[index].qty += 1;
          } else if (action === 'decr') {
            if (cart[index].qty > 1) {
              cart[index].qty -= 1;
            } else {
              cart.splice(index, 1);
            }
          } else if (action === 'remove') {
            cart.splice(index, 1);
          }
          saveCart();
          renderCart();
        });
      });
    }

    // إضافة إلى السلة
    function addToCart(name, price) {
      const existing = cart.find(item => item.name === name);
      if (existing) {
        existing.qty += 1;
      } else {
        cart.push({ name, price: parseFloat(price), qty: 1 });
      }
      saveCart();
      renderCart();
      // فتح السلة تلقائياً
      cartSidebar.classList.add('open');
    }

    // ربط أزرار الإضافة
    document.querySelectorAll('.add-btn').forEach(btn => {
      btn.addEventListener('click', function(e) {
        e.stopPropagation();
        // البحث عن العنصر الأب (item أو drink-card)
        let parent = this.closest('.item') || this.closest('.drink-card');
        if (!parent) return;

        let name = parent.dataset.name;
        let price = parent.dataset.price;

        // إذا لم يجد، حاول استخراجها من النص (كحل احتياطي)
        if (!name || !price) {
          const nameEl = parent.querySelector('.item-name');
          if (nameEl) name = nameEl.textContent.replace(/[0-9]+/g, '').trim();
          const priceEl = parent.querySelector('.item-price');
          if (priceEl) {
            const match = priceEl.textContent.match(/(\d+[,.]\d+)/);
            if (match) price = match[0].replace(',', '.');
          }
        }

        if (name && price) {
          addToCart(name, price);
        } else {
          alert('لم نتمكن من إضافة هذا العنصر، تأكد من البيانات.');
        }
      });
    });

    // فتح / إغلاق السلة
    cartToggle.addEventListener('click', () => {
      cartSidebar.classList.toggle('open');
    });
    closeCart.addEventListener('click', () => {
      cartSidebar.classList.remove('open');
    });
    // إغلاق عند النقر خارجها
    document.addEventListener('click', function(e) {
      if (cartSidebar.classList.contains('open') && !cartSidebar.contains(e.target) && !cartToggle.contains(e.target)) {
        cartSidebar.classList.remove('open');
      }
    });

    // إرسال الطلب عبر واتساب
    checkoutBtn.addEventListener('click', function() {
      if (cart.length === 0) {
        alert('السلة فارغة! أضف بعض الأطباق أولاً.');
        return;
      }

      let message = '🍗 *طلب جديد من Elbehuhn 53* 🍗\n\n';
      let total = 0;
      cart.forEach(item => {
        const subtotal = item.price * item.qty;
        total += subtotal;
        message += `• ${item.name} × ${item.qty} = ${subtotal.toFixed(2)} €\n`;
      });
      message += `\n💰 *المجموع الكلي: ${total.toFixed(2)} €*`;
      message += '\n\n📞 الرجاء التأكيد عبر الرد على هذه الرسالة.';

      // الرقم: 0176 411 32 807 -> الدولي: 4917641132807
      const phone = '4917641132807';
      const url = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`;

      window.open(url, '_blank');
    });

    // التهيئة
    renderCart();
  })();
</script>

</body>
</html>
