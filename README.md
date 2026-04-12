<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kozbur — Blog</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --ink: #0a0a0a;
      --paper: #f8f7f4;
      --muted: #888;
      --rule: #d8d5cf;
      --accent: #0a0a0a;
    }

    html { font-size: 16px; scroll-behavior: smooth; }

    body {
      background: var(--paper);
      color: var(--ink);
      font-family: 'DM Sans', sans-serif;
      font-weight: 400;
      line-height: 1.7;
      min-height: 100vh;
      -webkit-font-smoothing: antialiased;
    }

    /* HEADER */
    header {
      border-bottom: 1px solid var(--ink);
      padding: 0 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 64px;
      position: sticky;
      top: 0;
      background: var(--paper);
      z-index: 100;
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.15rem;
      font-weight: 700;
      letter-spacing: -0.01em;
      text-decoration: none;
      color: var(--ink);
    }

    nav { display: flex; gap: 2rem; }
    nav a {
      font-size: 0.8rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--muted);
      transition: color 0.2s;
    }
    nav a:hover { color: var(--ink); }

    /* HERO */
    .hero {
      border-bottom: 1px solid var(--rule);
      padding: 5rem 2rem 4rem;
      max-width: 860px;
      margin: 0 auto;
      animation: fadeUp 0.7s ease both;
    }

    .hero-label {
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 1.5rem;
    }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 6vw, 4rem);
      line-height: 1.1;
      letter-spacing: -0.02em;
      font-weight: 700;
      margin-bottom: 1.5rem;
    }

    .hero h1 em {
      font-style: italic;
      font-weight: 400;
    }

    .hero p {
      font-size: 1.05rem;
      color: #444;
      max-width: 520px;
      line-height: 1.8;
    }

    /* POSTS */
    .posts-section {
      max-width: 860px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      padding: 3rem 0 1.5rem;
      border-bottom: 1px solid var(--ink);
      margin-bottom: 0;
    }

    .section-title {
      font-size: 0.72rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .section-count {
      font-size: 0.72rem;
      color: var(--muted);
    }

    /* POST CARD */
    .post {
      display: grid;
      grid-template-columns: 80px 1fr auto;
      gap: 0 2rem;
      align-items: start;
      padding: 2rem 0;
      border-bottom: 1px solid var(--rule);
      text-decoration: none;
      color: inherit;
      transition: opacity 0.2s;
      animation: fadeUp 0.5s ease both;
    }

    .post:hover { opacity: 0.6; }
    .post:hover .post-arrow { transform: translate(4px, -4px); }

    .post-num {
      font-family: 'Playfair Display', serif;
      font-size: 0.8rem;
      font-style: italic;
      color: var(--muted);
      padding-top: 0.25rem;
    }

    .post-body {}

    .post-tag {
      font-size: 0.68rem;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 0.4rem;
    }

    .post-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.25rem;
      line-height: 1.3;
      font-weight: 700;
      letter-spacing: -0.01em;
      margin-bottom: 0.5rem;
    }

    .post-excerpt {
      font-size: 0.9rem;
      color: #555;
      line-height: 1.7;
      max-width: 480px;
    }

    .post-meta {
      font-size: 0.75rem;
      color: var(--muted);
      margin-top: 0.75rem;
    }

    .post-arrow {
      font-size: 1rem;
      color: var(--muted);
      margin-top: 0.2rem;
      transition: transform 0.2s;
    }

    /* FEATURED POST */
    .post.featured {
      grid-template-columns: 1fr;
      padding: 2.5rem 0;
      border-bottom: 1px solid var(--ink);
    }

    .post.featured .post-title {
      font-size: clamp(1.5rem, 3.5vw, 2.1rem);
      margin-bottom: 0.75rem;
    }

    .post.featured .featured-inner {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 1rem;
      align-items: end;
    }

    /* ABOUT STRIP */
    .about {
      border-top: 1px solid var(--ink);
      margin-top: 4rem;
      padding: 4rem 2rem;
      max-width: 860px;
      margin-left: auto;
      margin-right: auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
      animation: fadeUp 0.8s ease both;
    }

    .about-label {
      font-size: 0.72rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1.25rem;
    }

    .about-text {
      font-size: 0.95rem;
      color: #444;
      line-height: 1.8;
    }

    .about-links {
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .about-link {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.85rem;
      font-weight: 500;
      padding: 0.75rem 0;
      border-bottom: 1px solid var(--rule);
      text-decoration: none;
      color: var(--ink);
      transition: opacity 0.2s;
    }

    .about-link:hover { opacity: 0.5; }
    .about-link:last-child { border-bottom: none; }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--ink);
      padding: 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.78rem;
      color: var(--muted);
      max-width: 860px;
      margin: 0 auto;
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .post:nth-child(1) { animation-delay: 0.05s; }
    .post:nth-child(2) { animation-delay: 0.12s; }
    .post:nth-child(3) { animation-delay: 0.19s; }
    .post:nth-child(4) { animation-delay: 0.26s; }

    /* RESPONSIVE */
    @media (max-width: 600px) {
      header { padding: 0 1.25rem; }
      nav { gap: 1.2rem; }
      .hero, .posts-section, .about, footer { padding-left: 1.25rem; padding-right: 1.25rem; }
      .post { grid-template-columns: 1fr; gap: 0.25rem; }
      .post-num { display: none; }
      .post.featured .featured-inner { grid-template-columns: 1fr; }
      .about { grid-template-columns: 1fr; gap: 2rem; }
    }
  </style>
