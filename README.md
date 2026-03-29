<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>American Pie Pizza | אמריקאן פאי פיצה</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Oswald:wght@300;400;600;700&family=Heebo:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #080700;
    --deep: #0f0e09;
    --card: #161408;
    --border: #2e2a14;
    --red: #c9a84c;
    --red-hot: #e2bf6a;
    --red-glow: rgba(201,168,76,0.18);
    --cream: #f7f0d8;
    --gold: #c9a84c;
    --text: #ede4c4;
    --muted: #8a7d50;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--text);
    font-family: 'Heebo', sans-serif;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    background: rgba(10,10,10,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 2.5rem;
    height: 64px;
  }
  .nav-logo { font-family: 'Bebas Neue', sans-serif; font-size: 1.6rem; color: var(--red); letter-spacing: 2px; }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    color: var(--muted); text-decoration: none; font-size: 0.85rem;
    font-weight: 500; letter-spacing: 1px; text-transform: uppercase;
    transition: color .2s;
  }
  .nav-links a:hover { color: var(--red); }
  .nav-phone {
    font-family: 'Bebas Neue', sans-serif; font-size: 1.2rem;
    color: var(--cream); letter-spacing: 1px;
  }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    position: relative; text-align: center; padding: 6rem 2rem 4rem;
    background:
      radial-gradient(ellipse 80% 60% at 50% 80%, rgba(200,16,46,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 60% 40% at 50% 100%, rgba(200,16,46,0.08) 0%, transparent 60%),
      var(--black);
    overflow: hidden;
  }
  .hero::before {
    content: '🍕';
    position: absolute; font-size: 22rem; opacity: 0.04;
    top: 50%; left: 50%; transform: translate(-50%,-50%) rotate(-20deg);
    pointer-events: none;
  }

  .hero-badge {
    display: inline-block;
    background: var(--red);
    color: #080700; font-size: 0.7rem; font-weight: 700;
    letter-spacing: 3px; text-transform: uppercase;
    padding: 0.3rem 1.2rem; border-radius: 2px;
    margin-bottom: 1.5rem;
    animation: fadeDown .6s ease both;
  }

  .hero-logo-img {
    width: 200px; margin: 0 auto 1.5rem;
    filter: brightness(0) invert(1);
    animation: fadeDown .7s ease both .1s;
    opacity: 0;
  }

  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3.5rem, 9vw, 7rem);
    line-height: 1; color: var(--cream);
    letter-spacing: 4px;
    animation: fadeDown .7s ease both .2s; opacity: 0;
  }
  .hero h1 span { color: var(--red); }

  .hero-sub {
    margin-top: 1.2rem; font-size: 1rem; color: var(--muted);
    letter-spacing: 2px; text-transform: uppercase;
    animation: fadeDown .7s ease both .35s; opacity: 0;
  }

  .hero-ctas {
    display: flex; gap: 1rem; margin-top: 2.5rem; flex-wrap: wrap; justify-content: center;
    animation: fadeDown .7s ease both .5s; opacity: 0;
  }
  .btn-primary {
    background: var(--red); color: #080700;
    border: none; padding: 0.9rem 2.2rem;
    font-family: 'Bebas Neue', sans-serif; font-size: 1.1rem; letter-spacing: 2px;
    cursor: pointer; text-decoration: none; border-radius: 2px;
    transition: background .2s, transform .15s;
  }
  .btn-primary:hover { background: var(--red-hot); transform: translateY(-2px); }
  .btn-outline {
    background: transparent; color: var(--cream);
    border: 1px solid var(--border); padding: 0.9rem 2.2rem;
    font-family: 'Bebas Neue', sans-serif; font-size: 1.1rem; letter-spacing: 2px;
    cursor: pointer; text-decoration: none; border-radius: 2px;
    transition: border-color .2s, color .2s, transform .15s;
  }
  .btn-outline:hover { border-color: var(--red); color: var(--red); transform: translateY(-2px); }

  .hero-scroll {
    position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%);
    color: var(--muted); font-size: 0.75rem; letter-spacing: 2px;
    text-transform: uppercase; animation: bounce 2s infinite;
  }

  /* ── SECTION HEADERS ── */
  section { padding: 5rem 2rem; }
  .section-tag {
    display: block; font-size: 0.7rem; font-weight: 700; letter-spacing: 4px;
    text-transform: uppercase; color: var(--red); margin-bottom: 0.8rem;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif; font-size: clamp(2.5rem, 5vw, 4rem);
    color: var(--cream); letter-spacing: 3px; line-height: 1;
  }
  .section-header { text-align: center; margin-bottom: 3.5rem; }
  .divider {
    width: 60px; height: 3px; background: var(--red);
    margin: 1rem auto 0;
  }

  /* ── DEALS / SPECIALS ── */
  .specials { background: var(--deep); }
  .deals-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem; max-width: 1100px; margin: 0 auto;
  }
  .deal-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 4px; padding: 2rem;
    position: relative; overflow: hidden;
    transition: border-color .2s, transform .2s;
  }
  .deal-card:hover { border-color: var(--red); transform: translateY(-3px); }
  .deal-card::before {
    content: ''; position: absolute; top: 0; right: 0;
    width: 4px; height: 100%; background: var(--red);
  }
  .deal-emoji { font-size: 2rem; margin-bottom: 0.8rem; display: block; }
  .deal-title {
    font-family: 'Oswald', sans-serif; font-size: 1.3rem;
    color: var(--cream); font-weight: 600; margin-bottom: 0.5rem;
  }
  .deal-desc { font-size: 0.85rem; color: var(--muted); line-height: 1.6; }
  .deal-price {
    font-family: 'Bebas Neue', sans-serif; font-size: 2rem;
    color: var(--red); margin-top: 1rem; display: block;
  }

  /* ── MENU ── */
  .menu { background: var(--black); }
  .menu-tabs {
    display: flex; gap: 0.5rem; justify-content: center; flex-wrap: wrap;
    margin-bottom: 3rem;
  }
  .tab-btn {
    background: var(--card); border: 1px solid var(--border);
    color: var(--muted); padding: 0.6rem 1.4rem;
    font-family: 'Heebo', sans-serif; font-size: 0.85rem; font-weight: 500;
    cursor: pointer; border-radius: 2px; transition: all .2s;
  }
  .tab-btn.active, .tab-btn:hover {
    background: var(--red); border-color: var(--red); color: #080700;
  }
  .menu-panel { display: none; max-width: 1100px; margin: 0 auto; }
  .menu-panel.active { display: block; }
  .menu-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1px; background: var(--border);
  }
  .menu-item {
    background: var(--card); padding: 1.4rem 1.6rem;
    display: flex; justify-content: space-between; align-items: flex-start;
    gap: 1rem; transition: background .2s;
  }
  .menu-item:hover { background: #1e1e1e; }
  .item-info { flex: 1; }
  .item-name {
    font-size: 0.95rem; font-weight: 600; color: var(--cream);
    margin-bottom: 0.3rem;
  }
  .item-desc { font-size: 0.8rem; color: var(--muted); line-height: 1.5; }
  .item-price {
    font-family: 'Bebas Neue', sans-serif; font-size: 1.3rem;
    color: var(--red); white-space: nowrap; padding-top: 2px;
  }

  /* ── GALLERY ── */
  .gallery { background: var(--deep); }
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: auto;
    gap: 0.75rem; max-width: 1100px; margin: 0 auto;
  }
  .gallery-item {
    border-radius: 3px; overflow: hidden; position: relative;
    background: var(--card); min-height: 200px;
    display: flex; align-items: center; justify-content: center;
    font-size: 4rem;
    transition: transform .25s;
  }
  .gallery-item:hover { transform: scale(1.02); }
  .gallery-item:nth-child(1) { grid-column: span 3; grid-row: span 2; min-height: 380px; }
  .gallery-item:nth-child(2) { grid-column: span 2; }
  .gallery-item:nth-child(3) { grid-column: span 1; }
  .gallery-item:nth-child(4) { grid-column: span 1; }
  .gallery-item:nth-child(5) { grid-column: span 2; }
  .gallery-item:nth-child(6) { grid-column: span 3; }
  .gallery-label {
    position: absolute; bottom: 0; right: 0; left: 0;
    padding: 1rem; background: linear-gradient(transparent, rgba(0,0,0,0.85));
    font-size: 0.85rem; font-weight: 600; color: var(--cream); text-align: center;
  }

  /* ── HOURS ── */
  .hours-section { background: var(--black); }
  .hours-container {
    max-width: 1000px; margin: 0 auto;
    display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 2rem;
  }
  .hours-block {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 4px; padding: 2rem; position: relative; overflow: hidden;
  }
  .hours-block::after {
    content: ''; position: absolute; bottom: 0; right: 0; left: 0;
    height: 3px; background: var(--red);
  }
  .hours-block h3 {
    font-family: 'Bebas Neue', sans-serif; font-size: 1.4rem;
    color: var(--cream); margin-bottom: 1.2rem; letter-spacing: 2px;
  }
  .hours-row {
    display: flex; justify-content: space-between;
    padding: 0.45rem 0; border-bottom: 1px solid var(--border);
    font-size: 0.85rem;
  }
  .hours-row:last-child { border-bottom: none; }
  .hours-day { color: var(--muted); }
  .hours-time { color: var(--cream); font-weight: 500; }
  .hours-time.closed { color: #555; }

  .address-box {
    max-width: 1000px; margin: 2rem auto 0;
    background: var(--card); border: 1px solid var(--border);
    border-radius: 4px; padding: 1.5rem 2rem;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 1rem;
  }
  .address-info { display: flex; align-items: center; gap: 1rem; }
  .address-icon { font-size: 1.8rem; }
  .address-text h4 {
    font-family: 'Oswald', sans-serif; font-size: 1rem;
    color: var(--cream); margin-bottom: 0.2rem; letter-spacing: 1px;
  }
  .address-text p { font-size: 0.9rem; color: var(--muted); }
  .phone-big {
    font-family: 'Bebas Neue', sans-serif; font-size: 1.8rem;
    color: var(--red); letter-spacing: 2px; text-decoration: none;
  }
  .phone-big:hover { color: var(--cream); }

  /* ── CONTACT ── */
  .contact { background: var(--deep); }
  .contact-inner {
    max-width: 680px; margin: 0 auto;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1rem; }
  .form-group { display: flex; flex-direction: column; gap: 0.4rem; margin-bottom: 1rem; }
  .form-group label { font-size: 0.75rem; font-weight: 600; letter-spacing: 2px; text-transform: uppercase; color: var(--muted); }
  .form-group input, .form-group textarea, .form-group select {
    background: var(--card); border: 1px solid var(--border);
    color: var(--text); padding: 0.85rem 1rem; font-family: 'Heebo', sans-serif;
    font-size: 0.95rem; border-radius: 2px; outline: none;
    transition: border-color .2s;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--red); }
  .form-group textarea { resize: vertical; min-height: 130px; }
  .form-group select option { background: var(--card); }
  .form-submit {
    width: 100%; background: var(--red); color: #080700;
    border: none; padding: 1rem; cursor: pointer;
    font-family: 'Bebas Neue', sans-serif; font-size: 1.2rem; letter-spacing: 3px;
    border-radius: 2px; transition: background .2s, transform .15s;
  }
  .form-submit:hover { background: var(--red-hot); transform: translateY(-2px); }

  /* ── FOOTER ── */
  footer {
    background: var(--deep); border-top: 1px solid var(--border);
    padding: 2rem 2.5rem; text-align: center;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif; font-size: 1.8rem;
    color: var(--red); letter-spacing: 3px; margin-bottom: 0.5rem;
  }
  .footer-tagline { font-size: 0.8rem; color: var(--muted); letter-spacing: 2px; text-transform: uppercase; }

  /* ── KOSHER BADGE ── */
  .kosher-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: rgba(212,168,67,0.12); border: 1px solid var(--gold);
    color: var(--gold); padding: 0.35rem 1rem; border-radius: 2px;
    font-size: 0.75rem; font-weight: 700; letter-spacing: 2px;
    text-transform: uppercase; margin-top: 1.5rem;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes bounce {
    0%, 100% { transform: translateX(-50%) translateY(0); }
    50%       { transform: translateX(-50%) translateY(6px); }
  }

  /* ── TOAST ── */
  .toast {
    position: fixed; bottom: 2rem; left: 50%; transform: translateX(-50%) translateY(100px);
    background: var(--red); color: #fff; padding: 1rem 2rem;
    border-radius: 3px; font-weight: 600; font-size: 0.95rem;
    transition: transform .4s cubic-bezier(.34,1.56,.64,1);
    z-index: 999;
  }
  .toast.show { transform: translateX(-50%) translateY(0); }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .hours-container { grid-template-columns: 1fr; }
    .gallery-grid { grid-template-columns: 1fr 1fr; }
    .gallery-item { grid-column: span 1 !important; grid-row: span 1 !important; min-height: 140px !important; }
    .form-row { grid-template-columns: 1fr; }
    nav { padding: 0 1rem; }
    .nav-links { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">American Pie</div>
  <ul class="nav-links">
    <li><a href="#specials">מבצעים</a></li>
    <li><a href="#menu">תפריט</a></li>
    <li><a href="#gallery">גלריה</a></li>
    <li><a href="#hours">שעות</a></li>
    <li><a href="#contact">הזמנה</a></li>
  </ul>
  <a href="tel:1800353646" class="nav-phone">1-800-353-646</a>
</nav>

<!-- HERO -->
<section class="hero">
  <span class="hero-badge">🍕 כשר | ירושלים</span>
  <img src="" alt="American Pie Pizza" class="hero-logo-img" onerror="this.style.display='none'">
  <h1><span>American</span> Pie<br>Pizza</h1>
  <p class="hero-sub">אמריקאן פאי פיצה | בית לחם 51, ירושלים</p>
  <div class="kosher-badge">✡ כשר | משלוחים לכל ירושלים</div>
  <div class="hero-ctas">
    <a href="#menu" class="btn-primary">לתפריט המלא</a>
    <a href="#contact" class="btn-outline">הזמינו עכשיו</a>
  </div>
  <div class="hero-scroll">↓ גלול למטה</div>
</section>

<!-- SPECIALS -->
<section class="specials" id="specials">
  <div class="section-header">
    <span class="section-tag">🌟 מבצעים שווים</span>
    <h2 class="section-title">המחירים הכי טובים בעיר</h2>
    <div class="divider"></div>
  </div>
  <div class="deals-grid">
    <div class="deal-card">
      <span class="deal-emoji">🍕</span>
      <div class="deal-title">דיל זוגי</div>
      <div class="deal-desc">פיצה מרגריטה + פסטה/סלט לבחירה + 2 שתיות 0.5 + 2 קינוחי הפתעה</div>
      <span class="deal-price">₪159.90</span>
    </div>
    <div class="deal-card">
      <span class="deal-emoji">🍕🍕</span>
      <div class="deal-title">2 פיצות משפחתיות</div>
      <div class="deal-desc">שתי פיצות משפחתיות עם רוטב עגבניות וגבינה צהובה — ניתן להוסיף תוספות</div>
      <span class="deal-price">₪129.90</span>
    </div>
    <div class="deal-card">
      <span class="deal-emoji">👨‍👩‍👧‍👦</span>
      <div class="deal-title">דיל משפחתי</div>
      <div class="deal-desc">3 פיצות + מגש לחם שום + 2 פסטות/סלטים + 2 שתיות 1.5 ליטר</div>
      <span class="deal-price">₪369.90</span>
    </div>
  </div>
</section>

<!-- MENU -->
<section class="menu" id="menu">
  <div class="section-header">
    <span class="section-tag">🍽️ מה יש היום</span>
    <h2 class="section-title">התפריט שלנו</h2>
    <div class="divider"></div>
  </div>
  <div class="menu-tabs">
    <button class="tab-btn active" onclick="showTab('pizza')">🍕 פיצה</button>
    <button class="tab-btn" onclick="showTab('pasta')">🍝 פסטה</button>
    <button class="tab-btn" onclick="showTab('salad')">🥗 סלטים</button>
    <button class="tab-btn" onclick="showTab('bread')">🧄 לחם שום</button>
    <button class="tab-btn" onclick="showTab('dessert')">🍪 קינוחים</button>
    <button class="tab-btn" onclick="showTab('drinks')">🥤 שתיה</button>
    <button class="tab-btn" onclick="showTab('beer')">🍺 בירה</button>
  </div>

  <!-- PIZZA -->
  <div class="menu-panel active" id="tab-pizza">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה מרגריטה</div><div class="item-desc">בצק טרי, רוטב עגבניות, 100% גבינה צהובה</div></div><div class="item-price">₪79.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה פטריות טריות</div><div class="item-desc">על בסיס רוטב עגבניות וגבינה צהובה</div></div><div class="item-price">₪91.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה שום קונפי</div><div class="item-desc">שום קונפי עם עגבניות שרי תמר</div></div><div class="item-price">₪91.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה מיקס בצלים 🧅</div><div class="item-desc">בצק טרי, רוטב עגבניות, 100% גבינה צהובה, 3 סוגי בצלים</div></div><div class="item-price">₪91.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה שמנת פטריות 🍄</div><div class="item-desc">רוטב שמנת איכותי, גבינה צהובה, פטריות טריות</div></div><div class="item-price">₪92.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה עגבניות שרי וחלפיניו 🌶</div><div class="item-desc">עגבניות שרי תמר וחלפיניו על בסיס רוטב עגבניות</div></div><div class="item-price">₪99.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה אקסטרה גבינה וזיתים 🧀🫒</div><div class="item-desc">אקסטרה צ׳יז וזיתים ירוקים על בסיס קלאסי</div></div><div class="item-price">₪99.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה מונטנה</div><div class="item-desc">בולגרית, עגבניות שרי תמר, זיתים שחורים</div></div><div class="item-price">₪99.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה טקסס</div><div class="item-desc">חלפיניו, תירס, זיתים שחורים</div></div><div class="item-price">₪99.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה עגבניות שרי ופסטו 🍅🌶</div><div class="item-desc">עגבניות שרי תמר ופסטו על בסיס רוטב עגבניות</div></div><div class="item-price">₪99.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה פסטו עיזים</div><div class="item-desc">פסטו ביתי וגבינת עיזים על בצק טרי</div></div><div class="item-price">₪106.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיצה ביאנקה 🍯</div><div class="item-desc">רוטב שמנת, גבינה צהובה, גבינת עיזים ודבש</div></div><div class="item-price">₪106.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">ניו-יורק</div><div class="item-desc">גבינת עיזים וגבינת פרמז׳ן על בסיס קלאסי</div></div><div class="item-price">₪109.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">משולש פיצה</div><div class="item-desc">מנה אחת</div></div><div class="item-price">₪16.00</div></div>
    </div>
  </div>

  <!-- PASTA -->
  <div class="menu-panel" id="tab-pasta">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">פסטה מוקרמת</div><div class="item-desc">ברוטב עגבניות עם צהובה מוקרמת</div></div><div class="item-price">₪53.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פסטה אלפרדו</div><div class="item-desc">שמנת פטריות עם גבינה צהובה מוקרמת בתנור</div></div><div class="item-price">₪53.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פסטה רוזה</div><div class="item-desc">שמנת עגבניות בסגנון איטלקי עם גבינה מוקרמת</div></div><div class="item-price">₪53.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">מק אנד צ׳יז</div><div class="item-desc">רוטב שמנת ופולנטה מצופה גבינה צהובה מוקרמת</div></div><div class="item-price">₪53.00</div></div>
    </div>
  </div>

  <!-- SALAD -->
  <div class="menu-panel" id="tab-salad">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">סלט פסטו עיזים</div><div class="item-desc">גבינת עיזים, פסטו, חסה, עגבניות שרי, תירס, זיתים שחורים</div></div><div class="item-price">₪50.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">סלט טונה</div><div class="item-desc">טונה, חסה, עגבניות שרי, תירס, זיתים שחורים</div></div><div class="item-price">₪50.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">סלט בולגרית</div><div class="item-desc">בולגרית, חסה, עגבניות שרי, תירס, זיתים שחורים</div></div><div class="item-price">₪50.00</div></div>
    </div>
  </div>

  <!-- BREAD -->
  <div class="menu-panel" id="tab-bread">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">מגש לחם שום משפחתי</div><div class="item-desc">חמאה, עשבי תיבול, מיקס גבינות</div></div><div class="item-price">₪49.90</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">לחם שום אישי</div><div class="item-desc">מוגש עם רוטב לבחירה</div></div><div class="item-price">₪10.00</div></div>
    </div>
  </div>

  <!-- DESSERT -->
  <div class="menu-panel" id="tab-dessert">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">עוגיית קוקיס</div><div class="item-desc">קוטר 10 ס״מ</div></div><div class="item-price">₪15.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">קינוח בהפתעה</div><div class="item-desc">תנו לנו לבחור בשבילכם — תסמכו עלינו!</div></div><div class="item-price">₪12.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">גלידת בן אנד ג׳ריס</div><div class="item-desc">טעמים לבחירה | 0.5 ליטר</div></div><div class="item-price">₪49.90</div></div>
    </div>
  </div>

  <!-- DRINKS -->
  <div class="menu-panel" id="tab-drinks">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">קוקה קולה / קולה זירו</div><div class="item-desc">בקבוק פלסטיק 0.5L / בקבוק זכוכית 0.33</div></div><div class="item-price">₪12.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פחית קוקה קולה / ספרייט זירו / פאנטה</div><div class="item-desc">0.33</div></div><div class="item-price">₪12.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פיוז טי אפרסק / מנגו-אננס</div><div class="item-desc">0.5L / גדול 1.5L</div></div><div class="item-price">₪12–21</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">שוופס (סודה, ענבים, תות-ליים, מוחיטו, אננס, פירות יער)</div><div class="item-desc">בקבוק זכוכית 0.33</div></div><div class="item-price">₪9–12</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">ספרינג SHAKE</div><div class="item-desc">אננס מנגו פסיפלורה / בננה תמר תפוז / בננה אננס קוקוס</div></div><div class="item-price">₪13.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פרוט ווטר / תפוזינה / מים בטעם</div><div class="item-desc">בקבוק פלסטיק 0.5L — טעמים שונים</div></div><div class="item-price">₪12.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">משקה אנרגיה XL</div><div class="item-desc">0.25L</div></div><div class="item-price">₪12.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">מים מינרליים נביעות</div><div class="item-desc">0.5L</div></div><div class="item-price">₪8.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">שקית שוקו</div><div class="item-desc">250 מ״ל</div></div><div class="item-price">₪9.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">טרופית</div><div class="item-desc">100 מ״ל</div></div><div class="item-price">₪6.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">קוקה קולה גדול / קולה זירו גדול / פיוזטי גדול</div><div class="item-desc">1.5L</div></div><div class="item-price">₪21.00</div></div>
    </div>
  </div>

  <!-- BEER -->
  <div class="menu-panel" id="tab-beer">
    <div class="menu-grid">
      <div class="menu-item"><div class="item-info"><div class="item-name">סטלה ארטואה</div><div class="item-desc">0.33</div></div><div class="item-price">₪25.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">פחית 8.8</div><div class="item-desc">0.5</div></div><div class="item-price">₪21.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">מוסקו</div><div class="item-desc">0.33</div></div><div class="item-price">₪26.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">קורונה</div><div class="item-desc">0.33</div></div><div class="item-price">₪25.00</div></div>
      <div class="menu-item"><div class="item-info"><div class="item-name">בירה שחורה מאלטי</div><div class="item-desc">0.33</div></div><div class="item-price">₪12.00</div></div>
    </div>
  </div>
</section>

<!-- GALLERY -->
<section class="gallery" id="gallery">
  <div class="section-header">
    <span class="section-tag">📸 גלריה</span>
    <h2 class="section-title">מהמטבח אל השולחן</h2>
    <div class="divider"></div>
  </div>
  <div class="gallery-grid">
    <div class="gallery-item" style="padding:0; overflow:hidden;">
