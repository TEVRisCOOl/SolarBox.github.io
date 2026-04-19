<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SOLARBOX — Build. Explore. Conquer.</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --void: #000008;
    --star-white: #e8f4ff;
    --glow-cyan: #00d4ff;
    --glow-purple: #7b2fff;
    --text-dim: #5a7090;
    --text-mid: #8aa0bb;
    --card-bg: rgba(8,18,35,0.7);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--void);
    color: var(--star-white);
    font-family: 'Inter', sans-serif;
    overflow-x: hidden;
  }

  #starfield {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 0;
    pointer-events: none;
  }

  .layer { position: relative; z-index: 2; }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 0 60px;
    height: 72px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(0,0,8,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(0,212,255,0.1);
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
  }

  .logo-orb {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: radial-gradient(circle at 35% 35%, #c8e0ff, #6090c0, #203050);
    box-shadow: 0 0 16px rgba(0,212,255,0.5), inset -6px -3px 12px rgba(0,0,0,0.5);
    position: relative;
    overflow: hidden;
    flex-shrink: 0;
  }

  .logo-orb::after {
    content: '';
    position: absolute;
    width: 130%; height: 3px;
    background: rgba(0,212,255,0.95);
    top: 50%; left: -15%;
    transform: translateY(-50%) rotate(-10deg);
    box-shadow: 0 0 10px rgba(0,212,255,1);
  }

  .logo-text {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: 18px;
    letter-spacing: 5px;
    color: var(--star-white);
  }

  .nav-right { display: flex; align-items: center; gap: 32px; }

  .nav-link {
    text-decoration: none;
    color: var(--text-mid);
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 1px;
    transition: color 0.2s;
  }

  .nav-link:hover { color: var(--star-white); }

  .nav-btn {
    padding: 10px 24px;
    background: linear-gradient(135deg, var(--glow-cyan), var(--glow-purple));
    color: #000;
    font-family: 'Orbitron', sans-serif;
    font-size: 11px;
    letter-spacing: 2px;
    font-weight: 700;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.3s;
    display: inline-block;
  }

  .nav-btn:hover {
    box-shadow: 0 0 24px rgba(0,212,255,0.5);
    transform: translateY(-1px);
  }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 100px 32px 80px;
    position: relative;
  }

  .hero-tag {
    display: inline-block;
    padding: 6px 18px;
    border: 1px solid rgba(0,212,255,0.35);
    color: var(--glow-cyan);
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 32px;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s forwards;
    font-weight: 500;
  }

  .hero-title {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: clamp(64px, 12vw, 140px);
    line-height: 0.9;
    letter-spacing: -3px;
    background: linear-gradient(135deg, #fff 0%, #b0d8ff 45%, var(--glow-cyan) 75%, var(--glow-purple) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    opacity: 0;
    animation: fadeUp 0.8s 0.4s forwards;
    margin-bottom: 24px;
  }

  .hero-tagline {
    font-size: clamp(15px, 2.5vw, 20px);
    font-weight: 300;
    color: var(--text-mid);
    letter-spacing: 2px;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s forwards;
    margin-bottom: 20px;
  }

  .hero-tagline strong {
    color: var(--star-white);
    font-weight: 600;
  }

  .hero-desc {
    max-width: 520px;
    font-size: 15px;
    line-height: 1.85;
    color: var(--text-dim);
    opacity: 0;
    animation: fadeUp 0.8s 0.8s forwards;
    margin-bottom: 52px;
  }

  .hero-cta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    justify-content: center;
    opacity: 0;
    animation: fadeUp 0.8s 1s forwards;
    margin-bottom: 80px;
  }

  .btn-outline {
    padding: 16px 40px;
    border: 1px solid rgba(0,212,255,0.5);
    color: var(--glow-cyan);
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 2px;
    text-decoration: none;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .btn-outline::before {
    content: '';
    position: absolute;
    inset: 0;
    background: rgba(0,212,255,0.07);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .btn-outline:hover::before { opacity: 1; }
  .btn-outline:hover { transform: translateY(-2px); box-shadow: 0 0 24px rgba(0,212,255,0.2); }

  .btn-solid {
    padding: 16px 40px;
    background: linear-gradient(135deg, var(--glow-cyan), var(--glow-purple));
    color: #000;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 2px;
    text-decoration: none;
    transition: all 0.3s;
  }

  .btn-solid:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 40px rgba(0,212,255,0.45);
  }

  /* scroll hint */
  .scroll-hint {
    opacity: 0;
    animation: fadeUp 0.8s 1.4s forwards;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    color: var(--text-dim);
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  .scroll-line {
    width: 1px;
    height: 48px;
    background: linear-gradient(180deg, var(--glow-cyan), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  @keyframes scrollPulse {
    0%, 100% { opacity: 0.3; transform: scaleY(0.8); }
    50% { opacity: 1; transform: scaleY(1); }
  }

  /* ── WHAT IS SECTION ── */
  #what {
    padding: 100px 60px;
    max-width: 1100px;
    margin: 0 auto;
    width: 100%;
  }

  .what-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }

  @media (max-width: 768px) {
    .what-grid { grid-template-columns: 1fr; gap: 48px; }
    nav { padding: 0 24px; }
    #hero, #what, #features, #get { padding-left: 24px; padding-right: 24px; }
    .nav-right .nav-link { display: none; }
  }

  .what-label {
    font-size: 11px;
    letter-spacing: 4px;
    color: var(--glow-cyan);
    text-transform: uppercase;
    margin-bottom: 16px;
    font-weight: 500;
  }

  .what-title {
    font-family: 'Orbitron', sans-serif;
    font-weight: 700;
    font-size: clamp(24px, 4vw, 38px);
    line-height: 1.2;
    margin-bottom: 24px;
    letter-spacing: 1px;
  }

  .what-body {
    font-size: 15px;
    line-height: 1.9;
    color: var(--text-mid);
    margin-bottom: 16px;
  }

  .what-body strong { color: var(--star-white); font-weight: 600; }

  .what-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 28px;
  }

  .pill {
    padding: 6px 16px;
    border: 1px solid rgba(0,212,255,0.2);
    font-size: 12px;
    color: var(--text-mid);
    letter-spacing: 1px;
    background: rgba(0,212,255,0.04);
  }

  .what-visual {
    aspect-ratio: 1;
    max-width: 420px;
    width: 100%;
    margin: 0 auto;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .planet {
    width: 200px; height: 200px;
    border-radius: 50%;
    background: radial-gradient(circle at 35% 30%, #4090e0, #1040a0, #050820);
    box-shadow: 0 0 60px rgba(0,100,255,0.3), 0 0 120px rgba(0,50,200,0.15), inset -30px -20px 50px rgba(0,0,0,0.6);
    position: relative;
    animation: floatPlanet 6s ease-in-out infinite;
  }

  .planet::after {
    content: '';
    position: absolute;
    inset: -20px;
    border-radius: 50%;
    border: 1px solid rgba(0,212,255,0.15);
    animation: rotatering 12s linear infinite;
  }

  .orbit-ring {
    position: absolute;
    border-radius: 50%;
    border: 1px solid rgba(0,212,255,0.12);
  }

  .orbit-ring:nth-child(1) { width: 280px; height: 280px; animation: rotatering 20s linear infinite; }
  .orbit-ring:nth-child(2) { width: 360px; height: 360px; animation: rotatering 30s linear infinite reverse; }

  .orbit-dot {
    position: absolute;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--glow-cyan);
    box-shadow: 0 0 10px var(--glow-cyan);
    top: -3px; left: 50%;
    transform: translateX(-50%);
  }

  @keyframes floatPlanet {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-16px); }
  }

  @keyframes rotatering {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  /* ── FEATURES ── */
  #features {
    padding: 100px 60px;
    max-width: 1100px;
    margin: 0 auto;
    width: 100%;
  }

  .section-header {
    text-align: center;
    margin-bottom: 64px;
  }

  .section-label {
    font-size: 11px;
    letter-spacing: 4px;
    color: var(--glow-cyan);
    text-transform: uppercase;
    margin-bottom: 14px;
    font-weight: 500;
  }

  .section-title {
    font-family: 'Orbitron', sans-serif;
    font-weight: 700;
    font-size: clamp(26px, 4vw, 42px);
    letter-spacing: 2px;
  }

  .section-sub {
    font-size: 15px;
    color: var(--text-dim);
    margin-top: 14px;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
    line-height: 1.7;
  }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }

  .feature-card {
    border: 1px solid rgba(0,212,255,0.08);
    padding: 36px 28px;
    background: var(--card-bg);
    position: relative;
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
    backdrop-filter: blur(8px);
  }

  .feature-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--glow-cyan), var(--glow-purple));
    opacity: 0;
    transition: opacity 0.3s;
  }

  .feature-card:hover {
    border-color: rgba(0,212,255,0.2);
    transform: translateY(-6px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.4);
  }

  .feature-card:hover::before { opacity: 1; }

  .feature-num {
    font-family: 'Orbitron', sans-serif;
    font-size: 11px;
    color: var(--glow-cyan);
    opacity: 0.5;
    letter-spacing: 2px;
    margin-bottom: 16px;
    display: block;
  }

  .feature-title {
    font-family: 'Orbitron', sans-serif;
    font-size: 14px;
    letter-spacing: 2px;
    font-weight: 700;
    margin-bottom: 12px;
    color: var(--star-white);
  }

  .feature-text {
    font-size: 14px;
    line-height: 1.8;
    color: var(--text-dim);
  }

  /* ── GET STARTED ── */
  #get {
    padding: 100px 60px;
    max-width: 900px;
    margin: 0 auto;
    width: 100%;
    text-align: center;
  }

  .get-box {
    border: 1px solid rgba(0,212,255,0.15);
    padding: 72px 56px;
    background: var(--card-bg);
    position: relative;
    backdrop-filter: blur(12px);
  }

  .get-box::before, .get-box::after {
    content: '';
    position: absolute;
    width: 48px; height: 48px;
    border-color: var(--glow-cyan);
    border-style: solid;
    opacity: 0.4;
  }

  .get-box::before { top: -1px; left: -1px; border-width: 2px 0 0 2px; }
  .get-box::after { bottom: -1px; right: -1px; border-width: 0 2px 2px 0; }

  .get-title {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: clamp(28px, 5vw, 48px);
    letter-spacing: 2px;
    margin-bottom: 16px;
    line-height: 1.1;
  }

  .get-desc {
    font-size: 15px;
    line-height: 1.8;
    color: var(--text-mid);
    max-width: 440px;
    margin: 0 auto 48px;
  }

  .get-steps {
    display: flex;
    justify-content: center;
    gap: 0;
    margin-bottom: 48px;
    flex-wrap: wrap;
  }

  .step {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    padding: 0 32px;
    position: relative;
  }

  .step:not(:last-child)::after {
    content: '';
    position: absolute;
    right: 0; top: 20px;
    width: 1px; height: 20px;
    background: rgba(0,212,255,0.2);
  }

  .step-num {
    width: 40px; height: 40px;
    border: 1px solid rgba(0,212,255,0.4);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Orbitron', sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: var(--glow-cyan);
  }

  .step-label {
    font-size: 12px;
    color: var(--text-mid);
    letter-spacing: 1px;
    font-weight: 500;
  }

  .get-cta { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }

  /* ── FOOTER ── */
  footer {
    padding: 40px 60px;
    border-top: 1px solid rgba(255,255,255,0.05);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 16px;
  }

  .footer-brand {
    font-family: 'Orbitron', sans-serif;
    font-size: 13px;
    letter-spacing: 4px;
    color: rgba(255,255,255,0.2);
  }

  .footer-studio {
    font-size: 12px;
    color: var(--text-dim);
    letter-spacing: 1px;
  }

  .footer-studio span {
    color: var(--glow-cyan);
    font-weight: 600;
  }

  /* ── DIVIDER ── */
  .divider {
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,212,255,0.15), transparent);
    max-width: 1100px;
    margin: 0 auto;
  }

  /* ── GLOW BLOBS ── */
  .blob {
    position: fixed;
    border-radius: 50%;
    pointer-events: none;
    z-index: 0;
    filter: blur(120px);
    opacity: 0.06;
  }

  .blob-1 { width: 600px; height: 600px; background: var(--glow-cyan); top: -200px; left: -200px; }
  .blob-2 { width: 500px; height: 500px; background: var(--glow-purple); bottom: 100px; right: -150px; }

  /* ── SCAN LINE ── */
  .scan-line {
    position: fixed;
    left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(0,212,255,0.25), transparent);
    animation: scan 10s linear infinite;
    z-index: 1;
    pointer-events: none;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes scan {
    from { top: -2px; }
    to { top: 100%; }
  }

  ::-webkit-scrollbar { width: 3px; }
  ::-webkit-scrollbar-track { background: var(--void); }
  ::-webkit-scrollbar-thumb { background: rgba(0,212,255,0.3); }
