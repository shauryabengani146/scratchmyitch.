<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scratch The Itch — India's Biggest Problems. Your Next Big Startup.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,600;1,9..40,300&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a08;
    --surface: #111110;
    --surface2: #1a1a17;
    --border: #2a2a26;
    --accent: #e8ff00;
    --accent2: #ff4d1c;
    --accent3: #00e5ff;
    --text: #f0ede6;
    --muted: #7a7a70;
    --card-glow: rgba(232,255,0,0.06);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
    cursor: none;
  }

  /* CUSTOM CURSOR */
  .cursor {
    width: 12px; height: 12px;
    background: var(--accent);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none;
    z-index: 9999;
    transition: transform 0.15s ease, width 0.2s, height 0.2s;
    transform: translate(-50%,-50%);
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1.5px solid rgba(232,255,0,0.4);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%,-50%);
    transition: left 0.12s ease, top 0.12s ease, width 0.2s, height 0.2s, border-color 0.2s;
  }
  .cursor.hovered { width: 20px; height: 20px; }
  .cursor-ring.hovered { width: 52px; height: 52px; border-color: var(--accent); }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 20px 48px;
    border-bottom: 1px solid transparent;
    transition: border-color 0.3s, background 0.3s;
  }
  nav.scrolled {
    background: rgba(10,10,8,0.9);
    backdrop-filter: blur(12px);
    border-bottom-color: var(--border);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 2px;
    color: var(--accent);
  }
  .nav-links { display: flex; gap: 32px; }
  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 13px;
    letter-spacing: 1px;
    text-transform: uppercase;
    font-weight: 600;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column;
    justify-content: flex-end;
    padding: 0 48px 64px;
    position: relative;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 60% 60% at 70% 40%, rgba(232,255,0,0.07) 0%, transparent 70%),
                radial-gradient(ellipse 40% 40% at 20% 80%, rgba(255,77,28,0.05) 0%, transparent 60%);
  }
  .hero-noise {
    position: absolute; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
  }
  .hero-ticker {
    position: absolute; top: 100px; left: 0; right: 0;
    overflow: hidden;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 12px 0;
  }
  .ticker-inner {
    display: flex; gap: 60px;
    animation: ticker 30s linear infinite;
    white-space: nowrap;
  }
  .ticker-item {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 13px;
    letter-spacing: 3px;
    color: var(--muted);
  }
  .ticker-item span { color: var(--accent); margin-right: 10px; }
  @keyframes ticker {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  .hero-overline {
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    font-weight: 600;
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp 0.8s 0.3s forwards;
  }
  .hero-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(72px, 12vw, 180px);
    line-height: 0.88;
    color: var(--text);
    opacity: 0;
    animation: fadeUp 0.8s 0.5s forwards;
  }
  .hero-title .accent { color: var(--accent); }
  .hero-title .italic { font-family: 'Instrument Serif', serif; font-style: italic; color: var(--muted); }
  .hero-subtitle {
    max-width: 480px;
    font-size: 16px;
    line-height: 1.6;
    color: var(--muted);
    margin-top: 32px;
    font-weight: 300;
    opacity: 0;
    animation: fadeUp 0.8s 0.7s forwards;
  }
  .hero-stats {
    display: flex; gap: 48px;
    margin-top: 48px;
    opacity: 0;
    animation: fadeUp 0.8s 0.9s forwards;
  }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 40px;
    color: var(--accent);
    line-height: 1;
  }
  .stat-label {
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 4px;
  }
  .hero-scroll {
    position: absolute; right: 48px; bottom: 64px;
    display: flex; flex-direction: column;
    align-items: center; gap: 12px;
    opacity: 0;
    animation: fadeUp 0.8s 1.2s forwards;
  }
  .hero-scroll span {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
    writing-mode: vertical-rl;
  }
  .scroll-line {
    width: 1px; height: 60px;
    background: linear-gradient(to bottom, var(--accent), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }
  @keyframes scrollPulse {
    0%,100% { opacity: 0.3; } 50% { opacity: 1; }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* SECTION LABEL */
  .section-label {
    font-size: 10px;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--accent);
    font-weight: 600;
    margin-bottom: 16px;
    display: flex; align-items: center; gap: 12px;
  }
  .section-label::before {
    content: '';
    display: block; width: 32px; height: 1px;
    background: var(--accent);
  }

  /* INTRO STRIP */
  .intro-strip {
    padding: 80px 48px;
    border-top: 1px solid var(--border);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 64px;
    align-items: center;
  }
  .intro-strip h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(40px, 6vw, 80px);
    line-height: 0.9;
    color: var(--text);
  }
  .intro-strip h2 em {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    color: var(--muted);
  }
  .intro-strip p {
    font-size: 16px;
    line-height: 1.8;
    color: var(--muted);
    font-weight: 300;
  }
  .intro-strip strong { color: var(--text); font-weight: 600; }

  /* FILTER BAR */
  .filter-section {
    padding: 0 48px 40px;
  }
  .filter-bar {
    display: flex; gap: 10px; flex-wrap: wrap;
    padding: 20px 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    margin-bottom: 48px;
  }
  .filter-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 8px 20px;
    border-radius: 100px;
    font-size: 12px;
    font-family: 'DM Sans', sans-serif;
    letter-spacing: 0.5px;
    font-weight: 600;
    cursor: none;
    transition: all 0.2s;
  }
  .filter-btn:hover, .filter-btn.active {
    background: var(--accent);
    color: var(--bg);
    border-color: var(--accent);
  }

  /* PROBLEMS GRID */
  .problems-section {
    padding: 0 48px 120px;
  }
  .section-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 48px;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(48px, 8vw, 100px);
    line-height: 0.9;
    color: var(--text);
  }
  .section-title .dim { color: var(--border); }
  .problem-count {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 14px;
    letter-spacing: 3px;
    color: var(--muted);
  }

  .problems-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
    gap: 2px;
  }

  .problem-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 32px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s ease, border-color 0.3s;
    cursor: none;
  }
  .problem-card::before {
    content: '';
    position: absolute; inset: 0;
    background: var(--card-glow);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .problem-card:hover {
    border-color: var(--accent);
    transform: translateY(-4px);
    z-index: 2;
  }
  .problem-card:hover::before { opacity: 1; }

  .card-top {
    display: flex; justify-content: space-between; align-items: flex-start;
    margin-bottom: 20px;
  }
  .card-category {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
    font-weight: 600;
  }
  .itch-score {
    display: flex; flex-direction: column; align-items: flex-end;
    gap: 4px;
  }
  .itch-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    line-height: 1;
    color: var(--accent);
  }
  .itch-label {
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
  }
  .itch-bar {
    width: 60px; height: 3px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
    margin-top: 4px;
  }
  .itch-fill {
    height: 100%;
    background: var(--accent);
    border-radius: 2px;
    transition: width 1s ease;
  }

  .card-problem {
    font-family: 'Instrument Serif', serif;
    font-size: 19px;
    line-height: 1.4;
    color: var(--text);
    margin-bottom: 20px;
    font-style: italic;
  }

  .card-expand-btn {
    background: transparent;
    border: none;
    color: var(--accent);
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    font-family: 'DM Sans', sans-serif;
    font-weight: 700;
    cursor: none;
    padding: 0;
    display: flex; align-items: center; gap: 8px;
    transition: gap 0.2s;
  }
  .card-expand-btn:hover { gap: 14px; }
  .card-expand-btn svg {
    transition: transform 0.3s;
  }
  .card-expand-btn.open svg { transform: rotate(45deg); }

  .card-details {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.5s cubic-bezier(0.4,0,0.2,1), opacity 0.3s;
    opacity: 0;
  }
  .card-details.open {
    max-height: 400px;
    opacity: 1;
  }
  .card-details-inner {
    padding-top: 24px;
    border-top: 1px solid var(--border);
    margin-top: 20px;
  }
  .detail-block {
    margin-bottom: 16px;
  }
  .detail-block-label {
    font-size: 9px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent2);
    font-weight: 700;
    margin-bottom: 8px;
  }
  .detail-block p {
    font-size: 14px;
    line-height: 1.7;
    color: var(--muted);
    font-weight: 300;
  }
  .solution-tag {
    display: inline-block;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    color: var(--accent3);
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 4px;
    margin: 4px 4px 4px 0;
    font-weight: 600;
    letter-spacing: 0.3px;
  }
  .market-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 12px;
    color: var(--text);
    font-weight: 600;
    margin-top: 8px;
  }
  .market-pill .dot {
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
  }

  /* MARQUEE DIVIDER */
  .marquee-divider {
    overflow: hidden;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 20px 0;
    margin: 0;
  }
  .marquee-inner {
    display: flex; gap: 48px;
    animation: ticker 20s linear infinite;
    white-space: nowrap;
  }
  .marquee-word {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 32px;
    letter-spacing: 4px;
    color: transparent;
    -webkit-text-stroke: 1px var(--border);
  }
  .marquee-word.filled { color: var(--text); -webkit-text-stroke: none; }

  /* TOP 10 */
  .top10-section {
    padding: 80px 48px;
    background: var(--surface);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  .top10-list {
    display: flex; flex-direction: column;
    margin-top: 48px;
  }
  .top10-item {
    display: grid;
    grid-template-columns: 64px 1fr 100px 160px;
    align-items: center;
    gap: 24px;
    padding: 28px 0;
    border-bottom: 1px solid var(--border);
    transition: background 0.2s;
    cursor: none;
  }
  .top10-item:first-child { border-top: 1px solid var(--border); }
  .top10-item:hover { padding-left: 16px; }
  .top10-rank {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 48px;
    color: var(--border);
    line-height: 1;
    text-align: center;
    transition: color 0.2s;
  }
  .top10-item:hover .top10-rank { color: var(--accent); }
  .top10-problem {
    font-family: 'Instrument Serif', serif;
    font-size: 20px;
    font-style: italic;
    color: var(--text);
    line-height: 1.4;
  }
  .top10-category {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    font-weight: 600;
    text-align: center;
  }
  .top10-score {
    text-align: right;
  }
  .top10-score .num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 36px;
    color: var(--accent);
    line-height: 1;
  }
  .top10-score .label {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
  }

  /* MISSION SECTION */
  .mission-section {
    padding: 120px 48px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .mission-bg {
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 50% 60% at 50% 50%, rgba(232,255,0,0.04) 0%, transparent 70%);
  }
  .mission-section h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(48px, 9vw, 120px);
    line-height: 0.9;
    color: var(--text);
    position: relative;
  }
  .mission-section h2 .ghost {
    color: transparent;
    -webkit-text-stroke: 1px var(--border);
  }
  .mission-body {
    max-width: 640px;
    margin: 40px auto 0;
    font-size: 18px;
    line-height: 1.8;
    color: var(--muted);
    font-weight: 300;
    position: relative;
  }
  .mission-body strong { color: var(--text); font-weight: 600; }
  .cta-btn {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    margin-top: 48px;
    padding: 18px 40px;
    background: var(--accent);
    color: var(--bg);
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-decoration: none;
    font-family: 'DM Sans', sans-serif;
    transition: background 0.2s, transform 0.2s;
    cursor: none;
    position: relative;
  }
  .cta-btn:hover {
    background: var(--text);
    transform: translateY(-2px);
  }
  .cta-btn svg { transition: transform 0.2s; }
  .cta-btn:hover svg { transform: translateX(4px); }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 40px 48px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 20px;
    letter-spacing: 2px;
    color: var(--muted);
  }
  .footer-note {
    font-size: 12px;
    color: var(--muted);
    font-weight: 300;
  }
  .footer-note strong { color: var(--accent); }

  /* HIDDEN CARDS */
  .problem-card.hidden { display: none; }

  /* SCROLL REVEAL */
  .reveal {
    opacity: 0;
    transform: translateY(32px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  @media (max-width: 768px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    .hero, .problems-section, .filter-section, .intro-strip, .top10-section, .mission-section, footer {
      padding-left: 24px; padding-right: 24px;
    }
    .intro-strip { grid-template-columns: 1fr; gap: 32px; }
    .top10-item { grid-template-columns: 48px 1fr; }
    .top10-category, .top10-score { display: none; }
    .hero-stats { gap: 32px; }
    .problems-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav id="nav">
  <div class="nav-logo">SCRATCH THE ITCH</div>
  <div class="nav-links">
    <a href="#top10">Top 10</a>
    <a href="#problems">All Problems</a>
    <a href="#mission">Mission</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-noise"></div>
  <div class="hero-ticker">
    <div class="ticker-inner" id="tickerInner">
      <span class="ticker-item"><span>✦</span> 10,000+ VERIFIED PROBLEMS</span>
      <span class="ticker-item"><span>✦</span> 50,000+ CONTRIBUTORS</span>
      <span class="ticker-item"><span>✦</span> AI-POWERED CURATION</span>
      <span class="ticker-item"><span>✦</span> INDIA'S BIGGEST ITCHES</span>
      <span class="ticker-item"><span>✦</span> YOUR NEXT STARTUP IDEA</span>
      <span class="ticker-item"><span>✦</span> B2B · HEALTHTECH · FINTECH · EDTECH</span>
      <span class="ticker-item"><span>✦</span> 10,000+ VERIFIED PROBLEMS</span>
      <span class="ticker-item"><span>✦</span> 50,000+ CONTRIBUTORS</span>
      <span class="ticker-item"><span>✦</span> AI-POWERED CURATION</span>
      <span class="ticker-item"><span>✦</span> INDIA'S BIGGEST ITCHES</span>
      <span class="ticker-item"><span>✦</span> YOUR NEXT STARTUP IDEA</span>
      <span class="ticker-item"><span>✦</span> B2B · HEALTHTECH · FINTECH · EDTECH</span>
    </div>
  </div>

  <div class="hero-overline">India's Problem Wishlist for Founders</div>
  <h1 class="hero-title">
    INDIA<br>
    <span class="accent">ITCHES.</span><br>
    <span class="italic">Do you dare</span><br>
    SCRATCH IT?
  </h1>
  <p class="hero-subtitle">50,000 Indians told us exactly where it hurts. These are the highest-itch problems across every industry — curated, ranked, and ready for the next generation of builders.</p>
  <div class="hero-stats">
    <div>
      <div class="stat-num">10K+</div>
      <div class="stat-label">Verified Problems</div>
    </div>
    <div>
      <div class="stat-num">50K+</div>
      <div class="stat-label">Contributors</div>
    </div>
    <div>
      <div class="stat-num">17</div>
      <div class="stat-label">Industries</div>
    </div>
    <div>
      <div class="stat-num">₹?T</div>
      <div class="stat-label">Market Waiting</div>
    </div>
  </div>

  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>Scroll</span>
  </div>
</section>

<!-- MARQUEE DIVIDER -->
<div class="marquee-divider">
  <div class="marquee-inner">
    <span class="marquee-word filled">BUILD</span>
    <span class="marquee-word">SOLVE</span>
    <span class="marquee-word filled">SCRATCH</span>
    <span class="marquee-word">DISRUPT</span>
    <span class="marquee-word filled">FOUND</span>
    <span class="marquee-word">ITERATE</span>
    <span class="marquee-word filled">GROW</span>
    <span class="marquee-word">BUILD</span>
    <span class="marquee-word filled">SOLVE</span>
    <span class="marquee-word">SCRATCH</span>
    <span class="marquee-word filled">DISRUPT</span>
    <span class="marquee-word">FOUND</span>
    <span class="marquee-word filled">ITERATE</span>
    <span class="marquee-word">GROW</span>
  </div>
</div>

<!-- INTRO STRIP -->
<section class="intro-strip reveal">
  <h2>WHAT IS<br><em>THIS</em><br>ALL ABOUT?</h2>
  <div>
    <div class="section-label">The Context</div>
    <p>India is a country of <strong>1.4 billion people</strong> — and 1.4 billion people means an almost infinite number of unsolved problems. We asked over 50,000 real Indians to describe their biggest daily frustrations across health, business, finance, housing, logistics, and more.</p>
    <br>
    <p>Each problem received an <strong>Itch Score</strong> — a composite metric measuring severity, frequency, and market readiness. The higher the score, the more urgent the itch. On this page, we show only the <strong>highest-scoring problem per category</strong> — the ones so painful, they're practically bleeding.</p>
    <br>
    <p>This isn't a think-piece. It's a <strong>founder's blueprint.</strong></p>
  </div>
</section>

<!-- TOP 10 SECTION -->
<section class="top10-section" id="top10">
  <div class="section-label reveal">Hall of Pain</div>
  <h2 class="section-title reveal">TOP <span class="dim">10</span><br>ITCHES</h2>

  <div class="top10-list">
    <div class="top10-item reveal">
      <div class="top10-rank">01</div>
      <div class="top10-problem">Why can't SMEs negotiate favorable payment terms with large buyers?</div>
      <div class="top10-category">B2B Services</div>
      <div class="top10-score"><div class="num">82.8</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">02</div>
      <div class="top10-problem">Why is managing multiple chronic conditions across hospitals still completely fragmented?</div>
      <div class="top10-category">Healthtech</div>
      <div class="top10-score"><div class="num">81.4</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">03</div>
      <div class="top10-problem">Why can't manufacturers rely on guaranteed, accountable pickup logistics for outbound deliveries?</div>
      <div class="top10-category">B2B Services</div>
      <div class="top10-score"><div class="num">79.0</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">04</div>
      <div class="top10-problem">Why do factory owners wait days for industrial repair technicians?</div>
      <div class="top10-category">B2B Services</div>
      <div class="top10-score"><div class="num">78.5</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">05</div>
      <div class="top10-problem">Why are first-time home buyers still falling prey to builder fraud and misleading property listings?</div>
      <div class="top10-category">Real Estate</div>
      <div class="top10-score"><div class="num">78.2</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">06</div>
      <div class="top10-problem">Why can't blue-collar workers build financial credit history to access affordable loans?</div>
      <div class="top10-category">FinTech</div>
      <div class="top10-score"><div class="num">77.6</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">07</div>
      <div class="top10-problem">Why do freelancers ghost projects after partial payments without any accountability?</div>
      <div class="top10-category">B2B Services</div>
      <div class="top10-score"><div class="num">76.0</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">08</div>
      <div class="top10-problem">Why can't Indian students with non-traditional learning paths find structured career guidance?</div>
      <div class="top10-category">EdTech</div>
      <div class="top10-score"><div class="num">75.8</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">09</div>
      <div class="top10-problem">Why do consumers have no way to verify kitchen hygiene on food delivery platforms?</div>
      <div class="top10-category">Consumer Services</div>
      <div class="top10-score"><div class="num">75.3</div><div class="label">Itch Score</div></div>
    </div>
    <div class="top10-item reveal">
      <div class="top10-rank">10</div>
      <div class="top10-problem">Why do businesses struggle finding reliable contract manufacturers for small-batch production?</div>
      <div class="top10-category">B2B Services</div>
      <div class="top10-score"><div class="num">75.2</div><div class="label">Itch Score</div></div>
    </div>
  </div>
</section>

<!-- MARQUEE DIVIDER 2 -->
<div class="marquee-divider">
  <div class="marquee-inner" style="animation-direction: reverse;">
    <span class="marquee-word">HEALTHCARE</span>
    <span class="marquee-word filled">FINTECH</span>
    <span class="marquee-word">EDTECH</span>
    <span class="marquee-word filled">B2B</span>
    <span class="marquee-word">LOGISTICS</span>
    <span class="marquee-word filled">REAL ESTATE</span>
    <span class="marquee-word">CONSUMER</span>
    <span class="marquee-word filled">SAAS</span>
    <span class="marquee-word">HEALTHCARE</span>
    <span class="marquee-word filled">FINTECH</span>
    <span class="marquee-word">EDTECH</span>
    <span class="marquee-word filled">B2B</span>
    <span class="marquee-word">LOGISTICS</span>
    <span class="marquee-word filled">REAL ESTATE</span>
  </div>
</div>

<!-- FILTER + PROBLEMS GRID -->
<section class="filter-section" id="problems">
  <div class="filter-bar">
    <button class="filter-btn active" data-filter="all">All Industries</button>
    <button class="filter-btn" data-filter="b2b">B2B Services</button>
    <button class="filter-btn" data-filter="healthtech">Healthtech</button>
    <button class="filter-btn" data-filter="fintech">FinTech</button>
    <button class="filter-btn" data-filter="edtech">EdTech</button>
    <button class="filter-btn" data-filter="consumer">Consumer</button>
    <button class="filter-btn" data-filter="realestate">Real Estate</button>
    <button class="filter-btn" data-filter="food">Food & Bev</button>
    <button class="filter-btn" data-filter="logistics">Logistics</button>
    <button class="filter-btn" data-filter="saas">SaaS</button>
    <button class="filter-btn" data-filter="transport">Transport</button>
  </div>
</section>

<section class="problems-section">
  <div class="section-header reveal">
    <h2 class="section-title">ALL <span class="dim">ITCHES</span></h2>
    <div class="problem-count" id="problemCount">SHOWING 20 PROBLEMS</div>
  </div>

  <div class="problems-grid" id="problemsGrid">

    <!-- B2B Services — HIGHEST: 82.8 -->
    <div class="problem-card reveal" data-cat="b2b">
      <div class="card-top">
        <div class="card-category">B2B Services</div>
        <div class="itch-score">
          <div class="itch-num">82.8</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:82.8%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't SMEs negotiate favorable payment terms with large buyers?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Small businesses supplying to large corporates routinely face 60–90 day payment cycles with zero negotiating power. This creates massive working capital gaps, forcing them into high-interest debt just to survive.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Supply Chain Finance Platform</span>
              <span class="solution-tag">Dynamic Discounting</span>
              <span class="solution-tag">Invoice Factoring</span>
            </div>
            <p style="margin-top:10px;">Build a B2B platform where suppliers can instantly sell their approved invoices at a small discount to get paid in 24–48 hours. Think a TReDS-lite model for mid-market SMEs with API integrations into ERP systems.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>Addressable Market: ₹45–60 Lakh Cr of SME receivables annually</div>
        </div>
      </div>
    </div>

    <!-- Healthtech — HIGHEST: 81.4 -->
    <div class="problem-card reveal" data-cat="healthtech">
      <div class="card-top">
        <div class="card-category">Healthtech</div>
        <div class="itch-score">
          <div class="itch-num">81.4</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:81.4%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why is managing multiple chronic conditions across hospitals still completely fragmented?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>A diabetic hypertension patient seeing 3 different doctors across 2 hospitals carries a plastic bag of paper prescriptions and has no way to share records. Medication conflicts and redundant tests are common, and often dangerous.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Unified Health Wallet</span>
              <span class="solution-tag">ABHA Integration</span>
              <span class="solution-tag">AI Drug Conflict Checker</span>
            </div>
            <p style="margin-top:10px;">A patient-controlled, ABHA-linked health record app that aggregates all prescriptions, labs, and diagnoses. Add an AI layer that flags drug interactions and sends proactive alerts to all treating doctors simultaneously.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India has 77M+ diabetics, 220M+ hypertension patients</div>
        </div>
      </div>
    </div>

    <!-- Real Estate — HIGHEST: 78.2 -->
    <div class="problem-card reveal" data-cat="realestate">
      <div class="card-top">
        <div class="card-category">Real Estate</div>
        <div class="itch-score">
          <div class="itch-num">78.2</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:78.2%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why are first-time home buyers still falling prey to builder fraud and misleading property listings?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>First-time buyers have no way to verify a builder's RERA compliance status, past delivery timelines, or legal encumbrances on land. Brochures are aspirational fiction. Buyers discover problems only after paying 20–30% of the cost.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">RERA Transparency Layer</span>
              <span class="solution-tag">Builder Score Engine</span>
              <span class="solution-tag">Legal Title Check API</span>
            </div>
            <p style="margin-top:10px;">A platform that aggregates RERA filings, court records, land registry data, and crowdsourced buyer reviews into a single "Builder Trust Score." Offer a paid legal due-diligence service to verify title deeds before booking.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India's housing market: ₹13+ Lakh Cr annually</div>
        </div>
      </div>
    </div>

    <!-- FinTech — HIGHEST: 77.6 -->
    <div class="problem-card reveal" data-cat="fintech">
      <div class="card-top">
        <div class="card-category">FinTech</div>
        <div class="itch-score">
          <div class="itch-num">77.6</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:77.6%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't blue-collar workers build financial credit history to access affordable loans?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Construction workers, domestic helpers, and gig drivers are paid in cash, have no formal income proof, and are invisible to credit bureaus. Banks reject them; moneylenders charge 40–80% interest. It's a poverty trap by design.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Alternative Credit Scoring</span>
              <span class="solution-tag">Employer-Linked Credit</span>
              <span class="solution-tag">UPI Behavior Analysis</span>
            </div>
            <p style="margin-top:10px;">Use UPI transaction history, employer attestations, utility payment records, and gig platform earnings as alternative credit signals. Build a credit score engine specifically calibrated for India's 400M+ informal workforce.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>400M+ informal workers — massively underserved</div>
        </div>
      </div>
    </div>

    <!-- EdTech — HIGHEST: 75.8 -->
    <div class="problem-card reveal" data-cat="edtech">
      <div class="card-top">
        <div class="card-category">EdTech</div>
        <div class="itch-score">
          <div class="itch-num">75.8</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:75.8%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't Indian students with non-traditional learning paths find structured career guidance?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Students who dropped out, took online courses, or followed non-IIT paths have no structured roadmap. Career counselors are expensive and generic. Peer pressure defaults everyone to "engineering or UPSC" even when they're mismatched.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">AI Career Mapping</span>
              <span class="solution-tag">Cohort-Based Mentorship</span>
              <span class="solution-tag">Outcome-Linked Programs</span>
            </div>
            <p style="margin-top:10px;">An AI-first platform that creates personalized career roadmaps based on aptitude, interests, and financial constraints — then connects students to cohort-based programs with verifiable outcomes and ISA-based payment models.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>30M+ students graduate annually without clear paths</div>
        </div>
      </div>
    </div>

    <!-- Consumer Services — HIGHEST: 75.3 -->
    <div class="problem-card reveal" data-cat="consumer">
      <div class="card-top">
        <div class="card-category">Consumer Services</div>
        <div class="itch-score">
          <div class="itch-num">75.3</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:75.3%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do consumers have no way to verify kitchen hygiene on food delivery platforms?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Restaurants on Swiggy and Zomato have beautiful food photos, but zero transparency into kitchen cleanliness, FSSAI compliance, or storage conditions. Food safety incidents keep rising — consumers are ordering blind.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">IoT Kitchen Sensors</span>
              <span class="solution-tag">Third-Party Audit Badges</span>
              <span class="solution-tag">FSSAI Score Display</span>
            </div>
            <p style="margin-top:10px;">A FoodSafe certification layer that integrates with Swiggy/Zomato APIs to display verified FSSAI scores, recent audit dates, and real-time temperature compliance badges. Offer restaurant subscriptions for IoT sensor monitoring.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India's food delivery market: ₹1.5 Lakh Cr by 2030</div>
        </div>
      </div>
    </div>

    <!-- Logistics — HIGHEST: 79.0 -->
    <div class="problem-card reveal" data-cat="logistics">
      <div class="card-top">
        <div class="card-category">Logistics</div>
        <div class="itch-score">
          <div class="itch-num">79.0</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:79.0%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't manufacturers rely on guaranteed, accountable pickup logistics for outbound deliveries?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Small and mid-size manufacturers experience last-minute courier no-shows, zero-accountability for delayed pickups, and complete loss of visibility once goods leave the factory. They negotiate with 4–5 vendors just to ship one day's output.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Guaranteed Pickup SLA</span>
              <span class="solution-tag">Multi-Carrier Orchestration</span>
              <span class="solution-tag">Live GPS Tracking</span>
            </div>
            <p style="margin-top:10px;">A logistics aggregator for manufacturers that guarantees pickup windows with penalty-backed SLAs, intelligently routes across 10+ carriers for lowest cost, and provides a unified tracking dashboard with automated delay compensation.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India's logistics market: $350B+ by 2030</div>
        </div>
      </div>
    </div>

    <!-- SaaS — HIGHEST: 74.8 -->
    <div class="problem-card reveal" data-cat="saas">
      <div class="card-top">
        <div class="card-category">SaaS</div>
        <div class="itch-score">
          <div class="itch-num">74.8</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:74.8%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do micro-SMEs waste 10+ hours weekly drowning in invoice and compliance management?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>The kirana store owner, the small manufacturer, the local contractor — they spend more time managing paperwork than running their business. GST returns, invoices, TDS, vendor payments: it's a full-time job that nobody trained them for.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">WhatsApp-Based Billing</span>
              <span class="solution-tag">Auto GST Filing</span>
              <span class="solution-tag">Vernacular Interface</span>
            </div>
            <p style="margin-top:10px;">Build the "Tally for Bharat" — a WhatsApp-first invoicing and compliance tool that lets business owners generate invoices, auto-file GST returns, and track payments in their local language with zero accounting knowledge required.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>63M+ MSMEs in India, 90% without proper accounting tools</div>
        </div>
      </div>
    </div>

    <!-- Food & Beverage — HIGHEST: 74.2 -->
    <div class="problem-card reveal" data-cat="food">
      <div class="card-top">
        <div class="card-category">Food & Beverage</div>
        <div class="itch-score">
          <div class="itch-num">74.2</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:74.2%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't small restaurants access wholesale ingredient pricing without minimum order requirements?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>A small restaurant ordering 5kg of tomatoes cannot access the ₹20/kg price that a hotel chain gets. They pay retail market prices, destroying margins. Distributors ignore small restaurants and large MOQs are inaccessible.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Group Purchasing Co-op</span>
              <span class="solution-tag">B2B Ingredient Marketplace</span>
              <span class="solution-tag">Demand Aggregation</span>
            </div>
            <p style="margin-top:10px;">Pool demand from 100s of small restaurants in a city, aggregate orders daily, and negotiate bulk pricing with suppliers — then distribute to each restaurant. Think "Udaan for micro-restaurants" with same-day delivery.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>7.5M+ restaurants in India — most are small format</div>
        </div>
      </div>
    </div>

    <!-- Transport — HIGHEST: 73.9 -->
    <div class="problem-card reveal" data-cat="transport">
      <div class="card-top">
        <div class="card-category">Transportation</div>
        <div class="itch-score">
          <div class="itch-num">73.9</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:73.9%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't first-time used car buyers verify vehicle history, condition, and future maintenance costs before purchasing?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>The used car market is rife with odometer fraud, undisclosed accidents, and flood-damaged vehicles. First-time buyers with limited mechanical knowledge are routinely deceived. RC transfers take weeks and involve brokers.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Vehicle History Report</span>
              <span class="solution-tag">AI Damage Scanner</span>
              <span class="solution-tag">TCO Calculator</span>
            </div>
            <p style="margin-top:10px;">An app-based platform where buyers scan a car's number plate to instantly see RTO records, insurance claims, service history, and an AI-generated condition report from photos. Include a 5-year total cost of ownership projection.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>Used car market: ₹2+ Lakh Cr/year in India</div>
        </div>
      </div>
    </div>

    <!-- Healthtech #2 — 78.5 - industrial -->
    <div class="problem-card reveal" data-cat="b2b">
      <div class="card-top">
        <div class="card-category">B2B Services</div>
        <div class="itch-score">
          <div class="itch-num">78.5</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:78.5%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do factory owners wait days for industrial repair technicians when machines break down?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>A machine breakdown costs a factory ₹50,000–₹5,00,000 per hour in lost output. Yet finding a qualified industrial technician for specialized CNC machines, hydraulics, or pneumatic systems can take 3–5 days. There's no Uber for industrial repair.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Industrial Gig Platform</span>
              <span class="solution-tag">Predictive Maintenance</span>
              <span class="solution-tag">IoT Early Warning</span>
            </div>
            <p style="margin-top:10px;">Build a verified marketplace of certified industrial technicians with SLA-backed 4–8 hour response times. Layer in IoT sensor monitoring to predict failures before they happen, moving customers from reactive to preventive maintenance.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India has 450K+ registered factories with aging equipment</div>
        </div>
      </div>
    </div>

    <!-- Payment Issues -->
    <div class="problem-card reveal" data-cat="fintech">
      <div class="card-top">
        <div class="card-category">Payment Issues</div>
        <div class="itch-score">
          <div class="itch-num">73.1</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:73.1%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do international freelancers and creators in India lose 5–12% on every cross-border payment they receive?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>An Indian developer earning $5,000/month from US clients loses $400–600 in hidden conversion fees, SWIFT charges, and unfavorable exchange rates. RBI's FEMA rules add compliance complexity. Creators on Gumroad or Patreon face even worse rates.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Virtual USD/EUR Accounts</span>
              <span class="solution-tag">Mid-Market FX Rates</span>
              <span class="solution-tag">Instant Remittance</span>
            </div>
            <p style="margin-top:10px;">A Wise-like product built specifically for Indian freelancers — virtual USD/EUR IBAN accounts that collect payments locally for clients, convert at mid-market rates, and settle instantly in INR with auto-generated FEMA-compliant receipts.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India is the world's top remittance recipient: $125B/year</div>
        </div>
      </div>
    </div>

    <!-- Home Services -->
    <div class="problem-card reveal" data-cat="consumer">
      <div class="card-top">
        <div class="card-category">Home Services</div>
        <div class="itch-score">
          <div class="itch-num">72.4</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:72.4%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do Indian homeowners still have no trustworthy platform to find, verify, and fairly price interior contractors?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Interior renovation is India's most trusted fraud industry. Homeowners face inflated quotes, material substitutions, project abandonment, and zero recourse. Finding a reliable contractor is entirely word-of-mouth — broken for new movers and tier-2 cities.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Verified Contractor Profiles</span>
              <span class="solution-tag">Milestone Payment Escrow</span>
              <span class="solution-tag">Material Price Transparency</span>
            </div>
            <p style="margin-top:10px;">A platform with background-checked contractors, photo portfolios of real completed work, milestone-based escrow payments (contractor paid only when client approves each stage), and a transparent material rate card updated weekly.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India's home improvement market: ₹3+ Lakh Cr</div>
        </div>
      </div>
    </div>

    <!-- Travel — HIGHEST: 71.8 -->
    <div class="problem-card reveal" data-cat="transport">
      <div class="card-top">
        <div class="card-category">Travel</div>
        <div class="itch-score">
          <div class="itch-num">71.8</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:71.8%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why is group travel planning for Indian families still a WhatsApp-to-chaos mess with zero coordination tools?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Planning a trip with 10 family members involves 4 WhatsApp groups, 20 screenshots, 3 people with conflicting opinions, and someone always missing a booking. No existing travel app handles multi-member itinerary building with democratic decision-making.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Group Itinerary Builder</span>
              <span class="solution-tag">Vote & Poll Integration</span>
              <span class="solution-tag">Split Payment Tracking</span>
            </div>
            <p style="margin-top:10px;">A collaborative travel app where members vote on destinations, hotels, and activities. AI suggests itineraries that balance diverse preferences. Integrated split payment tracking shows who owes whom. Built for the Indian joint family travel context.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>Indian travel market: $125B by 2027</div>
        </div>
      </div>
    </div>

    <!-- Beauty & Personal Care -->
    <div class="problem-card reveal" data-cat="consumer">
      <div class="card-top">
        <div class="card-category">Beauty & Personal Care</div>
        <div class="itch-score">
          <div class="itch-num">70.3</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:70.3%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do Indian consumers buy skincare products blind without knowing whether they're safe for their specific skin type and climate?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Influencer-driven skincare advice ignores India's diversity — a dark-skinned consumer in Chennai's humidity has completely different needs than someone in Rajasthan's dry heat. Ingredient labels are incomprehensible and allergic reactions are common.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Skin Type AI Scanner</span>
              <span class="solution-tag">Ingredient Safety Database</span>
              <span class="solution-tag">Climate-Personalized Recs</span>
            </div>
            <p style="margin-top:10px;">A "INCI Decoder" app that scans any product label, flags harmful ingredients, and personalizes safety ratings based on the user's skin type, known allergies, and local climate. Add a recommendation engine for safer alternatives.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India beauty & personal care: ₹1.8 Lakh Cr and growing at 11% CAGR</div>
        </div>
      </div>
    </div>

    <!-- E-commerce -->
    <div class="problem-card reveal" data-cat="b2b">
      <div class="card-top">
        <div class="card-category">E-Commerce</div>
        <div class="itch-score">
          <div class="itch-num">69.7</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:69.7%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why can't small D2C brands reliably detect and act on fake reviews destroying their marketplace reputation?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>Competitor brands pay ₹5–10 per fake 1-star review, destroying years of reputation building for honest D2C sellers. Amazon and Flipkart's review systems are easily gamed. Small brands have no tools to detect, report, or counter coordinated review attacks.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Fake Review Detection AI</span>
              <span class="solution-tag">Review Authenticity Score</span>
              <span class="solution-tag">Marketplace Brand Shield</span>
            </div>
            <p style="margin-top:10px;">A SaaS product for D2C brands that monitors reviews in real-time, uses NLP and behavioral signals to detect fake reviews, automatically generates evidence reports for marketplace appeals, and suggests proactive reputation repair strategies.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India e-commerce: $150B+ by 2026, 1M+ D2C sellers</div>
        </div>
      </div>
    </div>

    <!-- Healthtech — Mental Health -->
    <div class="problem-card reveal" data-cat="healthtech">
      <div class="card-top">
        <div class="card-category">Healthtech</div>
        <div class="itch-score">
          <div class="itch-num">74.1</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:74.1%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why do working professionals in India have no accessible, stigma-free pathway to mental health support?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>India has 1 psychiatrist per 250,000 people. Corporate therapy benefits exist on paper but nobody uses them. Stigma, cost (₹1,500–3,000 per session), waitlists, and the fear of being judged keep India's mental health crisis silent and invisible.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">Anonymous First Sessions</span>
              <span class="solution-tag">B2B EAP Integration</span>
              <span class="solution-tag">Vernacular Therapists</span>
            </div>
            <p style="margin-top:10px;">A corporate mental wellness platform sold to HR teams as an Employee Assistance Program — fully anonymous first sessions, a directory of therapists in 12 Indian languages, and AI-powered mood tracking between sessions. Price: ₹300–500/session through the employer.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India mental health gap: 80% with conditions receive no treatment</div>
        </div>
      </div>
    </div>

    <!-- FinTech — Insurance -->
    <div class="problem-card reveal" data-cat="fintech">
      <div class="card-top">
        <div class="card-category">FinTech / InsurTech</div>
        <div class="itch-score">
          <div class="itch-num">72.9</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:72.9%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why is making a health insurance claim in India still a nightmare of paperwork, rejections, and follow-ups?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>In medical emergencies, patients must simultaneously fight for their health AND manage insurance paperwork. Claim rejection rates are high, often on technicalities. Reimbursement cycles take 30–90 days. Most policyholders don't even understand their coverage until it's denied.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">AI Claims Co-pilot</span>
              <span class="solution-tag">Policy Plain-Language Decoder</span>
              <span class="solution-tag">Hospital TPA Liaison</span>
            </div>
            <p style="margin-top:10px;">A claims advocacy service powered by AI — interprets any health policy in plain language, pre-validates claims before submission to minimize rejection risk, and provides a human advocate to liaise with TPA offices and hospitals on the patient's behalf.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>India's health insurance market: ₹90,000+ Cr in premiums annually</div>
        </div>
      </div>
    </div>

    <!-- EdTech #2 -->
    <div class="problem-card reveal" data-cat="edtech">
      <div class="card-top">
        <div class="card-category">EdTech</div>
        <div class="itch-score">
          <div class="itch-num">73.4</div>
          <div class="itch-label">Itch Score</div>
          <div class="itch-bar"><div class="itch-fill" style="width:73.4%"></div></div>
        </div>
      </div>
      <div class="card-problem">Why are STEM students taking education loans with no idea of their actual post-graduation earning potential?</div>
      <button class="card-expand-btn" onclick="toggleCard(this)">
        Explore Solution
        <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
      </button>
      <div class="card-details">
        <div class="card-details-inner">
          <div class="detail-block">
            <div class="detail-block-label">The Pain</div>
            <p>A student taking a ₹20L education loan for a tier-3 engineering college has almost no data on actual placement rates, starting salaries, or loan repayment feasibility. The college's "average package" stat is a masterpiece of selective math.</p>
          </div>
          <div class="detail-block">
            <div class="detail-block-label">Potential Solution</div>
            <div>
              <span class="solution-tag">College ROI Calculator</span>
              <span class="solution-tag">Real Placement Data</span>
              <span class="solution-tag">Loan Repayability Score</span>
            </div>
            <p style="margin-top:10px;">A college transparency platform with crowdsourced actual placement data (verified via LinkedIn), a loan-to-income ratio calculator, and a "Should You Take This Loan?" score that factors in course, college tier, city, and target role. Think College Confidential meets personal finance for India.</p>
          </div>
          <div class="market-pill"><span class="dot"></span>Education loans outstanding: ₹1.07 Lakh Cr in India</div>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- MISSION -->
<div class="marquee-divider">
  <div class="marquee-inner">
    <span class="marquee-word filled">THE</span>
    <span class="marquee-word">MISSION</span>
    <span class="marquee-word filled">IS</span>
    <span class="marquee-word">SIMPLE</span>
    <span class="marquee-word filled">BUILD</span>
    <span class="marquee-word">WHAT</span>
    <span class="marquee-word filled">INDIA</span>
    <span class="marquee-word">NEEDS</span>
    <span class="marquee-word filled">THE</span>
    <span class="marquee-word">MISSION</span>
    <span class="marquee-word filled">IS</span>
    <span class="marquee-word">SIMPLE</span>
  </div>
</div>

<section class="mission-section" id="mission">
  <div class="mission-bg"></div>
  <div class="section-label reveal" style="justify-content: center;">Our Mission</div>
  <h2 class="reveal">
    START<br>
    <span class="ghost">WHERE</span><br>
    INDIA ITCHES
  </h2>
  <p class="mission-body reveal">
    These aren't abstract market reports. These are <strong>real people's real pains</strong> — verified, ranked, and handed to you on a silver platter. Every problem here has an itch score above 69. Every solution angle here has a multi-billion rupee market behind it.<br><br>
    The only question is: <strong>who's brave enough to scratch it?</strong>
  </p>
  <a href="#problems" class="cta-btn reveal">
    Explore All Problems
    <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
  </a>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">SCRATCH THE ITCH</div>
  <div class="footer-note">Inspired by <strong>Razorpay's Fix My Itch</strong> · Problems sourced from 50K+ Indians · Built for the next gen of founders</div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx + 'px';
    cursor.style.top = my + 'px';
  });

  function animRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  document.querySelectorAll('a, button, .problem-card, .top10-item, .filter-btn').forEach(el => {
    el.addEventListener('mouseenter', () => { cursor.classList.add('hovered'); ring.classList.add('hovered'); });
    el.addEventListener('mouseleave', () => { cursor.classList.remove('hovered'); ring.classList.remove('hovered'); });
  });

  // Nav scroll
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 60);
  });

  // Card toggle
  function toggleCard(btn) {
    const details = btn.nextElementSibling;
    const isOpen = details.classList.contains('open');
    // close all
    document.querySelectorAll('.card-details.open').forEach(d => { d.classList.remove('open'); d.previousElementSibling.classList.remove('open'); d.previousElementSibling.textContent = ''; });
    document.querySelectorAll('.card-expand-btn').forEach(b => { b.classList.remove('open'); b.innerHTML = 'Explore Solution <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>'; });
    if (!isOpen) {
      details.classList.add('open');
      btn.classList.add('open');
      btn.innerHTML = 'Close <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>';
    }
  }

  // Filter
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      const filter = btn.dataset.filter;
      const cards = document.querySelectorAll('.problem-card');
      let count = 0;
      cards.forEach(card => {
        const cat = card.dataset.cat;
        const show = filter === 'all' || cat === filter;
        card.style.display = show ? '' : 'none';
        if (show) count++;
      });
      document.getElementById('problemCount').textContent = `SHOWING ${count} PROBLEM${count !== 1 ? 'S' : ''}`;
    });
  });

  // Scroll reveal
  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), 60);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  revealEls.forEach(el => observer.observe(el));

  // Stagger grid cards
  document.querySelectorAll('.problem-card').forEach((card, i) => {
    card.style.transitionDelay = (i % 3) * 0.08 + 's';
  });
</script>
</body>
</html>
