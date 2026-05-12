[index.html](https://github.com/user-attachments/files/27648323/index.html)
# toomeysimon.github.io<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Your Name — Projects</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg:        #1e1628;
      --bg2:       #261c34;
      --surface:   #2e2040;
      --border:    #3d2f55;
      --accent:    #c084fc;
      --accent2:   #a78bfa;
      --muted:     #7c6a96;
      --text:      #ede8f5;
      --text-dim:  #b09ec8;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Mono', monospace;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* subtle noise grain overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
      opacity: 0.5;
    }

    /* faint radial glow top-left */
    body::after {
      content: '';
      position: fixed;
      top: -200px;
      left: -200px;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, #6b3fa030 0%, transparent 70%);
      pointer-events: none;
      z-index: 0;
    }

    main {
      position: relative;
      z-index: 1;
      max-width: 720px;
      margin: 0 auto;
      padding: 80px 28px 120px;
    }

    /* ── Header ── */
    .header {
      margin-bottom: 64px;
      animation: fadeUp 0.6s ease both;
    }

    .header h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(2.4rem, 6vw, 3.8rem);
      line-height: 1.05;
      letter-spacing: -0.02em;
      color: var(--text);
    }

    .header h1 span {
      color: var(--accent);
      font-style: italic;
    }

    .header .tagline {
      margin-top: 14px;
      font-size: 0.82rem;
      color: var(--text-dim);
      letter-spacing: 0.04em;
      line-height: 1.7;
      max-width: 480px;
    }

    .header-divider {
      margin-top: 28px;
      height: 1px;
      background: linear-gradient(90deg, var(--border), transparent);
    }

    /* ── Section label ── */
    .section-label {
      font-size: 0.68rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 28px;
      animation: fadeUp 0.6s 0.1s ease both;
    }

    /* ── Project list (the sketch layout) ── */
    .projects {
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    /* Each row = project card + description, alternating sides */
    .project-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      align-items: start;
      padding: 28px 0;
      border-bottom: 1px solid var(--border);
      opacity: 0;
      animation: fadeUp 0.55s ease forwards;
      position: relative;
    }

    .project-row:last-child { border-bottom: none; }

    /* connector dot line between rows */
    .project-row:not(:last-child)::after {
      content: '';
      position: absolute;
      bottom: -1px;
      left: 50%;
      transform: translateX(-50%);
      width: 1px;
      height: 28px;
      background: repeating-linear-gradient(
        to bottom,
        var(--border) 0px,
        var(--border) 4px,
        transparent 4px,
        transparent 8px
      );
    }

    /* odd rows: card left, description right */
    .project-row:nth-child(odd) .project-card  { grid-column: 1; grid-row: 1; }
    .project-row:nth-child(odd) .project-desc  { grid-column: 2; grid-row: 1; }

    /* even rows: description left, card right — mirrors the sketch */
    .project-row:nth-child(even) .project-card { grid-column: 2; grid-row: 1; }
    .project-row:nth-child(even) .project-desc { grid-column: 1; grid-row: 1; }

    .project-row:nth-child(1) { animation-delay: 0.15s; }
    .project-row:nth-child(2) { animation-delay: 0.28s; }
    .project-row:nth-child(3) { animation-delay: 0.41s; }
    .project-row:nth-child(4) { animation-delay: 0.54s; }
    .project-row:nth-child(5) { animation-delay: 0.67s; }

    /* ── Project Card ── */
    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 22px 20px;
      transition: border-color 0.25s, transform 0.25s, box-shadow 0.25s;
      cursor: pointer;
    }

    .project-card:hover {
      border-color: var(--accent2);
      transform: translateY(-3px);
      box-shadow: 0 8px 32px #6b21a818;
    }

    .project-card a {
      text-decoration: none;
      color: inherit;
      display: block;
    }

    .project-number {
      font-size: 0.65rem;
      color: var(--muted);
      letter-spacing: 0.12em;
      margin-bottom: 8px;
    }

    .project-title {
      font-family: 'DM Serif Display', serif;
      font-size: 1.15rem;
      color: var(--text);
      line-height: 1.25;
      margin-bottom: 10px;
      transition: color 0.2s;
    }

    .project-card:hover .project-title { color: var(--accent); }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .tag {
      font-size: 0.62rem;
      letter-spacing: 0.08em;
      padding: 3px 9px;
      border-radius: 99px;
      border: 1px solid var(--border);
      color: var(--text-dim);
      background: var(--bg2);
    }

    .link-hint {
      display: inline-flex;
      align-items: center;
      gap: 5px;
      font-size: 0.68rem;
      color: var(--accent2);
      margin-top: 12px;
      letter-spacing: 0.04em;
      transition: gap 0.2s;
    }

    .project-card:hover .link-hint { gap: 8px; }

    /* ── Description box ── */
    .project-desc {
      padding: 16px 4px;
      display: flex;
      align-items: flex-start;
    }

    .desc-inner {
      border-left: 2px solid var(--border);
      padding-left: 16px;
    }

    .project-row:nth-child(even) .desc-inner {
      border-left: none;
      border-right: 2px solid var(--border);
      padding-left: 0;
      padding-right: 16px;
      text-align: right;
    }

    .project-desc p {
      font-size: 0.78rem;
      color: var(--text-dim);
      line-height: 1.75;
    }

    /* ── Footer ── */
    footer {
      margin-top: 80px;
      font-size: 0.7rem;
      color: var(--muted);
      letter-spacing: 0.06em;
      animation: fadeUp 0.6s 0.7s ease both;
      opacity: 0;
    }

    footer a {
      color: var(--accent2);
      text-decoration: none;
      transition: color 0.2s;
    }

    footer a:hover { color: var(--accent); }

    /* ── Animation ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── Responsive ── */
    @media (max-width: 560px) {
      .project-row {
        grid-template-columns: 1fr;
      }
      .project-row:nth-child(even) .project-card,
      .project-row:nth-child(odd)  .project-card { grid-column: 1; grid-row: 1; }
      .project-row:nth-child(even) .project-desc,
      .project-row:nth-child(odd)  .project-desc { grid-column: 1; grid-row: 2; }
      .project-row:nth-child(even) .desc-inner {
        border-right: none;
        border-left: 2px solid var(--border);
        padding-right: 0;
        padding-left: 16px;
        text-align: left;
      }
    }
  </style>
