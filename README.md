index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yikey Cindy Nfotabong — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #F5F6FA;
    --surface: #FFFFFF;
    --ink: #1A1F36;
    --ink-soft: #565F7E;
    --accent: #2F9E76;
    --accent-2: #E8A23D;
    --line: #DFE3ED;
    --term-bg: #12151C;
    --term-text: #D7E4DE;
    --term-prompt: #4FD69C;
    --mono: 'JetBrains Mono', monospace;
    --body: 'Inter', sans-serif;
  }

  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    margin: 0;
    font-family: var(--body);
    background: var(--bg);
    color: var(--ink);
    line-height: 1.65;
  }

  a { color: inherit; }

  .wrap {
    max-width: 760px;
    margin: 0 auto;
    padding: 0 24px;
  }

  nav {
    position: sticky;
    top: 0;
    background: rgba(245, 246, 250, 0.92);
    backdrop-filter: blur(6px);
    border-bottom: 1px solid var(--line);
    z-index: 10;
  }
  .nav-inner {
    max-width: 760px;
    margin: 0 auto;
    padding: 16px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
  }
  .nav-brand {
    font-family: var(--mono);
    font-weight: 700;
    font-size: 0.95em;
  }
  .nav-links {
    display: flex;
    gap: 22px;
    font-family: var(--mono);
    font-size: 0.85em;
  }
  .nav-links a {
    text-decoration: none;
    color: var(--ink-soft);
    border-bottom: 2px solid transparent;
    padding-bottom: 2px;
  }
  .nav-links a:hover,
  .nav-links a:focus-visible {
    color: var(--ink);
    border-bottom-color: var(--accent);
  }
  .status-badge {
    font-family: var(--mono);
    font-size: 0.75em;
    background: #E7F5EE;
    color: var(--accent);
    padding: 4px 10px;
    border-radius: 100px;
    border: 1px solid #BFE6D3;
    white-space: nowrap;
  }
  .status-badge::before {
    content: "●";
    margin-right: 6px;
  }

  header.hero {
    padding: 64px 0 40px;
  }
  .hero-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 32px;
  }
  .eyebrow {
    font-family: var(--mono);
    font-size: 0.8em;
    color: var(--accent);
    letter-spacing: 0.04em;
    margin: 0 0 10px;
  }
  h1 {
    font-family: var(--body);
    font-size: clamp(1.9em, 5vw, 2.6em);
    font-weight: 700;
    margin: 0 0 14px;
    line-height: 1.15;
  }
  .hero-sub {
    color: var(--ink-soft);
    font-size: 1.05em;
    max-width: 46ch;
    margin: 0 0 24px;
  }

  .terminal {
    background: var(--term-bg);
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 20px 40px -18px rgba(18, 21, 28, 0.45);
    font-family: var(--mono);
  }
  .terminal-bar {
    display: flex;
    gap: 7px;
    padding: 12px 14px;
    background: #1B1F29;
  }
  .terminal-bar span {
    width: 11px;
    height: 11px;
    border-radius: 50%;
    display: inline-block;
    background: #3A3F4B;
  }
  .terminal-bar span:nth-child(1) { background: #E8746A; }
  .terminal-bar span:nth-child(2) { background: #E8A23D; }
  .terminal-bar span:nth-child(3) { background: #4FD69C; }
  .terminal-body {
    padding: 20px 18px 26px;
    color: var(--term-text);
    font-size: 0.88em;
    min-height: 168px;
  }
  .terminal-body .line { margin: 0 0 10px; }
  .prompt { color: var(--term-prompt); }
  .output { color: #9AA7A2; }
  .cursor {
    display: inline-block;
    width: 7px;
    height: 1em;
    background: var(--term-prompt);
    vertical-align: text-bottom;
    animation: blink 1s steps(1) infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }
  @media (prefers-reduced-motion: reduce) {
    .cursor { animation: none; }
  }

  section { padding: 48px 0; border-top: 1px solid var(--line); }
  .section-head {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 26px;
  }
  .section-num {
    font-family: var(--mono);
    color: var(--accent);
    font-size: 0.85em;
  }
  h2 {
    font-size: 1.3em;
    margin: 0;
  }

  .about-text { color: var(--ink-soft); max-width: 62ch; }
  .about-text strong { color: var(--ink); }

  .skills-list { display: flex; flex-direction: column; gap: 14px; }
  .skill-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    padding: 14px 16px;
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: 8px;
    flex-wrap: wrap;
  }
  .skill-name { font-weight: 600; font-size: 0.98em; }
  .skill-stage {
    font-family: var(--mono);
    font-size: 0.75em;
    padding: 4px 10px;
    border-radius: 100px;
    white-space: nowrap;
  }
  .stage-learning { background: #FDF1DF; color: #A8720F; border: 1px solid #F3D9A8; }
  .stage-familiar { background: #E7F5EE; color: #1E7A56; border: 1px solid #BFE6D3; }

  .commit-card {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 18px 20px;
    margin-bottom: 16px;
  }
  .commit-meta {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: var(--mono);
    font-size: 0.78em;
    color: var(--ink-soft);
    margin-bottom: 8px;
  }
  .commit-hash {
    background: #EEF1F7;
    color: var(--ink-soft);
    padding: 2px 8px;
    border-radius: 5px;
  }
  .commit-card h3 { margin: 0 0 8px; font-size: 1.05em; }
  .commit-card p { margin: 0 0 12px; color: var(--ink-soft); }
  .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-family: var(--mono);
    font-size: 0.75em;
    background: #F0F2F7;
    color: var(--ink-soft);
    padding: 3px 9px;
    border-radius: 100px;
  }
  .commit-card a.repo-link {
    display: inline-block;
    margin-top: 12px;
    font-family: var(--mono);
    font-size: 0.85em;
    color: var(--accent);
    text-decoration: none;
    border-bottom: 1px solid transparent;
  }
  .commit-card a.repo-link:hover,
  .commit-card a.repo-link:focus-visible {
    border-bottom-color: var(--accent);
  }

  .contact-terminal {
    background: var(--term-bg);
    border-radius: 10px;
    padding: 20px 22px;
    font-family: var(--mono);
    color: var(--term-text);
    font-size: 0.9em;
  }
  .contact-terminal .line { margin: 0 0 8px; }
  .contact-terminal a { color: var(--term-prompt); text-decoration: none; }
  .contact-terminal a:hover, .contact-terminal a:focus-visible { text-decoration: underline; }

  footer {
    text-align: center;
    padding: 30px 24px 50px;
    color: var(--ink-soft);
    font-family: var(--mono);
    font-size: 0.8em;
  }

  a:focus-visible, button:focus-visible {
    outline: 2px solid var(--accent);
    outline-offset: 3px;
  }

  @media (min-width: 640px) {
    .hero-grid { grid-template-columns: 1fr 1.05fr; align-items: center; gap: 40px; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <div class="nav-brand">yikey<span style="color:var(--accent)">.</span>dev</div>
    <div class="nav-links">
      <a href="#about">about</a>
      <a href="#skills">skills</a>
      <a href="#projects">projects</a>
      <a href="#contact">contact</a>
    </div>
    <div class="status-badge">learning in public</div>
  </div>
</nav>

<div class="wrap">

  <header class="hero">
    <div class="hero-grid">
      <div>
        <p class="eyebrow">// year 1 · software engineering</p>
        <h1>Yikey Cindy Nfotabong</h1>
        <p class="hero-sub">
          First-year software engineering student at the College of Technology,
          learning full-stack development one project at a time — currently
          focused on Python, JavaScript, and Node.js.
        </p>
      </div>

      <div class="terminal" role="img" aria-label="Terminal window showing an introduction">
        <div class="terminal-bar"><span></span><span></span><span></span></div>
        <div class="terminal-body">
          <p class="line"><span class="prompt">$</span> whoami</p>
          <p class="line output">&gt; Yikey Cindy Nfotabong<br>&gt; Year 1, Software Engineering</p>
          <p class="line"><span class="prompt">$</span> status --current</p>
          <p class="line output">&gt; learning: Python, JavaScript, Node.js<br>&gt; building: small practice projects</p>
          <p class="line"><span class="prompt">$</span> <span class="cursor"></span></p>
        </div>
      </div>
    </div>
  </header>

  <section id="about">
    <div class="section-head">
      <span class="section-num">01</span>
      <h2>About</h2>
    </div>
    <p class="about-text">
      I'm just getting started in software engineering, and I like it that way — every
      project teaches me something I didn't know last week. Right now I'm building a
      <strong>foundation in Python</strong> and picking up <strong>JavaScript and Node.js</strong>
      through coursework and small projects I build on my own. I'm especially drawn to
      backend logic — figuring out how the pieces of an app actually talk to each other.
      I'm looking for an internship where I can learn from people who've been doing this
      longer than I have, and contribute wherever I'm useful along the way.
    </p>
  </section>

  <section id="skills">
    <div class="section-head">
      <span class="section-num">02</span>
      <h2>Skills</h2>
    </div>
    <div class="skills-list">
      <div class="skill-row">
        <span class="skill-name">Python</span>
        <span class="skill-stage stage-familiar">working knowledge</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">JavaScript</span>
        <span class="skill-stage stage-learning">currently learning</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Node.js</span>
        <span class="skill-stage stage-learning">currently learning</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">HTML &amp; CSS</span>
        <span class="skill-stage stage-familiar">working knowledge</span>
      </div>
      <div class="skill-row">
        <span class="skill-name">Git &amp; GitHub</span>
        <span class="skill-stage stage-familiar">working knowledge</span>
      </div>
    </div>
  </section>

  <section id="projects">
    <div class="section-head">
      <span class="section-num">03</span>
      <h2>Projects</h2>
    </div>

    <div class="commit-card">
      <div class="commit-meta">
        <span class="commit-hash">#001</span>
        <span>practice project</span>
      </div>
      <h3>[Project Name 1]</h3>
      <p>[What it does and what you were practicing]</p>
      <div class="tag-row">
        <span class="tag">[tech 1]</span>
        <span class="tag">[tech 2]</span>
      </div>
      <a class="repo-link" href="#">[link to GitHub repo] →</a>
    </div>

    <div class="commit-card">
      <div class="commit-meta">
        <span class="commit-hash">#002</span>
        <span>practice project</span>
      </div>
      <h3>[Project Name 2]</h3>
      <p>[Short description]</p>
      <div class="tag-row">
        <span class="tag">[tech 1]</span>
        <span class="tag">[tech 2]</span>
      </div>
      <a class="repo-link" href="#">[link to GitHub repo] →</a>
    </div>
  </section>

  <section id="contact">
    <div class="section-head">
      <span class="section-num">04</span>
      <h2>Contact</h2>
    </div>
    <div class="contact-terminal">
      <p class="line"><span class="prompt">$</span> contact --info</p>
      <p class="line">&gt; phone: 676 533 009</p>
      <p class="line">&gt; email: <a href="mailto:your.email.com">[yikeycindy@gmail.com]</a></p>
      <p class="line">&gt; github: <a href="https://github.com/yikeycindy-beep">github.com/yikeycindy-beep</a></p>
    </div>
  </section>

</div>

<footer>
  built by Yikey Cindy Nfotabong · 2026
</footer>

</body>
</html>