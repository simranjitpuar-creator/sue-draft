<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SUE — Society of Undergraduates in Economics | University of Calgary</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,300&display=swap" rel="stylesheet">
<style>
  :root {
    --red: #CC0000;
    --red-dark: #990000;
    --red-light: #F5E6E6;
    --gold: #C4A44A;
    --gold-light: #F7F0DC;
    --black: #0E0E0E;
    --off-white: #FAF9F6;
    --gray-100: #F2F0EB;
    --gray-200: #E2DFD8;
    --gray-400: #9B9690;
    --gray-600: #5C5852;
    --gray-800: #2A2825;
    --font-display: 'DM Serif Display', Georgia, serif;
    --font-body: 'DM Sans', system-ui, sans-serif;
    --nav-h: 72px;
    --max-w: 1200px;
    --radius: 4px;
    --radius-lg: 12px;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--font-body);
    background: var(--off-white);
    color: var(--black);
    overflow-x: hidden;
    -webkit-font-smoothing: antialiased;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    height: var(--nav-h);
    background: rgba(14,14,14,0.96);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,0.07);
    display: flex; align-items: center;
    padding: 0 clamp(1.5rem, 5vw, 4rem);
  }
  .nav-inner {
    width: 100%; max-width: var(--max-w);
    margin: 0 auto;
    display: flex; align-items: center; justify-content: space-between;
  }
  .nav-logo {
    display: flex; align-items: center; gap: 12px;
    text-decoration: none;
  }
  .nav-logo-mark {
    width: 38px; height: 38px;
    background: var(--red);
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    font-family: var(--font-display);
    font-size: 18px; color: #fff; font-weight: 400;
    letter-spacing: -0.5px;
    flex-shrink: 0;
  }
  .nav-logo-text {
    display: flex; flex-direction: column;
    line-height: 1.1;
  }
  .nav-logo-text span:first-child {
    font-family: var(--font-display); font-size: 16px; color: #fff; letter-spacing: 0.3px;
  }
  .nav-logo-text span:last-child {
    font-size: 10px; color: var(--gray-400); letter-spacing: 1.5px; text-transform: uppercase;
    font-weight: 500;
  }
  .nav-links {
    display: flex; align-items: center; gap: 2rem; list-style: none;
  }
  .nav-links a {
    text-decoration: none; font-size: 13px; font-weight: 500;
    color: rgba(255,255,255,0.65); letter-spacing: 0.5px;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: #fff; }
  .nav-cta {
    background: var(--red); color: #fff !important;
    padding: 8px 18px; border-radius: var(--radius);
    transition: background 0.2s !important;
  }
  .nav-cta:hover { background: var(--red-dark) !important; color: #fff; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    background: var(--black);
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: calc(var(--nav-h) + 4rem) clamp(1.5rem, 5vw, 4rem) 5rem;
    position: relative; overflow: hidden;
  }
  .hero-grid {
    position: absolute; inset: 0; opacity: 0.04;
    background-image:
      linear-gradient(rgba(255,255,255,0.8) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.8) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .hero-accent {
    position: absolute; top: 0; right: 0;
    width: 55vw; height: 100%;
    background: linear-gradient(135deg, rgba(204,0,0,0.12) 0%, transparent 60%);
    pointer-events: none;
  }
  .hero-accent-line {
    position: absolute; top: 50%; right: 0;
    width: 45vw; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(196,164,74,0.4));
    transform: translateY(-50%);
  }
  .hero-inner {
    max-width: var(--max-w); margin: 0 auto; width: 100%;
    position: relative; z-index: 2;
  }
  .hero-tag {
    display: inline-flex; align-items: center; gap: 8px;
    font-size: 11px; font-weight: 600; letter-spacing: 2px;
    text-transform: uppercase; color: var(--gold);
    margin-bottom: 2rem;
  }
  .hero-tag::before {
    content: ''; display: block; width: 28px; height: 1px; background: var(--gold);
  }
  .hero-h1 {
    font-family: var(--font-display);
    font-size: clamp(3.2rem, 7vw, 7rem);
    line-height: 0.95;
    color: #fff;
    letter-spacing: -2px;
    margin-bottom: 2.5rem;
    max-width: 14ch;
  }
  .hero-h1 em {
    font-style: italic; color: var(--gold);
  }
  .hero-bottom {
    display: flex; align-items: flex-end; justify-content: space-between;
    gap: 2rem; flex-wrap: wrap;
  }
  .hero-desc {
    font-size: clamp(1rem, 1.6vw, 1.15rem);
    color: rgba(255,255,255,0.55);
    max-width: 40ch; line-height: 1.7; font-weight: 300;
  }
  .hero-actions {
    display: flex; gap: 12px; flex-wrap: wrap; align-items: center;
  }
  .btn-primary {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--red); color: #fff;
    padding: 14px 28px; border-radius: var(--radius);
    text-decoration: none; font-size: 14px; font-weight: 600;
    letter-spacing: 0.3px;
    transition: background 0.2s, transform 0.15s;
    border: none; cursor: pointer;
  }
  .btn-primary:hover { background: var(--red-dark); transform: translateY(-1px); }
  .btn-outline {
    display: inline-flex; align-items: center; gap: 8px;
    background: transparent; color: rgba(255,255,255,0.7);
    padding: 14px 28px; border-radius: var(--radius);
    text-decoration: none; font-size: 14px; font-weight: 500;
    border: 1px solid rgba(255,255,255,0.2);
    transition: all 0.2s; cursor: pointer;
  }
  .btn-outline:hover { border-color: rgba(255,255,255,0.5); color: #fff; }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 3rem;
    border-top: 1px solid rgba(255,255,255,0.08);
  }
  .hero-stat {}
  .hero-stat-num {
    font-family: var(--font-display);
    font-size: 2.8rem; color: #fff; line-height: 1;
    margin-bottom: 4px;
  }
  .hero-stat-num span { color: var(--red); }
  .hero-stat-label {
    font-size: 12px; color: rgba(255,255,255,0.4); text-transform: uppercase;
    letter-spacing: 1.5px; font-weight: 500;
  }

  /* ── SECTIONS ── */
  section { padding: 6rem clamp(1.5rem, 5vw, 4rem); }
  .section-inner { max-width: var(--max-w); margin: 0 auto; }
  .section-eyebrow {
    font-size: 11px; font-weight: 600; letter-spacing: 2px;
    text-transform: uppercase; color: var(--red);
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 1rem;
  }
  .section-eyebrow::after {
    content: ''; flex: 1; max-width: 40px; height: 1px; background: var(--red);
  }
  .section-title {
    font-family: var(--font-display);
    font-size: clamp(2.2rem, 4vw, 3.5rem);
    letter-spacing: -1px; line-height: 1.05;
    margin-bottom: 1rem; color: var(--black);
  }
  .section-sub {
    font-size: 1.05rem; color: var(--gray-600);
    max-width: 50ch; line-height: 1.7; font-weight: 300;
    margin-bottom: 3.5rem;
  }

  /* ── ABOUT / PILLARS ── */
  .about { background: var(--off-white); }
  .pillars-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5px;
    background: var(--gray-200);
    border: 1.5px solid var(--gray-200);
    border-radius: var(--radius-lg);
    overflow: hidden;
  }
  .pillar {
    background: var(--off-white);
    padding: 2.5rem 2rem;
    position: relative;
    transition: background 0.2s;
  }
  .pillar:hover { background: #fff; }
  .pillar-num {
    font-family: var(--font-display);
    font-size: 4rem; color: var(--gray-200);
    line-height: 1; margin-bottom: 1.5rem;
    user-select: none;
  }
  .pillar-icon {
    width: 44px; height: 44px;
    background: var(--red-light); border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    margin-bottom: 1.25rem;
  }
  .pillar-icon svg { width: 22px; height: 22px; stroke: var(--red); fill: none; stroke-width: 1.8; stroke-linecap: round; stroke-linejoin: round; }
  .pillar h3 {
    font-family: var(--font-display); font-size: 1.4rem;
    margin-bottom: 0.75rem; color: var(--black);
  }
  .pillar p { font-size: 0.9rem; color: var(--gray-600); line-height: 1.7; font-weight: 300; }

  /* ── EVENTS ── */
  .events { background: var(--gray-100); }
  .events-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 1.5rem;
  }
  .event-card {
    background: #fff;
    border-radius: var(--radius-lg);
    overflow: hidden;
    border: 1px solid var(--gray-200);
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .event-card:hover { transform: translateY(-3px); box-shadow: 0 12px 32px rgba(0,0,0,0.08); }
  .event-card-featured {
    display: flex; flex-direction: column;
  }
  .event-card-img {
    background: var(--black);
    min-height: 200px;
    position: relative;
    display: flex; align-items: flex-end;
    padding: 1.5rem;
    overflow: hidden;
  }
  .event-card-img-bg {
    position: absolute; inset: 0;
    background: linear-gradient(135deg, #1a1a1a 0%, #330000 100%);
    opacity: 0.9;
  }
  .event-card-img-pattern {
    position: absolute; inset: 0; opacity: 0.07;
    background-image: radial-gradient(circle, #fff 1px, transparent 1px);
    background-size: 24px 24px;
  }
  .event-badge {
    position: relative; z-index: 1;
    background: var(--red); color: #fff;
    font-size: 10px; font-weight: 700; letter-spacing: 1.5px;
    text-transform: uppercase; padding: 4px 10px; border-radius: 2px;
  }
  .event-card-body { padding: 1.75rem; }
  .event-date-row {
    display: flex; align-items: center; gap: 8px;
    font-size: 12px; color: var(--gray-400); font-weight: 500;
    text-transform: uppercase; letter-spacing: 1px;
    margin-bottom: 0.6rem;
  }
  .event-card-body h3 {
    font-family: var(--font-display); font-size: 1.5rem;
    margin-bottom: 0.5rem; line-height: 1.2;
  }
  .event-card-body p { font-size: 0.875rem; color: var(--gray-600); line-height: 1.6; font-weight: 300; }
  .event-card-footer {
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 1.75rem;
    border-top: 1px solid var(--gray-200);
    font-size: 12px; color: var(--gray-400);
  }
  .event-card-footer a {
    color: var(--red); text-decoration: none; font-weight: 600; font-size: 13px;
  }
  .events-sidebar { display: flex; flex-direction: column; gap: 1rem; }
  .event-mini {
    background: #fff;
    border-radius: var(--radius-lg);
    border: 1px solid var(--gray-200);
    padding: 1.25rem 1.5rem;
    display: flex; gap: 1rem; align-items: flex-start;
    transition: transform 0.2s;
    cursor: pointer;
  }
  .event-mini:hover { transform: translateY(-2px); }
  .event-mini-date {
    flex-shrink: 0;
    width: 48px; text-align: center;
    background: var(--red-light); border-radius: 6px;
    padding: 6px 4px;
  }
  .event-mini-date-d {
    font-family: var(--font-display); font-size: 1.6rem; color: var(--red); line-height: 1;
  }
  .event-mini-date-m {
    font-size: 10px; font-weight: 700; letter-spacing: 1px;
    text-transform: uppercase; color: var(--red); opacity: 0.7;
  }
  .event-mini-info h4 { font-size: 0.95rem; font-weight: 600; margin-bottom: 3px; }
  .event-mini-info p { font-size: 0.8rem; color: var(--gray-400); }

  /* ── PARTNERS ── */
  .partners { background: var(--black); }
  .partners .section-title { color: #fff; }
  .partners .section-sub { color: rgba(255,255,255,0.4); }
  .partners .section-eyebrow { color: var(--gold); }
  .partners .section-eyebrow::after { background: var(--gold); }
  .partners-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 1px;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: var(--radius-lg);
    overflow: hidden;
  }
  .partner-tile {
    background: var(--black);
    padding: 2.5rem 2rem;
    text-align: center;
    transition: background 0.2s;
    cursor: pointer;
  }
  .partner-tile:hover { background: #1a1a1a; }
  .partner-tile-logo {
    font-family: var(--font-display);
    font-size: 1.5rem; color: rgba(255,255,255,0.35);
    margin-bottom: 0.5rem;
    transition: color 0.2s;
    font-weight: 400;
  }
  .partner-tile:hover .partner-tile-logo { color: rgba(255,255,255,0.75); }
  .partner-tile-sector {
    font-size: 10px; text-transform: uppercase; letter-spacing: 1.5px;
    color: rgba(255,255,255,0.2); font-weight: 500;
  }
  .partner-cta-box {
    margin-top: 3rem;
    border: 1px solid rgba(196,164,74,0.3);
    border-radius: var(--radius-lg);
    padding: 2.5rem;
    display: flex; align-items: center; justify-content: space-between;
    gap: 2rem; flex-wrap: wrap;
    background: rgba(196,164,74,0.04);
  }
  .partner-cta-box h3 {
    font-family: var(--font-display); font-size: 1.6rem;
    color: #fff; margin-bottom: 0.4rem;
  }
  .partner-cta-box p { color: rgba(255,255,255,0.4); font-size: 0.9rem; max-width: 40ch; }
  .btn-gold {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--gold); color: var(--black);
    padding: 14px 28px; border-radius: var(--radius);
    text-decoration: none; font-size: 14px; font-weight: 700;
    flex-shrink: 0;
    transition: background 0.2s, transform 0.15s;
  }
  .btn-gold:hover { background: #d4b558; transform: translateY(-1px); }

  /* ── OPPORTUNITIES ── */
  .opportunities { background: var(--off-white); }
  .opps-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
  }
  .opp-card {
    border: 1px solid var(--gray-200);
    border-radius: var(--radius-lg);
    padding: 2rem;
    background: #fff;
    position: relative; overflow: hidden;
    transition: transform 0.2s, border-color 0.2s;
  }
  .opp-card:hover { transform: translateY(-3px); border-color: var(--red); }
  .opp-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0;
    height: 3px; background: var(--red); transform: scaleX(0);
    transform-origin: left; transition: transform 0.3s;
  }
  .opp-card:hover::before { transform: scaleX(1); }
  .opp-tag {
    display: inline-block;
    font-size: 10px; font-weight: 700; letter-spacing: 1.5px;
    text-transform: uppercase; color: var(--red);
    background: var(--red-light);
    padding: 4px 10px; border-radius: 2px;
    margin-bottom: 1.25rem;
  }
  .opp-card h3 {
    font-family: var(--font-display); font-size: 1.35rem;
    margin-bottom: 0.75rem; line-height: 1.2;
  }
  .opp-card p { font-size: 0.875rem; color: var(--gray-600); line-height: 1.7; font-weight: 300; margin-bottom: 1.5rem; }
  .opp-card a {
    font-size: 13px; color: var(--red); text-decoration: none;
    font-weight: 600; display: flex; align-items: center; gap: 6px;
  }
  .opp-card a::after { content: '→'; transition: transform 0.2s; }
  .opp-card:hover a::after { transform: translateX(4px); }

  /* ── LEADERSHIP ── */
  .leadership { background: var(--gray-100); }
  .team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 1.5rem;
  }
  .team-card {
    background: #fff;
    border-radius: var(--radius-lg);
    border: 1px solid var(--gray-200);
    overflow: hidden;
    text-align: center;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .team-card:hover { transform: translateY(-3px); box-shadow: 0 10px 28px rgba(0,0,0,0.07); }
  .team-card-header {
    background: linear-gradient(135deg, var(--black), #2d0000);
    padding: 2.5rem 1rem 1.5rem;
    position: relative;
  }
  .team-avatar {
    width: 72px; height: 72px;
    border-radius: 50%;
    background: var(--red);
    display: inline-flex; align-items: center; justify-content: center;
    font-family: var(--font-display); font-size: 1.6rem;
    color: #fff; border: 3px solid rgba(255,255,255,0.15);
  }
  .team-card-body { padding: 1.25rem; }
  .team-card-body h4 { font-size: 1rem; font-weight: 600; margin-bottom: 2px; }
  .team-card-body .role {
    font-size: 11px; text-transform: uppercase; letter-spacing: 1.5px;
    color: var(--red); font-weight: 600; margin-bottom: 0.5rem;
  }
  .team-card-body .program {
    font-size: 12px; color: var(--gray-400);
  }

  /* ── JOIN ── */
  .join-section {
    background: var(--red);
    padding: 6rem clamp(1.5rem, 5vw, 4rem);
    text-align: center;
  }
  .join-inner { max-width: 640px; margin: 0 auto; }
  .join-inner .section-eyebrow {
    color: rgba(255,255,255,0.6); justify-content: center;
  }
  .join-inner .section-eyebrow::after { display: none; }
  .join-inner h2 {
    font-family: var(--font-display);
    font-size: clamp(2.5rem, 5vw, 4rem);
    color: #fff; margin-bottom: 1.25rem;
    letter-spacing: -1.5px;
  }
  .join-inner p {
    color: rgba(255,255,255,0.7); font-size: 1.1rem;
    line-height: 1.7; font-weight: 300; margin-bottom: 2.5rem;
  }
  .join-actions { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }
  .btn-white {
    display: inline-flex; align-items: center; gap: 8px;
    background: #fff; color: var(--red);
    padding: 14px 32px; border-radius: var(--radius);
    text-decoration: none; font-size: 14px; font-weight: 700;
    transition: all 0.2s;
  }
  .btn-white:hover { background: var(--off-white); transform: translateY(-1px); }
  .btn-white-outline {
    display: inline-flex; align-items: center; gap: 8px;
    background: transparent; color: rgba(255,255,255,0.85);
    padding: 14px 32px; border-radius: var(--radius);
    text-decoration: none; font-size: 14px; font-weight: 500;
    border: 1.5px solid rgba(255,255,255,0.35);
    transition: all 0.2s;
  }
  .btn-white-outline:hover { border-color: #fff; color: #fff; }

  /* ── FOOTER ── */
  footer {
    background: var(--gray-800);
    color: rgba(255,255,255,0.4);
    padding: 4rem clamp(1.5rem, 5vw, 4rem) 2.5rem;
  }
  .footer-inner {
    max-width: var(--max-w); margin: 0 auto;
  }
  .footer-top {
    display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 3rem; margin-bottom: 3rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid rgba(255,255,255,0.07);
  }
  .footer-brand p {
    font-size: 0.875rem; line-height: 1.7; margin-top: 1rem;
    max-width: 30ch; color: rgba(255,255,255,0.35);
  }
  .footer-col h5 {
    font-size: 11px; font-weight: 700; text-transform: uppercase;
    letter-spacing: 1.5px; color: rgba(255,255,255,0.6);
    margin-bottom: 1rem;
  }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 0.6rem; }
  .footer-col ul a {
    text-decoration: none; font-size: 13px;
    color: rgba(255,255,255,0.35);
    transition: color 0.2s;
  }
  .footer-col ul a:hover { color: rgba(255,255,255,0.8); }
  .footer-bottom {
    display: flex; justify-content: space-between; align-items: center;
    flex-wrap: wrap; gap: 1rem;
    font-size: 12px;
  }
  .footer-bottom a { color: rgba(255,255,255,0.35); text-decoration: none; }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .animate-in {
    animation: fadeUp 0.7s ease forwards;
    opacity: 0;
  }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.45s; }
  .delay-5 { animation-delay: 0.6s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .events-grid { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 640px) {
    .nav-links { display: none; }
    .hero-stats { gap: 2rem; }
    .footer-top { grid-template-columns: 1fr; gap: 2rem; }
    .hero-bottom { flex-direction: column; align-items: flex-start; }
  }

  /* ── SCROLL REVEAL ── */
  .reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.6s, transform 0.6s; }
  .reveal.visible { opacity: 1; transform: none; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-inner">
    <a class="nav-logo" href="#">
      <div class="nav-logo-mark">S</div>
      <div class="nav-logo-text">
        <span>Society of Undergraduates in Economics</span>
        <span>University of Calgary</span>
      </div>
    </a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#events">Events</a></li>
      <li><a href="#opportunities">Opportunities</a></li>
      <li><a href="#partners">Partners</a></li>
      <li><a href="#team">Leadership</a></li>
      <li><a href="#join" class="nav-cta">Join SUE</a></li>
    </ul>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-grid"></div>
  <div class="hero-accent"></div>
  <div class="hero-accent-line"></div>
  <div class="hero-inner">
    <div class="hero-tag animate-in delay-1">University of Calgary · Est. Faculty Club</div>
    <h1 class="hero-h1 animate-in delay-2">
      Where <em>economics</em> meets opportunity.
    </h1>
    <div class="hero-bottom animate-in delay-3">
      <p class="hero-desc">
        SUE bridges the gap between academic theory and real-world finance. We connect ambitious students with industry leaders, career pathways, and a community that thinks critically about markets and policy.
      </p>
      <div class="hero-actions">
        <a href="#join" class="btn-primary">Become a Member</a>
        <a href="#events" class="btn-outline">Upcoming Events</a>
      </div>
    </div>
    <div class="hero-stats animate-in delay-4">
      <div class="hero-stat">
        <div class="hero-stat-num">400<span>+</span></div>
        <div class="hero-stat-label">Active Members</div>
      </div>
      <div class="hero-stat">
        <div class="hero-stat-num">30<span>+</span></div>
        <div class="hero-stat-label">Annual Events</div>
      </div>
      <div class="hero-stat">
        <div class="hero-stat-num">15<span>+</span></div>
        <div class="hero-stat-label">Industry Partners</div>
      </div>
      <div class="hero-stat">
        <div class="hero-stat-num">4<span>th</span></div>
        <div class="hero-stat-label">Year Running</div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="section-inner">
    <div class="section-eyebrow reveal">What We Do</div>
    <h2 class="section-title reveal">Built on three pillars.</h2>
    <p class="section-sub reveal">SUE exists to develop the next generation of economists, analysts, and business leaders from the University of Calgary's Economics program.</p>

    <div class="pillars-grid">
      <div class="pillar reveal">
        <div class="pillar-icon">
          <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
        </div>
        <div class="pillar-num">01</div>
        <h3>Education</h3>
        <p>Case competitions, econ talks, and workshops that deepen your understanding of markets, policy, and applied economics beyond the classroom.</p>
      </div>
      <div class="pillar reveal">
        <div class="pillar-icon">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
        </div>
        <div class="pillar-num">02</div>
        <h3>Networking</h3>
        <p>Direct access to Calgary's financial, consulting, and policy ecosystem through curated industry nights, career panels, and alumni dinners.</p>
      </div>
      <div class="pillar reveal">
        <div class="pillar-icon">
          <svg viewBox="0 0 24 24"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
        </div>
        <div class="pillar-num">03</div>
        <h3>Professional Development</h3>
        <p>From resume clinics to interview prep with top firms, we equip members with the skills and connections to launch high-impact careers.</p>
      </div>
      <div class="pillar reveal">
        <div class="pillar-icon">
          <svg viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
        </div>
        <div class="pillar-num">04</div>
        <h3>Community</h3>
        <p>A vibrant student community united by intellectual curiosity — from social events to collaborative research projects with Economics faculty.</p>
      </div>
    </div>
  </div>
</section>

<!-- EVENTS -->
<section class="events" id="events">
  <div class="section-inner">
    <div class="section-eyebrow reveal">Calendar</div>
    <h2 class="section-title reveal">Upcoming Events</h2>
    <p class="section-sub reveal">Join us for speaker series, networking mixers, case competitions, and more.</p>

    <div class="events-grid">
      <div class="event-card event-card-featured reveal">
        <div class="event-card-img">
          <div class="event-card-img-bg"></div>
          <div class="event-card-img-pattern"></div>
          <span class="event-badge">Featured</span>
        </div>
        <div class="event-card-body">
          <div class="event-date-row">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
            April 3, 2026 · 6:00 PM — Scurfield Hall
          </div>
          <h3>Annual Economics Gala & Industry Showcase</h3>
          <p>Our flagship event of the year. An evening of keynotes, networking, and awards celebrating outstanding achievement in economics at UCalgary. Industry leaders from energy, finance, and consulting join faculty and students for an unforgettable night.</p>
        </div>
        <div class="event-card-footer">
          <span>🎟 Limited seats — RSVP required</span>
          <a href="#">Register Now</a>
        </div>
      </div>

      <div class="events-sidebar">
        <div class="event-mini reveal">
          <div class="event-mini-date">
            <div class="event-mini-date-d">24</div>
            <div class="event-mini-date-m">Mar</div>
          </div>
          <div class="event-mini-info">
            <h4>Case Competition Prep Workshop</h4>
            <p>MS 319 · 5:30 PM · Free</p>
          </div>
        </div>
        <div class="event-mini reveal">
          <div class="event-mini-date">
            <div class="event-mini-date-d">28</div>
            <div class="event-mini-date-m">Mar</div>
          </div>
          <div class="event-mini-info">
            <h4>Finance & Consulting Career Panel</h4>
            <p>Haskayne School · 6:00 PM</p>
          </div>
        </div>
        <div class="event-mini reveal">
          <div class="event-mini-date">
            <div class="event-mini-date-d">10</div>
            <div class="event-mini-date-m">Apr</div>
          </div>
          <div class="event-mini-info">
            <h4>Spring Networking Mixer</h4>
            <p>MacHall Ballroom · 7:00 PM</p>
          </div>
        </div>
        <div class="event-mini reveal">
          <div class="event-mini-date">
            <div class="event-mini-date-d">17</div>
            <div class="event-mini-date-m">Apr</div>
          </div>
          <div class="event-mini-info">
            <h4>Speaker Series: Energy Economics</h4>
            <p>Science B · 4:00 PM · Free</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- OPPORTUNITIES -->
<section class="opportunities" id="opportunities">
  <div class="section-inner">
    <div class="section-eyebrow reveal">Grow With Us</div>
    <h2 class="section-title reveal">Open Opportunities</h2>
    <p class="section-sub reveal">Whether you're looking to compete, lead, research, or connect — SUE has a pathway for you.</p>

    <div class="opps-grid">
      <div class="opp-card reveal">
        <span class="opp-tag">Compete</span>
        <h3>Intercollegiate Case Competition</h3>
        <p>Represent UCalgary against top universities nationwide. Teams of 3–4 students tackle real-world economic and business challenges judged by industry professionals.</p>
        <a href="#">Apply by April 1</a>
      </div>
      <div class="opp-card reveal">
        <span class="opp-tag">Lead</span>
        <h3>Executive Positions 2026–27</h3>
        <p>SUE elections are open. Run for President, VP Finance, VP Events, or Director roles and shape the future of economics at UCalgary.</p>
        <a href="#">Nominate yourself</a>
      </div>
      <div class="opp-card reveal">
        <span class="opp-tag">Research</span>
        <h3>SUE Economic Policy Journal</h3>
        <p>Submit an original research paper for publication in our peer-reviewed undergraduate journal. Submissions accepted from all disciplines touching economics.</p>
        <a href="#">Submit your paper</a>
      </div>
      <div class="opp-card reveal">
        <span class="opp-tag">Mentorship</span>
        <h3>Alumni Mentorship Program</h3>
        <p>Get paired 1:1 with a UCalgary Economics alumnus working in banking, consulting, government, or academia. Applications open each semester.</p>
        <a href="#">Apply now</a>
      </div>
      <div class="opp-card reveal">
        <span class="opp-tag">Internship</span>
        <h3>Partner Internship Pipeline</h3>
        <p>Exclusive access to internship openings from our corporate partners — before they're posted publicly. Member-only job board updated weekly.</p>
        <a href="#">View positions</a>
      </div>
      <div class="opp-card reveal">
        <span class="opp-tag">Workshop</span>
        <h3>Excel & Financial Modelling Series</h3>
        <p>A 4-session bootcamp on financial modelling, DCF analysis, and data tools. Skills tested directly used in finance and consulting interviews.</p>
        <a href="#">Register free</a>
      </div>
    </div>
  </div>
</section>

<!-- PARTNERS -->
<section class="partners" id="partners">
  <div class="section-inner">
    <div class="section-eyebrow reveal">Industry</div>
    <h2 class="section-title reveal">Our Partners</h2>
    <p class="section-sub reveal">SUE works with leading firms across energy, finance, consulting, and public policy to create meaningful pathways for our members.</p>

    <div class="partners-grid reveal">
      <div class="partner-tile">
        <div class="partner-tile-logo">ATB Financial</div>
        <div class="partner-tile-sector">Financial Services</div>
      </div>
      <div class="partner-tile">
        <div class="partner-tile-logo">Deloitte</div>
        <div class="partner-tile-sector">Consulting</div>
      </div>
      <div class="partner-tile">
        <div class="partner-tile-logo">Enbridge</div>
        <div class="partner-tile-sector">Energy</div>
      </div>
      <div class="partner-tile">
        <div class="partner-tile-logo">BMO Capital</div>
        <div class="partner-tile-sector">Investment Banking</div>
      </div>
      <div class="partner-tile">
        <div class="partner-tile-logo">McKinsey & Co</div>
        <div class="partner-tile-sector">Strategy</div>
      </div>
      <div class="partner-tile">
        <div class="partner-tile-logo">RBC</div>
        <div class="partner-tile-sector">Banking</div>
      </div>
    </div>

    <div class="partner-cta-box reveal">
      <div>
        <h3>Become a Partner</h3>
        <p>Gain direct access to UCalgary's top economics talent — through sponsorships, branded events, case challenges, and exclusive recruiting pipelines.</p>
      </div>
      <a href="mailto:partnerships@sue-ucalgary.ca" class="btn-gold">Partnership Enquiry →</a>
    </div>
  </div>
</section>

<!-- LEADERSHIP -->
<section class="leadership" id="team">
  <div class="section-inner">
    <div class="section-eyebrow reveal">People</div>
    <h2 class="section-title reveal">2025–26 Executive Team</h2>
    <p class="section-sub reveal">Led by students, for students — our executive team brings together passion, experience, and vision to drive SUE forward.</p>

    <div class="team-grid">
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">AP</div>
        </div>
        <div class="team-card-body">
          <div class="role">President</div>
          <h4>Alexandra Park</h4>
          <div class="program">BSc Economics, Year 4</div>
        </div>
      </div>
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">JM</div>
        </div>
        <div class="team-card-body">
          <div class="role">VP Finance</div>
          <h4>Jordan Mitchell</h4>
          <div class="program">BA Economics & Finance, Year 3</div>
        </div>
      </div>
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">SL</div>
        </div>
        <div class="team-card-body">
          <div class="role">VP Events</div>
          <h4>Sofia Larsen</h4>
          <div class="program">BSc Economics, Year 3</div>
        </div>
      </div>
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">RK</div>
        </div>
        <div class="team-card-body">
          <div class="role">VP External</div>
          <h4>Rahul Kapoor</h4>
          <div class="program">BA Economics & Poli Sci, Year 3</div>
        </div>
      </div>
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">EC</div>
        </div>
        <div class="team-card-body">
          <div class="role">Director, Marketing</div>
          <h4>Emily Chen</h4>
          <div class="program">BSc Economics, Year 2</div>
        </div>
      </div>
      <div class="team-card reveal">
        <div class="team-card-header">
          <div class="team-avatar">TB</div>
        </div>
        <div class="team-card-body">
          <div class="role">Director, Partnerships</div>
          <h4>Tyler Booth</h4>
          <div class="program">BA Economics, Year 3</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- JOIN CTA -->
<section class="join-section" id="join">
  <div class="join-inner">
    <div class="section-eyebrow">Ready?</div>
    <h2>Join SUE today.</h2>
    <p>Membership is open to all UCalgary students interested in economics, finance, and public policy. Annual dues are just $10 — one of the best investments you'll make at university.</p>
    <div class="join-actions">
      <a href="#" class="btn-white">Become a Member — $10/year</a>
      <a href="mailto:hello@sue-ucalgary.ca" class="btn-white-outline">Contact Us</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div class="footer-brand">
        <div class="nav-logo">
          <div class="nav-logo-mark" style="background: var(--red);">S</div>
          <div class="nav-logo-text">
            <span style="font-family: var(--font-display); font-size: 15px; color: rgba(255,255,255,0.8);">Society of Undergraduates in Economics</span>
            <span style="font-size: 10px; color: rgba(255,255,255,0.3); letter-spacing: 1.5px; text-transform: uppercase;">University of Calgary</span>
          </div>
        </div>
        <p>Cultivating the next generation of economic thinkers and leaders at the University of Calgary since our founding.</p>
      </div>
      <div class="footer-col">
        <h5>Navigate</h5>
        <ul>
          <li><a href="#about">About SUE</a></li>
          <li><a href="#events">Events</a></li>
          <li><a href="#opportunities">Opportunities</a></li>
          <li><a href="#partners">Partners</a></li>
          <li><a href="#team">Leadership</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Connect</h5>
        <ul>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">LinkedIn</a></li>
          <li><a href="#">Facebook</a></li>
          <li><a href="#">Discord Server</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Contact</h5>
        <ul>
          <li><a href="mailto:hello@sue-ucalgary.ca">hello@sue-ucalgary.ca</a></li>
          <li><a href="mailto:partnerships@sue-ucalgary.ca">partnerships@sue-ucalgary.ca</a></li>
          <li><a href="#">Submit a Speaker</a></li>
          <li><a href="#">Media Inquiries</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 Society of Undergraduates in Economics, University of Calgary. All rights reserved.</span>
      <span>Made with care in Calgary, AB 🍁</span>
    </div>
  </div>
</footer>

<script>
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
  reveals.forEach(el => observer.observe(el));
</script>

</body>
</html>
