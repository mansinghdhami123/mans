
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>B & B Cloud Kitchen – Shankhamul, Kathmandu</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --cream:     #f5efe6;
      --warm-bg:   #fdf6ec;
      --brown:     #5c3d2e;
      --gold:      #c8943a;
      --rust:      #b5541c;
      --dark:      #2c1a0e;
      --muted:     #8a6a52;
      --card-bg:   #fffaf4;
      --border:    #e8d5bc;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Lato', sans-serif;
      background: var(--warm-bg);
      color: var(--dark);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 100;
      background: rgba(253,246,236,0.92);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid var(--border);
      padding: 0 5%;
      display: flex; align-items: center; justify-content: space-between;
      height: 68px;
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem; font-weight: 700;
      color: var(--brown);
      letter-spacing: 0.02em;
    }
    .nav-logo span { color: var(--gold); }
    .nav-links { display: flex; gap: 2.2rem; list-style: none; }
    .nav-links a {
      text-decoration: none; font-size: 0.88rem; font-weight: 700;
      letter-spacing: 0.1em; text-transform: uppercase;
      color: var(--muted); transition: color 0.25s;
    }
    .nav-links a:hover { color: var(--rust); }
    .nav-order {
      background: var(--rust); color: #fff;
      padding: 0.55rem 1.4rem; border-radius: 4px;
      font-size: 0.82rem; font-weight: 700; letter-spacing: 0.1em;
      text-transform: uppercase; text-decoration: none;
      transition: background 0.25s;
    }
    .nav-order:hover { background: var(--brown); }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding: 0 6%;
      position: relative;
      background:
        radial-gradient(ellipse 70% 60% at 80% 50%, rgba(200,148,58,0.12) 0%, transparent 70%),
        radial-gradient(ellipse 50% 80% at 10% 60%, rgba(92,61,46,0.07) 0%, transparent 60%),
        var(--warm-bg);
      overflow: hidden;
    }
    .hero-pattern {
      position: absolute; inset: 0; opacity: 0.04;
      background-image:
        repeating-linear-gradient(45deg, var(--brown) 0, var(--brown) 1px, transparent 0, transparent 50%);
      background-size: 28px 28px;
      pointer-events: none;
    }
    .hero-content {
      max-width: 580px; position: relative; z-index: 2;
      animation: fadeUp 1s ease both;
    }
    .hero-tag {
      display: inline-block;
      background: var(--gold); color: #fff;
      font-size: 0.72rem; font-weight: 700; letter-spacing: 0.15em;
      text-transform: uppercase; padding: 0.35rem 0.9rem;
      border-radius: 2px; margin-bottom: 1.4rem;
    }
    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 6vw, 5.2rem);
      line-height: 1.1; color: var(--brown);
      margin-bottom: 0.3rem;
    }
    .hero-title em { color: var(--rust); font-style: italic; }
    .hero-sub {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem; color: var(--muted);
      font-style: italic; margin-bottom: 1.6rem;
      letter-spacing: 0.03em;
    }
    .hero-desc {
      font-size: 1rem; color: var(--muted);
      line-height: 1.8; max-width: 440px; margin-bottom: 2.4rem;
    }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
    .btn-primary {
      background: var(--rust); color: #fff;
      padding: 0.85rem 2rem; border-radius: 4px;
      font-size: 0.9rem; font-weight: 700; letter-spacing: 0.08em;
      text-transform: uppercase; text-decoration: none;
      transition: background 0.25s, transform 0.2s;
    }
    .btn-primary:hover { background: var(--brown); transform: translateY(-2px); }
    .btn-outline {
      border: 2px solid var(--gold); color: var(--gold);
      padding: 0.85rem 2rem; border-radius: 4px;
      font-size: 0.9rem; font-weight: 700; letter-spacing: 0.08em;
      text-transform: uppercase; text-decoration: none;
      transition: all 0.25s;
    }
    .btn-outline:hover { background: var(--gold); color: #fff; transform: translateY(-2px); }

    /* decorative bowl illustration */
    .hero-deco {
      position: absolute; right: 5%; top: 50%;
      transform: translateY(-50%);
      font-size: 18rem; opacity: 0.06; pointer-events: none;
      animation: float 6s ease-in-out infinite;
    }

    /* ── SECTION SHARED ── */
    section { padding: 6rem 6%; }
    .section-label {
      font-size: 0.72rem; font-weight: 700; letter-spacing: 0.2em;
      text-transform: uppercase; color: var(--gold);
      margin-bottom: 0.6rem;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      color: var(--brown); line-height: 1.2;
      margin-bottom: 1rem;
    }
    .section-divider {
      width: 50px; height: 3px;
      background: linear-gradient(90deg, var(--gold), var(--rust));
      border-radius: 2px; margin-bottom: 2rem;
    }

    /* ── ABOUT ── */
    #about {
      background: var(--cream);
      display: grid; grid-template-columns: 1fr 1fr; gap: 5rem;
      align-items: center;
    }
    .about-img-wrap {
      position: relative;
    }
    .about-img-box {
      width: 100%; aspect-ratio: 4/5;
      background: linear-gradient(135deg, var(--gold) 0%, var(--rust) 100%);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 9rem; opacity: 0.85;
      box-shadow: 12px 12px 0 var(--border);
    }
    .about-badge {
      position: absolute; bottom: -1.5rem; right: -1.5rem;
      background: var(--brown); color: var(--gold);
      width: 120px; height: 120px; border-radius: 50%;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      font-family: 'Playfair Display', serif;
      text-align: center; line-height: 1.3;
      border: 4px solid var(--cream);
      box-shadow: 0 4px 20px rgba(0,0,0,0.15);
    }
    .about-badge .big { font-size: 1.6rem; font-weight: 700; }
    .about-badge .small { font-size: 0.65rem; letter-spacing: 0.1em; text-transform: uppercase; }
    .about-text p {
      color: var(--muted); line-height: 1.9; margin-bottom: 1.2rem;
      font-size: 0.97rem;
    }
    .about-highlights {
      display: flex; gap: 2rem; margin-top: 2rem;
    }
    .highlight-item { text-align: center; }
    .highlight-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem; font-weight: 700; color: var(--rust);
    }
    .highlight-lbl {
      font-size: 0.75rem; color: var(--muted);
      letter-spacing: 0.08em; text-transform: uppercase;
    }

    /* ── MENU ── */
    #menu { background: var(--warm-bg); }
    .menu-intro { max-width: 520px; margin-bottom: 3rem; }
    .menu-categories {
      display: flex; gap: 0.8rem; flex-wrap: wrap; margin-bottom: 2.8rem;
    }
    .cat-btn {
      background: none; border: 1.5px solid var(--border);
      color: var(--muted); padding: 0.45rem 1.2rem;
      border-radius: 30px; font-size: 0.82rem; font-weight: 700;
      letter-spacing: 0.06em; cursor: pointer;
      transition: all 0.22s; font-family: 'Lato', sans-serif;
    }
    .cat-btn.active, .cat-btn:hover {
      background: var(--rust); border-color: var(--rust); color: #fff;
    }
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    .menu-card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 10px; padding: 1.6rem;
      transition: transform 0.25s, box-shadow 0.25s;
      position: relative; overflow: hidden;
    }
    .menu-card::before {
      content: ''; position: absolute; top: 0; left: 0;
      width: 4px; height: 100%;
      background: linear-gradient(180deg, var(--gold), var(--rust));
    }
    .menu-card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(92,61,46,0.12); }
    .menu-emoji { font-size: 2.2rem; margin-bottom: 0.8rem; display: block; }
    .menu-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.15rem; color: var(--brown);
      margin-bottom: 0.4rem;
    }
    .menu-desc { font-size: 0.83rem; color: var(--muted); line-height: 1.6; margin-bottom: 1rem; }
    .menu-footer { display: flex; align-items: center; justify-content: space-between; }
    .menu-price {
      font-family: 'Playfair Display', serif;
      font-size: 1.15rem; color: var(--rust); font-weight: 700;
    }
    .menu-tag {
      font-size: 0.68rem; background: rgba(200,148,58,0.15);
      color: var(--gold); padding: 0.25rem 0.7rem;
      border-radius: 30px; font-weight: 700; letter-spacing: 0.06em;
    }

    /* ── SPECIAL ── */
    #special {
      background: var(--brown);
      color: var(--cream);
      text-align: center;
      padding: 5rem 6%;
    }
    #special .section-title { color: var(--cream); }
    #special .section-label { color: var(--gold); }
    #special .section-divider { margin: 0 auto 2rem; }
    .special-desc { color: rgba(245,239,230,0.7); max-width: 480px; margin: 0 auto 3rem; line-height: 1.8; }
    .specials-row { display: flex; gap: 2rem; justify-content: center; flex-wrap: wrap; }
    .special-card {
      background: rgba(255,255,255,0.07);
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 10px; padding: 2rem 1.5rem;
      width: 220px; transition: background 0.25s;
    }
    .special-card:hover { background: rgba(255,255,255,0.12); }
    .special-card .emoji { font-size: 2.8rem; display: block; margin-bottom: 1rem; }
    .special-card h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem; color: var(--gold); margin-bottom: 0.5rem;
    }
    .special-card p { font-size: 0.82rem; color: rgba(245,239,230,0.65); line-height: 1.6; }

    /* ── CONTACT ── */
    #contact {
      background: var(--cream);
      display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start;
    }
    .contact-info h2 { margin-bottom: 2rem; }
    .info-block { display: flex; gap: 1rem; margin-bottom: 1.8rem; align-items: flex-start; }
    .info-icon {
      font-size: 1.4rem;
      background: rgba(200,148,58,0.15);
      width: 48px; height: 48px; border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      flex-shrink: 0;
    }
    .info-text strong {
      display: block; font-size: 0.78rem; letter-spacing: 0.1em;
      text-transform: uppercase; color: var(--gold); margin-bottom: 0.2rem;
    }
    .info-text span { font-size: 0.95rem; color: var(--muted); line-height: 1.6; }
    .map-placeholder {
      background: linear-gradient(135deg, #e8d5bc 0%, #d4b896 100%);
      border-radius: 10px; height: 300px;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      color: var(--brown); gap: 0.5rem;
      border: 1px solid var(--border);
      font-family: 'Playfair Display', serif;
    }
    .map-placeholder .map-pin { font-size: 3rem; }
    .map-placeholder p { font-size: 1rem; }
    .map-placeholder small { font-size: 0.78rem; color: var(--muted); }

    /* order form */
    .order-form { background: var(--card-bg); border: 1px solid var(--border); border-radius: 10px; padding: 2rem; }
    .order-form h3 { font-family: 'Playfair Display', serif; font-size: 1.4rem; color: var(--brown); margin-bottom: 1.5rem; }
    .form-group { margin-bottom: 1.2rem; }
    .form-group label { display: block; font-size: 0.78rem; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.4rem; }
    .form-group input, .form-group textarea, .form-group select {
      width: 100%; padding: 0.75rem 1rem;
      border: 1.5px solid var(--border); border-radius: 6px;
      background: var(--warm-bg); color: var(--dark);
      font-family: 'Lato', sans-serif; font-size: 0.93rem;
      transition: border-color 0.2s;
      outline: none;
    }
    .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--gold); }
    .form-group textarea { resize: vertical; min-height: 90px; }
    .form-submit {
      width: 100%; background: var(--rust); color: #fff;
      border: none; padding: 0.9rem;
      border-radius: 6px; font-family: 'Lato', sans-serif;
      font-size: 0.9rem; font-weight: 700; letter-spacing: 0.1em;
      text-transform: uppercase; cursor: pointer;
      transition: background 0.25s;
    }
    .form-submit:hover { background: var(--brown); }

    /* ── FOOTER ── */
    footer {
      background: var(--dark); color: rgba(245,239,230,0.6);
      text-align: center; padding: 2.5rem 6%;
    }
    footer .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.6rem; color: var(--gold); margin-bottom: 0.5rem;
    }
    footer p { font-size: 0.83rem; line-height: 1.8; }
    footer .socials { display: flex; gap: 1rem; justify-content: center; margin: 1rem 0; }
    footer .socials a {
      width: 38px; height: 38px; border-radius: 50%;
      border: 1px solid rgba(255,255,255,0.15);
      display: flex; align-items: center; justify-content: center;
      text-decoration: none; font-size: 1rem;
      transition: border-color 0.2s, background 0.2s;
    }
    footer .socials a:hover { background: var(--gold); border-color: var(--gold); }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(-50%) rotate(0deg); }
      50%       { transform: translateY(-54%) rotate(3deg); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      nav { padding: 0 4%; }
      .nav-links { display: none; }
      #about, #contact { grid-template-columns: 1fr; gap: 3rem; }
      .about-badge { right: 0; bottom: -1rem; }
      .hero-deco { display: none; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">B <span>&</span> B <span style="color:var(--muted);font-size:0.9rem;font-weight:300"> Cloud Kitchen</span></div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#special">Specials</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-order">Order Now</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-pattern"></div>
  <div class="hero-content">
    <span class="hero-tag">🇳🇵 Authentic Nepali Flavours</span>
    <h1 class="hero-title">B <em>&</em> B<br>Cloud Kitchen</h1>
    <p class="hero-sub">Ghar jastai mito khana — Taste like home.</p>
    <p class="hero-desc">
      Freshly cooked Nepali meals delivered right to your door from the heart of Shankhamul, Kathmandu. Made with love, served with warmth.
    </p>
    <div class="hero-btns">
      <a href="#menu" class="btn-primary">View Our Menu</a>
      <a href="#contact" class="btn-outline">Order Now</a>
    </div>
  </div>
  <div class="hero-deco">🍲</div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-img-wrap">
    <div class="about-img-box">🍛</div>
    <div class="about-badge">
      <span class="big">100%</span>
      <span class="small">Home<br>Style</span>
    </div>
  </div>
  <div class="about-text">
    <p class="section-label">Our Story</p>
    <h2 class="section-title">Made Fresh,<br>Served with Heart</h2>
    <div class="section-divider"></div>
    <p>B & B Cloud Kitchen was born out of a simple love for authentic Nepali cooking. Located in the lively neighbourhood of Shankhamul, Kathmandu, we bring the warmth of a home kitchen straight to your table.</p>
    <p>Every dish is prepared fresh daily using locally sourced ingredients — no shortcuts, no compromise. Whether it's a hearty dal bhat or a comforting thukpa on a cold Kathmandu evening, we cook it just like didi would at home.</p>
    <div class="about-highlights">
      <div class="highlight-item">
        <div class="highlight-num">100%</div>
        <div class="highlight-lbl">Fresh Daily</div>
      </div>
      <div class="highlight-item">
        <div class="highlight-num">Local</div>
        <div class="highlight-lbl">Ingredients</div>
      </div>
      <div class="highlight-item">
        <div class="highlight-num">Fast</div>
        <div class="highlight-lbl">Delivery</div>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-intro">
    <p class="section-label">What We Cook</p>
    <h2 class="section-title">Our Menu</h2>
    <div class="section-divider"></div>
  </div>
  <div class="menu-categories">
    <button class="cat-btn active">All</button>
    <button class="cat-btn">Main Course</button>
    <button class="cat-btn">Snacks</button>
    <button class="cat-btn">Drinks</button>
  </div>
  <div class="menu-grid">

    <div class="menu-card">
      <span class="menu-emoji">🍛</span>
      <h3 class="menu-name">Dal Bhat Set</h3>
      <p class="menu-desc">Steamed rice, lentil soup, seasonal tarkari, achar & papad. A complete Nepali meal.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 180</span>
        <span class="menu-tag">⭐ Best Seller</span>
      </div>
    </div>

    <div class="menu-card">
      <span class="menu-emoji">🍜</span>
      <h3 class="menu-name">Thukpa</h3>
      <p class="menu-desc">Hearty Tibetan-style noodle soup with vegetables and warming spices — perfect for Kathmandu winters.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 160</span>
        <span class="menu-tag">🔥 Popular</span>
      </div>
    </div>

    <div class="menu-card">
      <span class="menu-emoji">🥟</span>
      <h3 class="menu-name">Veg Momo (10 pcs)</h3>
      <p class="menu-desc">Steamed dumplings filled with spiced cabbage, carrot & herbs. Served with our house tomato chutney.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 140</span>
        <span class="menu-tag">🌿 Veg</span>
      </div>
    </div>

    <div class="menu-card">
      <span class="menu-emoji">🥩</span>
      <h3 class="menu-name">Chicken Momo (10 pcs)</h3>
      <p class="menu-desc">Juicy minced chicken momos, steamed fresh. A Kathmandu favourite with house-made sauce.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 180</span>
        <span class="menu-tag">⭐ Best Seller</span>
      </div>
    </div>

    <div class="menu-card">
      <span class="menu-emoji">🫓</span>
      <h3 class="menu-name">Sel Roti & Achar</h3>
      <p class="menu-desc">Traditional Nepali ring bread made from rice flour, served with a tangy tomato-sesame achar.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 80</span>
        <span class="menu-tag">🍃 Snack</span>
      </div>
    </div>

    <div class="menu-card">
      <span class="menu-emoji">☕</span>
      <h3 class="menu-name">Masala Chiya</h3>
      <p class="menu-desc">Freshly brewed spiced milk tea with ginger, cardamom and cinnamon. The true Nepali way to start a morning.</p>
      <div class="menu-footer">
        <span class="menu-price">Rs. 40</span>
        <span class="menu-tag">☕ Drink</span>
      </div>
    </div>

  </div>
</section>

<!-- SPECIALS -->
<section id="special">
  <p class="section-label">Why Choose Us</p>
  <h2 class="section-title">What Makes Us Special</h2>
  <div class="section-divider"></div>
  <p class="special-desc">We keep it simple — real ingredients, honest recipes, and the kind of food that reminds you of home.</p>
  <div class="specials-row">
    <div class="special-card">
      <span class="emoji">🌿</span>
      <h3>Fresh Ingredients</h3>
      <p>We source vegetables and spices fresh from local Kathmandu markets every single morning.</p>
    </div>
    <div class="special-card">
      <span class="emoji">🏠</span>
      <h3>Home-Style Cooking</h3>
      <p>No artificial shortcuts. Every dish is cooked the traditional Nepali way — slow and with love.</p>
    </div>
    <div class="special-card">
      <span class="emoji">🛵</span>
      <h3>Fast Delivery</h3>
      <p>We deliver hot and fresh to Shankhamul and surrounding areas of Kathmandu quickly.</p>
    </div>
    <div class="special-card">
      <span class="emoji">💸</span>
      <h3>Pocket Friendly</h3>
      <p>Great food doesn't have to be expensive. Our menu is designed to be filling and affordable.</p>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-info">
    <p class="section-label">Find Us</p>
    <h2 class="section-title">Visit or<br>Order Online</h2>
    <div class="section-divider"></div>
    <div class="info-block">
      <div class="info-icon">📍</div>
      <div class="info-text">
        <strong>Address</strong>
        <span>Shankhamul Road, Shankhamul<br>Kathmandu, Nepal</span>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">🕐</div>
      <div class="info-text">
        <strong>Opening Hours</strong>
        <span>Daily: 7:00 AM – 9:00 PM<br>Open 7 days a week</span>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">📞</div>
      <div class="info-text">
        <strong>Phone / WhatsApp</strong>
        <span>+977 98X-XXXXXXX</span>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">📱</div>
      <div class="info-text">
        <strong>Also Available On</strong>
        <span>Foodmandu · Bhojdeals</span>
      </div>
    </div>
    <div class="map-placeholder" style="margin-top:2rem;">
      <span class="map-pin">📌</span>
      <p>Shankhamul, Kathmandu</p>
      <small>Google Maps integration can be added here</small>
    </div>
  </div>

  <div class="order-form">
    <h3>Place a Quick Order</h3>
    <div class="form-group">
      <label>Your Name</label>
      <input type="text" placeholder="Ram Bahadur"/>
    </div>
    <div class="form-group">
      <label>Phone Number</label>
      <input type="tel" placeholder="+977 98X-XXXXXXX"/>
    </div>
    <div class="form-group">
      <label>Delivery Address</label>
      <input type="text" placeholder="Your address near Shankhamul"/>
    </div>
    <div class="form-group">
      <label>Your Order</label>
      <select>
        <option>Dal Bhat Set – Rs. 180</option>
        <option>Thukpa – Rs. 160</option>
        <option>Veg Momo (10 pcs) – Rs. 140</option>
        <option>Chicken Momo (10 pcs) – Rs. 180</option>
        <option>Sel Roti & Achar – Rs. 80</option>
        <option>Masala Chiya – Rs. 40</option>
      </select>
    </div>
    <div class="form-group">
      <label>Special Instructions</label>
      <textarea placeholder="Extra achar? Less spicy? Let us know..."></textarea>
    </div>
    <button class="form-submit" onclick="alert('Order received! We will call you to confirm. Dhanyabad! 🙏')">
      Send Order 🛵
    </button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo">B & B Cloud Kitchen</div>
  <div class="socials">
    <a href="#" title="Facebook">📘</a>
    <a href="#" title="Instagram">📸</a>
    <a href="#" title="WhatsApp">💬</a>
  </div>
  <p>Shankhamul, Kathmandu, Nepal &nbsp;|&nbsp; Open Daily 7 AM – 9 PM</p>
  <p style="margin-top:0.6rem; font-size:0.75rem;">© 2025 B & B Cloud Kitchen. Made with ❤️ in Kathmandu.</p>
</footer>

<script>
  // Category filter buttons (visual only for now)
  document.querySelectorAll('.cat-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
    });
  });

  // Scroll-reveal for menu cards
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        e.target.style.animation = `fadeUp 0.5s ease ${i * 0.08}s both`;
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.menu-card, .special-card').forEach(el => observer.observe(el));
</script>
</body>
</html
