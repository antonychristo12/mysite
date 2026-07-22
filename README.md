<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Antony Christo A — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0a0e14;
    --panel:#101620;
    --panel-2:#0d1218;
    --line:#1c2530;
    --text:#e6edf3;
    --muted:#7c8a9a;
    --cyan:#5ff0ff;
    --violet:#a78bfa;
    --green:#7ee787;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:
      radial-gradient(circle at 15% 0%, rgba(95,240,255,0.06), transparent 40%),
      radial-gradient(circle at 85% 20%, rgba(167,139,250,0.07), transparent 45%),
      var(--bg);
    color:var(--text);
    font-family:'Inter',sans-serif;
    min-height:100vh;
    padding:40px 16px 80px;
    line-height:1.6;
  }
  .grid-overlay{
    position:fixed; inset:0; pointer-events:none; z-index:0;
    background-image:
      linear-gradient(rgba(95,240,255,0.035) 1px, transparent 1px),
      linear-gradient(90deg, rgba(95,240,255,0.035) 1px, transparent 1px);
    background-size:38px 38px;
    mask-image:radial-gradient(circle at 50% 20%, black, transparent 75%);
  }
  .card{
    position:relative; z-index:1;
    max-width:640px;
    margin:0 auto;
    background:var(--panel);
    border:1px solid var(--line);
    border-radius:14px;
    overflow:hidden;
    box-shadow:0 0 0 1px rgba(95,240,255,0.04), 0 30px 80px -30px rgba(0,0,0,0.8);
  }
  .titlebar{
    display:flex; align-items:center; gap:8px;
    padding:12px 16px;
    background:var(--panel-2);
    border-bottom:1px solid var(--line);
    font-family:'JetBrains Mono',monospace;
    font-size:12px;
    color:var(--muted);
  }
  .titlebar span{margin-left:8px;}
  .content{padding:40px 32px 8px;}

  .photo-wrap{
    display:flex; justify-content:center; margin-bottom:24px;
  }
  .photo-ring{
    width:190px; height:218px; border-radius:22px;
    padding:4px;
    background:conic-gradient(from 180deg, var(--cyan), var(--violet), var(--cyan));
    box-shadow:0 0 40px -6px rgba(95,240,255,0.35);
  }
  .photo-ring img{
    width:100%; height:100%; border-radius:18px;
    object-fit:cover; object-position:center top; display:block;
    border:4px solid var(--panel);
  }

  .name-block{text-align:center; margin-bottom:6px;}
  .prompt{
    font-family:'JetBrains Mono',monospace;
    font-size:13px;
    color:var(--green);
    opacity:0.85;
  }
  h1{
    font-family:'JetBrains Mono',monospace;
    font-size:30px;
    font-weight:800;
    margin:6px 0 4px;
    background:linear-gradient(90deg, var(--cyan), var(--violet));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    letter-spacing:0.5px;
  }
  .role{
    text-align:center;
    color:var(--muted);
    font-family:'JetBrains Mono',monospace;
    font-size:14px;
    margin-bottom:28px;
  }

  .section-label{
    font-family:'JetBrains Mono',monospace;
    font-size:15px;
    font-weight:700;
    color:var(--cyan);
    margin:36px 0 14px;
    display:flex; align-items:center; gap:10px;
  }
  .section-label::before{content:"//"; color:var(--muted);}
  .section-label::after{
    content:""; flex:1; height:1px;
    background:linear-gradient(90deg, var(--line), transparent);
  }

  table.info{width:100%; border-collapse:collapse;}
  table.info tr{border-bottom:1px solid var(--line);}
  table.info tr:last-child{border-bottom:none;}
  table.info td{padding:12px 0; vertical-align:top; font-size:14.5px;}
  table.info td.k{
    width:120px;
    color:var(--violet);
    font-family:'JetBrains Mono',monospace;
    font-size:13px;
    font-weight:500;
    padding-right:10px;
  }
  table.info td.v{color:var(--text);}
  table.info td.v a{color:var(--cyan); text-decoration:none;}

  p.body-text{color:#c3cdd9; font-size:14.5px; margin:0 0 12px;}

  .skills-grid{display:flex; flex-wrap:wrap; gap:10px;}
  .skill-chip{
    font-family:'JetBrains Mono',monospace;
    font-size:13px;
    padding:7px 14px;
    border:1px solid var(--line);
    border-radius:20px;
    background:var(--panel-2);
    color:var(--text);
    display:flex; align-items:center; gap:7px;
  }
  .skill-chip .bar{
    width:6px;height:6px;border-radius:50%;
    background:var(--green);
  }
  .skill-chip.learning{color:var(--muted); border-style:dashed;}
  .skill-chip.learning .bar{background:var(--muted);}

  .edu-block{
    background:var(--panel-2);
    border:1px solid var(--line);
    border-radius:10px;
    padding:16px 18px;
    margin-bottom:14px;
  }
  .edu-title{font-weight:600; color:var(--text); font-size:15px; margin-bottom:2px;}
  .edu-sub{color:var(--muted); font-size:13.5px;}
  .edu-score{
    font-family:'JetBrains Mono',monospace;
    font-size:13px; color:var(--green);
    margin-top:6px;
  }

  .social-row{display:flex; flex-direction:column; gap:10px; margin-top:4px;}
  .social-link{
    display:flex; align-items:center; gap:12px;
    padding:12px 14px;
    background:var(--panel-2);
    border:1px solid var(--line);
    border-radius:10px;
    text-decoration:none;
    transition:border-color .2s ease, transform .2s ease;
  }
  .social-link:hover{border-color:var(--cyan); transform:translateX(2px);}
  .social-icon{
    width:20px; height:20px; flex-shrink:0;
  }
  .social-label{
    font-family:'JetBrains Mono',monospace;
    font-size:12px; color:var(--muted);
    display:block;
  }
  .social-value{color:var(--cyan); font-size:14px;}

  .projects-toggle{cursor:pointer; user-select:none;}
  .toggle-arrow{
    color:var(--muted); font-size:13px;
    transition:transform .25s ease;
    margin-left:-2px;
  }
  .projects-toggle.open .toggle-arrow{transform:rotate(90deg);}
  .projects-panel{
    max-height:0;
    overflow:hidden;
    transition:max-height .3s ease;
  }
  .projects-panel.open{max-height:400px;}
  .project-block{
    background:var(--panel-2);
    border:1px solid var(--line);
    border-radius:10px;
    padding:16px 18px;
    margin-bottom:12px;
  }
  .project-title{
    font-weight:600; color:var(--cyan); font-size:15px; margin-bottom:4px;
    font-family:'JetBrains Mono',monospace;
  }
  .project-desc{color:#c3cdd9; font-size:13.5px;}

  .footer-bar{
    text-align:center;
    padding:28px 20px 32px;
    font-family:'JetBrains Mono',monospace;
    font-size:11.5px;
    color:var(--muted);
    letter-spacing:0.5px;
  }
  .footer-bar .cursor{
    display:inline-block; width:7px; height:13px;
    background:var(--cyan); margin-left:3px;
    animation:blink 1.1s steps(1) infinite;
    vertical-align:middle;
  }
  @keyframes blink{50%{opacity:0;}}

  @media (max-width:480px){
    .content{padding:32px 20px 8px;}
    h1{font-size:25px;}
  }
</style>
</head>
<body>
<div class="grid-overlay"></div>

<div class="card">
  <div class="titlebar">
    <span>~/portfolio/antony-christo — zsh</span>
  </div>

  <div class="content">

    <div class="photo-wrap">
      <div class="photo-ring">
        <img src="profile.png" alt="Antony Christo A">
      </div>
    </div>

    <div class="name-block">
      <h1>Antony Christo A</h1>
    </div>
    <div class="role">B.E. Computer Science Engineering</div>

    <!-- Personal Information -->
    <div class="section-label">Personal Information</div>
    <table class="info">
      <tr><td class="k">college</td><td class="v">Madras Institute of Technology, Anna University, Chennai</td></tr>
      <tr><td class="k">department</td><td class="v">Computer Science Engineering (CSE)</td></tr>
      <tr><td class="k">dob</td><td class="v">12/07/2007</td></tr>
      <tr><td class="k">email</td><td class="v"><a href="mailto:antonychristo1213@gmail.com">antonychristo1213@gmail.com</a></td></tr>
      <tr><td class="k">phone</td><td class="v">9344236099</td></tr>
      <tr><td class="k">location</td><td class="v">Chennai</td></tr>
    </table>

    <!-- About Me -->
    <div class="section-label">About Me</div>
    <p class="body-text">Hi, I'm A. Antony Christo, a Computer Science Engineering student passionate about programming, software development, and technology. I enjoy learning new concepts, building projects, and continuously improving my skills to become a successful software engineer.</p>
    <p class="body-text">I completed my schooling at Vivekananda Vidyalaya Matriculation Higher Secondary School, building a strong academic foundation — 94% in Class X and 95% in Class XII. I'm currently pursuing my B.E. in Computer Science Engineering at MIT Campus, Anna University, expanding my knowledge in programming, software development, and emerging technologies.</p>

    <!-- Skills -->
    <div class="section-label">Skills</div>
    <div class="skills-grid">
      <div class="skill-chip"><span class="bar"></span>C</div>
      <div class="skill-chip"><span class="bar"></span>C++</div>
      <div class="skill-chip"><span class="bar"></span>Python</div>
      <div class="skill-chip learning"><span class="bar"></span>Java (learning)</div>
      <div class="skill-chip learning"><span class="bar"></span>Data Structures (learning)</div>
    </div>

    <!-- Education -->
    <div class="section-label">Education</div>
    <div class="edu-block">
      <div class="edu-title">Bachelor of Engineering (B.E.)</div>
      <div class="edu-sub">Computer Science Engineering · MIT Campus, Anna University</div>
    </div>
    <div class="edu-block">
      <div class="edu-title">Higher Secondary (Class XII)</div>
      <div class="edu-sub">Vivekananda Vidyalaya Matriculation Higher Secondary School</div>
      <div class="edu-score">score: 95%</div>
    </div>
    <div class="edu-block">
      <div class="edu-title">Secondary School (Class X)</div>
      <div class="edu-sub">Vivekananda Vidyalaya Matriculation Higher Secondary School</div>
      <div class="edu-score">score: 94%</div>
    </div>

    <!-- Projects -->
    <div class="section-label projects-toggle" id="projectsToggle">
      Projects <span class="toggle-arrow" id="toggleArrow">▸</span>
    </div>
    <div class="projects-panel" id="projectsPanel">
      <div class="project-block">
        <div class="project-title">Student Management System</div>
        <div class="project-desc">A system to manage student records, academics, and administrative data efficiently.</div>
      </div>
      <div class="project-block">
        <div class="project-title">Attendance Management in School/College</div>
        <div class="project-desc">A system to track and manage student attendance for schools and colleges.</div>
      </div>
    </div>

    <!-- Social -->
    <div class="section-label">Social Media</div>
    <div class="social-row">
      <a class="social-link" href="https://github.com/antonychristo12" target="_blank" rel="noopener">
        <svg class="social-icon" viewBox="0 0 24 24" fill="#e6edf3"><path d="M12 0C5.37 0 0 5.5 0 12.3c0 5.44 3.44 10.05 8.21 11.68.6.12.82-.27.82-.6 0-.3-.01-1.08-.02-2.12-3.34.75-4.04-1.64-4.04-1.64-.55-1.43-1.34-1.82-1.34-1.82-1.09-.77.08-.75.08-.75 1.2.09 1.84 1.26 1.84 1.26 1.07 1.87 2.81 1.33 3.49 1.02.11-.79.42-1.33.76-1.64-2.67-.31-5.47-1.37-5.47-6.1 0-1.35.47-2.45 1.24-3.32-.12-.31-.54-1.57.12-3.28 0 0 1.01-.33 3.3 1.27a11.2 11.2 0 0 1 6 0c2.29-1.6 3.3-1.27 3.3-1.27.66 1.71.24 2.97.12 3.28.77.87 1.24 1.97 1.24 3.32 0 4.74-2.81 5.78-5.49 6.09.43.38.81 1.13.81 2.28 0 1.65-.02 2.98-.02 3.38 0 .33.22.72.83.6C20.57 22.34 24 17.74 24 12.3 24 5.5 18.63 0 12 0z"/></svg>
        <div>
          <span class="social-label">github</span>
          <span class="social-value">github.com/antonychristo12</span>
        </div>
      </a>
      <a class="social-link" href="#" target="_blank" rel="noopener">
        <svg class="social-icon" viewBox="0 0 24 24" fill="#e6edf3"><path d="M20.45 20.45h-3.56v-5.58c0-1.33-.02-3.04-1.85-3.04-1.85 0-2.14 1.45-2.14 2.94v5.68H9.34V9h3.42v1.56h.05c.48-.9 1.64-1.85 3.38-1.85 3.6 0 4.27 2.37 4.27 5.46v6.28zM5.34 7.43a2.07 2.07 0 1 1 0-4.13 2.07 2.07 0 0 1 0 4.13zM7.12 20.45H3.56V9h3.56v11.45z"/></svg>
        <div>
          <span class="social-label">linkedin</span>
          <span class="social-value">Antony Christo</span>
        </div>
      </a>
    </div>

  </div>

  <div class="footer-bar">Thanks for visiting<span class="cursor"></span></div>
</div>

<script>
  const toggle = document.getElementById('projectsToggle');
  const panel = document.getElementById('projectsPanel');
  toggle.addEventListener('click', () => {
    toggle.classList.toggle('open');
    panel.classList.toggle('open');
  });
</script>

</body>
</html>
