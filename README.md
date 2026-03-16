<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sujal Shelke — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #0d1117;
    --bg2:       #131922;
    --clay-base: #1a2236;
    --clay-top:  #1f2a40;
    --clay-hi:   rgba(255,255,255,0.07);
    --clay-sh:   rgba(0,0,0,0.55);
    --border:    rgba(255,255,255,0.06);
    --txt:       #dde8ff;
    --muted:     #4a607a;
    --accent:    #7eb8ff;
    --green:     #5effa0;
    --yellow:    #ffe066;
    --pink:      #ff7eb8;
    --orange:    #ff9d5c;
    --purple:    #b57bff;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--txt);
    font-family: 'Nunito', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── BACKGROUND ── */
  .bg-blobs {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    animation: blobDrift 12s ease-in-out infinite alternate;
  }
  .blob1 { width:500px;height:500px;background:#3b6fd4;top:-150px;left:-100px;animation-duration:10s; }
  .blob2 { width:400px;height:400px;background:#7b3fc4;top:40%;right:-120px;animation-duration:14s; }
  .blob3 { width:300px;height:300px;background:#1a8a5a;bottom:-80px;left:30%;animation-duration:11s; }

  @keyframes blobDrift {
    from { transform: translate(0,0) scale(1); }
    to   { transform: translate(30px,20px) scale(1.06); }
  }

  /* ── WRAPPER ── */
  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 680px;
    margin: 0 auto;
    padding: 52px 20px 80px;
  }

  /* ── CLAY MIXIN ── */
  .clay {
    background: linear-gradient(145deg, var(--clay-top), var(--clay-base));
    border: 1px solid var(--border);
    border-top-color: rgba(255,255,255,0.1);
    border-left-color: rgba(255,255,255,0.08);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.06) inset,
      0 -2px 0 rgba(0,0,0,0.3) inset,
      0 12px 40px rgba(0,0,0,0.5),
      0 2px 8px rgba(0,0,0,0.3);
    border-radius: 20px;
  }

  /* ── HEADER ── */
  .header {
    display: flex;
    align-items: center;
    gap: 22px;
    margin-bottom: 32px;
    opacity: 0;
    animation: popUp 0.6s cubic-bezier(.34,1.56,.64,1) forwards 0.1s;
  }

  .avatar-wrap {
    position: relative;
    flex-shrink: 0;
  }

  .avatar {
    width: 80px; height: 80px;
    border-radius: 22px;
    background: linear-gradient(145deg, #2a3a5c, #1a2540);
    border: 1px solid rgba(255,255,255,0.1);
    border-top-color: rgba(255,255,255,0.18);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.08) inset,
      0 -2px 0 rgba(0,0,0,0.4) inset,
      0 16px 40px rgba(0,0,0,0.6),
      0 0 0 3px rgba(126,184,255,0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 34px;
    font-weight: 900;
    color: var(--accent);
    letter-spacing: -2px;
  }

  .status-dot {
    position: absolute;
    bottom: -3px; right: -3px;
    width: 18px; height: 18px;
    border-radius: 50%;
    background: var(--green);
    border: 3px solid var(--bg);
    box-shadow: 0 0 10px var(--green);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { box-shadow: 0 0 8px var(--green); }
    50%      { box-shadow: 0 0 18px var(--green), 0 0 30px rgba(94,255,160,0.3); }
  }

  .header-text h1 {
    font-size: 30px;
    font-weight: 900;
    line-height: 1.1;
    letter-spacing: -0.5px;
  }
  .header-text h1 .first { color: var(--txt); }
  .header-text h1 .last  {
    background: linear-gradient(90deg, var(--accent), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .header-text .tagline {
    font-family: 'Fira Code', monospace;
    font-size: 11.5px;
    color: var(--muted);
    margin-top: 7px;
    letter-spacing: 0.03em;
  }
  .header-text .tagline span { color: var(--green); }

  /* ── SECTION TITLE ── */
  .sec-title {
    font-family: 'Fira Code', monospace;
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
    opacity: 0.8;
  }
  .sec-title::after {
    content:'';
    flex:1;
    height:1px;
    background: linear-gradient(90deg, rgba(126,184,255,0.25), transparent);
  }

  /* ── SECTION ── */
  .section {
    margin-bottom: 28px;
    opacity: 0;
    animation: popUp 0.6s cubic-bezier(.34,1.56,.64,1) forwards;
  }
  .s1{animation-delay:.15s} .s2{animation-delay:.25s}
  .s3{animation-delay:.35s} .s4{animation-delay:.45s}
  .s5{animation-delay:.55s}

  @keyframes popUp {
    from { opacity:0; transform:translateY(24px) scale(0.97); }
    to   { opacity:1; transform:translateY(0)    scale(1); }
  }

  /* ── ABOUT CARD ── */
  .about-card {
    padding: 22px 24px;
  }
  .about-items { display:flex; flex-direction:column; gap:13px; }
  .about-item  { display:flex; align-items:center; gap:13px; }

  .about-icon {
    width: 40px; height: 40px;
    border-radius: 13px;
    background: linear-gradient(145deg, #22304a, #192537);
    border: 1px solid rgba(255,255,255,0.08);
    border-top-color: rgba(255,255,255,0.14);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.06) inset,
      0 4px 12px rgba(0,0,0,0.4);
    display:flex; align-items:center; justify-content:center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .about-item span {
    font-size: 14px;
    font-weight: 600;
    color: #c8d8f0;
  }

  /* ── 3D SOCIAL BUTTONS ── */
  .socials-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 13px;
  }

  .clay-btn {
    display: flex;
    align-items: center;
    gap: 13px;
    padding: 15px 18px;
    border-radius: 16px;
    text-decoration: none;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    transition: transform 0.15s cubic-bezier(.34,1.56,.64,1),
                box-shadow 0.15s ease;
    /* 3D clay button */
    border: 1px solid rgba(255,255,255,0.08);
    border-top-color: rgba(255,255,255,0.16);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.07) inset,
      0 -3px 0 rgba(0,0,0,0.4) inset,
      0 8px 0 var(--btn-shadow),
      0 10px 20px rgba(0,0,0,0.5);
  }

  .clay-btn:hover {
    transform: translateY(-3px);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.07) inset,
      0 -3px 0 rgba(0,0,0,0.4) inset,
      0 10px 0 var(--btn-shadow),
      0 14px 28px rgba(0,0,0,0.55);
  }

  .clay-btn:active {
    transform: translateY(4px);
    box-shadow:
      0 1px 0 rgba(255,255,255,0.05) inset,
      0 -1px 0 rgba(0,0,0,0.3) inset,
      0 3px 0 var(--btn-shadow),
      0 4px 10px rgba(0,0,0,0.4);
  }

  /* per-button colors */
  .btn-ig   { background:linear-gradient(145deg,#2e1f2e,#1f1525); --btn-shadow:#1a0d1f; }
  .btn-li   { background:linear-gradient(145deg,#1a2438,#111c2e); --btn-shadow:#0c1420; }
  .btn-cp   { background:linear-gradient(145deg,#1a2c20,#111f18); --btn-shadow:#0c1a10; }
  .btn-gm   { background:linear-gradient(145deg,#2c2218,#1e180f); --btn-shadow:#18110a; }

  .btn-icon-wrap {
    width: 36px; height: 36px;
    border-radius: 11px;
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
    box-shadow: 0 3px 10px rgba(0,0,0,0.4);
  }

  .btn-ig .btn-icon-wrap   { background: linear-gradient(135deg,#833ab4,#fd1d1d,#fcb045); }
  .btn-li .btn-icon-wrap   { background: #0a66c2; }
  .btn-cp .btn-icon-wrap   { background: #1e1e1e; border: 1px solid #47cf73; }
  .btn-gm .btn-icon-wrap   { background: linear-gradient(135deg,#ea4335,#fbbc05,#34a853,#4285f4); }

  .btn-label { display:flex; flex-direction:column; }
  .btn-label .name { font-size:13.5px; font-weight:800; color:#e8f0ff; }
  .btn-label .handle {
    font-family:'Fira Code',monospace;
    font-size:10px;
    opacity:0.45;
    margin-top:1px;
  }

  /* ── TECH STACK ── */
  .tech-wrap { display:flex; flex-wrap:wrap; gap:10px; }

  .tech-tag {
    display:flex; align-items:center; gap:8px;
    padding: 9px 16px;
    border-radius: 50px;
    font-family:'Fira Code', monospace;
    font-size:12px;
    font-weight:600;
    letter-spacing:0.04em;
    border: 1px solid rgba(255,255,255,0.07);
    border-top-color: rgba(255,255,255,0.13);
    box-shadow:
      0 2px 0 rgba(255,255,255,0.05) inset,
      0 -2px 0 rgba(0,0,0,0.35) inset,
      0 5px 0 var(--tag-sh),
      0 6px 14px rgba(0,0,0,0.4);
    transition: transform 0.15s cubic-bezier(.34,1.56,.64,1);
  }
  .tech-tag:hover { transform: translateY(-2px); }

  .tag-html { background:linear-gradient(145deg,#2c1e18,#1f150f); color:#ff7c44; --tag-sh:#1a0f08; }
  .tag-css  { background:linear-gradient(145deg,#162238,#0f1928); color:#5eb8ff; --tag-sh:#0a1118; }
  .tag-js   { background:linear-gradient(145deg,#2a2410,#1e1a0a); color:#ffe066; --tag-sh:#181400; }
  .tag-git  { background:linear-gradient(145deg,#2c1c18,#1e120f); color:#ff7055; --tag-sh:#1a0c08; }
  .tag-gh   { background:linear-gradient(145deg,#1e2030,#141822); color:#c0cce8; --tag-sh:#0e121a; }

  .tech-dot {
    width:7px; height:7px;
    border-radius:50%;
  }
  .tag-html .tech-dot { background:#ff7c44; box-shadow:0 0 8px #ff7c44; }
  .tag-css  .tech-dot { background:#5eb8ff; box-shadow:0 0 8px #5eb8ff; }
  .tag-js   .tech-dot { background:#ffe066; box-shadow:0 0 8px #ffe066; }
  .tag-git  .tech-dot { background:#ff7055; box-shadow:0 0 8px #ff7055; }
  .tag-gh   .tech-dot { background:#c0cce8; }

  /* ── STATS ── */
  .stats-row { display:grid; grid-template-columns:repeat(3,1fr); gap:12px; }

  .stat-clay {
    padding: 20px 14px;
    text-align:center;
    position:relative;
    overflow:hidden;
  }
  .stat-clay::before {
    content:'';
    position:absolute; inset:0;
    background: radial-gradient(circle at 50% 0%, rgba(255,255,255,0.04), transparent 60%);
    pointer-events:none;
  }
  .stat-val {
    font-family:'Fira Code',monospace;
    font-size:28px;
    font-weight:600;
    line-height:1;
    margin-bottom:6px;
  }
  .stat-lbl {
    font-size:10px;
    font-family:'Fira Code',monospace;
    color:var(--muted);
    line-height:1.4;
  }
  .sv-blue   { color:var(--accent); text-shadow:0 0 20px rgba(126,184,255,0.5); }
  .sv-green  { color:var(--green);  text-shadow:0 0 20px rgba(94,255,160,0.5);  }
  .sv-yellow { color:var(--yellow); text-shadow:0 0 20px rgba(255,224,102,0.5); }

  /* ── LANGUAGE CARD ── */
  .lang-clay { padding: 20px 24px; }
  .lang-head { display:flex; justify-content:space-between; align-items:center; margin-bottom:13px; }
  .lang-name-row { display:flex; align-items:center; gap:9px; font-size:13px; font-weight:700; }
  .lang-pct { font-family:'Fira Code',monospace; font-size:12px; color:var(--accent); }
  .bar-bg {
    height:8px;
    border-radius:99px;
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(255,255,255,0.06);
    box-shadow: inset 0 2px 4px rgba(0,0,0,0.4);
    overflow:hidden;
  }
  .bar-fill {
    height:100%;
    border-radius:99px;
    background: linear-gradient(90deg, #ff7c44, #ff4040, #ff9d5c);
    box-shadow: 0 0 12px rgba(255,100,60,0.6);
    animation: barIn 1.4s cubic-bezier(.4,0,.2,1) 0.7s both;
    transform-origin: left;
  }
  @keyframes barIn { from{transform:scaleX(0)} to{transform:scaleX(1)} }

  /* ── LIVE BADGE ── */
  .live-badge {
    display:inline-flex; align-items:center; gap:6px;
    padding: 4px 10px;
    border-radius:99px;
    background: rgba(94,255,160,0.08);
    border: 1px solid rgba(94,255,160,0.2);
    font-family:'Fira Code',monospace;
    font-size:9px;
    color:var(--green);
    margin-left:10px;
    letter-spacing:0.08em;
  }
  .live-dot {
    width:6px; height:6px;
    border-radius:50%;
    background:var(--green);
    box-shadow:0 0 6px var(--green);
    animation: pulse 2s infinite;
  }

  /* ── GITHUB STATS IMAGES ── */
  .gh-stats-wrap { display:flex; flex-direction:column; gap:12px; }
  .gh-img-clay { padding:16px; overflow:hidden; }
  .gh-img-clay img { width:100%; border-radius:10px; display:block; }

  /* ── FOOTER ── */
  .footer {
    margin-top:44px;
    text-align:center;
    font-family:'Fira Code',monospace;
    font-size:10px;
    color:var(--muted);
    letter-spacing:0.1em;
    opacity:0;
    animation: popUp 0.6s ease forwards 0.9s;
  }
  .footer span { color:var(--pink); }

  /* ── RESPONSIVE ── */
  @media(max-width:480px){
    .socials-grid { grid-template-columns:1fr 1fr; }
    .stats-row    { grid-template-columns:repeat(3,1fr); }
    .header-text h1 { font-size:24px; }
  }
</style>
</head>
<body>

<div class="bg-blobs">
  <div class="blob blob1"></div>
  <div class="blob blob2"></div>
  <div class="blob blob3"></div>
</div>

<div class="wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="avatar-wrap">
      <div class="avatar">SS</div>
      <div class="status-dot"></div>
    </div>
    <div class="header-text">
      <h1><span class="first">Sujal </span><span class="last">Shelke</span></h1>
      <div class="tagline"><span>const</span> role = "Student · Web Developer · Builder"</div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section s1">
    <div class="sec-title">About Me</div>
    <div class="clay about-card">
      <div class="about-items">
        <div class="about-item"><div class="about-icon">🚀</div><span>Student &amp; Web Developer</span></div>
        <div class="about-item"><div class="about-icon">📖</div><span>Learning HTML, CSS &amp; JavaScript</span></div>
        <div class="about-item"><div class="about-icon">⚡</div><span>Building landing pages &amp; web projects</span></div>
        <div class="about-item"><div class="about-icon">🎯</div><span>Future full-stack developer</span></div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section s2">
    <div class="sec-title">
      Connect
      <span class="live-badge"><span class="live-dot"></span>live links</span>
    </div>
    <div class="socials-grid">

      <a href="https://instagram.com/sujal_shelke_" target="_blank" class="clay-btn btn-ig">
        <div class="btn-icon-wrap">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="white">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/>
          </svg>
        </div>
        <div class="btn-label">
          <span class="name">Instagram</span>
          <span class="handle">@sujal_shelke_</span>
        </div>
      </a>

      <a href="https://linkedin.com/in/sujalshelke" target="_blank" class="clay-btn btn-li">
        <div class="btn-icon-wrap">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="white">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </div>
        <div class="btn-label">
          <span class="name">LinkedIn</span>
          <span class="handle">sujalshelke</span>
        </div>
      </a>

      <a href="https://codepen.io/Sujal-Shelke" target="_blank" class="clay-btn btn-cp">
        <div class="btn-icon-wrap">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="#47cf73">
            <path d="M18.144 13.067v-2.134L16.55 12zm1.276 1.194a.628.628 0 01-.006.083l-.005.028-.011.053-.01.031c-.005.016-.01.031-.017.047l-.014.03a.78.78 0 01-.021.043l-.019.03a.57.57 0 01-.08.1l-.026.025a.602.602 0 01-.036.03l-.016.014-6.782 4.522a.637.637 0 01-.708 0L4.864 14.2l-.016-.014a.85.85 0 01-.036-.03l-.026-.025a.57.57 0 01-.08-.1l-.019-.03a.78.78 0 01-.021-.043l-.014-.03a1.088 1.088 0 01-.017-.047l-.01-.031-.011-.053-.005-.028a.628.628 0 01-.006-.083V9.739a.628.628 0 01.006-.083l.005-.028.011-.053.01-.031c.005-.016.01-.031.017-.047l.014-.03a.78.78 0 01.021-.043l.019-.03a.57.57 0 01.08-.1l.026-.025a.602.602 0 01.036-.03l.016-.014 6.782-4.522a.637.637 0 01.708 0l6.782 4.522.016.014a.602.602 0 01.036.03l.026.025a.57.57 0 01.08.1l.019.03a.78.78 0 01.021.043l.014.03c.007.016.012.031.017.047l.01.031.011.053.005.028a.628.628 0 01.006.083zM12 4.755L6.788 8.25 9.648 10.1 12 8.551V4.755zm0 14.49v-3.796l-2.352-1.549-2.86 1.849zm-5.212-3.837v-2.134L5.144 12zm10.424 0l1.444-1.067-1.444-1.067zm-1.28-4.17l-2.86-1.849L12 10.838l2.352 1.55zm-1.576 4.17L12 16.86l-3.356-2.452.856-.565L12 15.432l2.5-1.589.856.565zm1.276-1.194L15.352 13l-3.352-2.21-3.352 2.21 3.352 2.21zm0 0"/>
          </svg>
        </div>
        <div class="btn-label">
          <span class="name">CodePen</span>
          <span class="handle">Sujal-Shelke</span>
        </div>
      </a>

      <a href="mailto:sujalshelke33@gmail.com" class="clay-btn btn-gm">
        <div class="btn-icon-wrap">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="white">
            <path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.909v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.909 1.528-1.146C21.69 2.28 24 3.434 24 5.457z"/>
          </svg>
        </div>
        <div class="btn-label">
          <span class="name">Gmail</span>
          <span class="handle">sujalshelke33</span>
        </div>
      </a>

    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section s3">
    <div class="sec-title">Tech Stack</div>
    <div class="tech-wrap">
      <div class="tech-tag tag-html"><div class="tech-dot"></div>HTML5</div>
      <div class="tech-tag tag-css"><div class="tech-dot"></div>CSS3</div>
      <div class="tech-tag tag-js"><div class="tech-dot"></div>JavaScript</div>
      <div class="tech-tag tag-git"><div class="tech-dot"></div>Git</div>
      <div class="tech-tag tag-gh"><div class="tech-dot"></div>GitHub</div>
    </div>
  </div>

  <!-- GITHUB LIVE STATS -->
  <div class="section s4">
    <div class="sec-title">
      GitHub Stats
      <span class="live-badge"><span class="live-dot"></span>live · auto-updates</span>
    </div>
    <div class="gh-stats-wrap">
      <div class="clay gh-img-clay">
        <img src="https://github-readme-stats.vercel.app/api?username=Sujal-Shelke&show_icons=true&theme=transparent&hide_border=true&title_color=7eb8ff&text_color=c0d4f0&icon_color=5effa0&bg_color=00000000&rank_icon=github&include_all_commits=true" alt="GitHub Stats" loading="lazy"/>
      </div>
      <div class="clay gh-img-clay">
        <img src="https://github-readme-streak-stats.herokuapp.com?user=Sujal-Shelke&theme=transparent&hide_border=true&stroke=7eb8ff&ring=5effa0&fire=ffe066&currStreakNum=c0d4f0&sideNums=c0d4f0&currStreakLabel=7eb8ff&sideLabels=7eb8ff&dates=5a7090