</style>
</head>
<body>

<canvas id="starfield"></canvas>
<div class="blob blob-1"></div>
<div class="blob blob-2"></div>
<div class="scan-line"></div>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">
    <div class="logo-orb"></div>
    <span class="logo-text">SOLARBOX</span>
  </a>
  <div class="nav-right">
    <a href="#what" class="nav-link">About</a>
    <a href="#features" class="nav-link">Features</a>
    <a href="#get" class="nav-link">Get Started</a>
    <a href="https://neonmonkalt.itch.io/solarbox" target="_blank" class="nav-btn">Download</a>
  </div>
</nav>

<!-- HERO -->
<section id="hero" class="layer">
  <div class="hero-tag">Free to Play — Now in Development</div>
  <h1 class="hero-title">SOLARBOX</h1>
  <p class="hero-tagline">Build spaceships. <strong>Explore the galaxy.</strong> Find your universe.</p>
  <p class="hero-desc">
    SOLARBOX is a space exploration game where you design your own ships and venture into an infinite, procedurally generated universe. No two playthroughs are the same.
  </p>
  <div class="hero-cta">
    <a href="https://discord.gg/Yttu8Ftvb" target="_blank" class="btn-outline">Join the Community</a>
    <a href="https://neonmonkalt.itch.io/solarbox" target="_blank" class="btn-solid">Download Free on Itch</a>
  </div>
  <div class="scroll-hint">
    <div class="scroll-line"></div>
    Scroll to explore
  </div>
