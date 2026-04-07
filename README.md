
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tharun Naredla – Product-Focused Engineering Leader</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&family=Inter:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    :root {
      --primary: #00d4ff;
      --bg: #0f1419;
      --card: #1a1f2e;
      --border: #2a3142;
      --fg: #e8eef5;
      --fg-muted: #8a92a8;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { background: var(--bg); color: var(--fg); font-family: 'Inter', sans-serif; overflow-x: hidden; }
    h1, h2, h3, h4 { font-family: 'Poppins', sans-serif; }

    .text-gradient {
      background: linear-gradient(90deg, #22d3ee, #facc15);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .accent-line {
      height: 4px; width: 48px;
      background: linear-gradient(90deg, #22d3ee, #facc15);
      border-radius: 9999px;
      margin-bottom: 1rem;
    }
    .glass {
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255,255,255,0.1);
    }
    .glow { box-shadow: 0 8px 32px rgba(0, 212, 255, 0.15); }
    .btn-primary {
      background: var(--primary); color: #0f1419;
      padding: 0.75rem 1.75rem; border-radius: 0.5rem;
      font-weight: 600; font-size: 0.95rem;
      border: none; cursor: pointer;
      transition: opacity 0.2s, transform 0.2s;
      display: inline-flex; align-items: center; gap: 0.5rem;
    }
    .btn-primary:hover { opacity: 0.85; transform: translateY(-1px); }
    .btn-outline {
      background: transparent; color: var(--primary);
      padding: 0.75rem 1.75rem; border-radius: 0.5rem;
      font-weight: 600; font-size: 0.95rem;
      border: 1px solid rgba(0, 212, 255, 0.5); cursor: pointer;
      transition: border-color 0.2s, transform 0.2s;
      display: inline-flex; align-items: center; gap: 0.5rem;
    }
    .btn-outline:hover { border-color: var(--primary); transform: translateY(-1px); }

    /* NAV */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 50;
      transition: background 0.3s, border-color 0.3s;
    }
    nav.scrolled {
      background: rgba(15,20,25,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }
    .nav-inner {
      max-width: 1280px; margin: 0 auto; padding: 0 2rem;
      display: flex; align-items: center; justify-content: space-between;
      height: 64px;
    }
    .nav-links { display: flex; align-items: center; gap: 2rem; }
    .nav-links a {
      color: rgba(232,238,245,0.7); text-decoration: none;
      font-size: 0.875rem; transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--primary); }

    /* HERO */
    .hero {
      min-height: 100vh; display: flex; align-items: center;
      justify-content: center; padding-top: 80px; position: relative; overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background-image: url('https://d2xsxph8kpxj0f.cloudfront.net/310519663039612424/6Jda9qj7WmyFQ6XMExcTkt/hero_background-4aq73S2XRsDmTDRp4HUads.webp');
      background-size: cover; background-position: center;
    }
    .hero-bg::after { content: ''; position: absolute; inset: 0; background: rgba(0,0,0,0.45); }
    .hero-content {
      position: relative; z-index: 10;
      max-width: 1280px; margin: 0 auto; padding: 0 2rem;
      display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center;
    }
    @media (max-width: 768px) {
      .hero-content { grid-template-columns: 1fr; }
      .stats-grid { display: none; }
      .nav-links a { display: none; }
    }
    .hero-title { font-size: clamp(2.5rem, 6vw, 4.5rem); font-weight: 700; line-height: 1.1; margin-bottom: 1.5rem; }
    .hero-sub { font-size: 1.1rem; color: rgba(232,238,245,0.8); max-width: 420px; line-height: 1.7; margin-bottom: 2rem; }
    .hero-btns { display: flex; flex-wrap: wrap; gap: 1rem; margin-bottom: 2.5rem; }
    .social-links { display: flex; gap: 1rem; }
    .social-links a {
      padding: 0.75rem; border-radius: 0.5rem;
      background: rgba(255,255,255,0.05); backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.1);
      color: var(--primary); text-decoration: none;
      transition: background 0.2s; display: flex; align-items: center;
    }
    .social-links a:hover { background: rgba(255,255,255,0.12); }
    .social-links svg { width: 20px; height: 20px; fill: currentColor; }

    .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }
    .stat-card {
      padding: 1.5rem; border-radius: 0.75rem;
    }
    .stat-num { font-size: 2rem; font-weight: 700; margin-bottom: 0.25rem; }
    .stat-label { font-size: 0.8rem; color: rgba(232,238,245,0.6); }

    .scroll-indicator {
      position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%); z-index: 10;
      animation: bounce 2s infinite;
    }
    .scroll-indicator .mouse {
      width: 24px; height: 40px; border: 2px solid var(--primary);
      border-radius: 9999px; display: flex; align-items: flex-start;
      justify-content: center; padding: 6px;
    }
    .scroll-indicator .dot { width: 4px; height: 8px; background: var(--primary); border-radius: 9999px; animation: pulse 2s infinite; }
    @keyframes bounce { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(10px); } }
    @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.4; } }

    /* SECTIONS */
    section { padding: 5rem 0; }
    .container { max-width: 1280px; margin: 0 auto; padding: 0 2rem; }
    .section-alt { background: rgba(26,31,46,0.5); }
    .section-header { margin-bottom: 3rem; }
    .section-title { font-size: clamp(2rem, 4vw, 3rem); font-weight: 700; }

    /* ABOUT */
    .about-text { font-size: 1.05rem; color: rgba(232,238,245,0.8); max-width: 760px; line-height: 1.8; margin-bottom: 1.25rem; }

    /* EXPERIENCE */
    .exp-list { display: flex; flex-direction: column; gap: 1.5rem; }
    .exp-card { padding: 2rem; border-radius: 0.75rem; }
    .exp-header { display: flex; justify-content: space-between; align-items: flex-start; gap: 1rem; margin-bottom: 0.75rem; flex-wrap: wrap; }
    .exp-title { font-size: 1.1rem; font-weight: 600; color: var(--primary); margin-bottom: 0.15rem; }
    .exp-company { color: rgba(232,238,245,0.65); font-size: 0.95rem; }
    .exp-meta { text-align: right; font-size: 0.82rem; color: rgba(232,238,245,0.5); white-space: nowrap; }
    .exp-desc { color: rgba(232,238,245,0.75); line-height: 1.7; font-size: 0.95rem; }

    /* SKILLS */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 2rem; }
    .skill-card { padding: 1.75rem; border-radius: 0.75rem; }
    .skill-cat { font-size: 1rem; font-weight: 600; color: var(--primary); margin-bottom: 1rem; }
    .skill-list { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }
    .skill-list li { color: rgba(232,238,245,0.75); font-size: 0.92rem; display: flex; gap: 0.6rem; align-items: flex-start; }
    .skill-list li span { color: var(--primary); margin-top: 1px; }

    /* CTA */
    .cta-card { padding: 4rem 3rem; border-radius: 0.75rem; text-align: center; }
    .cta-title { font-size: clamp(1.5rem, 3vw, 2.25rem); font-weight: 700; margin-bottom: 1rem; }
    .cta-sub { color: rgba(232,238,245,0.75); max-width: 520px; margin: 0 auto 2rem; line-height: 1.7; }
    .cta-btns { display: flex; flex-wrap: wrap; gap: 1rem; justify-content: center; }

    /* FOOTER */
    footer { border-top: 1px solid var(--border); padding: 2rem 0; }
    .footer-inner { max-width: 1280px; margin: 0 auto; padding: 0 2rem; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1rem; }
    .footer-copy { font-size: 0.82rem; color: rgba(232,238,245,0.45); }
    .footer-links { display: flex; gap: 1.5rem; }
    .footer-links a { font-size: 0.82rem; color: rgba(232,238,245,0.45); text-decoration: none; transition: color 0.2s; }
    .footer-links a:hover { color: var(--primary); }

    /* ANIMATIONS */
    .fade-in { opacity: 0; transform: translateY(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .fade-in.visible { opacity: 1; transform: translateY(0); }
    .fade-in-left { opacity: 0; transform: translateX(-24px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .fade-in-left.visible { opacity: 1; transform: translateX(0); }
    .fade-in-right { opacity: 0; transform: translateX(24px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .fade-in-right.visible { opacity: 1; transform: translateX(0); }
    .delay-1 { transition-delay: 0.1s; }
    .delay-2 { transition-delay: 0.2s; }
    .delay-3 { transition-delay: 0.3s; }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav id="navbar">
    <div class="nav-inner">
      <span style="font-size:3.1rem;font-weight:700;" class="text-gradient">Tharun Naredla</span>
      <div class="nav-links">
        <a href="#about">About</a>
        <a href="#experience">Experience</a>
        <a href="#skills">Skills</a>
        <a href="mailto:naredlatharun@gmail.com" class="btn-outline" style="padding:0.4rem 1rem;font-size:0.85rem;">Contact</a>
      </div>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="hero-content">
      <div>
        <div class="accent-line"></div>
        <h1 class="hero-title">
          Product-Focused<br>
          <span class="text-gradient">Engineering Leader</span>
        </h1>
        <p class="hero-sub">
          6+ years driving end-to-end product development from concept to manufacturing. Specialized in electromechanical systems, cross-functional leadership, and scalable solutions.
        </p>
        <div class="hero-btns">
          <a href="#experience" class="btn-primary">
            View My Work
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
          <a href="#" class="btn-outline">Download Resume</a>
        </div>
        <div class="social-links">
          <a href="https://linkedin.com/in/tharun-naredla" target="_blank" title="LinkedIn">
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          </a>
          <a href="mailto:naredlatharun@gmail.com" title="Email">
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4-8 5-8-5V6l8 5 8-5v2z"/></svg>
          </a>
          <a href="#" title="GitHub">
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
          </a>
        </div>
      </div>
      <div class="stats-grid">
        <div class="stat-card glass glow fade-in delay-1">
          <div class="stat-num text-gradient">6+</div>
          <p class="stat-label">Years Experience</p>
        </div>
        <div class="stat-card glass glow fade-in delay-2">
          <div class="stat-num text-gradient">50+</div>
          <p class="stat-label">Projects Delivered</p>
        </div>
        <div class="stat-card glass glow fade-in delay-3">
          <div class="stat-num text-gradient">15+</div>
          <p class="stat-label">Team Members Led</p>
        </div>
        <div class="stat-card glass glow fade-in delay-1">
          <div class="stat-num text-gradient">1</div>
          <p class="stat-label">Patent Holder</p>
        </div>
      </div>
    </div>
    <div class="scroll-indicator">
      <div class="mouse"><div class="dot"></div></div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about" class="section-alt">
    <div class="container">
      <div class="section-header fade-in">
        <div class="accent-line"></div>
        <h2 class="section-title">About Me</h2>
      </div>
      <p class="about-text fade-in">
        I'm a product-focused engineering leader with a passion for translating complex user needs into scalable, manufacturable solutions. My journey spans electromechanical design, cross-functional team leadership, and driving products from concept through to market.
      </p>
      <p class="about-text fade-in delay-1">
        Currently leading product development at Keystone Robotix, where I'm architecting an AI-powered automated cooking platform. My expertise includes product lifecycle management, DFM/DFA optimization, rapid prototyping, and building high-performing teams across mechanical, electronics, and embedded systems disciplines.
      </p>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="experience">
    <div class="container">
      <div class="section-header fade-in">
        <div class="accent-line"></div>
        <h2 class="section-title">Experience</h2>
      </div>
      <div class="exp-list">

        <div class="exp-card glass glow fade-in-left">
          <div class="exp-header">
            <div>
              <p class="exp-title">Senior Product Design Engineer & Project Lead</p>
              <p class="exp-company">Keystone Robotix</p>
            </div>
            <div class="exp-meta">
              <p>Aug 2024 – Present</p>
              <p>Hyderabad</p>
            </div>
          </div>
          <p class="exp-desc">
            Leading development of an AI-powered automated cooking platform from concept to production. Defined product architecture, managed cross-functional teams, and conducted DFMEA for manufacturing readiness.
          </p>
        </div>

        <div class="exp-card glass glow fade-in-right delay-1">
          <div class="exp-header">
            <div>
              <p class="exp-title">Senior Product Design Engineer</p>
              <p class="exp-company">Quainnt Techsoft Pvt. Ltd.</p>
            </div>
            <div class="exp-meta">
              <p>May 2022 – Aug 2024</p>
              <p>Hyderabad</p>
            </div>
          </div>
          <p class="exp-desc">
            Owned mechanical design for multiple consumer and industrial products. Led design team in delivering production-ready CAD, BOM, and manufacturing packages.
          </p>
        </div>

        <div class="exp-card glass glow fade-in-left delay-2">
          <div class="exp-header">
            <div>
              <p class="exp-title">Product Development Engineer</p>
              <p class="exp-company">Quainnt Techsoft Pvt. Ltd.</p>
            </div>
            <div class="exp-meta">
              <p>May 2019 – May 2022</p>
              <p>Hyderabad</p>
            </div>
          </div>
          <p class="exp-desc">
            Designed and developed electromechanical assemblies for early-stage products. Built and tested prototypes to validate design concepts.
          </p>
        </div>

      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills" class="section-alt">
    <div class="container">
      <div class="section-header fade-in">
        <div class="accent-line"></div>
        <h2 class="section-title">Core Skills</h2>
      </div>
      <div class="skills-grid">
        <div class="skill-card glass glow fade-in">
          <p class="skill-cat">Product & Strategy</p>
          <ul class="skill-list">
            <li><span>•</span> Product Lifecycle Management</li>
            <li><span>•</span> PRD Definition</li>
            <li><span>•</span> User-Centric Design</li>
            <li><span>•</span> Product Roadmapping</li>
          </ul>
        </div>
        <div class="skill-card glass glow fade-in delay-1">
          <p class="skill-cat">Leadership & Execution</p>
          <ul class="skill-list">
            <li><span>•</span> Cross-functional Team Leadership</li>
            <li><span>•</span> Project Planning & Agile</li>
            <li><span>•</span> Stakeholder Management</li>
            <li><span>•</span> Risk Analysis (DFMEA)</li>
          </ul>
        </div>
        <div class="skill-card glass glow fade-in delay-2">
          <p class="skill-cat">Engineering & Design</p>
          <ul class="skill-list">
            <li><span>•</span> Electromechanical Systems</li>
            <li><span>•</span> DFM / DFA / GD&T</li>
            <li><span>•</span> Rapid Prototyping</li>
            <li><span>•</span> Manufacturing Scale-up</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section>
    <div class="container">
      <div class="cta-card glass glow fade-in">
        <h2 class="cta-title">Let's Build Something Great Together</h2>
        <p class="cta-sub">
          Whether you're looking to develop a new product, scale your team, or solve a complex engineering challenge, I'd love to connect.
        </p>
        <div class="cta-btns">
          <a href="mailto:naredlatharun@gmail.com" class="btn-primary">Get In Touch</a>
          <a href="#" class="btn-outline">View Resume</a>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-inner">
      <p class="footer-copy">© 2026 Tharun Naredla. All rights reserved.</p>
      <div class="footer-links">
        <a href="https://linkedin.com/in/tharun-naredla" target="_blank">LinkedIn</a>
        <a href="mailto:naredlatharun@gmail.com">Email</a>
        <a href="#">GitHub</a>
      </div>
    </div>
  </footer>

  <script>
    // Sticky nav
    window.addEventListener('scroll', () => {
      document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 50);
    });

    // Scroll animations
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
    }, { threshold: 0.15 });

    document.querySelectorAll('.fade-in, .fade-in-left, .fade-in-right').forEach(el => observer.observe(el));

    // Trigger hero stats on load
    window.addEventListener('load', () => {
      document.querySelectorAll('.hero .fade-in').forEach(el => {
        setTimeout(() => el.classList.add('visible'), 300);
      });
    });
  </script>
</body>
</html>
