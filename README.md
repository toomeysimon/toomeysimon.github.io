<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Your Name</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: #1e1628;
      color: #e0d6f0;
      font-family: Verdana, Geneva, sans-serif;
      font-size: 15px;
      padding: 40px 20px;
    }

    .container {
      max-width: 650px;
      margin: 0 auto;
    }

    h1 {
      font-size: 2rem;
      color: #c084fc;
      margin-bottom: 6px;
      animation: fadeIn 0.6s ease both;
    }

    .subtitle {
      color: #9d89b8;
      font-size: 0.88rem;
      margin-bottom: 30px;
      animation: fadeIn 0.6s 0.1s ease both;
      opacity: 0;
    }

    hr {
      border: none;
      border-top: 1px solid #3d2f55;
      margin-bottom: 32px;
      animation: fadeIn 0.6s 0.2s ease both;
      opacity: 0;
    }

    .about {
      margin-bottom: 36px;
      line-height: 1.8;
      color: #c4b8d8;
      font-size: 0.9rem;
      animation: fadeIn 0.6s 0.25s ease both;
      opacity: 0;
    }

    .section-title {
      font-size: 1rem;
      color: #c084fc;
      margin-bottom: 18px;
      animation: fadeIn 0.6s 0.3s ease both;
      opacity: 0;
    }

    .projects {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .project {
      background: #261c34;
      border: 1px solid #3d2f55;
      border-radius: 6px;
      overflow: hidden;
      opacity: 0;
      animation: slideUp 0.5s ease forwards;
      transition: border-color 0.2s, transform 0.2s;
    }

    .project:hover {
      border-color: #c084fc;
      transform: translateY(-2px);
    }

    .project:nth-child(1) { animation-delay: 0.35s; }
    .project:nth-child(2) { animation-delay: 0.48s; }
    .project:nth-child(3) { animation-delay: 0.61s; }
    .project:nth-child(4) { animation-delay: 0.74s; }

    /* image area */
    .project-img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      display: block;
      background: #2e2040;
    }

    /* placeholder shown when no real image is set */
    .project-img-placeholder {
      width: 100%;
      height: 180px;
      background: #2e2040;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #4a3860;
      font-size: 0.75rem;
      letter-spacing: 0.05em;
      border-bottom: 1px solid #3d2f55;
    }

    .project-body {
      padding: 16px 20px 18px;
    }

    .project a {
      color: #c084fc;
      text-decoration: none;
      font-size: 1rem;
      font-weight: bold;
    }

    .project a:hover {
      text-decoration: underline;
    }

    .project p {
      margin-top: 8px;
      font-size: 0.82rem;
      color: #a094bb;
      line-height: 1.7;
    }

    .project-meta {
      margin-top: 10px;
      font-size: 0.72rem;
      color: #6b5a85;
    }

    footer {
      margin-top: 48px;
      font-size: 0.78rem;
      color: #6b5a85;
      animation: fadeIn 0.6s 0.8s ease both;
      opacity: 0;
    }

    footer a {
      color: #a78bfa;
      text-decoration: none;
    }

    footer a:hover { text-decoration: underline; }

    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }

    @keyframes slideUp {
      from { opacity: 0; transform: translateY(14px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
<div class="container">

  <h1>Simon Toomey</h1>
  <p class="subtitle">cs student / content creator / making stuff for fun</p>

  <hr>

  <p class="about">
    junior studying computer science at west high.
    im not good at anything but i like to think i make an honest effort
    anyway here are some things that i do:
  </p>

  <p class="section-title">— projects</p>

  <div class="projects">

    <div class="project">
      <!-- Replace the placeholder div below with:
           <img class="project-img" src="images/project1.png" alt="Project One screenshot" />  -->
      <div class="project-img-placeholder">[ add a screenshot here ]</div>
      <div class="project-body">
        <a href="https://github.com/yourusername/project-one" target="_blank">bongomatic</a>
        <p>a youtube channel formed out of sheer boredom 1.5k subscribers and counting, 140,000 total views across 7 videos, taught me how to handle video editing, audio engineering, image editing, voice acting, and commenters telling me to kill myself</p>
        <div class="project-meta">youtube · 2025</div>
      </div>
    </div>

    <div class="project">
      <div class="project-img-placeholder">[ add a screenshot here ]</div>
      <div class="project-body">
        <a href="https://github.com/yourusername/project-two" target="_blank">jakfruit jonez</a>
        <p>following the mediocre lucrative success of bongomatic, i used the money to kickstart jakfruit jonez; a music coalition consisting of me and my friends. is the music good? no. but ive learned a lot about art, animation, music production, vocals, and more commenters telling me to kill myself. </p>
        <div class="project-meta">youtube · 2026</div>
      </div>
    </div>

    <div class="project">
      <div class="project-img-placeholder">[ add a screenshot here ]</div>
      <div class="project-body">
        <a href="https://github.com/yourusername/project-three" target="_blank">Double Entendre</a>
        <p>Maybe a hackathon project or something you built at 2am. That's the most honest kind of project description.</p>
        <div class="project-meta">Python · 2027</div>
      </div>
    </div>

  </div>

  <footer>
    <p>find me on <a href="https://github.com/toomeysimon" target="_blank">github</a> · <a href="mailto:toomeysimon09@gmail.com">email me</a></p>
  </footer>

</div>
</body>
</html>
