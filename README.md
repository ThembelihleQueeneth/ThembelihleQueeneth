
<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0f;
    --card: #12121a;
    --card2: #1a1a26;
    --gold: #f4c542;
    --coral: #ff6b6b;
    --teal: #4ecdc4;
    --purple: #a78bfa;
    --text: #e8e8f0;
    --muted: #7a7a9a;
    --border: rgba(255,255,255,0.07);
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    line-height: 1.6;
    padding: 0;
  }

  .wrap { max-width: 860px; margin: 0 auto; padding: 2rem 1.5rem 4rem; }

  .hero {
    text-align: center;
    padding: 3rem 1rem 2.5rem;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; left: 50%; transform: translateX(-50%);
    width: 500px; height: 300px;
    background: radial-gradient(ellipse, rgba(167,139,250,0.15) 0%, transparent 70%);
    pointer-events: none;
  }

  .avatar-ring {
    width: 96px; height: 96px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--gold), var(--coral), var(--purple));
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1.5rem;
    padding: 3px;
  }

  .avatar-inner {
    width: 90px; height: 90px;
    border-radius: 50%;
    background: var(--card);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    background: linear-gradient(135deg, #2a1a3e, #1a2e3e);
    color: var(--gold);
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(1.8rem, 5vw, 2.8rem);
    font-weight: 800;
    background: linear-gradient(135deg, #ffffff 30%, var(--gold) 70%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: -0.02em;
    line-height: 1.1;
    margin-bottom: 0.5rem;
  }

  .hero-role {
    font-size: 1rem;
    color: var(--muted);
    font-weight: 300;
    letter-spacing: 0.04em;
    margin-bottom: 1.5rem;
  }

  .pill-row {
    display: flex; flex-wrap: wrap; gap: 8px;
    justify-content: center;
    margin-bottom: 1.5rem;
  }

  .pill {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    border: 1px solid var(--border);
    background: var(--card);
    color: var(--muted);
    letter-spacing: 0.05em;
  }

  .pill.gold { border-color: rgba(244,197,66,0.3); color: var(--gold); background: rgba(244,197,66,0.05); }
  .pill.coral { border-color: rgba(255,107,107,0.3); color: var(--coral); background: rgba(255,107,107,0.05); }
  .pill.teal { border-color: rgba(78,205,196,0.3); color: var(--teal); background: rgba(78,205,196,0.05); }

  .cta-row {
    display: flex; flex-wrap: wrap; gap: 10px;
    justify-content: center;
  }

  .btn {
    padding: 9px 20px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    font-family: 'DM Sans', sans-serif;
    cursor: pointer;
    border: 1px solid var(--border);
    text-decoration: none;
    transition: all 0.2s;
    display: inline-flex; align-items: center; gap: 6px;
  }

  .btn-primary {
    background: var(--gold);
    color: #1a1000;
    border-color: var(--gold);
    font-weight: 600;
  }

  .btn-ghost { background: transparent; color: var(--text); }
  .btn:hover { opacity: 0.85; transform: translateY(-1px); }

  .section { margin: 3rem 0; }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 1.25rem;
    display: flex; align-items: center; gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 10px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 12px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
  }

  .skill-card:hover {
    border-color: rgba(244,197,66,0.25);
    transform: translateY(-2px);
  }

  .skill-icon {
    font-size: 20px;
    line-height: 1;
  }

  .skill-name {
    font-size: 12px;
    font-weight: 500;
    color: var(--text);
    font-family: 'DM Mono', monospace;
  }

  .skill-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--gold);
    opacity: 0.5;
  }

  .skill-cat {
    font-size: 10px;
    color: var(--muted);
    margin-top: -2px;
  }

  .timeline {
    position: relative;
    padding-left: 28px;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 7px; top: 8px; bottom: 8px;
    width: 1px;
    background: linear-gradient(to bottom, var(--purple), var(--gold), var(--coral));
    opacity: 0.4;
  }

  .t-item {
    position: relative;
    margin-bottom: 1.75rem;
  }

  .t-item::before {
    content: '';
    position: absolute;
    left: -24px; top: 6px;
    width: 9px; height: 9px;
    border-radius: 50%;
    background: var(--gold);
    border: 2px solid var(--bg);
    box-shadow: 0 0 0 1px rgba(244,197,66,0.4);
  }

  .t-year {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: var(--gold);
    margin-bottom: 3px;
  }

  .t-title {
    font-weight: 500;
    font-size: 14px;
    color: var(--text);
    margin-bottom: 4px;
  }

  .t-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.55;
  }

  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 12px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.25rem 1rem;
    text-align: center;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 12px;
    color: var(--muted);
    font-weight: 300;
  }

  .code-block {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.5rem;
    font-family: 'DM Mono', monospace;
    font-size: 12.5px;
    line-height: 1.7;
    color: #c8c8e8;
    overflow-x: auto;
  }

  .code-block .kw { color: var(--purple); }
  .code-block .str { color: #79c7a7; }
  .code-block .key { color: #f4c542; }
  .code-block .comment { color: var(--muted); font-style: italic; }
  .code-block .num { color: var(--coral); }

  .goal-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 10px;
  }

  .goal-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 12px 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 13px;
    color: var(--text);
  }

  .goal-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--teal);
    flex-shrink: 0;
    margin-top: 5px;
  }

  .quote-box {
    border-left: 3px solid var(--gold);
    padding: 1rem 1.5rem;
    background: rgba(244,197,66,0.04);
    border-radius: 0 10px 10px 0;
    font-style: italic;
    color: var(--muted);
    font-size: 14px;
    line-height: 1.7;
  }

  .ai-badge {
    background: linear-gradient(135deg, rgba(167,139,250,0.15), rgba(78,205,196,0.1));
    border: 1px solid rgba(167,139,250,0.3);
    border-radius: 12px;
    padding: 1.25rem 1.5rem;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .ai-icon {
    font-size: 1.8rem;
    flex-shrink: 0;
  }

  .ai-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    color: var(--purple);
    font-size: 15px;
    margin-bottom: 4px;
  }

  .ai-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  .divider {
    height: 1px;
    background: var(--border);
    margin: 2.5rem 0;
  }

  .footer {
    text-align: center;
    padding: 2rem 0 0;
    font-size: 13px;
    color: var(--muted);
  }

  .footer strong { color: var(--gold); }

  .tab-row {
    display: flex; gap: 4px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 4px;
    margin-bottom: 1.25rem;
    flex-wrap: wrap;
  }

  .tab {
    padding: 6px 14px;
    border-radius: 7px;
    font-size: 12px;
    font-weight: 500;
    cursor: pointer;
    border: none;
    background: transparent;
    color: var(--muted);
    font-family: 'DM Sans', sans-serif;
    transition: all 0.15s;
  }

  .tab.active {
    background: rgba(244,197,66,0.12);
    color: var(--gold);
  }

  .tab-content { display: none; }
  .tab-content.visible { display: block; }
