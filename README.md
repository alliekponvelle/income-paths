<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Before You Start — COdex Academy</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&family=Manrope:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #12081d;
      --panel: rgba(248, 239, 221, 0.97);
      --panel-soft: rgba(255, 248, 234, 0.86);
      --text: #2e1a40;
      --muted: #66507b;
      --purple: #71419b;
      --purple-deep: #29123f;
      --purple-mid: #4a2870;
      --gold: #d7b15c;
      --gold-light: #f1d590;
      --gold-deep: #9b7427;
      --gold-pale: rgba(215, 177, 92, 0.14);
      --line: rgba(113, 65, 155, 0.12);
      --shadow: 0 24px 60px rgba(8, 2, 15, 0.35);
      --shadow-soft: 0 8px 32px rgba(8, 2, 15, 0.18);
      --radius: 28px;
      --radius-sm: 20px;
      --radius-xs: 12px;
    }

    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: "Manrope", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(215, 177, 92, 0.12), transparent 22%),
        radial-gradient(circle at 85% 15%, rgba(113, 65, 155, 0.24), transparent 24%),
        linear-gradient(160deg, #0f0618 0%, #1c0c2c 38%, #30124b 72%, #12081d 100%);
      color: #f9f0dc;
      line-height: 1.6;
      min-height: 100vh;
    }

    /* ── Reading Progress ── */
    .progress-wrap {
      position: fixed; top: 0; left: 0; right: 0; height: 3px;
      background: rgba(255,255,255,0.07); z-index: 999;
    }
    .progress-bar {
      height: 100%;
      background: linear-gradient(90deg, var(--purple), var(--gold));
      width: 0%; transition: width 80ms linear;
    }

    /* ── Sticky Nav ── */
    .nav {
      position: sticky; top: 3px; z-index: 100;
      display: flex; align-items: center; gap: 4px;
      padding: 10px 20px;
      background: rgba(14, 6, 24, 0.94);
      backdrop-filter: blur(18px);
      border-bottom: 1px solid rgba(113, 65, 155, 0.18);
      overflow-x: auto; scrollbar-width: none;
    }
    .nav::-webkit-scrollbar { display: none; }
    .nav-brand {
      font-family: "Cinzel", serif; font-size: 0.88rem; font-weight: 700;
      color: var(--gold); letter-spacing: 0.1em; margin-right: 10px;
      white-space: nowrap; flex-shrink: 0;
    }
    .nav-sep { width: 1px; height: 18px; background: rgba(215,177,92,0.2); flex-shrink: 0; margin: 0 4px; }
    .nav-link {
      display: inline-flex; align-items: center; gap: 5px;
      padding: 6px 13px; border-radius: 999px;
      font-size: 0.78rem; font-weight: 700; letter-spacing: 0.03em;
      text-decoration: none; color: rgba(255, 240, 210, 0.65);
      white-space: nowrap; transition: background 150ms, color 150ms;
      flex-shrink: 0;
    }
    .nav-link:hover { background: rgba(255,255,255,0.09); color: #fff5dd; }

    /* ── Page Wrapper ── */
    .page {
      width: min(1200px, calc(100% - 32px));
      margin: 0 auto;
      padding: 0 0 80px;
    }

    /* ── Hero ── */
    .hero {
      position: relative; overflow: hidden;
      padding: 72px 52px 60px;
      border-radius: 0 0 42px 42px;
      background: linear-gradient(140deg, #160920 0%, #341552 34%, #71419b 68%, #c9a24e 100%);
      box-shadow: var(--shadow); isolation: isolate;
    }
    .hero::before {
      content: ""; position: absolute;
      width: 460px; height: 460px; border-radius: 50%;
      background: radial-gradient(circle, rgba(255,255,255,0.06), transparent 70%);
      top: -180px; right: -120px; z-index: -1;
    }
    .hero::after {
      content: ""; position: absolute;
      width: 220px; height: 220px; border-radius: 50%;
      background: rgba(215, 177, 92, 0.09); filter: blur(50px);
      bottom: -50px; left: 60px; z-index: -1;
    }

    .eyebrow {
      display: inline-flex; padding: 8px 18px; border-radius: 999px;
      background: rgba(255,255,255,0.13); border: 1px solid rgba(255,255,255,0.2);
      font-size: 10.5px; font-weight: 800; letter-spacing: 0.2em;
      text-transform: uppercase; color: rgba(255,248,225,0.88);
    }

    h1, h2, h3 { margin: 0; font-family: "Cinzel", serif; letter-spacing: 0.02em; }

    h1 {
      margin-top: 22px;
      font-size: clamp(3rem, 8vw, 5.6rem);
      font-weight: 700; line-height: 0.93; max-width: 12ch;
    }
    .hero-sub {
      max-width: 58ch; margin: 22px 0 28px;
      font-size: 1.06rem; font-weight: 500;
      color: rgba(255, 248, 235, 0.88); line-height: 1.7;
    }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 8px; }

    .btn, .btn-ghost, .btn-gold {
      display: inline-flex; align-items: center; justify-content: center; gap: 7px;
      text-decoration: none; padding: 13px 22px; border-radius: 999px;
      font-weight: 800; font-size: 0.88rem; letter-spacing: 0.02em;
      transition: transform 180ms, box-shadow 180ms;
    }
    .btn { background: linear-gradient(135deg, #28113d, #71419b); color: #fff4de; box-shadow: 0 12px 28px rgba(25,8,44,0.3); }
    .btn-ghost { background: rgba(255,255,255,0.13); color: #fff4de; border: 1px solid rgba(255,255,255,0.2); }
    .btn-gold { background: linear-gradient(135deg, #9b7427, #d7b15c); color: #29123f; box-shadow: 0 12px 28px rgba(155,116,39,0.28); }
    .btn:hover, .btn-ghost:hover, .btn-gold:hover { transform: translateY(-2px); }

    .hero-stats {
      display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; margin-top: 44px;
    }
    .hero-stat {
      padding: 18px; border-radius: 20px;
      background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.15);
      backdrop-filter: blur(8px);
    }
    .stat-num {
      display: block; font-family: "Cinzel", serif;
      font-size: 1.7rem; font-weight: 700; color: var(--gold-light);
      line-height: 1; margin-bottom: 6px;
    }
    .stat-label { display: block; font-size: 0.84rem; font-weight: 800; color: rgba(255,248,225,0.88); margin-bottom: 4px; }
    .stat-desc { display: block; font-size: 0.77rem; color: rgba(255,240,210,0.58); line-height: 1.45; }

    /* ── Shared Panel / Section ── */
    .section {
      margin-top: 20px; padding: 38px;
      background: var(--panel); color: var(--text);
      border-radius: var(--radius); border: 1px solid rgba(255,255,255,0.26);
      box-shadow: var(--shadow);
    }
    .notice-panel {
      margin-top: 20px; padding: 22px 28px;
      background: var(--panel); color: var(--text);
      border-radius: var(--radius); border: 1px solid rgba(255,255,255,0.26);
      border-left: 5px solid var(--gold);
      box-shadow: var(--shadow-soft);
      font-size: 1.02rem; line-height: 1.75;
    }
    .notice-panel strong { color: var(--gold-deep); }

    .section-tag {
      display: inline-flex; align-items: center; gap: 6px;
      padding: 6px 14px; border-radius: 999px;
      background: var(--gold-pale); color: var(--purple);
      font-size: 10.5px; font-weight: 800; letter-spacing: 0.14em;
      text-transform: uppercase; margin-bottom: 16px;
    }
    .section h2 {
      font-size: clamp(1.9rem, 4vw, 2.85rem);
      color: var(--purple-deep); line-height: 1.02; margin-bottom: 14px;
    }
    .section-lead {
      font-size: 1.02rem; color: var(--muted);
      max-width: 70ch; margin: 0 0 26px; line-height: 1.72;
    }

    /* ── Grids ── */
    .grid-2 { display: grid; grid-template-columns: repeat(2, 1fr); gap: 18px; margin-top: 22px; }
    .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; margin-top: 22px; }
    .grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; margin-top: 20px; }

    /* ── Cards ── */
    .card {
      background: var(--panel-soft);
      border: 1px solid var(--line);
      border-radius: var(--radius-sm); padding: 22px;
    }
    .card-accent { border-top: 4px solid var(--purple); }
    .card-gold { border-top: 4px solid var(--gold); }
    .card h3 { font-size: 1.08rem; color: var(--purple-deep); margin-bottom: 10px; }
    .card p { font-size: 0.9rem; color: var(--muted); margin: 0 0 10px; line-height: 1.62; }
    .card p:last-child { margin-bottom: 0; }
    .card-icon {
      width: 44px; height: 44px; border-radius: 14px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.25rem; margin-bottom: 14px; background: var(--gold-pale);
    }

    /* ── Steps ── */
    .steps { display: grid; gap: 0; margin-top: 26px; }
    .step {
      display: grid; grid-template-columns: 58px 1fr; gap: 20px;
      padding: 22px 0; border-bottom: 1px solid var(--line); align-items: start;
    }
    .step:last-child { border-bottom: none; padding-bottom: 0; }
    .step-num {
      width: 46px; height: 46px; border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-family: "Cinzel", serif; font-size: 1rem; font-weight: 700;
      color: var(--purple-deep);
      background: linear-gradient(135deg, var(--gold), var(--gold-light));
      flex-shrink: 0; box-shadow: 0 4px 14px rgba(155, 116, 39, 0.22);
    }
    .step-body h3 { font-size: 1.05rem; color: var(--purple-deep); margin-bottom: 7px; }
    .step-body p { font-size: 0.9rem; color: var(--muted); margin: 0; line-height: 1.65; }

    /* ── Callout / Quote ── */
    .callout {
      margin-top: 22px; padding: 20px 24px; border-radius: var(--radius-sm);
      background: linear-gradient(135deg, rgba(215,177,92,0.16), rgba(113,65,155,0.07));
      border: 1px solid rgba(215,177,92,0.24);
      color: var(--purple-deep); font-weight: 600; font-size: 0.95rem; line-height: 1.65;
    }
    .callout.purple {
      background: linear-gradient(135deg, rgba(113,65,155,0.1), rgba(41,18,63,0.05));
      border-color: rgba(113,65,155,0.2);
    }

    /* ── Notice ── */
    .inline-notice {
      margin-top: 18px; padding: 15px 18px; border-radius: var(--radius-xs);
      border-left: 4px solid var(--gold); background: rgba(215,177,92,0.08);
      font-size: 0.9rem; color: var(--text); line-height: 1.6;
    }
    .inline-notice strong { color: var(--gold-deep); }

    /* ── Check Lists ── */
    .check-list { display: grid; gap: 12px; margin: 16px 0 0; }
    .check-item { display: flex; align-items: flex-start; gap: 11px; }
    .check-dot {
      width: 26px; height: 26px; border-radius: 50%; flex-shrink: 0;
      display: flex; align-items: center; justify-content: center;
      background: linear-gradient(135deg, var(--gold), var(--gold-light));
      color: var(--purple-deep); font-size: 0.75rem; font-weight: 900;
      box-shadow: 0 3px 8px rgba(155,116,39,0.18);
    }
    .check-title { font-size: 0.92rem; font-weight: 700; color: var(--text); display: block; line-height: 1.4; }
    .check-desc { font-size: 0.84rem; color: var(--muted); display: block; margin-top: 2px; line-height: 1.45; }

    /* ── Interactive Checklist ── */
    .ci-wrap { margin-top: 4px; }
    .ci {
      display: flex; align-items: flex-start; gap: 13px;
      padding: 14px 16px; border-radius: var(--radius-xs);
      border: 1px solid var(--line); background: var(--panel-soft);
      margin-bottom: 9px; cursor: pointer;
      transition: background 130ms, border-color 130ms; user-select: none;
    }
    .ci:hover { border-color: rgba(113,65,155,0.22); }
    .ci.done { background: rgba(113,65,155,0.055); border-color: rgba(113,65,155,0.18); }
    .ci.done .ci-title { text-decoration: line-through; color: var(--muted); }
    .ci-box {
      width: 24px; height: 24px; border-radius: 7px; flex-shrink: 0;
      border: 2px solid rgba(113,65,155,0.28);
      display: flex; align-items: center; justify-content: center;
      font-size: 0.78rem; color: transparent;
      transition: all 140ms;
    }
    .ci.done .ci-box { background: var(--purple); border-color: var(--purple); color: white; }
    .ci-title { font-weight: 700; font-size: 0.91rem; color: var(--text); display: block; line-height: 1.4; }
    .ci-note { font-size: 0.82rem; color: var(--muted); display: block; margin-top: 3px; line-height: 1.4; }

    /* ── Timeline ── */
    .timeline { display: grid; gap: 18px; margin-top: 24px; }
    .tl-row { display: grid; grid-template-columns: 82px 1fr; gap: 18px; align-items: start; }
    .tl-day {
      text-align: center; padding: 11px 8px; border-radius: var(--radius-xs);
      background: linear-gradient(135deg, rgba(215,177,92,0.18), rgba(113,65,155,0.1));
      border: 1px solid rgba(215,177,92,0.2); flex-shrink: 0;
    }
    .tl-day-label { font-size: 0.67rem; font-weight: 800; letter-spacing: 0.12em; text-transform: uppercase; color: var(--gold-deep); display: block; }
    .tl-day-num { font-family: "Cinzel", serif; font-size: 1.4rem; font-weight: 700; color: var(--purple-deep); display: block; line-height: 1; margin: 2px 0; }
    .tl-body h3 { font-size: 1rem; color: var(--purple-deep); margin-bottom: 6px; }
    .tl-body p { font-size: 0.88rem; color: var(--muted); margin: 0 0 10px; line-height: 1.62; }
    .tl-tags { display: flex; flex-wrap: wrap; gap: 6px; }
    .tl-tag {
      padding: 3px 10px; border-radius: 6px;
      background: var(--gold-pale); color: var(--purple-deep);
      font-size: 0.77rem; font-weight: 700;
    }

    /* ── Vault Items ── */
    .vault-item {
      display: flex; gap: 14px; align-items: flex-start;
      padding: 18px; border-radius: var(--radius-sm);
      background: var(--panel-soft); border: 1px solid var(--line);
    }
    .vault-icon {
      width: 42px; height: 42px; border-radius: 13px; flex-shrink: 0;
      background: linear-gradient(135deg, var(--gold-pale), rgba(113,65,155,0.08));
      display: flex; align-items: center; justify-content: center; font-size: 1.15rem;
    }
    .vault-body h3 { font-size: 0.96rem; color: var(--purple-deep); margin-bottom: 6px; }
    .vault-body p { font-size: 0.85rem; color: var(--muted); margin: 0 0 9px; line-height: 1.58; }
    .vault-tag {
      display: inline-flex; padding: 2px 10px; border-radius: 999px;
      background: var(--gold-pale); color: var(--gold-deep);
      font-size: 0.74rem; font-weight: 800;
    }

    /* ── Path Cards ── */
    .path-card {
      background: var(--panel-soft); border: 1px solid var(--line);
      border-radius: var(--radius-sm); padding: 24px;
      border-top: 5px solid var(--purple);
    }
    .path-card.gold-top { border-top-color: var(--gold); }
    .path-card.teal-top { border-top-color: #5a9b8e; }
    .path-badge {
      display: inline-flex; padding: 4px 11px; border-radius: 999px;
      font-size: 10px; font-weight: 800; letter-spacing: 0.1em;
      text-transform: uppercase; margin-bottom: 12px;
    }
    .path-badge.pb-purple { background: rgba(113,65,155,0.11); color: var(--purple); }
    .path-badge.pb-gold { background: rgba(215,177,92,0.18); color: var(--gold-deep); }
    .path-badge.pb-teal { background: rgba(90,155,142,0.12); color: #3d7a6e; }
    .path-card h3 { font-size: 1.22rem; color: var(--purple-deep); margin-bottom: 9px; }
    .path-desc { font-size: 0.9rem; color: var(--muted); margin: 0 0 18px; line-height: 1.62; }
    .path-rows { display: grid; gap: 9px; margin-top: 14px; }
    .path-row { display: flex; gap: 10px; font-size: 0.86rem; line-height: 1.48; }
    .pr-label { font-weight: 800; color: var(--purple-deep); min-width: 92px; flex-shrink: 0; }
    .pr-val { color: var(--muted); }
    .path-mods { margin-top: 16px; padding-top: 16px; border-top: 1px solid var(--line); }
    .path-mods h4 {
      font-size: 0.8rem; font-weight: 800; letter-spacing: 0.1em;
      text-transform: uppercase; color: var(--purple); margin: 0 0 10px;
    }
    .mod-tag {
      display: inline-flex; padding: 3px 10px; border-radius: 6px;
      background: rgba(113,65,155,0.08); color: var(--purple-deep);
      font-size: 0.78rem; font-weight: 700; margin: 3px 3px 3px 0;
    }

    /* ── Mistake Cards ── */
    .mistake {
      padding: 20px; border-radius: var(--radius-sm);
      background: var(--panel-soft); border: 1px solid var(--line);
      border-left: 4px solid #c86060;
    }
    .mistake h3 { font-size: 0.98rem; color: var(--purple-deep); margin-bottom: 8px; }
    .mistake p { font-size: 0.87rem; color: var(--muted); margin: 0 0 11px; line-height: 1.62; }
    .instead {
      padding: 10px 14px; border-radius: var(--radius-xs);
      background: rgba(113,65,155,0.07); border-left: 3px solid var(--purple);
      font-size: 0.84rem; font-weight: 700; color: var(--purple-deep);
    }
    .instead::before { content: "✓  Instead: "; color: var(--purple); }

    /* ── FAQ ── */
    details.faq { border-bottom: 1px solid var(--line); }
    details.faq summary {
      display: flex; justify-content: space-between; align-items: center; gap: 16px;
      padding: 18px 0; cursor: pointer; font-weight: 700; font-size: 0.96rem;
      color: var(--text); list-style: none; user-select: none;
      transition: color 150ms;
    }
    details.faq summary:hover { color: var(--purple); }
    details.faq summary::-webkit-details-marker { display: none; }
    .faq-arrow {
      width: 28px; height: 28px; border-radius: 50%; background: var(--gold-pale);
      display: flex; align-items: center; justify-content: center;
      font-size: 0.72rem; color: var(--purple); flex-shrink: 0;
      transition: transform 200ms;
    }
    details.faq[open] .faq-arrow { transform: rotate(180deg); }
    .faq-body { padding: 0 0 18px; font-size: 0.9rem; color: var(--muted); line-height: 1.72; }

    /* ── Divider ── */
    .divider { height: 1px; background: linear-gradient(90deg, transparent, rgba(215,177,92,0.22), transparent); margin: 28px 0; }

    /* ── CTA ── */
    .cta {
      margin-top: 20px; padding: 52px 40px; text-align: center;
      background: linear-gradient(140deg, rgba(41,18,63,0.98), rgba(100,55,145,0.96));
      color: #fff4de; border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,0.12); box-shadow: var(--shadow);
    }
    .cta h2 { font-size: clamp(2rem, 5vw, 3.2rem); margin-bottom: 16px; }
    .cta p { max-width: 60ch; margin: 0 auto 30px; color: rgba(255,243,221,0.86); font-size: 1.04rem; line-height: 1.72; }
    .cta-actions { display: flex; flex-wrap: wrap; justify-content: center; gap: 13px; }

    /* ── Responsive ── */
    @media (max-width: 980px) {
      .hero-stats, .grid-4 { grid-template-columns: repeat(2, 1fr); }
      .grid-3 { grid-template-columns: repeat(2, 1fr); }
    }
    @media (max-width: 720px) {
      .hero { padding: 50px 26px 44px; }
      .section { padding: 28px 22px; }
      .nav { padding: 9px 14px; }
    }
    @media (max-width: 640px) {
      .hero-stats, .grid-4, .grid-3, .grid-2 { grid-template-columns: 1fr; }
      .tl-row { grid-template-columns: 66px 1fr; }
      .hero-actions, .cta-actions { flex-direction: column; align-items: stretch; }
      .step { grid-template-columns: 50px 1fr; }
    }
  </style>
</head>
<body>

<!-- Reading Progress Bar -->
<div class="progress-wrap"><div class="progress-bar" id="progressBar"></div></div>

<!-- Sticky Navigation -->
<nav class="nav">
  <span class="nav-brand">COdex</span>
  <span class="nav-sep"></span>
  <a class="nav-link" href="#how">🗺 How It Works</a>
  <a class="nav-link" href="#start">🏁 Where to Start</a>
  <a class="nav-link" href="#week-one">📅 First 7 Days</a>
  <a class="nav-link" href="#vault">🗃 Vault</a>
  <a class="nav-link" href="#support">💬 Support</a>
  <a class="nav-link" href="#paths">🛤 Paths</a>
  <a class="nav-link" href="#mistakes">⚠️ Mistakes</a>
  <a class="nav-link" href="#checklist">✅ Checklist</a>
  <a class="nav-link" href="#faq">❓ FAQ</a>
</nav>

<div class="page">

  <!-- ═══════════════════════════════ HERO ═══════════════════════════════ -->
  <section class="hero">
    <span class="eyebrow">COdex Academy &mdash; Welcome</span>
    <h1>Before You<br>Start</h1>
    <p class="hero-sub">
      Take five minutes to read this page. It will save you hours of confusion, give you the clearest path forward inside the academy, and make sure you start in the right place instead of jumping around and getting overwhelmed.
    </p>
    <div class="hero-actions">
      <a class="btn" href="#start">🏁 Start Here First</a>
      <a class="btn-ghost" href="#paths">🛤 See the Paths</a>
      <a class="btn-gold" href="#checklist">✅ Jump to Checklist</a>
    </div>
    <div class="hero-stats">
      <div class="hero-stat">
        <span class="stat-num">2</span>
        <span class="stat-label">Start Simple</span>
        <span class="stat-desc">Just the first two sections. No jumping around.</span>
      </div>
      <div class="hero-stat">
        <span class="stat-num">3</span>
        <span class="stat-label">Paths Available</span>
        <span class="stat-desc">Creator, Digital Product, Ecommerce — pick one and go.</span>
      </div>
      <div class="hero-stat">
        <span class="stat-num">1</span>
        <span class="stat-label">The Focus Rule</span>
        <span class="stat-desc">One income stream first. Build it right, then expand.</span>
      </div>
      <div class="hero-stat">
        <span class="stat-num">7</span>
        <span class="stat-label">Days to Launch</span>
        <span class="stat-desc">Follow the First 7 Days plan to reach your first milestone.</span>
      </div>
    </div>
  </section>

  <!-- Lead Notice -->
  <div class="notice-panel">
    This academy is designed to reduce overwhelm and eliminate confusion. <strong>You do not need to do everything at once.</strong> You need to know where to begin, where to find support, and which path you are focusing on first. The rest follows naturally once you have momentum.
  </div>

  <!-- ═══════════════════════════ HOW IT WORKS ═══════════════════════════ -->
  <section class="section" id="how">
    <div class="section-tag">🗺 Overview</div>
    <h2>How This Academy Works</h2>
    <p class="section-lead">The COdex Academy is organized into a clear, step-by-step system. Understanding the structure before you dive in is what separates people who make consistent progress from people who feel lost. Here is exactly how everything connects.</p>

    <div class="steps">
      <div class="step">
        <div class="step-num">1</div>
        <div class="step-body">
          <h3>Read This Page in Full</h3>
          <p>This orientation page is your map. Understand the structure, choose your path, and know where to start before opening anything else. This single step eliminates the majority of the confusion new members experience in their first week.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <div class="step-body">
          <h3>Complete the Start Here Section</h3>
          <p>The Start Here module is your full orientation. It explains how the academy is structured, what each section covers, and why the order you work through the content matters. Do not skip it — it gives you the mental framework everything else builds on.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <div class="step-body">
          <h3>Work Through the Creator Plug Launch Challenge</h3>
          <p>This is your launchpad. It is a structured, action-based challenge designed to get you doing real things immediately — instead of planning indefinitely. Each task builds on the one before. It teaches the execution habit that every other module in the academy requires.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">4</div>
        <div class="step-body">
          <h3>Commit to One Income Path</h3>
          <p>After completing the launch challenge, choose one of the three paths: Creator, Digital Product, or Ecommerce/Service. Read the full path descriptions before deciding. Once you choose, commit fully. That path determines which modules you focus on next. Do not try to pursue two paths at the same time.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">5</div>
        <div class="step-body">
          <h3>Work Through Your Path's Modules in Order</h3>
          <p>Each path has specific modules assigned to it. Work through them in the order they are presented. The sequence is intentional — each module builds on the one before it, and going out of order often leads to confusion and rework. Resist the urge to skip ahead.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">6</div>
        <div class="step-body">
          <h3>Use the Vault and Support as You Go</h3>
          <p>While working through your modules, use the Template Vault for ready-made resources — prompts, scripts, templates, sales pages, and planning tools. Use the Coaching Hub and Community when you need help, accountability, or motivation. These exist so you never feel stuck or alone in the process.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">7</div>
        <div class="step-body">
          <h3>Launch Your First Income Stream</h3>
          <p>Your goal at the end of this phase is to complete the modules for your chosen path and launch your first income stream — your first content system, your first product, or your first paying client. Focus on reaching this milestone before anything else. A working foundation is worth more than a half-built everything.</p>
        </div>
      </div>
      <div class="step">
        <div class="step-num">8</div>
        <div class="step-body">
          <h3>Expand Once the Foundation Is Working</h3>
          <p>Once you have consistent results from your first path — whether that is steady content, a selling product, or repeat clients — you can revisit the other paths and begin layering in additional income streams. The academy is designed to grow with you at every stage.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════ WHERE TO START ═══════════════════════════ -->
  <section class="section" id="start">
    <div class="section-tag">🏁 Getting Started</div>
    <h2>Where You Should Start</h2>
    <p class="section-lead">Always start with the foundation. These first two sections are your mandatory starting point — they give you the right order, the right momentum, and the clearest next moves. Do not skip ahead to other modules before these are complete.</p>

    <div class="grid-2">
      <div class="card card-accent">
        <div class="card-icon">📍</div>
        <h3>Step 1 — The Start Here Section</h3>
        <p>This is your orientation module. It shows you the big picture of the entire program, explains how all the pieces connect, and makes sure you have a clear mental model of the academy before you go any deeper.</p>
        <div class="check-list">
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Understand the full layout of the program</span>
              <span class="check-desc">Know what modules exist, what each section covers, and why the order matters</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Get a step-by-step view of the academy structure</span>
              <span class="check-desc">Build a mental map of the whole system so nothing catches you off guard later</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Set realistic expectations for your journey</span>
              <span class="check-desc">Know what results are realistic, what time frames look like, and what consistent effort produces</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Understand how to use the academy correctly</span>
              <span class="check-desc">Learn how modules, the Vault, coaching, and the community all work together as one system</span>
            </div>
          </div>
        </div>
      </div>

      <div class="card card-gold">
        <div class="card-icon">🚀</div>
        <h3>Step 2 — Creator Plug Launch Challenge</h3>
        <p>This is your action module. It is specifically designed to stop you from planning and get you doing. Every task in the challenge produces a real, tangible result — not just more information to sit with.</p>
        <div class="check-list">
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Follow the challenge tasks in the exact order given</span>
              <span class="check-desc">Each task is designed to build on the previous one — the sequence is deliberate, not random</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Use it to build your first real momentum</span>
              <span class="check-desc">Momentum is a skill. The challenge teaches you how to generate it and keep it going</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Complete every task — skip nothing</span>
              <span class="check-desc">Even the small tasks matter. They build the identity of someone who follows through</span>
            </div>
          </div>
          <div class="check-item">
            <span class="check-dot">→</span>
            <div>
              <span class="check-title">Treat this as your formal entry into the program</span>
              <span class="check-desc">Finishing this challenge signals to yourself that you are here to build, not just to browse</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="callout">
      💡 <strong>Not sure where to begin?</strong> The answer is always the same: open the <strong>Start Here</strong> section first, then go directly to the <strong>Creator Plug Launch Challenge</strong>. Do not start anywhere else. Do not explore other modules yet. Just these two.
    </div>

    <div class="inline-notice">
      <strong>A note on feeling overwhelmed:</strong> If opening the academy feels like a lot, that reaction is completely normal — and it is exactly why this page exists. You do not have to do everything. You have to do <strong>two things</strong>: the Start Here section, then the Launch Challenge. Everything else waits until those are done.
    </div>
  </section>

  <!-- ═══════════════════════════ FIRST 7 DAYS ═══════════════════════════ -->
  <section class="section" id="week-one">
    <div class="section-tag">📅 Your First Week</div>
    <h2>What to Do in Your First 7 Days</h2>
    <p class="section-lead">This is the fastest path from joining the academy to having real results and real momentum. Follow this plan and you will end your first week with a solid foundation, a clear direction, and more progress than most people make in a month.</p>

    <div class="timeline">
      <div class="tl-row">
        <div class="tl-day">
          <span class="tl-day-label">Day</span>
          <span class="tl-day-num">1</span>
        </div>
        <div class="tl-body">
          <h3>Orient Yourself — Read Everything Before You Act</h3>
          <p>Read this page from top to bottom. Go through the Start Here section completely. Do not touch any other module yet. Understanding the system before you act is what separates people who build quickly from people who restart repeatedly.</p>
          <div class="tl-tags">
            <span class="tl-tag">Read Before You Start</span>
            <span class="tl-tag">Complete Start Here</span>
            <span class="tl-tag">Decide on a path</span>
          </div>
        </div>
      </div>

      <div class="tl-row">
        <div class="tl-day">
          <span class="tl-day-label">Days</span>
          <span class="tl-day-num">2–3</span>
        </div>
        <div class="tl-body">
          <h3>Begin the Creator Plug Launch Challenge</h3>
          <p>Open the challenge and start working through it task by task. Set a timer if you need to. Take each task seriously — do not skim or rush. If you cannot finish everything in one sitting, that is fine. Stop at a natural break point and pick it back up tomorrow without skipping anything.</p>
          <div class="tl-tags">
            <span class="tl-tag">Begin Launch Challenge</span>
            <span class="tl-tag">Complete first 3 tasks</span>
            <span class="tl-tag">Introduce yourself in the community</span>
          </div>
        </div>
      </div>

      <div class="tl-row">
        <div class="tl-day">
          <span class="tl-day-label">Day</span>
          <span class="tl-day-num">4</span>
        </div>
        <div class="tl-body">
          <h3>Finish the Launch Challenge</h3>
          <p>Complete every remaining task in the challenge. By the end of today you will have taken more concrete action than most people take in their first month inside an online program. That difference is what builds real confidence and forward motion.</p>
          <div class="tl-tags">
            <span class="tl-tag">Finish all challenge tasks</span>
            <span class="tl-tag">Explore the Vault</span>
            <span class="tl-tag">Post a win in the community</span>
          </div>
        </div>
      </div>

      <div class="tl-row">
        <div class="tl-day">
          <span class="tl-day-label">Day</span>
          <span class="tl-day-num">5</span>
        </div>
        <div class="tl-body">
          <h3>Commit to Your Path and Start Module 1</h3>
          <p>With the foundation complete, officially commit to one path: Creator, Digital Product, or Ecommerce/Service. Open that path and start working through Module 1. Use the Vault if a template applies to what you are doing. Do not open another path at the same time — this is the most common mistake.</p>
          <div class="tl-tags">
            <span class="tl-tag">Commit to your path</span>
            <span class="tl-tag">Start Module 1</span>
            <span class="tl-tag">Download relevant templates</span>
          </div>
        </div>
      </div>

      <div class="tl-row">
        <div class="tl-day">
          <span class="tl-day-label">Days</span>
          <span class="tl-day-num">6–7</span>
        </div>
        <div class="tl-body">
          <h3>Implement, Show Up, and Share Your Progress</h3>
          <p>Apply what you have learned from Module 1. Then share a win, a question, or a work-in-progress in the community. Attend or watch a coaching session. Sharing your progress publicly makes the work feel real and creates the kind of accountability that keeps you consistent beyond the first week.</p>
          <div class="tl-tags">
            <span class="tl-tag">Complete Module 1 task</span>
            <span class="tl-tag">Share in community</span>
            <span class="tl-tag">Attend a coaching call</span>
            <span class="tl-tag">Plan next week</span>
          </div>
        </div>
      </div>
    </div>

    <div class="callout">
      🎯 <strong>Here is the honest truth:</strong> If you follow this 7-day plan as written, you will be ahead of roughly 80% of people who join online academies. Most people spend their first two weeks watching content and waiting to feel ready. You will already be building. That gap compounds over time.
    </div>
  </section>

  <!-- ═══════════════════════════ VAULT ═══════════════════════════ -->
  <section class="section" id="vault">
    <div class="section-tag">🗃 Resources</div>
    <h2>The Template Vault</h2>
    <p class="section-lead">The Vault is where you go when you need a head start. Instead of building from a blank page, you find the right template, customize it to your situation, and move significantly faster. Here is everything that lives inside and when to use each resource.</p>

    <div class="grid-2">
      <div class="vault-item">
        <div class="vault-icon">📝</div>
        <div class="vault-body">
          <h3>Content Templates</h3>
          <p>Pre-structured frameworks for social media posts, carousels, reel scripts, long-form captions, email newsletters, and content series. Use these when you need to create content quickly, when you are stuck on structure, or when you want a proven format you can fill in and publish.</p>
          <span class="vault-tag">Best for: Daily content creation</span>
        </div>
      </div>

      <div class="vault-item">
        <div class="vault-icon">🤖</div>
        <div class="vault-body">
          <h3>AI Prompts</h3>
          <p>Curated, tested prompts for brainstorming content ideas, writing captions and scripts, generating product descriptions, drafting sales copy, and refining offers. Use these to accelerate your creative process — they reduce the blank-page problem significantly.</p>
          <span class="vault-tag">Best for: Brainstorming and drafting</span>
        </div>
      </div>

      <div class="vault-item">
        <div class="vault-icon">💰</div>
        <div class="vault-body">
          <h3>Sales Page Templates</h3>
          <p>Ready-to-customize sales page layouts and copy frameworks for digital products, courses, coaching packages, and service offers. Use these when you are preparing to launch or sell something and want a professional, proven structure without starting from scratch.</p>
          <span class="vault-tag">Best for: Product and offer launches</span>
        </div>
      </div>

      <div class="vault-item">
        <div class="vault-icon">🎙</div>
        <div class="vault-body">
          <h3>Scripts</h3>
          <p>Word-for-word and fill-in-the-blank scripts for live selling, DM conversations, discovery calls, short-form video hooks, pitching brand deals, and onboarding new clients. Use these when you need to communicate with clarity and confidence in high-stakes situations.</p>
          <span class="vault-tag">Best for: Selling and communication</span>
        </div>
      </div>

      <div class="vault-item">
        <div class="vault-icon">🗂</div>
        <div class="vault-body">
          <h3>Canva Design Templates</h3>
          <p>Done-for-you Canva designs for social media graphics, product mockups, story slides, lead magnets, digital product covers, and promotional materials. Fully editable — add your brand colors, swap the text, and publish without needing design skills.</p>
          <span class="vault-tag">Best for: Visual content and branding</span>
        </div>
      </div>

      <div class="vault-item">
        <div class="vault-icon">📊</div>
        <div class="vault-body">
          <h3>Business Planning Tools</h3>
          <p>Worksheets, content calendars, income trackers, launch planners, offer pricing frameworks, and audience targeting guides. Use these to stay organized, measure your progress objectively, and make decisions based on data instead of guesswork.</p>
          <span class="vault-tag">Best for: Strategy and planning</span>
        </div>
      </div>
    </div>

    <div class="callout">
      📌 <strong>Important:</strong> The Vault is a support tool — not a starting point. Open it when you are working on a specific module and need a resource to complete a task. Do not spend your first session browsing the Vault before you know what you need it for. Use it with a purpose and it will save you enormous amounts of time.
    </div>
  </section>

  <!-- ═══════════════════════════ SUPPORT ═══════════════════════════ -->
  <section class="section" id="support">
    <div class="section-tag">💬 Support</div>
    <h2>Coaching and Community Support</h2>
    <p class="section-lead">You do not have to build this alone. The academy includes two main places to get help, stay accountable, and connect with others doing the exact same work. Here is how each one works and when to use it.</p>

    <div class="grid-2">
      <div class="card card-accent" style="padding: 28px;">
        <div class="card-icon">🏋️</div>
        <h3>Rise and Grind Coaching Hub</h3>
        <p>Your structured accountability and coaching space. Use this when you need daily direction, a coaching session, or assigned tasks that keep you moving forward even on days when motivation is low and action feels hard.</p>
        <div class="check-list">
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Daily motivation and mindset content</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Live and recorded coaching calls</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Accountability tasks to maintain momentum</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Direct guidance on specific challenges you face</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Progress milestones and structured check-ins</span>
          </div>
        </div>
        <div class="inline-notice" style="margin-top: 16px;">
          <strong>Use this when:</strong> You feel stuck, need a structured plan for the day, want to attend a live coaching session, or need someone to tell you clearly what to do next.
        </div>
      </div>

      <div class="card card-gold" style="padding: 28px;">
        <div class="card-icon">🤝</div>
        <h3>The Community</h3>
        <p>Your network of other creators and entrepreneurs at different stages of the same journey. Use this for real answers, honest feedback, shared wins, and the reminder that you are not building in isolation — others are doing this right now alongside you.</p>
        <div class="check-list">
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Ask questions at any level — nothing is too basic</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Share wins and get genuine celebration</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Connect with others on the same path as you</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Get real feedback on your content and ideas</span>
          </div>
          <div class="check-item">
            <span class="check-dot">✓</span>
            <span class="check-title">Find accountability partners and collaborators</span>
          </div>
        </div>
        <div class="inline-notice" style="margin-top: 16px;">
          <strong>Use this when:</strong> You have a question, want honest feedback, hit a milestone worth sharing, or simply want to be around people who are actually doing the work — not just talking about it.
        </div>
      </div>
    </div>

    <div class="callout purple">
      💬 <strong>This is not optional:</strong> The community and coaching are built-in accelerators. People who show up consistently in both spaces make faster progress, stay more consistent, and launch sooner than people who try to go it alone. Use them from day one.
    </div>
  </section>

  <!-- ═══════════════════════════ PATHS ═══════════════════════════ -->
  <section class="section" id="paths">
    <div class="section-tag">🛤 Your Income Path</div>
    <h2>Choose One Path. Build It First.</h2>
    <p class="section-lead">The most important decision you will make in this academy is which income path to start with. Not which is objectively the best — which is best <em>for where you are right now</em>. Read each description carefully, then commit to one and only one until your foundation is working.</p>

    <div class="callout" style="margin-bottom: 26px;">
      ⚠️ <strong>The One Rule:</strong> Do not try to do everything. Choose one path. Build one income stream. Finish the modules. Then expand. One focused path completed fully will always outperform three half-started ones.
    </div>

    <div class="grid-3" style="align-items: start;">

      <\!-- CREATOR PATH -->
      <div class="path-card">
        <span class="path-badge pb-purple">Most Common Start</span>
        <img src="creator-path.jpg" alt="Creator Path — Grow &amp; Monetize Your Audience" style="width:100%; border-radius: 14px; margin-bottom: 16px; display: block; box-shadow: 0 8px 24px rgba(0,0,0,0.15);">
        <h3>Creator Path</h3>
        <p class="path-desc">Build an audience first, then monetize from it. Best if you want to grow a personal brand, create consistent content, build trust with a following, and turn that attention into multiple income streams over time.</p>
        <div class="path-rows">
          <div class="path-row"><span class="pr-label">Best For</span><span class="pr-val">People who want to build a personal brand and turn content into income across multiple platforms</span></div>
          <div class="path-row"><span class="pr-label">Timeline</span><span class="pr-val">30–90 days to first consistent monetized results with daily action</span></div>
          <div class="path-row"><span class="pr-label">First Milestone</span><span class="pr-val">Consistent posting schedule + first affiliate sale or paid collaboration</span></div>
          <div class="path-row"><span class="pr-label">Income Streams</span><span class="pr-val">Affiliate marketing, brand deals, digital products, memberships, UGC</span></div>
          <div class="path-row"><span class="pr-label">Goal</span><span class="pr-val">Build your following and monetize your content</span></div>
        </div>
        <div class="path-mods">
          <h4>Your Modules</h4>
          <span class="mod-tag">Start Here</span>
          <span class="mod-tag">Creator Plug Launch Challenge</span>
          <span class="mod-tag">Audience Growth &amp; Traffic System</span>
          <span class="mod-tag">Content Creation System</span>
          <span class="mod-tag">Live Selling &amp; Streaming System</span>
          <span class="mod-tag">Personal Branding System</span>
          <span class="mod-tag">Creator Store Setup</span>
          <span class="mod-tag">Scaling Your Creator Business</span>
        </div>
      </div>

      <\!-- DIGITAL PRODUCT PATH -->
      <div class="path-card gold-top">
        <span class="path-badge pb-gold">Passive Income Focus</span>
        <img src="digital-product-path.jpg" alt="Digital Product Path — Create &amp; Sell Your Digital Products" style="width:100%; border-radius: 14px; margin-bottom: 16px; display: block; box-shadow: 0 8px 24px rgba(0,0,0,0.15);">
        <h3>Digital Product Path</h3>
        <p class="path-desc">Create a digital asset once and sell it repeatedly. Best if you want to package your knowledge or skills into something people can buy — and generate income without trading your time for money every single time.</p>
        <div class="path-rows">
          <div class="path-row"><span class="pr-label">Best For</span><span class="pr-val">People who want to package their expertise into a scalable product that generates recurring revenue</span></div>
          <div class="path-row"><span class="pr-label">Timeline</span><span class="pr-val">2–4 weeks to create and launch your first product with focused effort</span></div>
          <div class="path-row"><span class="pr-label">First Milestone</span><span class="pr-val">Launch a digital product and make your first sale</span></div>
          <div class="path-row"><span class="pr-label">Income Streams</span><span class="pr-val">Ebooks, courses, templates, digital bundles, paid newsletters, memberships</span></div>
          <div class="path-row"><span class="pr-label">Goal</span><span class="pr-val">Create digital assets that sell</span></div>
        </div>
        <div class="path-mods">
          <h4>Your Modules</h4>
          <span class="mod-tag">Start Here</span>
          <span class="mod-tag">Creator Plug Launch Challenge</span>
          <span class="mod-tag">Creator Store Setup</span>
          <span class="mod-tag">Monetization Systems</span>
          <span class="mod-tag">Sales and Funnels</span>
          <span class="mod-tag">Template Vault</span>
          <span class="mod-tag">Licensing and Legal</span>
        </div>
      </div>

      <\!-- ECOMMERCE / SERVICE PATH -->
      <div class="path-card teal-top">
        <span class="path-badge pb-teal">Fastest First Dollar</span>
        <img src="ecommerce-path.jpg" alt="E-Commerce / Service Path" style="width:100%; border-radius: 14px; margin-bottom: 16px; display: block; box-shadow: 0 8px 24px rgba(0,0,0,0.15);">
        <h3>Ecommerce &amp; Service Path</h3>
        <p class="path-desc">Sell products or offer services online. Best if you want to start earning quickly, build a client-based or product-based business, with the shortest runway from start to your first real payment.</p>
        <div class="path-rows">
          <div class="path-row"><span class="pr-label">Best For</span><span class="pr-val">People who want to sell products, offer services, or build an ecommerce store online</span></div>
          <div class="path-row"><span class="pr-label">Timeline</span><span class="pr-val">1–3 weeks to first paying client or first product sale with consistent outreach</span></div>
          <div class="path-row"><span class="pr-label">First Milestone</span><span class="pr-val">Land your first paying client or make your first product sale</span></div>
          <div class="path-row"><span class="pr-label">Income Streams</span><span class="pr-val">UGC, print-on-demand, Amazon KDP, dropshipping, services, affiliate</span></div>
          <div class="path-row"><span class="pr-label">Goal</span><span class="pr-val">Build your e-commerce or service business</span></div>
        </div>
        <div class="path-mods">
          <h4>Your Modules</h4>
          <span class="mod-tag">Start Here</span>
          <span class="mod-tag">Creator Plug Launch Challenge</span>
          <span class="mod-tag">AI Content Tools</span>
          <span class="mod-tag">UGC Creator System</span>
          <span class="mod-tag">Print-On-Demand Business</span>
          <span class="mod-tag">Amazon KDP Publishing</span>
          <span class="mod-tag">AI Ecommerce &amp; Dropshipping</span>
          <span class="mod-tag">Creator Store Setup</span>
          <span class="mod-tag">Sales and Funnels</span>
          <span class="mod-tag">Bridge Income Streams</span>
        </div>
      </div>

    </div>

    <div class="divider"></div>

    <h3 style="font-size: 1.12rem; color: var(--purple-deep); margin-bottom: 16px; font-family: Cinzel;">Still Not Sure Which Path Is Right for You?</h3>
    <div class="grid-3" style="margin-top: 0;">
      <div class="card">
        <p style="margin-bottom: 6px;"><strong style="color: var(--purple-deep);">You already create content online →</strong></p>
        <p>You have the habit. The Creator Path builds the monetization system around what you are already doing.</p>
      </div>
      <div class="card">
        <p style="margin-bottom: 6px;"><strong style="color: var(--purple-deep);">You have knowledge worth teaching →</strong></p>
        <p>Any skill, story, or system that others want to learn can become a sellable digital product. Start there.</p>
      </div>
      <div class="card">
        <p style="margin-bottom: 6px;"><strong style="color: var(--purple-deep);">You want to earn money as fast as possible →</strong></p>
        <p>The Service Path has the shortest path to a first real result. Build confidence and cash flow there first.</p>
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════ MISTAKES ═══════════════════════════ -->
  <section class="section" id="mistakes">
    <div class="section-tag">⚠️ What to Avoid</div>
    <h2>Common Mistakes to Avoid</h2>
    <p class="section-lead">These are the patterns that most consistently slow people down or cause them to quit. Read through all of them now — not because you will definitely make these mistakes, but so you can recognize them quickly if they start to happen and correct course before they cost you momentum.</p>

    <div class="grid-2" style="align-items: start;">
      <div class="mistake">
        <h3>🔀 Jumping Between Modules Out of Order</h3>
        <p>The modules are sequenced intentionally. Each one builds on what came before. When you skip ahead, you are often building without the foundation the next steps assume you have — which leads to confusion, gaps in understanding, and eventually having to go back anyway.</p>
        <div class="instead">Complete modules in the presented order before exploring advanced sections.</div>
      </div>

      <div class="mistake">
        <h3>🛤 Pursuing Two Paths Simultaneously</h3>
        <p>It seems smart to build multiple income streams at once. In practice, split focus leads to half-built results everywhere, a feeling of being buried under your own goals, and slow progress that feels discouraging instead of energizing. The compound effect only works on things you complete.</p>
        <div class="instead">Commit fully to one path until you have your first real, working result. Then expand.</div>
      </div>

      <div class="mistake">
        <h3>📚 Consuming Content Without Taking Action</h3>
        <p>Watching every video and reading every module feels productive. It is not — not without action attached. Learning without application has zero practical value in business. Modules are not meant to be studied like textbooks. They are instructions. The value comes from doing what they say.</p>
        <div class="instead">Complete the assigned task at the end of every module before moving to the next one.</div>
      </div>

      <div class="mistake">
        <h3>🔄 Waiting Until Everything Is Perfect</h3>
        <p>The product does not have to be perfect. The content does not have to be flawless. The offer does not have to be complete in every detail. Waiting for everything to be ready is indistinguishable from not starting. The market gives you feedback that no amount of planning can replicate.</p>
        <div class="instead">Publish the rough version. Get real feedback. Improve from there. Move fast.</div>
      </div>

      <div class="mistake">
        <h3>🤫 Working Through the Program in Complete Silence</h3>
        <p>Not using the community or coaching means missing out on feedback, accountability, shared knowledge, and connections that accelerate everything. Isolation feels safe but is deeply inefficient. The people progressing fastest in this academy are the ones showing up in both the community and coaching consistently.</p>
        <div class="instead">Post at least once a week in the community. Attend at least one coaching call this month.</div>
      </div>

      <div class="mistake">
        <h3>⏰ Treating the Academy Like a Subscription You Will Get to Later</h3>
        <p>Content that is always available often gets treated as content that can always wait. But wait long enough and motivation fades, momentum never builds, and the program that was supposed to change things just becomes another tab you never open. Treat this like the business investment it is.</p>
        <div class="instead">Block dedicated time in your calendar every single day — even 30 minutes — and protect it.</div>
      </div>
    </div>
  </section>

  <!-- ═══════════════════════════ CHECKLIST ═══════════════════════════ -->
  <section class="section" id="checklist">
    <div class="section-tag">✅ Quick Start Checklist</div>
    <h2>Your Complete Starting Checklist</h2>
    <p class="section-lead">Use this as your master checklist for your first week. Click each item to mark it complete as you go. Follow the order — every item here matters and none of them are optional.</p>

    <div class="grid-2" style="align-items: start;">
      <div>
        <h3 style="font-size: 0.88rem; font-family: Manrope; font-weight: 800; letter-spacing: 0.1em; text-transform: uppercase; color: var(--purple); margin-bottom: 14px;">Foundation — Do These First</h3>
        <div class="ci-wrap">
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Read the full Before You Start page</span>
              <span class="ci-note">Finish reading this page completely before doing anything else in the academy.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Complete the Start Here section</span>
              <span class="ci-note">Work through the orientation module and understand the full structure of the program.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Choose your path and commit to it in writing</span>
              <span class="ci-note">Creator, Digital Product, or Ecommerce. Write down your choice. Say it out loud. Make it real.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Join the community and post an introduction</span>
              <span class="ci-note">Share your name, your path, and one goal. This step costs two minutes and pays back for months.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Block time in your calendar for daily academy work</span>
              <span class="ci-note">Even 30 minutes a day is enough. Put it in your calendar right now before you close this page.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Locate and bookmark the Template Vault</span>
              <span class="ci-note">Know where it is before you need it. You will use it often once you start working through modules.</span>
            </div>
          </div>
        </div>
      </div>

      <div>
        <h3 style="font-size: 0.88rem; font-family: Manrope; font-weight: 800; letter-spacing: 0.1em; text-transform: uppercase; color: var(--purple); margin-bottom: 14px;">Action — Complete This Week</h3>
        <div class="ci-wrap">
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Complete the Creator Plug Launch Challenge</span>
              <span class="ci-note">Every task. In order. No skipping. This is the most important thing you will do in week one.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Start Module 1 of your chosen path</span>
              <span class="ci-note">Open your path, start the first module, and complete whatever task it assigns.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Download and actually use one Vault template</span>
              <span class="ci-note">Do not just download it. Apply it to something you are actively building right now.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Attend or watch one coaching session</span>
              <span class="ci-note">Join live or watch a replay from the Coaching Hub. Commit to one session this first week.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Share your first progress win in the community</span>
              <span class="ci-note">Any win counts — finishing this page, choosing your path, completing a task. Share it.</span>
            </div>
          </div>
          <div class="ci" onclick="this.classList.toggle('done')">
            <div class="ci-box">✓</div>
            <div>
              <span class="ci-title">Plan your goals for week two</span>
              <span class="ci-note">Before your first week ends, decide what you want to have done by the end of week two. Write it down.</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="callout">
      🎉 If you complete this checklist in order, you have done more than most members accomplish in their first full month. You are already building. Keep going from here.
    </div>
  </section>

  <!-- ═══════════════════════════ FAQ ═══════════════════════════ -->
  <section class="section" id="faq">
    <div class="section-tag">❓ Common Questions</div>
    <h2>Frequently Asked Questions</h2>
    <p class="section-lead">These are the questions new members ask most often. At least one of these is probably something you have already wondered about — find it, read the answer, and keep moving.</p>

    <details class="faq">
      <summary class="faq-q">I just joined and I already feel overwhelmed. Where do I even begin?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">Start with this page and only this page. Close every other tab. Do not open any other module yet. Read the full Before You Start page from top to bottom, then go directly into the Start Here section. You have exactly two tasks right now: finish this, then complete Start Here. Nothing else exists until those are done. Overwhelm almost always comes from trying to see the whole picture at once — you do not need to. You just need to take the next step.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">Can I work on two paths at the same time?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">Technically yes. In practice, it is one of the most consistent patterns among people who stall out. Every person who has tried to pursue two paths simultaneously has made slower progress on both than they would have made going all-in on one. The paths are designed to be completed sequentially, not in parallel. Choose one, get your first real result, and then add the next path. The second path will always be there. The momentum you lose by splitting your focus is much harder to recover.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">How long does it realistically take to start making money?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">It depends on your path and how consistently you take action. The Ecommerce/Service path can produce a first client or sale in 1–3 weeks if you are reaching out and making offers daily. The Digital Product path typically takes 2–4 weeks to create, launch, and start selling with focused effort. The Creator path focuses on audience first, so expect 30–90 days before you see consistent monetization — the earlier phase is about building the asset. All of these timelines assume daily action. Inconsistency extends every single one of them significantly.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">I am not very tech-savvy. Can I still make this work?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">Yes. The templates, AI prompts, and scripts in the Vault are specifically designed to lower the technical barrier as much as possible. Most of the tools used in this academy are visual, drag-and-drop, and require no coding knowledge. If you hit a technical wall, ask in the community — there is almost always someone who has already solved the exact problem you are facing and is happy to help. The technical side is almost never the real obstacle. Consistency and action are.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">How much time do I need to commit every day?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">Minimum 30 minutes per day to make real, meaningful progress. One hour per day is the ideal target for your first 30 days. More time accelerates results, but consistency matters far more than quantity. Thirty minutes every single day will always outperform three-hour sessions twice a week — the habit of showing up daily builds the identity of someone who follows through, which is the most important asset you can build in the early stages. Start with 30 minutes, build the habit, then increase from there.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">I already started and jumped around. Should I go back to the beginning?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">Yes — go back. Complete the Start Here section and the Creator Plug Launch Challenge if you have not done both in full. Then choose one path and follow it from Module 1, in order. Jumping ahead often creates gaps in your foundation and strategy that become bigger problems later. Going back feels like losing ground but almost always saves significant time and frustration. A solid foundation built right the first time is worth far more than a fast-moving but shaky one.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">Is there a right or wrong path to choose?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">No — all three paths can produce strong results. The right path is the one that aligns with where you are right now: your existing skills, your available time, the assets you already have, and the kind of business you actually want to build long term. If you are still genuinely unsure after reading all three descriptions, start with the Service/Ecommerce path. It has the shortest runway to a first real result, and that first result builds the confidence and proof-of-concept you need to fuel everything else.</p>
    </details>

    <details class="faq">
      <summary class="faq-q">What exactly is the Template Vault and when should I actually use it?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">The Vault is a library of ready-to-use resources: content templates, AI prompts, sales scripts, Canva designs, business planning docs, and launch tools. Use it when you are working on a specific module and need a resource to complete a task — not before. Do not browse the Vault during your first session as a starting point; it is a support tool you reach for when you are actively building something and need a shortcut. Think of it as a toolkit you open when you are in the middle of a project, not when you are still figuring out what you are building.</p>
    </details>

    <details class="faq" style="border-bottom: none;">
      <summary class="faq-q">What if I fall behind or go days without showing up? Is it too late?<span class="faq-arrow">▼</span></summary>
      <p class="faq-body">It is never too late. The academy does not expire and the modules do not disappear. If you fall off, the only thing required is to come back — without judgment, without a story about having lost too much time, and without starting over from scratch unless you genuinely need to. Pick up exactly where you left off, rejoin the community, and start with one small action. Progress is not linear, and everyone who has built something real has had gaps in the process. What matters is that you come back and keep moving.</p>
    </details>
  </section>

  <!-- ═══════════════════════════ CTA ═══════════════════════════ -->
  <section class="cta">
    <div class="section-tag" style="background: rgba(255,255,255,0.13); color: #fff5dd;">🚀 Your Next Step</div>
    <h2>Now Let&rsquo;s Get Started</h2>
    <p>You have everything you need to begin. Open the Start Here section, complete the Creator Plug Launch Challenge, choose one path, and work through the modules one at a time. Build one income stream first. Expand once the foundation is solid and producing results.</p>
    <div class="cta-actions">
      <a class="btn-gold" href="#start">🏁 Start Here First</a>
      <a class="btn-ghost" href="#checklist">✅ View My Checklist</a>
      <a class="btn-ghost" href="#paths">🛤 Review the Paths</a>
    </div>
  </section>

</div><!-- /page -->

<script>
  // Reading progress bar
  const bar = document.getElementById('progressBar');
  window.addEventListener('scroll', () => {
    const scrolled = document.documentElement.scrollTop;
    const total = document.documentElement.scrollHeight - window.innerHeight;
    bar.style.width = (total > 0 ? (scrolled / total) * 100 : 0) + '%';
  }, { passive: true });
</script>
</body>
</html>
