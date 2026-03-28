

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;600;700&family=Space+Mono:wght@400;700&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{--void:#07080f;--panel:#161929;--dim:#1e2540;--a1:#a78bfa;--a2:#38bdf8;--a3:#f0abfc;--gold:#fbbf24;--green:#4ade80;--text:#e2e8f0;--muted:#64748b}
body{background:var(--void);font-family:'Space Grotesk',sans-serif;color:var(--text)}
canvas#stars{position:absolute;inset:0;width:100%;height:100%;pointer-events:none}
.hero{position:relative;min-height:260px;overflow:hidden;background:var(--void);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:3rem 1rem 2.5rem}
.ring{position:absolute;border-radius:50%;border:1px solid;pointer-events:none;top:50%;left:50%;transform:translate(-50%,-50%)}
.hero-name{font-family:'Space Mono',monospace;font-size:clamp(1.8rem,5vw,2.8rem);font-weight:700;letter-spacing:6px;background:linear-gradient(90deg,var(--a1),var(--a2),var(--a3));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;position:relative;z-index:2}
.hero-sub{font-family:'Space Mono',monospace;font-size:.72rem;letter-spacing:4px;color:var(--a2);margin-top:.5rem;position:relative;z-index:2}
.typing-row{display:flex;align-items:center;gap:6px;margin-top:1.2rem;position:relative;z-index:2;min-height:22px}
.typer{font-family:'Space Mono',monospace;font-size:.82rem;color:var(--a1)}
.cur{display:inline-block;width:2px;height:15px;background:var(--a1);animation:bl .7s infinite;vertical-align:middle}
@keyframes bl{0%,100%{opacity:1}50%{opacity:0}}
.main{max-width:780px;margin:0 auto;padding:0 1rem 2rem}
.sec{font-family:'Space Mono',monospace;font-size:.62rem;letter-spacing:3px;color:var(--a2);margin:2.2rem 0 1rem;display:flex;align-items:center;gap:10px}
.sec::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,#38bdf822,transparent)}
.gbadge{display:inline-block;border:1px solid;border-radius:20px;padding:2px 10px;font-size:.6rem;font-family:'Space Mono',monospace;letter-spacing:1px;margin-left:6px}
.bp{border-color:var(--a1);color:var(--a1);background:#a78bfa11}
.bb{border-color:var(--a2);color:var(--a2);background:#38bdf811}
.bg{border-color:var(--gold);color:var(--gold);background:#fbbf2411}
.bgg{border-color:var(--green);color:var(--green);background:#4ade8011}

/* HOLOGRAPHIC ID CARD */
.holo-card{position:relative;border-radius:16px;overflow:hidden;padding:1.5rem;background:var(--panel);border:1px solid #38bdf833}
.holo-scanline{position:absolute;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,#38bdf8aa,transparent);animation:scan 3s ease-in-out infinite;top:0;pointer-events:none}
@keyframes scan{0%{top:0;opacity:0}10%{opacity:1}90%{opacity:1}100%{top:100%;opacity:0}}
.holo-corner{position:absolute;width:16px;height:16px;border-color:#38bdf8;border-style:solid;opacity:.7}
.holo-corner.tl{top:8px;left:8px;border-width:2px 0 0 2px}
.holo-corner.tr{top:8px;right:8px;border-width:2px 2px 0 0}
.holo-corner.bl{bottom:8px;left:8px;border-width:0 0 2px 2px}
.holo-corner.br{bottom:8px;right:8px;border-width:0 2px 2px 0}
.holo-grid{display:grid;grid-template-columns:auto 1fr;gap:1.2rem;align-items:start}
.holo-avatar{width:80px;height:80px;border-radius:10px;background:linear-gradient(135deg,#1e2540,#0d0f1e);border:1px solid #38bdf844;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:4px;flex-shrink:0}
.holo-initials{font-family:'Space Mono',monospace;font-size:1.4rem;font-weight:700;background:linear-gradient(135deg,var(--a1),var(--a2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.holo-uid{font-family:'Space Mono',monospace;font-size:.5rem;color:var(--muted);letter-spacing:1px}
.holo-right{display:flex;flex-direction:column;gap:.5rem}
.holo-name-row{display:flex;align-items:baseline;gap:10px;flex-wrap:wrap}
.holo-name{font-family:'Space Mono',monospace;font-size:1.1rem;font-weight:700;color:var(--text)}
.holo-clearance{font-size:.58rem;font-family:'Space Mono',monospace;letter-spacing:2px;padding:2px 8px;border-radius:4px;background:#38bdf811;border:1px solid #38bdf844;color:var(--a2)}
.holo-bio{font-size:.78rem;color:#94a3b8;line-height:1.7}
.holo-bio strong{color:var(--a2)}
.holo-fields{display:flex;flex-wrap:wrap;gap:8px;margin-top:.4rem}
.holo-field{display:flex;flex-direction:column;background:#0d0f1e;border:1px solid var(--dim);border-radius:6px;padding:5px 10px;min-width:80px}
.hf-label{font-size:.52rem;font-family:'Space Mono',monospace;letter-spacing:1.5px;color:var(--muted);text-transform:uppercase}
.hf-val{font-size:.72rem;font-weight:600;color:var(--text);margin-top:2px}
.holo-bar{position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--a1),var(--a2),var(--a3),var(--a1));background-size:200%;animation:shimmer 3s linear infinite}
@keyframes shimmer{0%{background-position:0%}100%{background-position:200%}}

/* TECH ICONS */
.skill-cat{font-size:.62rem;font-family:'Space Mono',monospace;letter-spacing:2px;color:var(--muted);margin-bottom:.6rem;text-transform:uppercase}
.icon-row{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:1.2rem}
.icon-chip{background:var(--panel);border:1px solid var(--dim);border-radius:10px;padding:8px 10px;display:flex;align-items:center;gap:8px;transition:border-color .2s,transform .2s;cursor:default}
.icon-chip:hover{border-color:var(--a1);transform:translateY(-3px)}
.icon-chip img{width:24px;height:24px;object-fit:contain;display:block}
.icon-chip span{font-size:.72rem;font-weight:500;color:var(--text);white-space:nowrap}

/* PROJECTS */
.proj-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px}
.proj-card{background:var(--panel);border:1px solid var(--dim);border-radius:12px;padding:1rem 1.1rem;border-left:2px solid;transition:transform .2s,border-color .25s;cursor:default}
.proj-card:hover{transform:translateY(-4px) scale(1.01)}
.proj-lang{font-size:.68rem;font-weight:700;font-family:'Space Mono',monospace;letter-spacing:1px}
.proj-title{font-size:.85rem;margin:.35rem 0 .25rem;font-weight:600;color:var(--text)}
.proj-desc{font-size:.68rem;color:var(--muted);line-height:1.6}
.proj-tags{display:flex;flex-wrap:wrap;gap:4px;margin-top:.6rem}
.tag{font-size:.58rem;font-family:'Space Mono',monospace;padding:2px 7px;border-radius:4px;background:#1e2540;color:var(--muted)}

/* METRICS */
.stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
.sc{background:var(--panel);border:1px solid var(--dim);border-radius:12px;padding:1.2rem;text-align:center;position:relative;overflow:hidden}
.snum{font-family:'Space Mono',monospace;font-size:1.8rem;font-weight:700}
.slbl{font-size:.62rem;letter-spacing:2px;color:var(--muted);margin-top:4px;text-transform:uppercase}

/* FUN FACTS */
.facts-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:10px}
.fact-card{background:var(--panel);border:1px solid var(--dim);border-radius:10px;padding:1rem;display:flex;align-items:flex-start;gap:10px}
.fact-txt{font-size:.78rem;color:var(--text);line-height:1.5}
.fact-sub{font-size:.65rem;color:var(--muted);margin-top:2px}
.fact-icon{font-size:1.1rem;flex-shrink:0;line-height:1}

/* RADAR */
.radar-wrap{background:var(--panel);border:1px solid var(--dim);border-radius:16px;padding:1.5rem;display:flex;align-items:center;gap:2rem;flex-wrap:wrap}
.radar-svg-wrap{flex-shrink:0;width:130px;height:130px}
@keyframes sweep{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.status-info{flex:1;min-width:180px}
.status-title{font-family:'Space Mono',monospace;font-size:.62rem;letter-spacing:3px;color:var(--a2);margin-bottom:.8rem}
.status-row{display:flex;align-items:center;gap:10px;margin-bottom:.6rem}
.ping-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;position:relative}
.ping-dot.green{background:var(--green);box-shadow:0 0 8px var(--green)}
.ping-dot.gold{background:var(--gold);box-shadow:0 0 8px var(--gold)}
.ping-dot.purple{background:var(--a1);box-shadow:0 0 8px var(--a1)}
.ping-dot::after{content:'';position:absolute;inset:-3px;border-radius:50%;border:1px solid;animation:fadepulse 1.5s infinite}
@keyframes fadepulse{0%,100%{opacity:.7}50%{opacity:0}}
.ping-dot.green::after{border-color:var(--green)}
.ping-dot.gold::after{border-color:var(--gold)}
.ping-dot.purple::after{border-color:var(--a1)}
.status-key{font-size:.7rem;color:var(--muted);font-family:'Space Mono',monospace;min-width:90px}
.status-val{font-size:.78rem;color:var(--text);font-weight:500}

/* PORTAL WEBSITE — wormhole style */
.portal-outer{position:relative;border-radius:16px;overflow:hidden;background:#030508;border:1px solid #a78bfa33;padding:0;min-height:160px;display:flex;align-items:center;justify-content:center}
.portal-canvas-wrap{position:absolute;inset:0}
.portal-content{position:relative;z-index:5;display:flex;flex-direction:column;align-items:center;gap:.6rem;padding:1.5rem}
.portal-label{font-family:'Space Mono',monospace;font-size:.58rem;letter-spacing:4px;color:#a78bfa88;text-transform:uppercase}
.portal-title{font-family:'Space Mono',monospace;font-size:1rem;font-weight:700;color:#fff;letter-spacing:2px;text-align:center}
.portal-url{font-size:.72rem;color:var(--a2);font-family:'Space Mono',monospace;opacity:.8}
.portal-btn{margin-top:.4rem;font-family:'Space Mono',monospace;font-size:.65rem;letter-spacing:2px;color:#030508;background:linear-gradient(90deg,var(--a1),var(--a2));border:none;border-radius:20px;padding:7px 22px;cursor:pointer;font-weight:700;transition:opacity .2s}
.portal-btn:hover{opacity:.85}

.footer{text-align:center;padding:1.5rem 0;font-family:'Space Mono',monospace;font-size:.62rem;color:var(--muted);letter-spacing:2px;border-top:1px solid var(--dim);margin-top:2rem}
</style>

<div style="background:var(--void);min-height:100vh">
<div class="hero" id="hero">
  <canvas id="stars"></canvas>
  <div class="ring" style="width:280px;height:280px;border-color:#a78bfa18"></div>
  <div class="ring" style="width:460px;height:460px;border-color:#38bdf810"></div>
  <div class="ring" style="width:600px;height:600px;border-color:#f0abfc08"></div>
  <div class="hero-name">HUDSON</div>
  <div class="hero-sub">DATA ANALYTICS · SYSTEMS · APU 2024</div>
  <div class="typing-row"><span class="typer" id="typer"></span><span class="cur"></span></div>
</div>

<div class="main">

<!-- HOLOGRAPHIC ID -->
<div class="sec">WHO AM I</div>
<div class="holo-card">
  <div class="holo-scanline"></div>
  <div class="holo-corner tl"></div><div class="holo-corner tr"></div>
  <div class="holo-corner bl"></div><div class="holo-corner br"></div>
  <div class="holo-grid">
    <div class="holo-avatar">
      <div class="holo-initials">CJH</div>
      <div class="holo-uid">UID · HDS-2024</div>
    </div>
    <div class="holo-right">
      <div class="holo-name-row">
        <div class="holo-name">CHIA JIN HAU</div>
        <div class="holo-clearance">CLEARANCE · ANALYST</div>
      </div>
      <div class="holo-bio">CS undergrad specialising in <strong>Data Analytics</strong> at APU. Backed by <strong>6 years</strong> of real-world operations — data decisions that drove a <strong>25% revenue boost</strong>, cut costs <strong>12%</strong>, and lifted satisfaction by <strong>20%</strong>. Red Hat certified. Codes from Assembly to Python.</div>
      <div class="holo-fields">
        <div class="holo-field"><span class="hf-label">Degree</span><span class="hf-val">BSc CS · Analytics</span></div>
        <div class="holo-field"><span class="hf-label">Certified</span><span class="hf-val">Red Hat Admin</span></div>
        <div class="holo-field"><span class="hf-label">Spoken</span><span class="hf-val">EN · BM · ZH · 粤</span></div>
        <div class="holo-field"><span class="hf-label">Status</span><span class="hf-val" style="color:var(--green)">Open to hire</span></div>
      </div>
    </div>
  </div>
  <div class="holo-bar"></div>
</div>

<!-- TECH ARSENAL -->
<div class="sec">TECH ARSENAL <span class="gbadge bp">LANGUAGES</span></div>
<div class="icon-row">
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Python.png" alt="Python"><span>Python</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Java.png" alt="Java"><span>Java</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_C.png" alt="C"><span>C</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_C++.png" alt="C++"><span>C++</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_C%23.png" alt="C#"><span>C#</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_R.png" alt="R"><span>R</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Assembly.png" alt="Assembly"><span>Assembly</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_JavaScript.png" alt="JavaScript"><span>JavaScript</span></div>
</div>
<div class="skill-cat">Web & Markup</div>
<div class="icon-row">
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_HTML5.png" alt="HTML5"><span>HTML5</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_CSS3.png" alt="CSS3"><span>CSS3</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_ASP.NET.png" alt="ASP.NET"><span>ASP.NET</span></div>
</div>
<div class="skill-cat">Databases & Analytics</div>
<div class="icon-row">
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_MySQL.png" alt="MySQL"><span>MySQL</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_SQLServer.png" alt="SQL Server"><span>SQL Server</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_SAS.png" alt="SAS"><span>SAS</span></div>
</div>
<div class="skill-cat">Tools & OS</div>
<div class="icon-row">
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Git.png" alt="Git"><span>Git</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_GitHub.png" alt="GitHub"><span>GitHub</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_VisualStudioCode.png" alt="VS Code"><span>VS Code</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_VisualStudio.png" alt="Visual Studio"><span>Visual Studio</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_ApacheNetbeans.png" alt="NetBeans"><span>NetBeans</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_CodeBlock.png" alt="CodeBlocks"><span>CodeBlocks</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Figma.png" alt="Figma"><span>Figma</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Slack.png" alt="Slack"><span>Slack</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Ubuntu.png" alt="Ubuntu"><span>Ubuntu</span></div>
  <div class="icon-chip"><img src="https://raw.githubusercontent.com/itsHudson/hudsonlab/main/Images/TE_Rocky.png" alt="Rocky Linux"><span>Rocky Linux</span></div>
</div>

<!-- PROJECTS -->
<div class="sec">PROJECT CONSTELLATION <span class="gbadge bg">7 SYSTEMS</span></div>
<div class="proj-grid">
  <div class="proj-card" style="border-left-color:var(--a1)"><div class="proj-lang" style="color:var(--a1)">Python</div><div class="proj-title">Classroom Mgmt System</div><div class="proj-desc">Attendance tracking & schedule management with file I/O and modular design</div><div class="proj-tags"><span class="tag">file I/O</span><span class="tag">scheduling</span><span class="tag">modular</span></div></div>
  <div class="proj-card" style="border-left-color:var(--a2)"><div class="proj-lang" style="color:var(--a2)">Java</div><div class="proj-title">APU Medical Centre</div><div class="proj-desc">OOP system with patient records, appointments & billing via inheritance</div><div class="proj-tags"><span class="tag">OOP</span><span class="tag">inheritance</span><span class="tag">billing</span></div></div>
  <div class="proj-card" style="border-left-color:var(--a3)"><div class="proj-lang" style="color:var(--a3)">C</div><div class="proj-title">Bus Reservation System</div><div class="proj-desc">Seat reservation & cancellation using arrays, pointers and file I/O</div><div class="proj-tags"><span class="tag">arrays</span><span class="tag">pointers</span><span class="tag">file I/O</span></div></div>
  <div class="proj-card" style="border-left-color:var(--gold)"><div class="proj-lang" style="color:var(--gold)">Assembly</div><div class="proj-title">Shape Generation System</div><div class="proj-desc">Geometric rendering using registers, loops and low-level memory ops</div><div class="proj-tags"><span class="tag">registers</span><span class="tag">loops</span><span class="tag">memory</span></div></div>
  <div class="proj-card" style="border-left-color:var(--green)"><div class="proj-lang" style="color:var(--green)">SAS</div><div class="proj-title">Education Domain EDA</div><div class="proj-desc">Data cleaning & statistical modelling on education datasets in SAS Studio</div><div class="proj-tags"><span class="tag">EDA</span><span class="tag">data cleaning</span><span class="tag">stats</span></div></div>
  <div class="proj-card" style="border-left-color:#f87171"><div class="proj-lang" style="color:#f87171">Systems Design</div><div class="proj-title">Green Haven Resorts</div><div class="proj-desc">SDLC Waterfall system with use-case & process diagrams</div><div class="proj-tags"><span class="tag">SDLC</span><span class="tag">waterfall</span><span class="tag">UML</span></div></div>
  <div class="proj-card" style="border-left-color:#fb923c"><div class="proj-lang" style="color:#fb923c">Agile</div><div class="proj-title">APU TalentLink</div><div class="proj-desc">Internship/job matching platform with sprints, user stories & UI/UX mockups</div><div class="proj-tags"><span class="tag">agile</span><span class="tag">UI/UX</span><span class="tag">Figma</span></div></div>
</div>

<!-- METRICS -->
<div class="sec">SYSTEM METRICS</div>
<div class="stats-row">
  <div class="sc"><div style="position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--a1),var(--a2))"></div><div class="snum" style="color:var(--a2)" id="s-repos">—</div><div class="slbl">Public Repos</div></div>
  <div class="sc"><div style="position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--a3),var(--gold))"></div><div class="snum" style="color:var(--a3)">7+</div><div class="slbl">Languages</div></div>
  <div class="sc"><div style="position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--gold),var(--green))"></div><div class="snum" style="color:var(--gold)">6yr</div><div class="slbl">Ops Experience</div></div>
</div>

<!-- FUN FACTS -->
<div class="sec">FUN FACTS <span class="gbadge bp">ABOUT ME</span></div>
<div class="facts-grid">
  <div class="fact-card"><div class="fact-icon">🎂</div><div><div class="fact-txt">Ran a cake empire for 6 years</div><div class="fact-sub">Ops Manager · AC Cake House</div></div></div>
  <div class="fact-card"><div class="fact-icon">📡</div><div><div class="fact-txt">Red Hat certified</div><div class="fact-sub">Linux system administration</div></div></div>
  <div class="fact-card"><div class="fact-icon">📊</div><div><div class="fact-txt">Data drove 25% revenue boost</div><div class="fact-sub">Real-world analytics impact</div></div></div>
  <div class="fact-card"><div class="fact-icon">⚡</div><div><div class="fact-txt">Codes in 7+ languages</div><div class="fact-sub">From Assembly to Python</div></div></div>
</div>

<!-- RADAR STATUS -->
<div class="sec">SYSTEM STATUS <span class="gbadge bgg">LIVE</span></div>
<div class="radar-wrap">
  <div class="radar-svg-wrap">
    <svg viewBox="0 0 130 130" fill="none" xmlns="http://www.w3.org/2000/svg" width="130" height="130">
      <circle cx="65" cy="65" r="58" stroke="#1e2540" stroke-width="1"/>
      <circle cx="65" cy="65" r="40" stroke="#1e2540" stroke-width="1"/>
      <circle cx="65" cy="65" r="22" stroke="#1e2540" stroke-width="1"/>
      <line x1="65" y1="7" x2="65" y2="123" stroke="#1e2540" stroke-width=".5"/>
      <line x1="7" y1="65" x2="123" y2="65" stroke="#1e2540" stroke-width=".5"/>
      <g style="transform-origin:65px 65px;animation:sweep 3s linear infinite">
        <path d="M65 65 L65 7 A58 58 0 0 1 123 65 Z" fill="url(#sg)" opacity=".5"/>
      </g>
      <defs>
        <radialGradient id="sg" cx="0%" cy="100%" r="100%">
          <stop offset="0%" stop-color="#38bdf8" stop-opacity="0"/>
          <stop offset="100%" stop-color="#38bdf8" stop-opacity=".6"/>
        </radialGradient>
      </defs>
      <circle cx="65" cy="65" r="3" fill="#38bdf8"/>
      <circle cx="82" cy="40" r="3.5" fill="#4ade80"><animate attributeName="opacity" values="1;0.3;1" dur="2.1s" repeatCount="indefinite"/></circle>
      <circle cx="44" cy="78" r="2.5" fill="#a78bfa"><animate attributeName="opacity" values="1;0.3;1" dur="1.7s" repeatCount="indefinite"/></circle>
      <circle cx="95" cy="72" r="2" fill="#fbbf24"><animate attributeName="opacity" values="1;0.3;1" dur="2.5s" repeatCount="indefinite"/></circle>
      <circle cx="55" cy="35" r="2" fill="#f0abfc"><animate attributeName="opacity" values="1;0.3;1" dur="1.4s" repeatCount="indefinite"/></circle>
      <text x="65" y="117" text-anchor="middle" fill="#38bdf8" font-family="Space Mono,monospace" font-size="7" letter-spacing="2">SCANNING</text>
    </svg>
  </div>
  <div class="status-info">
    <div class="status-title">// hudson · system diagnostics</div>
    <div class="status-row"><div class="ping-dot green"></div><span class="status-key">kernel</span><span class="status-val">ONLINE — all systems nominal</span></div>
    <div class="status-row"><div class="ping-dot gold"></div><span class="status-key">mission</span><span class="status-val">seeking internship / data role</span></div>
    <div class="status-row"><div class="ping-dot purple"></div><span class="status-key">degree</span><span class="status-val">BSc CS · Data Analytics · APU</span></div>
    <div class="status-row"><div class="ping-dot green"></div><span class="status-key">location</span><span class="status-val">Cheras, MY · open to remote</span></div>
  </div>
</div>

<!-- WORMHOLE PORTAL WEBSITE -->
<div class="sec">PERSONAL WEBSITE</div>
<div class="portal-outer">
  <div class="portal-canvas-wrap"><canvas id="wormhole" style="width:100%;height:100%"></canvas></div>
  <div class="portal-content">
    <div class="portal-label">// enter the lab</div>
    <div class="portal-title">HUDSON LAB</div>
    <div class="portal-url">itshudson.github.io/hudsonlab</div>
    <button class="portal-btn" onclick="openLink('https://itshudson.github.io/hudsonlab/')">ENTER PORTAL ↗</button>
  </div>
</div>

<div class="footer">◈ HUDSON LAB · DATA ANALYTICS · GALAXY EDITION v4.0 ◈</div>
</div>
</div>

<script>
const lines=["Data Explorer & Analyst","Systems Programmer","Python · R · SQL · SAS","Building efficient solutions","Open to internships · Malaysia","Multilingual · EN · BM · ZH · 粤"];
let li=0,ci=0,del=false;
const el=document.getElementById('typer');
function tick(){if(!del){ci++;el.textContent=lines[li].slice(0,ci);if(ci===lines[li].length){del=true;setTimeout(tick,1800);return}setTimeout(tick,70);}else{ci--;el.textContent=lines[li].slice(0,ci);if(ci===0){del=false;li=(li+1)%lines.length;setTimeout(tick,300);return}setTimeout(tick,35);}}
tick();

const sc=document.getElementById('stars'),sctx=sc.getContext('2d');
function rsz(){sc.width=sc.offsetWidth;sc.height=sc.offsetHeight}rsz();
const stars=Array.from({length:140},()=>({x:Math.random()*sc.width,y:Math.random()*sc.height,r:Math.random()*1.6+.2,alpha:Math.random()*.8+.2,sp:Math.random()*.003+.001,ph:Math.random()*Math.PI*2,hue:Math.random()<.5?'167,139,250':'56,189,248'}));
function drawStars(t){sctx.clearRect(0,0,sc.width,sc.height);stars.forEach(s=>{const a=s.alpha*(0.5+0.5*Math.sin(t*s.sp+s.ph));sctx.beginPath();sctx.arc(s.x,s.y,s.r,0,Math.PI*2);sctx.fillStyle=`rgba(${s.hue},${a})`;sctx.fill();});requestAnimationFrame(drawStars);}
requestAnimationFrame(drawStars);

fetch('https://api.github.com/users/itsHudson').then(r=>r.json()).then(d=>{if(d.public_repos!==undefined)document.getElementById('s-repos').textContent=d.public_repos;}).catch(()=>{});

const wc=document.getElementById('wormhole'),wctx=wc.getContext('2d');
function rwc(){wc.width=wc.offsetWidth||700;wc.height=wc.offsetHeight||160}rwc();
const rings=Array.from({length:28},(_,i)=>({r:i*18+10,alpha:1-(i/28)*.85,speed:0.008+i*.001,angle:Math.random()*Math.PI*2}));
const particles=Array.from({length:60},()=>({angle:Math.random()*Math.PI*2,r:Math.random()*180+20,speed:0.003+Math.random()*.012,size:Math.random()*2+.5,color:Math.random()<.33?'167,139,250':Math.random()<.5?'56,189,248':'240,171,252'}));
function drawWormhole(t){
  const W=wc.width,H=wc.height,cx=W/2,cy=H/2;
  wctx.clearRect(0,0,W,H);
  wctx.fillStyle='#030508';wctx.fillRect(0,0,W,H);
  rings.forEach((ring,i)=>{
    ring.angle+=ring.speed*(i%2===0?1:-1);
    wctx.save();wctx.translate(cx,cy);wctx.rotate(ring.angle);
    wctx.beginPath();wctx.ellipse(0,0,ring.r,ring.r*(0.25+i*.005),0,0,Math.PI*2);
    const hue=i%3===0?'167,139,250':i%3===1?'56,189,248':'240,171,252';
    wctx.strokeStyle=`rgba(${hue},${ring.alpha*0.6})`;wctx.lineWidth=.8;wctx.stroke();wctx.restore();
  });
  particles.forEach(p=>{
    p.angle+=p.speed;
    const px=cx+Math.cos(p.angle)*p.r*(0.9+0.1*Math.sin(p.angle*3));
    const py=cy+Math.sin(p.angle)*p.r*0.28;
    wctx.beginPath();wctx.arc(px,py,p.size,0,Math.PI*2);
    wctx.fillStyle=`rgba(${p.color},0.8)`;wctx.fill();
  });
  const grad=wctx.createRadialGradient(cx,cy,0,cx,cy,60);
  grad.addColorStop(0,'rgba(167,139,250,0.15)');grad.addColorStop(1,'transparent');
  wctx.fillStyle=grad;wctx.beginPath();wctx.ellipse(cx,cy,60,22,0,0,Math.PI*2);wctx.fill();
  requestAnimationFrame(drawWormhole);
}
requestAnimationFrame(drawWormhole);
</script>
