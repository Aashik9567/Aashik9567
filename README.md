<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aashiq Kumar Mahato — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #04060f;
    --surface: #0a0e1a;
    --surface2: #0f1525;
    --border: rgba(14,165,233,0.15);
    --sky: #0ea5e9;
    --cyan: #22d3ee;
    --violet: #8b5cf6;
    --emerald: #10b981;
    --amber: #f59e0b;
    --rose: #f43f5e;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow: 0 0 40px rgba(14,165,233,0.2);
  }
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Space Grotesk',sans-serif;
    overflow-x:hidden;
    min-height:100vh;
  }

  /* === ANIMATED BG === */
  .bg-grid{
    position:fixed;inset:0;
    background-image:
      linear-gradient(rgba(14,165,233,0.04) 1px,transparent 1px),
      linear-gradient(90deg,rgba(14,165,233,0.04) 1px,transparent 1px);
    background-size:60px 60px;
    pointer-events:none;z-index:0;
  }
  .bg-orb{
    position:fixed;border-radius:50%;filter:blur(120px);pointer-events:none;z-index:0;
    animation:orbFloat 8s ease-in-out infinite;
  }
  .orb1{width:500px;height:500px;background:rgba(14,165,233,0.07);top:-200px;right:-100px;}
  .orb2{width:400px;height:400px;background:rgba(139,92,246,0.07);bottom:-100px;left:-100px;animation-delay:-4s;}
  .orb3{width:300px;height:300px;background:rgba(16,185,129,0.05);top:50%;left:50%;animation-delay:-2s;}
  @keyframes orbFloat{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-30px) scale(1.05)}}

  /* === LAYOUT === */
  .container{max-width:900px;margin:0 auto;padding:0 24px;position:relative;z-index:1;}
  section{padding:80px 0;}

  /* === HERO === */
  .hero{
    min-height:100vh;display:flex;align-items:center;justify-content:center;
    text-align:center;padding:40px 0;
  }
  .hero-inner{max-width:700px;}
  .hero-badge{
    display:inline-flex;align-items:center;gap:8px;
    background:rgba(14,165,233,0.1);border:1px solid rgba(14,165,233,0.3);
    border-radius:50px;padding:6px 18px;font-size:13px;color:var(--sky);
    margin-bottom:32px;
    animation:fadeDown 0.6s ease forwards;
  }
  .hero-badge .dot{width:6px;height:6px;background:var(--emerald);border-radius:50%;animation:pulse 2s infinite;}
  @keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(16,185,129,0.7)}50%{box-shadow:0 0 0 6px rgba(16,185,129,0)}}

  .hero-name{
    font-family:'Syne',sans-serif;
    font-size:clamp(42px,8vw,80px);
    font-weight:800;line-height:1;
    background:linear-gradient(135deg,#fff 0%,var(--sky) 50%,var(--violet) 100%);
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
    margin-bottom:16px;
    animation:fadeDown 0.6s 0.1s ease both;
  }
  .hero-title{
    font-size:18px;color:var(--muted);letter-spacing:2px;text-transform:uppercase;
    font-weight:500;margin-bottom:24px;
    animation:fadeDown 0.6s 0.2s ease both;
  }
  .typing-wrap{
    font-family:'JetBrains Mono',monospace;font-size:18px;color:var(--cyan);
    height:32px;margin-bottom:40px;
    animation:fadeDown 0.6s 0.3s ease both;
  }
  .cursor{animation:blink 1s infinite;}
  @keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

  .hero-btns{
    display:flex;gap:12px;justify-content:center;flex-wrap:wrap;
    animation:fadeDown 0.6s 0.4s ease both;
  }
  .btn{
    display:inline-flex;align-items:center;gap:8px;padding:12px 24px;
    border-radius:10px;font-size:14px;font-weight:600;text-decoration:none;
    transition:all 0.3s;cursor:pointer;border:none;font-family:inherit;
  }
  .btn-primary{
    background:linear-gradient(135deg,var(--sky),var(--violet));
    color:#fff;box-shadow:0 0 30px rgba(14,165,233,0.3);
  }
  .btn-primary:hover{transform:translateY(-2px);box-shadow:0 0 50px rgba(14,165,233,0.5);}
  .btn-outline{
    background:transparent;border:1px solid var(--border);color:var(--text);
  }
  .btn-outline:hover{border-color:var(--sky);color:var(--sky);transform:translateY(-2px);}

  /* === SECTION TITLES === */
  .sec-label{
    font-size:12px;letter-spacing:3px;text-transform:uppercase;
    color:var(--sky);font-weight:600;margin-bottom:12px;
  }
  .sec-title{
    font-family:'Syne',sans-serif;font-size:clamp(28px,5vw,42px);font-weight:800;
    color:#fff;margin-bottom:48px;
  }
  .sec-title span{
    background:linear-gradient(135deg,var(--sky),var(--violet));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  }

  /* === CARDS === */
  .card{
    background:var(--surface);border:1px solid var(--border);
    border-radius:16px;padding:28px;
    transition:all 0.3s;position:relative;overflow:hidden;
  }
  .card::before{
    content:'';position:absolute;inset:0;
    background:linear-gradient(135deg,rgba(14,165,233,0.05),transparent);
    opacity:0;transition:opacity 0.3s;pointer-events:none;
  }
  .card:hover{border-color:rgba(14,165,233,0.4);transform:translateY(-4px);box-shadow:var(--glow);}
  .card:hover::before{opacity:1;}

  /* === ABOUT === */
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;}
  @media(max-width:640px){.about-grid{grid-template-columns:1fr;}}
  .about-stat{text-align:center;padding:20px;}
  .about-stat .num{
    font-family:'Syne',sans-serif;font-size:40px;font-weight:800;
    background:linear-gradient(135deg,var(--sky),var(--cyan));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  }
  .about-stat .label{font-size:13px;color:var(--muted);margin-top:4px;}

  /* === SKILLS === */
  .skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(100px,1fr));gap:16px;}
  .skill-chip{
    background:var(--surface);border:1px solid var(--border);border-radius:12px;
    padding:16px 12px;text-align:center;transition:all 0.3s;cursor:default;
  }
  .skill-chip:hover{
    border-color:var(--sky);background:rgba(14,165,233,0.08);
    transform:translateY(-4px) scale(1.05);box-shadow:0 8px 24px rgba(14,165,233,0.2);
  }
  .skill-chip .icon{font-size:28px;margin-bottom:8px;}
  .skill-chip .name{font-size:12px;font-weight:600;color:var(--muted);}
  .skill-chip:hover .name{color:var(--sky);}

  /* === PROJECTS === */
  .projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:24px;}
  .project-card{cursor:pointer;}
  .project-tag{
    display:inline-block;padding:3px 10px;border-radius:50px;
    font-size:11px;font-weight:600;letter-spacing:1px;margin-bottom:12px;
  }
  .tag-blue{background:rgba(14,165,233,0.15);color:var(--sky);}
  .tag-purple{background:rgba(139,92,246,0.15);color:var(--violet);}
  .tag-green{background:rgba(16,185,129,0.15);color:var(--emerald);}
  .project-title{font-family:'Syne',sans-serif;font-size:20px;font-weight:700;margin-bottom:8px;color:#fff;}
  .project-desc{font-size:14px;color:var(--muted);line-height:1.6;margin-bottom:16px;}
  .project-techs{display:flex;flex-wrap:wrap;gap:8px;}
  .tech-badge{
    font-size:11px;font-family:'JetBrains Mono',monospace;
    padding:3px 10px;border-radius:6px;
    background:var(--surface2);border:1px solid var(--border);color:var(--muted);
  }
  .project-link{
    display:inline-flex;align-items:center;gap:6px;margin-top:16px;
    font-size:13px;color:var(--sky);text-decoration:none;font-weight:600;
    transition:gap 0.2s;
  }
  .project-link:hover{gap:10px;}

  /* === STATS BAR === */
  .stat-row{display:flex;align-items:center;gap:16px;margin-bottom:16px;}
  .stat-lang{font-family:'JetBrains Mono',monospace;font-size:13px;color:var(--text);width:90px;flex-shrink:0;}
  .stat-bar-wrap{flex:1;height:8px;background:var(--surface2);border-radius:50px;overflow:hidden;}
  .stat-bar{height:100%;border-radius:50px;transition:width 1.5s cubic-bezier(0.4,0,0.2,1);}
  .stat-pct{font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--muted);width:40px;text-align:right;}

  /* === TIMELINE === */
  .timeline{position:relative;padding-left:32px;}
  .timeline::before{
    content:'';position:absolute;left:0;top:0;bottom:0;
    width:2px;background:linear-gradient(to bottom,var(--sky),var(--violet),transparent);
    border-radius:2px;
  }
  .tl-item{position:relative;margin-bottom:32px;}
  .tl-dot{
    position:absolute;left:-39px;top:4px;
    width:14px;height:14px;border-radius:50%;
    background:linear-gradient(135deg,var(--sky),var(--violet));
    box-shadow:0 0 12px rgba(14,165,233,0.5);
  }
  .tl-year{font-size:12px;color:var(--sky);font-weight:600;letter-spacing:1px;margin-bottom:4px;}
  .tl-title{font-weight:700;color:#fff;margin-bottom:4px;}
  .tl-sub{font-size:14px;color:var(--muted);}

  /* === SOCIAL === */
  .social-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:16px;}
  .social-card{
    display:flex;align-items:center;gap:14px;
    background:var(--surface);border:1px solid var(--border);
    border-radius:12px;padding:16px 20px;text-decoration:none;
    transition:all 0.3s;
  }
  .social-card:hover{transform:translateY(-4px);border-color:var(--sky);box-shadow:var(--glow);}
  .social-icon{font-size:24px;}
  .social-info .s-name{font-weight:700;color:#fff;font-size:14px;}
  .social-info .s-handle{font-size:12px;color:var(--muted);}

  /* === GAME === */
  .game-wrap{
    background:var(--surface);border:1px solid var(--border);border-radius:20px;
    padding:32px;text-align:center;max-width:500px;margin:0 auto;
  }
  .game-title{font-family:'Syne',sans-serif;font-size:24px;font-weight:800;color:#fff;margin-bottom:8px;}
  .game-sub{font-size:14px;color:var(--muted);margin-bottom:24px;}
  #gameCanvas{
    border:2px solid var(--border);border-radius:12px;
    background:#060810;display:block;margin:0 auto;
    max-width:100%;cursor:none;
  }
  .game-score-row{
    display:flex;gap:24px;justify-content:center;margin-bottom:16px;
  }
  .game-stat{text-align:center;}
  .game-stat .gs-val{font-family:'JetBrains Mono',monospace;font-size:28px;font-weight:700;color:var(--sky);}
  .game-stat .gs-label{font-size:12px;color:var(--muted);}
  #gameMsg{
    font-size:14px;color:var(--muted);min-height:22px;margin:12px 0;
  }
  .game-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:16px;}

  /* === ANIMATIONS === */
  @keyframes fadeDown{from{opacity:0;transform:translateY(-20px)}to{opacity:1;transform:translateY(0)}}
  @keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}
  @keyframes shimmer{
    0%{background-position:-200% 0}
    100%{background-position:200% 0}
  }
  .reveal{opacity:0;transform:translateY(30px);transition:opacity 0.7s ease,transform 0.7s ease;}
  .reveal.visible{opacity:1;transform:translateY(0);}

  /* === NAV === */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    padding:16px 24px;display:flex;align-items:center;justify-content:space-between;
    background:rgba(4,6,15,0.85);backdrop-filter:blur(20px);
    border-bottom:1px solid rgba(14,165,233,0.08);
    transition:all 0.3s;
  }
  .nav-logo{
    font-family:'Syne',sans-serif;font-size:20px;font-weight:800;
    background:linear-gradient(135deg,var(--sky),var(--violet));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  }
  .nav-links{display:flex;gap:28px;list-style:none;}
  .nav-links a{font-size:13px;color:var(--muted);text-decoration:none;font-weight:600;letter-spacing:0.5px;transition:color 0.2s;}
  .nav-links a:hover{color:var(--sky);}
  @media(max-width:600px){.nav-links{display:none;}}

  /* === FOOTER === */
  footer{
    text-align:center;padding:48px 24px;border-top:1px solid var(--border);
    font-size:13px;color:var(--muted);
  }
  footer span{color:var(--rose);}

  /* === QUOTE === */
  .quote-card{
    background:var(--surface);border:1px solid var(--border);border-radius:16px;
    padding:32px;text-align:center;position:relative;overflow:hidden;
  }
  .quote-card::before{
    content:'"';
    position:absolute;top:-20px;left:20px;
    font-size:160px;font-family:'Syne',sans-serif;font-weight:800;
    color:rgba(14,165,233,0.06);line-height:1;pointer-events:none;
  }
  .quote-text{font-size:18px;color:#fff;font-style:italic;line-height:1.7;margin-bottom:12px;}
  .quote-author{font-size:13px;color:var(--sky);font-weight:600;}

  /* bar colors */
  .bar-react{background:linear-gradient(90deg,#61dafb,#0ea5e9);}
  .bar-next{background:linear-gradient(90deg,#fff,#94a3b8);}
  .bar-js{background:linear-gradient(90deg,#f7df1e,#f59e0b);}
  .bar-ts{background:linear-gradient(90deg,#3178c6,#6366f1);}
  .bar-py{background:linear-gradient(90deg,#3776ab,#22d3ee);}
  .bar-other{background:linear-gradient(90deg,var(--emerald),#06b6d4);}
</style>
</head>
<body>

<div class="bg-grid"></div>
<div class="bg-orb orb1"></div>
<div class="bg-orb orb2"></div>
<div class="bg-orb orb3"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">AKM</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#game">Game</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="container">
    <div class="hero-inner">
      <div class="hero-badge">
        <span class="dot"></span>
        Available for opportunities
      </div>
      <h1 class="hero-name">Aashiq Kumar<br/>Mahato</h1>
      <p class="hero-title">Full-Stack Developer · Electronics Engineer</p>
      <div class="typing-wrap">
        <span id="typingText"></span><span class="cursor">|</span>
      </div>
      <div class="hero-btns">
        <a href="#projects" class="btn btn-primary">⚡ View Projects</a>
        <a href="mailto:aashikmahato9567@gmail.com" class="btn btn-outline">✉ Get In Touch</a>
        <a href="#game" class="btn btn-outline">🎮 Play Game</a>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container reveal">
    <p class="sec-label">Who I Am</p>
    <h2 class="sec-title">About <span>Me</span></h2>
    <div class="about-grid">
      <div class="card" style="grid-column:1/-1">
        <p style="font-size:16px;line-height:1.8;color:#94a3b8;">
          Dynamic and results-driven <strong style="color:#fff">Full-Stack Developer</strong> with expertise in cutting-edge web technologies. My background in
          <strong style="color:var(--sky)">Electronics & Communication Engineering</strong> gives me a unique perspective on hardware-software integrations —
          I don't just build apps, I build <em style="color:var(--cyan)">experiences</em>.
          Based in <strong style="color:#fff">Kathmandu, Nepal</strong>, I'm passionate about crafting clean, performant digital products that solve real problems.
        </p>
      </div>
      <div class="card about-stat">
        <div class="num" data-target="3">0</div>
        <div class="label">Years Coding</div>
      </div>
      <div class="card about-stat">
        <div class="num" data-target="10">0</div>
        <div class="label">Projects Built</div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container reveal">
    <p class="sec-label">What I Work With</p>
    <h2 class="sec-title">Tech <span>Stack</span></h2>
    <div class="skills-grid">
      <div class="skill-chip"><div class="icon">⚛️</div><div class="name">React</div></div>
      <div class="skill-chip"><div class="icon">▲</div><div class="name">Next.js</div></div>
      <div class="skill-chip"><div class="icon">🟨</div><div class="name">JavaScript</div></div>
      <div class="skill-chip"><div class="icon">🔷</div><div class="name">TypeScript</div></div>
      <div class="skill-chip"><div class="icon">🟢</div><div class="name">Node.js</div></div>
      <div class="skill-chip"><div class="icon">🐍</div><div class="name">Python</div></div>
      <div class="skill-chip"><div class="icon">🍃</div><div class="name">MongoDB</div></div>
      <div class="skill-chip"><div class="icon">💨</div><div class="name">Tailwind</div></div>
      <div class="skill-chip"><div class="icon">📡</div><div class="name">Express</div></div>
      <div class="skill-chip"><div class="icon">🎨</div><div class="name">Figma</div></div>
      <div class="skill-chip"><div class="icon">🔧</div><div class="name">Git</div></div>
      <div class="skill-chip"><div class="icon">🤖</div><div class="name">Arduino</div></div>
    </div>

    <div style="margin-top:48px">
      <h3 style="font-family:'Syne',sans-serif;font-size:20px;font-weight:700;color:#fff;margin-bottom:24px;">📊 Weekly Coding Activity</h3>
      <div id="statsContainer">
        <div class="stat-row">
          <span class="stat-lang">React.js</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-react" style="width:0%" data-w="42.3"></div></div>
          <span class="stat-pct">42.3%</span>
        </div>
        <div class="stat-row">
          <span class="stat-lang">Next.js</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-next" style="width:0%" data-w="27.1"></div></div>
          <span class="stat-pct">27.1%</span>
        </div>
        <div class="stat-row">
          <span class="stat-lang">JavaScript</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-js" style="width:0%" data-w="13.5"></div></div>
          <span class="stat-pct">13.5%</span>
        </div>
        <div class="stat-row">
          <span class="stat-lang">TypeScript</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-ts" style="width:0%" data-w="8.7"></div></div>
          <span class="stat-pct">8.7%</span>
        </div>
        <div class="stat-row">
          <span class="stat-lang">Python</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-py" style="width:0%" data-w="5.7"></div></div>
          <span class="stat-pct">5.7%</span>
        </div>
        <div class="stat-row">
          <span class="stat-lang">Other</span>
          <div class="stat-bar-wrap"><div class="stat-bar bar-other" style="width:0%" data-w="2.7"></div></div>
          <span class="stat-pct">2.7%</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container reveal">
    <p class="sec-label">What I've Built</p>
    <h2 class="sec-title">Featured <span>Projects</span></h2>
    <div class="projects-grid">
      <div class="card project-card" onclick="window.open('https://github.com/Aashik9567/Automated_Attendance_Management_System','_blank')">
        <span class="project-tag tag-blue">AI / ML</span>
        <h3 class="project-title">🎯 Automated Attendance System</h3>
        <p class="project-desc">Facial recognition-based attendance with real-time tracking, email notifications, and YOLOv8 + FaceNet integration.</p>
        <div class="project-techs">
          <span class="tech-badge">React</span>
          <span class="tech-badge">Node.js</span>
          <span class="tech-badge">MongoDB</span>
          <span class="tech-badge">YOLOv8</span>
          <span class="tech-badge">FaceNet</span>
        </div>
        <a class="project-link" href="https://github.com/Aashik9567/Automated_Attendance_Management_System" target="_blank">View on GitHub →</a>
      </div>
      <div class="card project-card" onclick="window.open('https://github.com/Aashik9567/weather-app-NextJs','_blank')">
        <span class="project-tag tag-purple">Web App</span>
        <h3 class="project-title">🌦️ AI Weather Dashboard</h3>
        <p class="project-desc">Smart weather app with AI-powered analysis, GPS support, 10-day forecasts, and glassmorphism dark UI.</p>
        <div class="project-techs">
          <span class="tech-badge">Next.js</span>
          <span class="tech-badge">OpenAI</span>
          <span class="tech-badge">Tailwind</span>
          <span class="tech-badge">REST API</span>
        </div>
        <a class="project-link" href="https://github.com/Aashik9567/weather-app-NextJs" target="_blank">View on GitHub →</a>
      </div>
      <div class="card project-card" onclick="window.open('https://github.com/Aashik9567/Portfolio-website','_blank')">
        <span class="project-tag tag-green">Portfolio</span>
        <h3 class="project-title">🖥️ Personal Portfolio</h3>
        <p class="project-desc">Responsive, performance-optimized portfolio showcasing my work with interactive UI and smooth animations.</p>
        <div class="project-techs">
          <span class="tech-badge">React</span>
          <span class="tech-badge">CSS3</span>
          <span class="tech-badge">Framer</span>
        </div>
        <a class="project-link" href="https://github.com/Aashik9567/Portfolio-website" target="_blank">View on GitHub →</a>
      </div>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="container reveal">
    <p class="sec-label">My Journey</p>
    <h2 class="sec-title"><span>Education</span></h2>
    <div class="timeline">
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-year">2021 — 2025</div>
        <div class="tl-title">B.E. Electronics, Communication & Information Engineering</div>
        <div class="tl-sub">Advanced College of Engineering and Management, Kathmandu</div>
      </div>
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-year">2018 — 2019</div>
        <div class="tl-title">High School Diploma</div>
        <div class="tl-sub">Prasadi Academy, Kathmandu</div>
      </div>
      <div class="tl-item">
        <div class="tl-dot"></div>
        <div class="tl-year">2012 — 2017</div>
        <div class="tl-title">School Leaving Certificate</div>
        <div class="tl-sub">Swastik Pathshala, Mirchaiya</div>
      </div>
    </div>
  </div>
</section>

<!-- GAME -->
<section id="game">
  <div class="container reveal">
    <p class="sec-label">Take a Break</p>
    <h2 class="sec-title">Mini <span>Game</span></h2>
    <div class="game-wrap">
      <div class="game-title">⚡ Code Catcher</div>
      <div class="game-sub">Catch falling code symbols with your cursor! Move mouse or tap to dodge bugs 🐛</div>
      <div class="game-score-row">
        <div class="game-stat"><div class="gs-val" id="scoreVal">0</div><div class="gs-label">SCORE</div></div>
        <div class="game-stat"><div class="gs-val" id="livesVal">3</div><div class="gs-label">LIVES</div></div>
        <div class="game-stat"><div class="gs-val" id="levelVal">1</div><div class="gs-label">LEVEL</div></div>
      </div>
      <canvas id="gameCanvas" width="440" height="320"></canvas>
      <div id="gameMsg">Click START to play!</div>
      <div class="game-btns">
        <button class="btn btn-primary" id="startBtn" onclick="startGame()">▶ START</button>
        <button class="btn btn-outline" id="resetBtn" onclick="resetGame()" style="display:none">↺ Restart</button>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container reveal">
    <p class="sec-label">Let's Connect</p>
    <h2 class="sec-title">Get In <span>Touch</span></h2>
    <div class="social-grid">
      <a href="https://www.linkedin.com/in/aashiq-mahato-9a343b2b4/" target="_blank" class="social-card">
        <span class="social-icon">💼</span>
        <div class="social-info"><div class="s-name">LinkedIn</div><div class="s-handle">aashiq-mahato</div></div>
      </a>
      <a href="https://github.com/Aashik9567" target="_blank" class="social-card">
        <span class="social-icon">🐙</span>
        <div class="social-info"><div class="s-name">GitHub</div><div class="s-handle">Aashik9567</div></div>
      </a>
      <a href="https://aashiqmahato.com" target="_blank" class="social-card">
        <span class="social-icon">🌐</span>
        <div class="social-info"><div class="s-name">Portfolio</div><div class="s-handle">aashiqmahato.com</div></div>
      </a>
      <a href="mailto:aashikmahato9567@gmail.com" class="social-card">
        <span class="social-icon">✉️</span>
        <div class="social-info"><div class="s-name">Email</div><div class="s-handle">aashikmahato9567</div></div>
      </a>
    </div>
    <div style="margin-top:40px">
      <div class="quote-card">
        <p class="quote-text">"The only way to do great work is to love what you do."</p>
        <p class="quote-author">— Steve Jobs</p>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="container">
    Built with <span>❤</span> by Aashiq Kumar Mahato · Kathmandu, Nepal<br/>
    <span style="font-size:11px;margin-top:8px;display:block;">© 2025 All Rights Reserved</span>
  </div>
</footer>

<script>
// ======== TYPING EFFECT ========
const phrases = [
  "Building React experiences ⚛️",
  "Next.js full-stack dev 🚀",
  "Electronics × Software 🔌",
  "Open to opportunities ✨",
  "Based in Kathmandu 🇳🇵"
];
let pi=0,ci=0,deleting=false;
function type(){
  const el=document.getElementById('typingText');
  const phrase=phrases[pi];
  if(!deleting){
    el.textContent=phrase.slice(0,ci+1);ci++;
    if(ci===phrase.length){deleting=true;setTimeout(type,1800);return;}
  } else {
    el.textContent=phrase.slice(0,ci-1);ci--;
    if(ci===0){deleting=false;pi=(pi+1)%phrases.length;}
  }
  setTimeout(type,deleting?50:80);
}
type();

// ======== SCROLL REVEAL ========
const observer=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('visible');
      // animate bars
      e.target.querySelectorAll('.stat-bar').forEach(b=>{
        setTimeout(()=>{b.style.width=b.dataset.w+'%';},200);
      });
      // animate counters
      e.target.querySelectorAll('.num[data-target]').forEach(n=>{
        const target=+n.dataset.target,dur=1500,step=dur/target;
        let count=0;
        const t=setInterval(()=>{count++;n.textContent=count;if(count>=target)clearInterval(t);},step);
      });
    }
  });
},{threshold:0.15});
document.querySelectorAll('.reveal').forEach(el=>observer.observe(el));

// ======== MINI GAME ========
const canvas=document.getElementById('gameCanvas');
const ctx=canvas.getContext('2d');
const W=canvas.width,H=canvas.height;

// scale for mobile
function resizeCanvas(){
  const maxW=Math.min(440,window.innerWidth-64);
  canvas.style.width=maxW+'px';
  canvas.style.height=(maxW*320/440)+'px';
}
resizeCanvas();
window.addEventListener('resize',resizeCanvas);

let gameRunning=false,gameOver=false;
let score=0,lives=3,level=1,frame=0;
let playerX=W/2;
const PY=H-40,PW=50,PH=12;
const symbols=['⚛','{}','</>','//','fn()','[];','===','&&','npm','git'];
const bugSymbols=['🐛','💀','⚠️'];
let items=[],particles=[];
let lastLevel=0;
let animId;

function resetGame(){
  score=0;lives=3;level=1;frame=0;items=[];particles=[];playerX=W/2;gameRunning=false;gameOver=false;lastLevel=0;
  updateUI();
  document.getElementById('gameMsg').textContent='Click START to play!';
  document.getElementById('startBtn').style.display='inline-flex';
  document.getElementById('resetBtn').style.display='none';
  drawIdle();
}

function startGame(){
  if(gameRunning)return;
  gameRunning=true;gameOver=false;
  document.getElementById('startBtn').style.display='none';
  document.getElementById('resetBtn').style.display='inline-flex';
  document.getElementById('gameMsg').textContent='Move mouse over canvas!';
  if(animId)cancelAnimationFrame(animId);
  loop();
}

function updateUI(){
  document.getElementById('scoreVal').textContent=score;
  document.getElementById('livesVal').textContent=lives;
  document.getElementById('levelVal').textContent=level;
}

canvas.addEventListener('mousemove',e=>{
  const rect=canvas.getBoundingClientRect();
  const scaleX=W/rect.width;
  playerX=(e.clientX-rect.left)*scaleX;
});
canvas.addEventListener('touchmove',e=>{
  e.preventDefault();
  const rect=canvas.getBoundingClientRect();
  const scaleX=W/rect.width;
  playerX=(e.touches[0].clientX-rect.left)*scaleX;
},{passive:false});

function spawnItem(){
  const isBug=Math.random()<0.22+level*0.02;
  items.push({
    x:Math.random()*(W-30)+15,
    y:-20,
    speed:(1.5+Math.random()*1.5+level*0.3),
    label:isBug?bugSymbols[Math.floor(Math.random()*bugSymbols.length)]:symbols[Math.floor(Math.random()*symbols.length)],
    isBug,
    size:isBug?22:16,
    color:isBug?'#f43f5e':'#0ea5e9',
    glow:isBug?'rgba(244,63,94,0.6)':'rgba(14,165,233,0.6)',
    wobble:Math.random()*Math.PI*2,
  });
}

function spawnParticle(x,y,color){
  for(let i=0;i<8;i++){
    const angle=Math.random()*Math.PI*2;
    const speed=1+Math.random()*3;
    particles.push({x,y,vx:Math.cos(angle)*speed,vy:Math.sin(angle)*speed,life:1,color});
  }
}

function loop(){
  if(!gameRunning){return;}
  animId=requestAnimationFrame(loop);
  frame++;

  // spawn
  const spawnRate=Math.max(25,60-level*5);
  if(frame%spawnRate===0)spawnItem();

  // level up
  if(score>0&&score%50===0&&score!==lastLevel){lastLevel=score;level++;updateUI();}

  ctx.clearRect(0,0,W,H);

  // bg
  ctx.fillStyle='#060810';ctx.fillRect(0,0,W,H);
  // grid
  ctx.strokeStyle='rgba(14,165,233,0.04)';ctx.lineWidth=1;
  for(let x=0;x<W;x+=40){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke();}
  for(let y=0;y<H;y+=40){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke();}

  // player
  const px=Math.max(PW/2,Math.min(W-PW/2,playerX));
  const grad=ctx.createLinearGradient(px-PW/2,0,px+PW/2,0);
  grad.addColorStop(0,'#8b5cf6');grad.addColorStop(1,'#0ea5e9');
  ctx.shadowBlur=20;ctx.shadowColor='rgba(14,165,233,0.8)';
  ctx.fillStyle=grad;
  ctx.beginPath();ctx.roundRect(px-PW/2,PY,PW,PH,6);ctx.fill();
  ctx.shadowBlur=0;

  // items
  for(let i=items.length-1;i>=0;i--){
    const item=items[i];
    item.y+=item.speed;
    item.wobble+=0.05;
    const drawX=item.x+(item.isBug?Math.sin(item.wobble)*4:0);

    // check catch
    if(item.y+item.size>PY&&item.y<PY+PH&&drawX>px-PW/2-10&&drawX<px+PW/2+10){
      spawnParticle(drawX,PY,item.color);
      if(!item.isBug){
        score+=10+level*2;
        document.getElementById('gameMsg').textContent='+' + (10+level*2) + ' pts! 🎉';
      } else {
        lives--;
        document.getElementById('gameMsg').textContent='Got hit by a bug! 🐛';
        if(lives<=0){endGame();return;}
      }
      items.splice(i,1);
      updateUI();
      continue;
    }
    // miss good item
    if(item.y>H){
      if(!item.isBug){
        // no penalty for miss, just remove
      }
      items.splice(i,1);
      continue;
    }

    // draw item
    ctx.shadowBlur=12;ctx.shadowColor=item.glow;
    ctx.font=`${item.size}px 'JetBrains Mono',monospace`;
    ctx.fillStyle=item.color;
    ctx.textAlign='center';
    ctx.fillText(item.label,drawX,item.y);
    ctx.shadowBlur=0;
  }

  // particles
  for(let i=particles.length-1;i>=0;i--){
    const p=particles[i];
    p.x+=p.vx;p.y+=p.vy;p.vy+=0.1;p.life-=0.05;
    if(p.life<=0){particles.splice(i,1);continue;}
    ctx.globalAlpha=p.life;
    ctx.fillStyle=p.color;
    ctx.beginPath();ctx.arc(p.x,p.y,3,0,Math.PI*2);ctx.fill();
    ctx.globalAlpha=1;
  }

  // HUD
  ctx.font="bold 14px 'Space Grotesk',sans-serif";
  ctx.fillStyle='rgba(14,165,233,0.6)';
  ctx.textAlign='left';
  ctx.fillText(`LVL ${level}`,10,20);
  // lives as hearts
  ctx.font='16px sans-serif';
  ctx.textAlign='right';
  for(let l=0;l<lives;l++) ctx.fillText('❤',W-10-l*22,22);
}

function endGame(){
  gameRunning=false;gameOver=true;
  cancelAnimationFrame(animId);
  ctx.fillStyle='rgba(6,8,16,0.85)';ctx.fillRect(0,0,W,H);
  ctx.textAlign='center';
  ctx.font="bold 36px 'Syne',sans-serif";
  ctx.fillStyle='#f43f5e';
  ctx.fillText('GAME OVER',W/2,H/2-40);
  ctx.font="bold 20px 'Space Grotesk',sans-serif";
  ctx.fillStyle='#e2e8f0';
  ctx.fillText(`Score: ${score}  |  Level: ${level}`,W/2,H/2);
  ctx.font="14px 'Space Grotesk',sans-serif";
  ctx.fillStyle='#64748b';
  ctx.fillText('Click Restart to play again',W/2,H/2+35);
  document.getElementById('gameMsg').textContent=score>100?'Amazing run! 🏆':'Keep practicing! 💪';
  document.getElementById('startBtn').style.display='none';
  updateUI();
}

function drawIdle(){
  ctx.fillStyle='#060810';ctx.fillRect(0,0,W,H);
  ctx.strokeStyle='rgba(14,165,233,0.04)';ctx.lineWidth=1;
  for(let x=0;x<W;x+=40){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke();}
  for(let y=0;y<H;y+=40){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke();}
  ctx.textAlign='center';
  ctx.font="bold 18px 'Space Grotesk',sans-serif";
  ctx.fillStyle='rgba(14,165,233,0.5)';
  ctx.fillText('⚡ Code Catcher',W/2,H/2-15);
  ctx.font="14px 'Space Grotesk',sans-serif";
  ctx.fillStyle='rgba(100,116,139,0.8)';
  ctx.fillText('Catch ⚛ {} </> — Dodge 🐛 💀',W/2,H/2+20);
}
drawIdle();
</script>
</body>
</html>