</head>
<body>
<main>

  <!-- ── Header ── -->
  <header class="header">
    <h1>Your <span>Name</span></h1>
    <p class="tagline">
      Insert a short line about yourself here — your field, your vibe,
      what you're building or studying. Keep it human.
    </p>
    <div class="header-divider"></div>
  </header>

  <p class="section-label">// selected projects</p>

  <!-- ── Projects ── -->
  <section class="projects">

    <!-- Project 1 — card left, description right -->
    <div class="project-row">
      <div class="project-card">
        <a href="https://github.com/yourusername/project-one" target="_blank" rel="noopener">
          <div class="project-number">01</div>
          <div class="project-title">Project One</div>
          <div class="project-tags">
            <span class="tag">Python</span>
            <span class="tag">Machine Learning</span>
          </div>
          <div class="link-hint">View on GitHub &rarr;</div>
        </a>
      </div>
      <div class="project-desc">
        <div class="desc-inner">
          <p>A short description of what this project does, why you built it, and what makes it interesting. Keep it conversational — you're talking to a person, not writing a resume.</p>
        </div>
      </div>
    </div>

    <!-- Project 2 — description left, card right -->
    <div class="project-row">
      <div class="project-card">
        <a href="https://github.com/yourusername/project-two" target="_blank" rel="noopener">
          <div class="project-number">02</div>
          <div class="project-title">Project Two</div>
          <div class="project-tags">
            <span class="tag">React</span>
            <span class="tag">Node.js</span>
          </div>
          <div class="link-hint">View on GitHub &rarr;</div>
        </a>
      </div>
      <div class="project-desc">
        <div class="desc-inner">
          <p>Describe what problem this solves or what you learned making it. A sentence or two is plenty — let the link do the rest of the talking.</p>
        </div>
      </div>
    </div>

    <!-- Project 3 — card left, description right -->
    <div class="project-row">
      <div class="project-card">
        <a href="https://github.com/yourusername/project-three" target="_blank" rel="noopener">
          <div class="project-number">03</div>
          <div class="project-title">Project Three</div>
          <div class="project-tags">
            <span class="tag">C++</span>
            <span class="tag">OpenGL</span>
          </div>
          <div class="link-hint">View on GitHub &rarr;</div>
        </a>
      </div>
      <div class="project-desc">
        <div class="desc-inner">
          <p>Maybe this one is a class project, a hackathon submission, or something you built for fun at 2am. That context is worth sharing.</p>
        </div>
      </div>
    </div>

  </section>

  <!-- ── Footer ── -->
  <footer>
    <p>
      &mdash; find me on
      <a href="https://github.com/yourusername" target="_blank">GitHub</a> &nbsp;·&nbsp;
      <a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a> &nbsp;·&nbsp;
      <a href="mailto:you@email.com">email</a>
    </p>
  </footer>

</main>
</body>
</html>