</section>

<div class="divider"></div>

<!-- WHAT IS SOLARBOX -->
<section id="what" class="layer">
  <div style="max-width:1100px;margin:0 auto;width:100%;padding:100px 60px;">
    <div class="what-grid">
      <div>
        <p class="what-label">What is SOLARBOX?</p>
        <h2 class="what-title">A universe built for<br>builders and explorers</h2>
        <p class="what-body">
          SOLARBOX is a <strong>3D space game</strong> set in an endlessly generated galaxy. You start with nothing and work your way up — discovering planets, gathering resources, and constructing ships piece by piece.
        </p>
        <p class="what-body">
          Whether you want to quietly explore distant star systems or build the most powerful ship in the cosmos, <strong>the universe is yours to shape</strong>.
        </p>
        <div class="what-pills">
          <span class="pill">Windows</span>
          <span class="pill">Free to Play</span>
          <span class="pill">In Development</span>
          <span class="pill">3D Space Game</span>
        </div>
      </div>
      <div class="what-visual">
        <div class="orbit-ring"><div class="orbit-dot"></div></div>
        <div class="orbit-ring"><div class="orbit-dot"></div></div>
        <div class="planet"></div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- FEATURES -->
<section id="features" class="layer">
  <div class="section-header">
    <p class="section-label">What you can do</p>
    <h2 class="section-title">Core Features</h2>
    <p class="section-sub">Everything you need to know about what SOLARBOX has to offer right now and what's coming.</p>
  </div>
  <div class="features-grid">
    <div class="feature-card">
      <span class="feature-num">01</span>
      <h3 class="feature-title">Spaceship Builder</h3>
      <p class="feature-text">Snap together modular parts to design your own ship. Change the shape, size, and layout however you want — then take it for a spin.</p>
    </div>
    <div class="feature-card">
      <span class="feature-num">02</span>
      <h3 class="feature-title">Galaxy Exploration</h3>
      <p class="feature-text">Fly through a vast, procedurally generated galaxy filled with unique star systems, planets, moons, and deep space anomalies.</p>
    </div>
    <div class="feature-card">
      <span class="feature-num">03</span>
      <h3 class="feature-title">Colorful Star Systems</h3>
      <p class="feature-text">Every star is different — from small cool red dwarfs to blazing blue giants. Each one may have its own worlds orbiting around it.</p>
    </div>
    <div class="feature-card">
      <span class="feature-num">04</span>
      <h3 class="feature-title">Realistic Space Visuals</h3>
      <p class="feature-text">Experience stunning nebulae, asteroid belts, and planetary atmospheres rendered in real-time 3D.</p>
    </div>
    <div class="feature-card">
      <span class="feature-num">05</span>
      <h3 class="feature-title">Infinite Universe</h3>
      <p class="feature-text">The game world never repeats. Every time you play, you're looking at a galaxy no one has ever seen before.</p>
    </div>
    <div class="feature-card">
      <span class="feature-num">06</span>
      <h3 class="feature-title">More Coming Soon</h3>
      <p class="feature-text">SOLARBOX is actively in development. New features, systems, and content are being added regularly. Join the Discord to follow progress.</p>
    </div>
  </div>