</style>

<div class="wrap">

  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar-inner">TQ</div>
    </div>
    <div class="hero-name">Thembelihle Queeneth Maluka</div>
    <div class="hero-role">Full Stack Developer &nbsp;·&nbsp; UI/UX Designer &nbsp;·&nbsp; AI Practitioner</div>
    <div class="pill-row">
      <span class="pill gold">South Africa</span>
      <span class="pill">TUT Computer Science</span>
      <span class="pill coral">She / Her</span>
      <span class="pill teal">Open to Opportunities</span>
    </div>
    <div class="cta-row">
      <button class="btn btn-primary" onclick="openLink('https://thembelihle-dev.vercel.app/')">Portfolio</button>
      <button class="btn btn-ghost" onclick="openLink('mailto:malukathembelihle95@gmail.com')">Get in touch</button>
    </div>
  </div>

  <div class="stats-row section">
    <div class="stat-card">
      <div class="stat-num">16</div>
      <div class="stat-label">months dev experience</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">3</div>
      <div class="stat-label">months UI/UX in Figma</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">15+</div>
      <div class="stat-label">technologies mastered</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">5</div>
      <div class="stat-label">years of perseverance</div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">Technical Skills</div>

    <div class="tab-row">
      <button class="tab active" onclick="switchTab(this,'frontend')">Frontend</button>
      <button class="tab" onclick="switchTab(this,'backend')">Backend</button>
      <button class="tab" onclick="switchTab(this,'data')">Databases</button>
      <button class="tab" onclick="switchTab(this,'lang')">Languages</button>
      <button class="tab" onclick="switchTab(this,'tools')">Tools & Design</button>
    </div>

    <div id="frontend" class="tab-content visible skill-grid">
      <div class="skill-card"><div class="skill-icon">🌐</div><div class="skill-name">HTML5</div><div class="skill-cat">Markup</div></div>
      <div class="skill-card"><div class="skill-icon">🎨</div><div class="skill-name">CSS3</div><div class="skill-cat">Styling</div></div>
      <div class="skill-card"><div class="skill-icon">⚡</div><div class="skill-name">JavaScript</div><div class="skill-cat">Core language</div></div>
      <div class="skill-card"><div class="skill-icon">🔷</div><div class="skill-name">TypeScript</div><div class="skill-cat">Typed JS</div></div>
      <div class="skill-card"><div class="skill-icon">⚛️</div><div class="skill-name">React</div><div class="skill-cat">UI library</div></div>
      <div class="skill-card"><div class="skill-icon">📱</div><div class="skill-name">React Native</div><div class="skill-cat">Mobile</div></div>
      <div class="skill-card"><div class="skill-icon">💨</div><div class="skill-name">Tailwind CSS</div><div class="skill-cat">Utility CSS</div></div>
      <div class="skill-card"><div class="skill-icon">🅱️</div><div class="skill-name">Bootstrap</div><div class="skill-cat">Framework</div></div>
    </div>

    <div id="backend" class="tab-content skill-grid">
      <div class="skill-card"><div class="skill-icon">🟢</div><div class="skill-name">Node.js</div><div class="skill-cat">Runtime</div></div>
      <div class="skill-card"><div class="skill-icon">🚂</div><div class="skill-name">Express.js</div><div class="skill-cat">Web framework</div></div>
      <div class="skill-card"><div class="skill-icon">🐘</div><div class="skill-name">PHP</div><div class="skill-cat">Server-side</div></div>
      <div class="skill-card"><div class="skill-icon">🐍</div><div class="skill-name">Python</div><div class="skill-cat">Scripting & AI</div></div>
      <div class="skill-card"><div class="skill-icon">🔗</div><div class="skill-name">REST API</div><div class="skill-cat">API design</div></div>
    </div>

    <div id="data" class="tab-content skill-grid">
      <div class="skill-card"><div class="skill-icon">🐘</div><div class="skill-name">PostgreSQL</div><div class="skill-cat">Relational DB</div></div>
      <div class="skill-card"><div class="skill-icon">🐬</div><div class="skill-name">MySQL</div><div class="skill-cat">Relational DB</div></div>
    </div>

    <div id="lang" class="tab-content skill-grid">
      <div class="skill-card"><div class="skill-icon">☕</div><div class="skill-name">Java</div><div class="skill-cat">OOP</div></div>
      <div class="skill-card"><div class="skill-icon">💜</div><div class="skill-name">C#</div><div class="skill-cat">.NET</div></div>
      <div class="skill-card"><div class="skill-icon">🐍</div><div class="skill-name">Python</div><div class="skill-cat">Multi-purpose</div></div>
      <div class="skill-card"><div class="skill-icon">🐘</div><div class="skill-name">PHP</div><div class="skill-cat">Web scripting</div></div>
    </div>

    <div id="tools" class="tab-content skill-grid">
      <div class="skill-card"><div class="skill-icon">🎭</div><div class="skill-name">Figma</div><div class="skill-cat">UI/UX Design</div></div>
      <div class="skill-card"><div class="skill-icon">▲</div><div class="skill-name">Vercel</div><div class="skill-cat">Deployment</div></div>
      <div class="skill-card"><div class="skill-icon">📬</div><div class="skill-name">Postman</div><div class="skill-cat">API testing</div></div>
      <div class="skill-card"><div class="skill-icon">📄</div><div class="skill-name">Swagger</div><div class="skill-cat">API docs</div></div>
      <div class="skill-card"><div class="skill-icon">⚡</div><div class="skill-name">Thunder Client</div><div class="skill-cat">VS Code tool</div></div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">AI Proficiency</div>
    <div class="ai-badge">
      <div class="ai-icon">🤖</div>
      <div>
        <div class="ai-title">AI-Augmented Development</div>
        <div class="ai-desc">Experienced in leveraging AI tools effectively — from prompt engineering and using LLMs like Claude, ChatGPT, and Copilot to accelerate development, debug complex issues, and generate design ideas. Understands how to critically evaluate AI output, integrate it into real workflows, and use Python for AI-adjacent scripting and automation. Not just using AI — using it wisely.</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">My Journey</div>
    <div class="timeline">
      <div class="t-item">
        <div class="t-year">2019 — The Spark</div>
        <div class="t-desc">WeThinkCode visited my Grade 12 school. One mention of developer salaries and my curiosity was ignited. This was my first glimpse into software development.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2020 — Gap Year & Discovery</div>
        <div class="t-desc">No university accepted me. I watched The Social Network and became obsessed with how Facebook was built. Tech wasn't just a career anymore — it was a fascination.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2021 — The Beginning</div>
        <div class="t-desc">Applied to TUT for Computer Science — not even knowing how to use a PC properly. Typed my first "Hello World" and felt like I'd done something extraordinary.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2022 — The Struggle</div>
        <div class="t-desc">The learning curve was brutal. I questioned myself constantly. This was the year that tested my resolve — and I chose to stay.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2023 — The Turnaround</div>
        <div class="t-desc">Concepts began clicking. Academic confidence grew. The pieces were finally falling into place and I could feel a shift in my understanding.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2024 — The Fire Ignites</div>
        <div class="t-desc">Everything changed. I stopped coding to pass and started coding because I loved it. Building, creating, solving — the passion was real and unstoppable.</div>
      </div>
      <div class="t-item">
        <div class="t-year">2025–2026 — Present Day</div>
        <div class="t-desc">16 months of development experience, 3 months of UI/UX design, PHP, Python, and AI tooling now in the toolkit. Actively seeking a team where I can grow and contribute.</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">What I Bring</div>
    <div class="code-block">
