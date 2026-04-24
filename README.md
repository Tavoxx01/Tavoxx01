<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Tavoxx01 — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --panel: #10101a;
    --border: #1e1e30;
    --accent: #7fffb2;
    --accent2: #5b8cff;
    --accent3: #ff6b6b;
    --text: #e0e0f0;
    --muted: #6b6b8a;
    --font-mono: 'Space Mono', monospace;
    --font-display: 'Syne', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(127,255,178,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(127,255,178,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 820px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 56px;
    animation: fadeDown 0.8s ease both;
  }

  .avatar-ring {
    display: inline-block;
    width: 96px;
    height: 96px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent3), var(--accent));
    padding: 3px;
    margin-bottom: 20px;
    animation: spin 6s linear infinite;
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--panel);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.4rem;
    animation: spin 6s linear infinite reverse;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .handle {
    font-family: var(--font-display);
    font-size: 2.8rem;
    font-weight: 800;
    letter-spacing: -1px;
    line-height: 1;
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 60%, var(--accent3) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .tagline {
    color: var(--muted);
    font-size: 0.78rem;
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  /* Typing bar */
  .typing-bar {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    margin-top: 18px;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 8px 16px;
    font-size: 0.82rem;
    color: var(--accent);
  }

  .typing-bar .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: blink 1.1s ease infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.2} }

  .typing-text::after {
    content: '|';
    animation: blink 0.8s step-start infinite;
    color: var(--accent);
  }

  /* ── SECTIONS ── */
  section {
    margin-bottom: 40px;
    animation: fadeUp 0.7s ease both;
  }

  section:nth-child(2) { animation-delay: 0.1s; }
  section:nth-child(3) { animation-delay: 0.2s; }
  section:nth-child(4) { animation-delay: 0.3s; }
  section:nth-child(5) { animation-delay: 0.4s; }
  section:nth-child(6) { animation-delay: 0.5s; }

  @keyframes fadeDown { from{opacity:0;transform:translateY(-20px)} to{opacity:1;transform:none} }
  @keyframes fadeUp   { from{opacity:0;transform:translateY(24px)}  to{opacity:1;transform:none} }

  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: var(--font-display);
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT CARD ── */
  .about-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .about-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 0.82rem;
    line-height: 1.5;
    color: var(--text);
  }

  .about-item .icon {
    font-size: 1rem;
    flex-shrink: 0;
    margin-top: 2px;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .project-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 16px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    transition: border-color 0.25s, transform 0.25s;
    text-decoration: none;
    color: inherit;
    display: block;
  }

  .project-card:hover {
    border-color: var(--accent);
    transform: translateY(-3px);
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.25s;
  }

  .project-card:hover::before { opacity: 1; }

  .project-icon {
    font-size: 1.4rem;
    margin-bottom: 10px;
  }

  .project-name {
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 0.85rem;
    color: var(--text);
    margin-bottom: 4px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .project-desc {
    font-size: 0.72rem;
    color: var(--muted);
    line-height: 1.4;
  }

  .project-arrow {
    position: absolute;
    top: 14px; right: 14px;
    color: var(--muted);
    font-size: 0.75rem;
    transition: color 0.2s, transform 0.2s;
  }

  .project-card:hover .project-arrow {
    color: var(--accent);
    transform: translate(2px, -2px);
  }

  /* ── TECH STACK ── */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 8px;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 8px 14px;
    font-size: 0.8rem;
    font-family: var(--font-mono);
    transition: border-color 0.2s, background 0.2s;
  }

  .tech-pill:hover {
    border-color: var(--accent2);
    background: rgba(91,140,255,0.08);
  }

  .tech-pill .t-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .stat-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent2), var(--accent));
  }

  .stat-value {
    font-family: var(--font-display);
    font-size: 2rem;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 0.7rem;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  /* ── STATUS ── */
  .status-card {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 22px;
    display: flex;
    align-items: center;
    gap: 20px;
  }

  .status-indicator {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.8rem;
  }

  .status-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 8px var(--accent);
    animation: pulse 2s ease infinite;
  }

  @keyframes pulse {
    0%,100% { box-shadow: 0 0 6px var(--accent); }
    50%      { box-shadow: 0 0 14px var(--accent); }
  }

  .status-divider {
    width: 1px; height: 28px;
    background: var(--border);
  }

  .status-text {
    font-size: 0.78rem;
    color: var(--muted);
  }

  .status-text strong {
    color: var(--text);
    display: block;
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 56px;
    text-align: center;
    font-size: 0.72rem;
    color: var(--muted);
    letter-spacing: 1px;
  }

  .footer span { color: var(--accent); }

  /* ── RESPONSIVE ── */
  @media (max-width: 600px) {
    .about-card { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr 1fr; }
    .handle { font-size: 2rem; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="avatar-ring">
      <div class="avatar-inner">👨‍💻</div>
    </div>
    <div class="handle">Tavoxx01</div>
    <div class="tagline">Developer · Scripter · Builder</div>
    <div class="typing-bar">
      <span class="dot"></span>
      <span class="typing-text">Automação · Roblox · Minecraft · Bots</span>
    </div>
  </header>

  <!-- SOBRE MIM -->
  <section>
    <div class="section-label">// sobre mim</div>
    <div class="about-card">
      <div class="about-item"><span class="icon">⚡</span><span>Scripts Roblox em Lua com foco em performance e escalabilidade</span></div>
      <div class="about-item"><span class="icon">🧱</span><span>Mods e Add-ons para Minecraft com Java & Bedrock</span></div>
      <div class="about-item"><span class="icon">🌐</span><span>Bots, APIs REST e servidores backend para automação</span></div>
      <div class="about-item"><span class="icon">🔗</span><span>Integração entre plataformas: Minecraft ↔ Roblox ↔ Discord</span></div>
    </div>
  </section>

  <!-- PROJETOS -->
  <section>
    <div class="section-label">// projetos em destaque</div>
    <div class="projects-grid">
      <a class="project-card" href="https://github.com/Tavoxx01/Game-videos-audios" target="_blank">
        <div class="project-arrow">↗</div>
        <div class="project-icon">🎮</div>
        <div class="project-name">Game-videos-audios</div>
        <div class="project-desc">Mídia e assets para projetos de jogos</div>
      </a>
      <a class="project-card" href="https://github.com/Tavoxx01/roblox-camera-server" target="_blank">
        <div class="project-arrow">↗</div>
        <div class="project-icon">📷</div>
        <div class="project-name">roblox-camera-server</div>
        <div class="project-desc">Servidor de câmera para experiências Roblox</div>
      </a>
      <a class="project-card" href="https://github.com/Tavoxx01/Ticketbotphotos" target="_blank">
        <div class="project-arrow">↗</div>
        <div class="project-icon">🤖</div>
        <div class="project-name">Ticketbotphotos</div>
        <div class="project-desc">Bot de tickets com suporte a imagens</div>
      </a>
    </div>
  </section>

  <!-- TECH STACK -->
  <section>
    <div class="section-label">// tecnologias</div>
    <div class="tech-grid">
      <div class="tech-pill"><span class="t-dot" style="background:#00aeff"></span>Lua</div>
      <div class="tech-pill"><span class="t-dot" style="background:#3572a5"></span>Python</div>
      <div class="tech-pill"><span class="t-dot" style="background:#b07219"></span>Java</div>
      <div class="tech-pill"><span class="t-dot" style="background:#f1e05a"></span>JavaScript</div>
      <div class="tech-pill"><span class="t-dot" style="background:#f05032"></span>Git</div>
      <div class="tech-pill"><span class="t-dot" style="background:#7fffb2"></span>GitHub</div>
    </div>
  </section>

  <!-- STATS -->
  <section>
    <div class="section-label">// estatísticas</div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-value">3+</div>
        <div class="stat-label">Projetos</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">4</div>
        <div class="stat-label">Linguagens</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">∞</div>
        <div class="stat-label">Em evolução</div>
      </div>
    </div>
  </section>

  <!-- STATUS -->
  <section>
    <div class="section-label">// status atual</div>
    <div class="status-card">
      <div class="status-indicator">
        <div class="status-dot"></div>
        <span style="color:var(--accent);font-size:0.8rem">Online</span>
      </div>
      <div class="status-divider"></div>
      <div class="status-text"><strong>Criando projetos</strong>construindo coisas novas</div>
      <div class="status-divider"></div>
      <div class="status-text"><strong>Evoluindo</strong>sempre aprendendo</div>
    </div>
  </section>

  <!-- FOOTER -->
  <div class="footer">
    Feito com <span>♥</span> por Tavoxx01 · github.com/Tavoxx01
  </div>

</div>
</body>
</html>