</section>

<div class="divider" style="margin-top:100px;"></div>

<!-- GET STARTED -->
<section id="get" class="layer">
  <div class="get-box">
    <p class="section-label">Ready to play?</p>
    <h2 class="get-title">Get Started in Minutes</h2>
    <p class="get-desc">SOLARBOX is completely free. Download it, launch it, and you're in space. No account required.</p>
    <div class="get-steps">
      <div class="step">
        <div class="step-num">1</div>
        <span class="step-label">Download</span>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <span class="step-label">Install</span>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <span class="step-label">Explore</span>
      </div>
    </div>
    <div class="get-cta">
      <a href="https://discord.gg/your-invite" target="_blank" class="btn-outline">Join Discord</a>
      <a href="https://neonmonkalt.itch.io/solarbox" target="_blank" class="btn-solid">Download on Itch.io</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span class="footer-brand">SOLARBOX</span>
  <span class="footer-studio">Made by <span>Sink Edge Studio</span></span>
  <span class="footer-studio" style="color:var(--text-dim);">2026 — All rights reserved</span>
</footer>

<script>
const c = document.getElementById('starfield');
const ctx = c.getContext('2d');
let stars = [];

function resize() {
  c.width = window.innerWidth;
  c.height = window.innerHeight;
}

function init() {
  stars = Array.from({ length: 350 }, () => ({
    x: Math.random() * c.width,
    y: Math.random() * c.height,
    r: Math.random() * 1.4 + 0.2,
    a: Math.random() * 0.8 + 0.2,
    speed: Math.random() * 0.4 + 0.05,
    t: Math.random() * Math.PI * 2
  }));
}

function draw() {
  ctx.clearRect(0, 0, c.width, c.height);
  stars.forEach(s => {
    s.t += s.speed * 0.015;
    const alpha = (Math.sin(s.t) * 0.35 + 0.65) * s.a;
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(210, 235, 255, ${alpha})`;
    ctx.fill();
  });
  requestAnimationFrame(draw);
}

window.addEventListener('resize', () => { resize(); init(); });
resize(); init(); draw();
</script>
</body>
</html>