<span class="kw">const</span> <span class="key">myValue</span> = {<br>
&nbsp;&nbsp;<span class="key">frontend</span>: [<span class="str">"React"</span>, <span class="str">"TypeScript"</span>, <span class="str">"Tailwind"</span>, <span class="str">"React Native"</span>],<br>
&nbsp;&nbsp;<span class="key">backend</span>: [<span class="str">"Node.js"</span>, <span class="str">"Express"</span>, <span class="str">"PHP"</span>, <span class="str">"Python"</span>, <span class="str">"REST APIs"</span>],<br>
&nbsp;&nbsp;<span class="key">databases</span>: [<span class="str">"PostgreSQL"</span>, <span class="str">"MySQL"</span>],<br>
&nbsp;&nbsp;<span class="key">design</span>: [<span class="str">"Figma"</span>, <span class="str">"UI/UX principles"</span>, <span class="str">"Responsive design"</span>],<br>
&nbsp;&nbsp;<span class="key">ai</span>: [<span class="str">"Prompt engineering"</span>, <span class="str">"LLM integration"</span>, <span class="str">"GitHub Copilot"</span>, <span class="str">"AI-assisted dev"</span>],<br>
&nbsp;&nbsp;<span class="key">softSkills</span>: [<span class="str">"Problem solver"</span>, <span class="str">"Quick learner"</span>, <span class="str">"Resilient"</span>, <span class="str">"Self-driven"</span>],<br>
&nbsp;&nbsp;<span class="key">superpower</span>: <span class="str">"Started from zero — so I build with empathy"</span><br>
}
    </div>
  </div>

  <div class="section">
    <div class="section-label">Goals</div>
    <div class="goal-grid">
      <div class="goal-item"><div class="goal-dot"></div>Join an innovative tech company where I can grow</div>
      <div class="goal-item"><div class="goal-dot"></div>Build impactful full-stack products</div>
      <div class="goal-item"><div class="goal-dot"></div>Master Next.js &amp; server-side rendering</div>
      <div class="goal-item"><div class="goal-dot"></div>Deepen Python for AI and automation</div>
      <div class="goal-item"><div class="goal-dot"></div>Advance Figma design systems &amp; prototyping</div>
      <div class="goal-item"><div class="goal-dot"></div>Contribute to open-source communities</div>
      <div class="goal-item"><div class="goal-dot"></div>Explore Docker &amp; cloud platforms (AWS/GCP)</div>
      <div class="goal-item"><div class="goal-dot"></div>Launch a social platform for book lovers</div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="quote-box">
    "From not knowing how to use a PC to building full-stack applications — if I can do it, anyone can. It's all about persistence, passion, and never letting a hard year write the final chapter."
  </div>

  <div class="footer" style="margin-top: 2rem;">
    Made with passion by <strong>Thembelihle Queeneth Maluka</strong><br>
    <span style="font-size: 12px; margin-top: 4px; display: block;">From confusion to passion &nbsp;·&nbsp; From struggle to strength &nbsp;·&nbsp; This is just the beginning.</span>
  </div>

</div>

<script>
function switchTab(el, id) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('visible'));
  el.classList.add('active');
  document.getElementById(id).classList.add('visible');
}
</script>
