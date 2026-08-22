<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pouria Shaigan · ascii resume</title>
  <!-- Font Awesome (optional, for subtle icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0b0e14;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Fira Code', 'JetBrains Mono', 'Cascadia Code', monospace;
      padding: 1.5rem;
    }

    .ascii-card {
      max-width: 880px;
      width: 100%;
      background: #121820;
      border: 2px solid #2e3b4e;
      border-radius: 32px;
      padding: 2rem 2rem 2.2rem;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.8), 0 0 0 1px #2a3647 inset;
      transition: all 0.2s ease;
    }

    /* glow effect for the ascii art */
    .ascii-art {
      color: #b7d0e6;
      font-size: 0.75rem;
      line-height: 1.3;
      white-space: pre;
      font-weight: 400;
      letter-spacing: 0.02em;
      text-shadow: 0 0 6px rgba(100, 180, 255, 0.2);
      animation: flicker 3.2s infinite alternate;
      overflow-x: auto;
      padding: 0.5rem 0;
    }

    @keyframes flicker {
      0% { opacity: 0.92; text-shadow: 0 0 4px #3f6b9f; }
      100% { opacity: 1; text-shadow: 0 0 12px #6aa6ff, 0 0 20px #3f7bc0; }
    }

    /* blinking cursor effect on the header line */
    .cursor-blink {
      display: inline-block;
      width: 12px;
      height: 1.2em;
      background: #9bbdf0;
      margin-left: 4px;
      animation: blink 1s step-end infinite;
      vertical-align: text-bottom;
      border-radius: 2px;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }

    .tagline {
      color: #9bbdf0;
      font-size: 0.9rem;
      border-left: 3px solid #3f7bc0;
      padding-left: 1rem;
      margin: 0.5rem 0 1.5rem 0;
      letter-spacing: 0.3px;
      font-weight: 300;
      background: #1a2533;
      padding: 0.6rem 1rem;
      border-radius: 40px;
      display: inline-block;
      backdrop-filter: blur(2px);
      box-shadow: 0 0 12px rgba(60, 130, 255, 0.1);
    }

    .divider {
      border: 0;
      height: 1px;
      background: linear-gradient(90deg, #2e3f5a, #6a8bb0, #2e3f5a);
      margin: 1.4rem 0 1.8rem 0;
      opacity: 0.5;
    }

    .resume-grid {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 2rem;
      margin-top: 1rem;
    }

    @media (max-width: 650px) {
      .resume-grid {
        grid-template-columns: 1fr;
        gap: 1.2rem;
      }
    }

    .section-title {
      color: #c7ddf5;
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 2px;
      font-weight: 500;
      border-bottom: 1px dashed #3a506e;
      padding-bottom: 0.4rem;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .section-title i {
      color: #5f8bc9;
      font-size: 0.9rem;
      width: 1.4rem;
    }

    .info-line {
      color: #b7cfe5;
      font-size: 0.9rem;
      padding: 0.35rem 0;
      display: flex;
      align-items: center;
      gap: 12px;
      border-bottom: 1px solid #1e2b3b;
    }

    .info-line:last-child {
      border-bottom: none;
    }

    .info-label {
      color: #7f9fc9;
      min-width: 70px;
      font-weight: 300;
      letter-spacing: 0.3px;
    }

    .info-value {
      color: #d6e6ff;
      font-weight: 400;
      word-break: break-word;
    }

    .info-value a {
      color: #8bb9ff;
      text-decoration: none;
      border-bottom: 1px dotted #3d618b;
      transition: 0.2s;
    }

    .info-value a:hover {
      color: #b8d6ff;
      border-bottom: 1px solid #8bb9ff;
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px 10px;
      margin-top: 6px;
    }

    .skill-tag {
      background: #1f2d40;
      color: #bdd6f0;
      padding: 0.2rem 0.9rem;
      border-radius: 30px;
      font-size: 0.75rem;
      letter-spacing: 0.3px;
      border: 1px solid #314a66;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
      transition: all 0.15s;
      font-weight: 400;
    }

    .skill-tag:hover {
      background: #2b3f5a;
      border-color: #5f86b3;
      color: #e5f0ff;
      transform: scale(1.02);
      box-shadow: 0 0 12px #2f5580;
    }

    .social-icon {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: #1b2637;
      padding: 0.3rem 1rem 0.3rem 0.8rem;
      border-radius: 40px;
      border: 1px solid #314a66;
      transition: 0.2s;
    }

    .social-icon i {
      color: #7fa9e6;
      font-size: 1rem;
    }

    .social-icon:hover {
      background: #25344b;
      border-color: #5f86b3;
    }

    .footer-note {
      margin-top: 2rem;
      color: #4b678a;
      font-size: 0.7rem;
      text-align: center;
      letter-spacing: 1px;
      border-top: 1px solid #1f2d40;
      padding-top: 1.2rem;
      opacity: 0.8;
    }

    /* ascii decoration line */
    .ascii-divider {
      color: #2f4b6e;
      font-size: 0.6rem;
      letter-spacing: 2px;
      text-align: center;
      opacity: 0.5;
      margin: 0.2rem 0 0.8rem 0;
    }

    /* small screens */
    @media (max-width: 480px) {
      .ascii-art {
        font-size: 0.58rem;
        line-height: 1.2;
      }
      .ascii-card {
        padding: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <div class="ascii-card">

    <!-- ASCII HEADER with animation & blinking cursor -->
    <div class="ascii-art" aria-label="ASCII art header">
      <span style="color: #88b5f0;">╔</span><span style="color: #5e85b5;">═══════════════════════════════════════════</span><span style="color: #88b5f0;">╗</span>
      <span style="display:block; color: #b7d6ff;">║  ██╗  ██╗██╗    ██╗  ██╗ █████╗ ██╗ ██████╗ █████╗ ███╗   ██╗  ║</span>
      <span style="display:block; color: #a6c6f0;">║  ██║  ██║██║    ██║  ██║██╔══██╗██║██�════╝██╔══██╗████╗  ██║  ║</span>
      <span style="display:block; color: #94b8e6;">║  ███████║██║    ███████║███████║██║██║     ███████║██╔██╗ ██║  ║</span>
      <span style="display:block; color: #82aadc;">║  ██╔══██║██║    ██╔══██║██╔══██║██║██║     ██╔══██║██║╚██╗██║  ║</span>
      <span style="display:block; color: #6f96cf;">║  ██║  ██║██║    ██║  ██║██║  ██║██║╚██████╗██║  ██║██║ ╚████║  ║</span>
      <span style="display:block; color: #5581bf;">║  ╚═╝  ╚═╝╚═╝    ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝ ╚═════╝╚═╝  ╚═╝╚═╝  ╚═══╝  ║</span>
      <span style="color: #88b5f0;">╚</span><span style="color: #5e85b5;">═══════════════════════════════════════════</span><span style="color: #88b5f0;">╝</span>
      <span style="display:block; text-align:center; margin-top: 2px; color: #7ba0d0; letter-spacing: 6px;">◈  P O U R I A   S H A I G A N  ◈</span>
      <span style="display:block; text-align:center; font-size: 0.65rem; color: #4c6f97; margin-top: 2px;">&lt; programmer · cs student &gt;</span>
      <span style="display:block; text-align:center; margin-top: 3px;"><span class="cursor-blink" style="background: #6f9ae0;"></span> <span style="color: #6f9ae0; font-size: 0.7rem;">// resume loaded · 0x2A</span></span>
    </div>

    <!-- Tagline / contact -->
    <div class="tagline">
      <i class="fas fa-envelope" style="margin-right: 10px; color: #6590cf;"></i> 
      <span style="color: #b3d0f5;">shaiganidev@gmail.com</span> 
      <span style="margin: 0 8px; color: #3f618b;">|</span> 
      <i class="fab fa-linkedin" style="margin-right: 4px; color: #6590cf;"></i>
      <a href="#" style="color: #b3d0f5; text-decoration: none; border-bottom: 1px dotted #3d618b;">/in/pouriashaigani</a>
    </div>

    <hr class="divider">

    <!-- RESUME CONTENT: two columns -->
    <div class="resume-grid">
      <!-- left column: about + connect + skills -->
      <div>
        <div class="section-title">
          <i class="fas fa-user-astronaut"></i> about
        </div>
        <div class="info-line">
          <span class="info-label"><i class="fas fa-graduation-cap" style="margin-right: 6px;"></i>study</span>
          <span class="info-value">Computer Science · 2026</span>
        </div>
        <div class="info-line">
          <span class="info-label"><i class="fas fa-code"></i> role</span>
          <span class="info-value">Programmer · full-stack dev</span>
        </div>
        <div class="info-line" style="border-bottom: none; padding-bottom: 0;">
          <span class="info-label"><i class="fas fa-map-pin"></i> based</span>
          <span class="info-value">remote · global</span>
        </div>

        <div style="margin: 1.4rem 0 1rem 0;">
          <div class="section-title" style="margin-bottom: 0.5rem;">
            <i class="fas fa-handshake"></i> connect
          </div>
          <div style="display: flex; flex-wrap: wrap; gap: 10px;">
            <span class="social-icon"><i class="fab fa-linkedin-in"></i> <a href="#" style="color:#b3d0f5; text-decoration:none;">LinkedIn</a></span>
            <span class="social-icon"><i class="fab fa-github"></i> <a href="#" style="color:#b3d0f5; text-decoration:none;">GitHub</a></span>
            <span class="social-icon"><i class="fas fa-envelope"></i> <span style="color:#b3d0f5;">email</span></span>
          </div>
        </div>

        <!-- tools & languages (condensed) -->
        <div style="margin-top: 1.2rem;">
          <div class="section-title">
            <i class="fas fa-tools"></i> toolchain
          </div>
          <div class="skill-tags">
            <span class="skill-tag">Python</span>
            <span class="skill-tag">C#</span>
            <span class="skill-tag">Django</span>
            <span class="skill-tag">PostgreSQL</span>
            <span class="skill-tag">MySQL</span>
            <span class="skill-tag">MongoDB</span>
            <span class="skill-tag">MSSQL</span>
            <span class="skill-tag">HTML5</span>
            <span class="skill-tag">CSS3</span>
            <span class="skill-tag">Bootstrap</span>
            <span class="skill-tag">Git</span>
            <span class="skill-tag">Linux</span>
            <span class="skill-tag">Pandas</span>
            <span class="skill-tag">Postman</span>
          </div>
        </div>
      </div>

      <!-- right column: experience / projects / highlights -->
      <div>
        <div class="section-title">
          <i class="fas fa-laptop-code"></i> highlights
        </div>
        <div style="display: flex; flex-direction: column; gap: 0.7rem;">
          <div style="background: #17212e; padding: 0.6rem 1rem; border-radius: 16px; border-left: 3px solid #3f7bc0;">
            <div style="color: #c7ddf5; font-weight: 400; font-size: 0.8rem;">🧩 full-stack projects</div>
            <div style="color: #99bce6; font-size: 0.75rem; margin-top: 3px;">Django + PostgreSQL · REST APIs</div>
          </div>
          <div style="background: #17212e; padding: 0.6rem 1rem; border-radius: 16px; border-left: 3px solid #3f7bc0;">
            <div style="color: #c7ddf5; font-weight: 400; font-size: 0.8rem;">⚙️ C# & .NET core</div>
            <div style="color: #99bce6; font-size: 0.75rem; margin-top: 3px;">desktop apps · game dev playground</div>
          </div>
          <div style="background: #17212e; padding: 0.6rem 1rem; border-radius: 16px; border-left: 3px solid #3f7bc0;">
            <div style="color: #c7ddf5; font-weight: 400; font-size: 0.8rem;">📊 data & automation</div>
            <div style="color: #99bce6; font-size: 0.75rem; margin-top: 3px;">Pandas · ETL scripts · Linux tooling</div>
          </div>
          <div style="background: #17212e; padding: 0.6rem 1rem; border-radius: 16px; border-left: 3px solid #3f7bc0;">
            <div style="color: #c7ddf5; font-weight: 400; font-size: 0.8rem;">🌐 bootstrap & responsive</div>
            <div style="color: #99bce6; font-size: 0.75rem; margin-top: 3px;">modern UI · mobile-first</div>
          </div>
        </div>

        <!-- ascii mini divider -->
        <div class="ascii-divider">◈ ◈ ◈ ◈ ◈</div>

        <!-- quick resume note -->
        <div style="background: #101a26; border-radius: 20px; padding: 0.8rem 1.2rem; margin-top: 0.4rem; border: 1px solid #25364b;">
          <span style="color: #7f9fc9; font-size: 0.7rem; letter-spacing: 1px;"><i class="fas fa-terminal" style="margin-right: 8px;"></i>  cs student · building things</span>
          <div style="color: #9bb7dd; font-size: 0.8rem; margin-top: 3px;">“ clean code, creative solutions ”</div>
        </div>
      </div>
    </div>

    <!-- footer: ascii signature -->
    <div class="footer-note">
      <span style="color: #3a5a7a;">$</span>  Pouria Shaigan · <span style="color: #3a5a7a;">//</span>  ascii resume v1.0  <span style="color: #3a5a7a;">|</span>  <i class="fas fa-crown" style="color: #476f9e;"></i> 2026
    </div>

  </div>
</body>
</html>