</head>
<body>

  <header>
    <a class="logo" href="/">Kozbur.com</a>
    <nav>
      <a href="#yazilar">Yazılar</a>
      <a href="#hakkimda">Hakkımda</a>
    </nav>
  </header>

  <!-- HERO -->
  <section class="hero">
    <p class="hero-label">Kişisel Blog</p>
    <h1>Düşünceler, <em>notlar</em><br>ve keşifler.</h1>
    <p>Teknoloji, tasarım ve hayat üzerine yazılar. Kısa ya da uzun, ham ya da olgun — düşüncelerimi burada paylaşıyorum.</p>
  </section>

  <!-- POSTS -->
  <main class="posts-section" id="yazilar">

    <div class="section-header">
      <span class="section-title">Son Yazılar</span>
      <span class="section-count">4 yazı</span>
    </div>

    <!-- Featured -->
    <a class="post featured" href="#">
      <div class="post-tag">Öne Çıkan</div>
      <div class="featured-inner">
        <div>
          <h2 class="post-title">Basitliğin ardındaki karmaşıklık</h2>
          <p class="post-excerpt">İyi bir tasarımın "görünmez" olduğunu söylüyoruz, ama görünmez hale gelmek için ne kadar çok şey gerekiyor? Bir düğmenin doğru hissettirmesi için yapılan onlarca deneme üzerine.</p>
          <p class="post-meta">12 Nisan 2025 · 7 dk okuma</p>
        </div>
        <span class="post-arrow">↗</span>
      </div>
    </a>

    <!-- Post 1 -->
    <a class="post" href="#">
      <span class="post-num">01</span>
      <div class="post-body">
        <div class="post-tag">Teknoloji</div>
        <h2 class="post-title">Yapay zekayla çalışmayı öğrenmek</h2>
        <p class="post-excerpt">Araçlar değişiyor, ama düşünme biçimi daha da önemli hale geliyor.</p>
        <p class="post-meta">3 Mart 2025 · 5 dk okuma</p>
      </div>
      <span class="post-arrow">↗</span>
    </a>

    <!-- Post 2 -->
    <a class="post" href="#">
      <span class="post-num">02</span>
      <div class="post-body">
        <div class="post-tag">Erasmus Rehberi</div>
        <h2 class="post-title">Krosno, Polonya'da bir günüm.</h2>
        <p class="post-excerpt">Burası bir harika!</p>
        <p class="post-meta">15 Şubat 2025 · 3 dk okuma</p>
      </div>
      <span class="post-arrow">↗</span>
    </a>

    <!-- Post 3 -->
    <a class="post" href="#">
      <span class="post-num">03</span>
      <div class="post-body">
        <div class="post-tag">Tasarım</div>
        <h2 class="post-title">Tipografi bir ses tonudur</h2>
        <p class="post-excerpt">Font seçimi, kelimelerin içeriğinden önce nasıl bir ruh hali yaratır?</p>
        <p class="post-meta">8 Ocak 2025 · 4 dk okuma</p>
      </div>
      <span class="post-arrow">↗</span>
    </a>

  </main>

  <!-- ABOUT -->
  <section class="about" id="hakkimda">
    <div>
      <p class="about-label">Hakkımda</p>
      <p class="about-text">
        Merhaba, ben Mert. Muğla'da yaşıyorum.
        Bu blog, aklımı meşgul eden konuları yazıya dökmek için var. Bazen teknik, bazen kişisel ama her zaman dürüst.
      </p>
    </div>
    <div>
      <p class="about-label">Bağlantılar</p>
      <div class="about-links">
        <a class="about-link" href="https://github.com/ryocs15" target="_blank">
          GitHub <span>↗</span>
        </a>
        <a class="about-link" href="https://twitter.com/combosgombos" target="_blank">
          Twitter / X <span>↗</span>
        </a>
        <a class="about-link" href="mailto:mertahmetos@hotmail.com">
          E-posta <span>→</span>
        </a>
      </div>
    </div>
  </section>

  <footer>
    <span>© 2025 Mert </span>
    <span>GitHub Pages üzerinde yayınlanmaktadır</span>
  </footer>

</body>
</html>
