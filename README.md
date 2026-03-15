<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Jeison Caguana — Tech Lead & Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Mono:ital,wght@0,300;0,400;1,300&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #0b0b0b;
  --bg2: #111111;
  --bg3: #161616;
  --accent: #ff5c28;
  --accent2: #ff8c5a;
  --text: #f0ede6;
  --muted: #666;
  --muted2: #999;
  --border: #1f1f1f;
  --border2: #2a2a2a;
  --green: #22c55e;
  --mono: 'DM Mono', monospace;
  --display: 'Syne', sans-serif;
}
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--mono);
  font-weight: 300;
  line-height: 1.7;
  overflow-x: hidden;
}
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
  opacity: 0.025;
  pointer-events: none;
  z-index: 999;
}

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  padding: 20px 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: linear-gradient(to bottom, #0b0b0bdd, transparent);
  backdrop-filter: blur(8px);
}
.nav-logo {
  font-family: var(--display);
  font-weight: 800;
  font-size: 18px;
  letter-spacing: -0.02em;
  color: var(--text);
  text-decoration: none;
}
.nav-logo span { color: var(--accent); }
.nav-links { display: flex; gap: 32px; list-style: none; }
.nav-links a {
  font-size: 11px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  text-decoration: none;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--text); }

/* HERO */
.hero-wrap {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 120px 48px 80px;
  max-width: 1100px;
  margin: 0 auto;
  position: relative;
}
.hero-glow-1 {
  position: absolute; top: 10%; right: 5%;
  width: 500px; height: 500px;
  background: radial-gradient(circle, #ff5c2812 0%, transparent 65%);
  pointer-events: none;
}
.hero-glow-2 {
  position: absolute; bottom: 15%; left: -5%;
  width: 400px; height: 400px;
  background: radial-gradient(circle, #3b82f60a 0%, transparent 65%);
  pointer-events: none;
}
.hero-content { position: relative; z-index: 1; max-width: 680px; }
.hero-tag {
  display: inline-flex; align-items: center; gap: 8px;
  font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--accent); border: 1px solid #ff5c2830;
  padding: 5px 12px; border-radius: 4px; margin-bottom: 28px;
  animation: fadeUp 0.5s ease both;
}
.avail-dot {
  width: 6px; height: 6px; background: var(--green);
  border-radius: 50%; animation: pulse 2s ease-in-out infinite;
}
.hero-name {
  font-family: var(--display); font-weight: 800;
  font-size: clamp(52px, 8vw, 88px);
  line-height: 0.95; letter-spacing: -0.03em; color: var(--text);
  animation: fadeUp 0.5s ease 0.1s both;
}
.hero-name span { color: var(--accent); }
.hero-role {
  font-family: var(--display); font-size: clamp(15px, 2vw, 20px);
  font-weight: 400; color: var(--muted2); margin-top: 14px;
  animation: fadeUp 0.5s ease 0.2s both;
}
.hero-divider {
  width: 56px; height: 2px; background: var(--accent);
  margin: 28px 0; animation: fadeUp 0.5s ease 0.25s both;
}
.hero-pitch {
  font-size: 15px; line-height: 1.85; color: var(--muted2);
  max-width: 520px; animation: fadeUp 0.5s ease 0.3s both;
}
.hero-pitch strong { color: var(--text); font-weight: 400; }
.hero-stack {
  display: flex; flex-wrap: wrap; gap: 8px;
  margin-top: 28px; animation: fadeUp 0.5s ease 0.35s both;
}
.stack-badge {
  font-size: 11px; letter-spacing: 0.06em; color: var(--muted);
  background: var(--bg3); border: 1px solid var(--border2);
  padding: 5px 13px; border-radius: 3px;
  transition: border-color 0.2s, color 0.2s;
}
.stack-badge:hover { border-color: var(--accent); color: var(--accent); }
.hero-ctas {
  display: flex; gap: 12px; margin-top: 36px; flex-wrap: wrap;
  animation: fadeUp 0.5s ease 0.4s both;
}
.btn-primary {
  font-family: var(--mono); font-size: 12px; letter-spacing: 0.08em;
  text-transform: uppercase; background: var(--accent); color: #0b0b0b;
  border: none; padding: 14px 28px; border-radius: 4px; cursor: pointer;
  text-decoration: none; display: inline-block;
  transition: background 0.2s, transform 0.15s;
}
.btn-primary:hover { background: var(--accent2); transform: translateY(-1px); }
.btn-secondary {
  font-family: var(--mono); font-size: 12px; letter-spacing: 0.08em;
  text-transform: uppercase; background: transparent; color: var(--muted2);
  border: 1px solid var(--border2); padding: 14px 28px; border-radius: 4px;
  cursor: pointer; text-decoration: none; display: inline-block;
  transition: border-color 0.2s, color 0.2s, transform 0.15s;
}
.btn-secondary:hover { border-color: var(--muted); color: var(--text); transform: translateY(-1px); }
.hero-location {
  margin-top: 32px; font-size: 11px; color: var(--muted);
  letter-spacing: 0.06em; animation: fadeUp 0.5s ease 0.45s both;
}

/* SECTIONS */
section { padding: 100px 48px; max-width: 1100px; margin: 0 auto; }
.section-label {
  font-size: 11px; letter-spacing: 0.14em; text-transform: uppercase;
  color: var(--accent); margin-bottom: 12px;
}
.section-title {
  font-family: var(--display); font-weight: 800;
  font-size: clamp(32px, 4vw, 48px);
  letter-spacing: -0.02em; line-height: 1.1; color: var(--text); margin-bottom: 20px;
}
.section-line { width: 40px; height: 2px; background: var(--accent); margin-bottom: 48px; }
.sep { border: none; border-top: 1px solid var(--border); margin: 0 48px; }

/* ABOUT */
.about-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 64px; align-items: start;
}
.about-text p { font-size: 14px; color: var(--muted2); line-height: 1.9; margin-bottom: 16px; }
.about-text p strong { color: var(--text); font-weight: 400; }
.about-facts { display: flex; flex-direction: column; gap: 16px; }
.fact-card {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: 8px; padding: 20px 24px;
  display: flex; align-items: flex-start; gap: 16px;
  transition: border-color 0.2s;
}
.fact-card:hover { border-color: var(--border2); }
.fact-icon { font-size: 18px; line-height: 1; margin-top: 2px; }
.fact-label { font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); margin-bottom: 4px; }
.fact-value { font-size: 13px; color: var(--text); }

/* STACK */
.stack-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 12px;
}
.stack-card {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: 8px; padding: 24px 20px; text-align: center;
  transition: border-color 0.2s, transform 0.15s; cursor: default;
}
.stack-card:hover { border-color: var(--accent); transform: translateY(-3px); }
.stack-card-icon { font-size: 22px; margin-bottom: 10px; }
.stack-card-name { font-family: var(--display); font-size: 14px; font-weight: 700; color: var(--text); margin-bottom: 4px; }
.stack-card-type { font-size: 10px; letter-spacing: 0.08em; color: var(--muted); text-transform: uppercase; }

/* PROJECTS */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}
.project-card {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: 10px; padding: 28px;
  display: flex; flex-direction: column; gap: 14px;
  transition: border-color 0.25s, transform 0.2s;
  position: relative; overflow: hidden;
}
.project-card::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0;
  height: 2px; background: var(--accent); opacity: 0; transition: opacity 0.25s;
}
.project-card:hover { border-color: var(--border2); transform: translateY(-4px); }
.project-card:hover::before { opacity: 1; }
.project-header { display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; }
.project-title { font-family: var(--display); font-size: 17px; font-weight: 700; color: var(--text); letter-spacing: -0.01em; }
.project-company {
  font-size: 10px; letter-spacing: 0.08em; text-transform: uppercase;
  color: var(--accent); background: #ff5c2810; border: 1px solid #ff5c2825;
  padding: 3px 9px; border-radius: 3px; white-space: nowrap;
}
.project-date { font-size: 11px; color: var(--muted); letter-spacing: 0.06em; }
.project-desc { font-size: 13px; color: var(--muted2); line-height: 1.75; }
.project-tech { display: flex; flex-wrap: wrap; gap: 6px; margin-top: auto; }
.tech-pill {
  font-size: 10px; letter-spacing: 0.06em; color: var(--muted);
  background: var(--bg2); border: 1px solid var(--border2);
  padding: 3px 10px; border-radius: 3px;
}

/* EXPERIENCE / TIMELINE */
.timeline { position: relative; padding-left: 32px; }
.timeline::before {
  content: ''; position: absolute; left: 0; top: 8px; bottom: 8px;
  width: 1px; background: var(--border2);
}
.timeline-item { position: relative; padding-bottom: 52px; }
.timeline-item:last-child { padding-bottom: 0; }
.timeline-dot {
  position: absolute; left: -36px; top: 6px;
  width: 10px; height: 10px; border-radius: 50%;
  background: var(--accent); border: 2px solid var(--bg);
  box-shadow: 0 0 0 1px var(--accent);
}
.timeline-dot.past {
  background: var(--muted); box-shadow: 0 0 0 1px var(--muted);
}
.timeline-date { font-size: 11px; letter-spacing: 0.08em; color: var(--muted); margin-bottom: 6px; }
.timeline-role {
  font-family: var(--display); font-size: 20px; font-weight: 700;
  color: var(--text); letter-spacing: -0.01em; margin-bottom: 2px;
}
.timeline-company { font-size: 13px; color: var(--accent); margin-bottom: 12px; }
.timeline-desc { font-size: 13px; color: var(--muted2); line-height: 1.8; max-width: 600px; }
.timeline-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 12px; }
.timeline-tag {
  font-size: 10px; letter-spacing: 0.06em; color: var(--muted);
  background: var(--bg2); border: 1px solid var(--border2);
  padding: 3px 10px; border-radius: 3px;
}

/* EDUCATION */
.edu-card {
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: 10px; padding: 28px 32px;
  display: flex; align-items: center; gap: 24px;
  max-width: 560px;
}
.edu-icon { font-size: 32px; }
.edu-title { font-family: var(--display); font-size: 18px; font-weight: 700; color: var(--text); margin-bottom: 4px; }
.edu-sub { font-size: 13px; color: var(--muted2); }
.edu-date { font-size: 11px; color: var(--muted); margin-top: 4px; letter-spacing: 0.06em; }

/* CONTACT */
.contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 64px; align-items: start; }
.contact-text p { font-size: 14px; color: var(--muted2); line-height: 1.9; margin-bottom: 24px; }
.contact-links { display: flex; flex-direction: column; gap: 12px; }
.contact-link {
  display: flex; align-items: center; gap: 14px; padding: 16px 20px;
  background: var(--bg3); border: 1px solid var(--border);
  border-radius: 8px; text-decoration: none; color: var(--text);
  font-size: 13px; transition: border-color 0.2s, transform 0.15s;
}
.contact-link:hover { border-color: var(--accent); transform: translateX(4px); }
.contact-link-icon { font-size: 16px; width: 20px; text-align: center; }
.contact-link-label { font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); display: block; }
.contact-link-value { color: var(--text); }
.contact-form { display: flex; flex-direction: column; gap: 14px; }
.form-group { display: flex; flex-direction: column; gap: 6px; }
.form-label { font-size: 10px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); }
.form-input, .form-textarea {
  font-family: var(--mono); font-size: 13px; font-weight: 300;
  background: var(--bg3); border: 1px solid var(--border2);
  border-radius: 6px; padding: 12px 16px; color: var(--text);
  outline: none; transition: border-color 0.2s; resize: none;
}
.form-input:focus, .form-textarea:focus { border-color: var(--accent); }
.form-textarea { min-height: 120px; }

/* FOOTER */
footer {
  border-top: 1px solid var(--border); padding: 32px 48px;
  display: flex; justify-content: space-between; align-items: center;
  max-width: 1100px; margin: 0 auto;
}
.footer-copy { font-size: 12px; color: var(--muted); }
.footer-copy span { color: var(--accent); }
.footer-links { display: flex; gap: 24px; }
.footer-links a {
  font-size: 11px; letter-spacing: 0.08em; text-transform: uppercase;
  color: var(--muted); text-decoration: none; transition: color 0.2s;
}
.footer-links a:hover { color: var(--text); }

/* ANIMATIONS */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes pulse {
  0%,100% { opacity: 1; }
  50% { opacity: 0.3; }
}
.reveal { opacity: 0; transform: translateY(20px); transition: opacity 0.6s ease, transform 0.6s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }

/* RESPONSIVE */
@media (max-width: 768px) {
  nav { padding: 16px 24px; }
  .nav-links { display: none; }
  section, .hero-wrap { padding-left: 24px; padding-right: 24px; }
  .about-grid, .contact-inner { grid-template-columns: 1fr; gap: 40px; }
  footer { flex-direction: column; gap: 16px; padding: 24px; }
  .sep { margin: 0 24px; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">JC<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#about">Sobre mí</a></li>
    <li><a href="#stack">Stack</a></li>
    <li><a href="#projects">Proyectos</a></li>
    <li><a href="#experience">Experiencia</a></li>
    <li><a href="#contact">Contacto</a></li>
  </ul>
</nav>

<!-- HERO -->
<div class="hero-wrap">
  <div class="hero-glow-1"></div>
  <div class="hero-glow-2"></div>
  <div class="hero-content">
    <div class="hero-tag">
      <span class="avail-dot"></span>
      Disponible para proyectos
    </div>
    <h1 class="hero-name">Jeison<br><span>Caguana</span></h1>
    <p class="hero-role">Director IT · Tech Lead · FoodTech & POS · Software Developer</p>
    <div class="hero-divider"></div>
    <p class="hero-pitch">
      Construyo <strong>soluciones de software a medida</strong> para restaurantes y negocios.<br>
      Especializado en <strong>POS, comanderos, backoffice</strong> y sistemas orientados<br>
      a eficiencia, escalabilidad y resultados reales.
    </p>
    <div class="hero-stack">
      <span class="stack-badge">Node.js</span>
      <span class="stack-badge">Laravel</span>
      <span class="stack-badge">React Native</span>
      <span class="stack-badge">Angular</span>
      <span class="stack-badge">Swift</span>
      <span class="stack-badge">SQL Server</span>
    </div>
    <div class="hero-ctas">
      <a href="#projects" class="btn-primary">Ver proyectos</a>
      <a href="#contact" class="btn-secondary">Contactar</a>
    </div>
    <p class="hero-location">📍 Madrid, España &nbsp;·&nbsp; jeisoncaguana@gmail.com</p>
  </div>
</div>

<hr class="sep"/>

<!-- ABOUT -->
<section id="about">
  <div class="reveal">
    <p class="section-label">01 — Sobre mí</p>
    <h2 class="section-title">Desarrollador con foco<br>en resultados reales</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid reveal">
    <div class="about-text">
      <p>
        Soy un desarrollador full stack originario de <strong>Quito, Ecuador</strong>, actualmente viviendo y trabajando en <strong>Madrid, España</strong>. Me especializo en construir aplicaciones robustas para el sector de restauración y hostelería.
      </p>
      <p>
        Actualmente dirijo el área IT y lidero el equipo técnico de <strong>Grupo Cañas y Tapas</strong>, donde desarrollo soluciones de software a medida enfocadas en la optimización de procesos operativos, control interno y mejora del negocio — con sistemas POS ya operando en <strong>21 restaurantes</strong>.
      </p>
      <p>
        Antes de España trabajé varios años en <strong>KFC Ecuador</strong> como administrador de aplicaciones y en <strong>GoApps CL</strong> desarrollando apps móviles y web para distintos sectores. Cuando no estoy programando, estoy en moto explorando nuevas rutas.
      </p>
    </div>
    <div class="about-facts">
      <div class="fact-card">
        <div class="fact-icon">📍</div>
        <div>
          <p class="fact-label">Ubicación</p>
          <p class="fact-value">Madrid, España</p>
        </div>
      </div>
      <div class="fact-card">
        <div class="fact-icon">💼</div>
        <div>
          <p class="fact-label">Rol actual</p>
          <p class="fact-value">Director IT · Tech Lead @ Grupo Cañas y Tapas</p>
        </div>
      </div>
      <div class="fact-card">
        <div class="fact-icon">🎓</div>
        <div>
          <p class="fact-label">Formación</p>
          <p class="fact-value">Sistemas — Universitario Rumiñahui, Ecuador</p>
        </div>
      </div>
      <div class="fact-card">
        <div class="fact-icon">🏍️</div>
        <div>
          <p class="fact-label">Fuera del teclado</p>
          <p class="fact-value">Motorista · Viajero · Ecuador → España</p>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="sep"/>

<!-- STACK -->
<section id="stack">
  <div class="reveal">
    <p class="section-label">02 — Tecnologías</p>
    <h2 class="section-title">Stack tecnológico</h2>
    <div class="section-line"></div>
  </div>
  <div class="stack-grid reveal">
    <div class="stack-card">
      <div class="stack-card-icon">🟢</div>
      <p class="stack-card-name">Node.js</p>
      <p class="stack-card-type">Backend</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🔴</div>
      <p class="stack-card-name">Laravel</p>
      <p class="stack-card-type">Backend · PHP</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">📱</div>
      <p class="stack-card-name">React Native</p>
      <p class="stack-card-type">Mobile</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🔺</div>
      <p class="stack-card-name">Angular</p>
      <p class="stack-card-type">Frontend</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🍎</div>
      <p class="stack-card-name">Swift</p>
      <p class="stack-card-type">iOS Native</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🗄️</div>
      <p class="stack-card-name">SQL Server</p>
      <p class="stack-card-type">Base de datos</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🔧</div>
      <p class="stack-card-name">SQL · QA · TFS</p>
      <p class="stack-card-type">Calidad & control</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">🔗</div>
      <p class="stack-card-name">REST APIs</p>
      <p class="stack-card-type">Integración</p>
    </div>
    <div class="stack-card">
      <div class="stack-card-icon">📦</div>
      <p class="stack-card-name">ERP</p>
      <p class="stack-card-type">Integración empresarial</p>
    </div>
  </div>
</section>

<hr class="sep"/>

<!-- PROJECTS -->
<section id="projects">
  <div class="reveal">
    <p class="section-label">03 — Proyectos</p>
    <h2 class="section-title">Trabajo destacado</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-grid reveal">

    <!-- 1 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">App Manager Grupo Cañas y Tapas</h3>
        <span class="project-company">Cañas y Tapas</span>
      </div>
      <p class="project-date">ene. 2025</p>
      <p class="project-desc">
        Todo lo que necesitas para gestionar tu restaurante en un solo lugar. App de administración diseñada para facilitar el pedido de productos, acceso a resúmenes diarios, revisión de transacciones y análisis de ventas en cada local.
      </p>
      <div class="project-tech">
        <span class="tech-pill">React Native</span>
        <span class="tech-pill">Node.js</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">REST API</span>
      </div>
    </div>

    <!-- 2 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Japp — POS & Facturación</h3>
        <span class="project-company">Cañas y Tapas</span>
      </div>
      <p class="project-date">ene. 2023 — ene. 2025</p>
      <p class="project-desc">
        Software de facturación en punto de venta. Optimiza el servicio, agiliza la atención al cliente, gestiona ventas, controla accesos de camareros y personaliza la comanda antes de enviarla a imprimir. Operando en 21 restaurantes.
      </p>
      <div class="project-tech">
        <span class="tech-pill">Angular</span>
        <span class="tech-pill">Node.js</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">POS</span>
      </div>
    </div>

    <!-- 3 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Panel Producción Agrícola</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">sept. 2021 — dic. 2022</p>
      <p class="project-desc">
        Plataforma de gestión de siembra, producción y cosecha de legumbres y hortalizas. Incluye gestión de lotes, cultivos, gastos, formulaciones, cosecha, productos, integración con ERP y administración de roles y seguridades.
      </p>
      <div class="project-tech">
        <span class="tech-pill">Laravel</span>
        <span class="tech-pill">Angular</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">ERP</span>
      </div>
    </div>

    <!-- 4 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Repartidor App</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">ago. 2020 — ene. 2021</p>
      <p class="project-desc">
        App móvil Al Paso Repartidor: registro de repartidores, recepción de pedidos, entrega en dirección del cliente y generación de ingresos. Cuenta activa en 48 horas tras registro y validación del vehículo.
      </p>
      <div class="project-tech">
        <span class="tech-pill">React Native</span>
        <span class="tech-pill">Node.js</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">GPS</span>
      </div>
    </div>

    <!-- 5 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Tienda App — Market Place</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">jul. 2020 — ene. 2021</p>
      <p class="project-desc">
        Plataforma digital Market Place lanzada durante emergencia sanitaria 2020. Recepción, despacho y entrega de productos de primera necesidad: tiendas, restaurantes, farmacias, ferreterías y más.
      </p>
      <div class="project-tech">
        <span class="tech-pill">React Native</span>
        <span class="tech-pill">Laravel</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">E-commerce</span>
      </div>
    </div>

    <!-- 6 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Despachos Web</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">oct. 2020 — dic. 2020</p>
      <p class="project-desc">
        Plataforma web para gestión de despachos y logística de entrega. Integrada con la app de repartidores para coordinar pedidos, rutas y confirmaciones en tiempo real.
      </p>
      <div class="project-tech">
        <span class="tech-pill">Angular</span>
        <span class="tech-pill">Node.js</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">Logística</span>
      </div>
    </div>

    <!-- 7 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Back Office — Al Paso</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">2020</p>
      <p class="project-desc">
        Panel de administración back office para la plataforma Al Paso. Gestión centralizada de tiendas, pedidos, usuarios, repartidores y configuración del marketplace.
      </p>
      <div class="project-tech">
        <span class="tech-pill">Angular</span>
        <span class="tech-pill">Laravel</span>
        <span class="tech-pill">SQL Server</span>
      </div>
    </div>

    <!-- 8 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Delivery App — Restaurantes</h3>
        <span class="project-company">GoApps CL</span>
      </div>
      <p class="project-date">abr. 2020 — oct. 2021</p>
      <p class="project-desc">
        Aplicación de delivery para restaurantes. Gestión de pedidos online, integración con cocina, seguimiento de estado del pedido y panel de administración para el restaurante.
      </p>
      <div class="project-tech">
        <span class="tech-pill">React Native</span>
        <span class="tech-pill">Node.js</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">FoodTech</span>
      </div>
    </div>

    <!-- 9 -->
    <div class="project-card">
      <div class="project-header">
        <h3 class="project-title">Administración de Impuestos — Bomberos Atacames</h3>
        <span class="project-company">Proyecto</span>
      </div>
      <p class="project-date">nov. 2019 — ene. 2020</p>
      <p class="project-desc">
        Sistema de administración de impuestos de tasa anual para toda razón social del cantón Atacames: empresas, microempresas y artesanos que realizan actividades comerciales.
      </p>
      <div class="project-tech">
        <span class="tech-pill">Laravel</span>
        <span class="tech-pill">SQL Server</span>
        <span class="tech-pill">Gestión pública</span>
      </div>
    </div>

  </div>
</section>

<hr class="sep"/>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="reveal">
    <p class="section-label">04 — Trayectoria</p>
    <h2 class="section-title">Experiencia profesional</h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline reveal">

    <!-- Cañas y Tapas -->
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <p class="timeline-date">feb. 2023 — actualidad · 3 años 2 meses · Madrid, España</p>
      <h3 class="timeline-role">Director IT | Tech Lead | FoodTech & POS</h3>
      <p class="timeline-company">Grupo Cañas y Tapas · Jornada completa</p>
      <p class="timeline-desc">
        Desarrollo de soluciones de software a medida para restaurantes, enfocadas en la optimización de procesos operativos, control interno y mejora de resultados del negocio. Experiencia en POS, comanderos, backoffice y sistemas orientados a eficiencia y escalabilidad. Actualmente operando en 21 restaurantes, con crecimiento activo.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">Node.js</span>
        <span class="timeline-tag">Angular</span>
        <span class="timeline-tag">React Native</span>
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">POS</span>
        <span class="timeline-tag">FoodTech</span>
      </div>
    </div>

    <!-- KFC España -->
    <div class="timeline-item">
      <div class="timeline-dot past"></div>
      <p class="timeline-date">ene. 2022 — ene. 2023 · 1 año 1 mes · Madrid, España · Presencial</p>
      <h3 class="timeline-role">Administración de Aplicaciones — España</h3>
      <p class="timeline-company">Grupo KFC Ecuador · Jornada completa</p>
      <p class="timeline-desc">
        Transición de Ecuador a España dentro del mismo grupo. Administración de aplicaciones corporativas, soporte técnico y mantenimiento de sistemas en el entorno español.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">TFS</span>
        <span class="timeline-tag">QA</span>
      </div>
    </div>

    <!-- KFC Mantenimiento SIR -->
    <div class="timeline-item">
      <div class="timeline-dot past"></div>
      <p class="timeline-date">dic. 2021 — ene. 2022 · 2 meses · Ecuador</p>
      <h3 class="timeline-role">Mantenimiento SIR — Países (Ec, Col, Ven, Esp)</h3>
      <p class="timeline-company">Grupo KFC Ecuador</p>
      <p class="timeline-desc">
        Mantenimiento y soporte del sistema SIR en múltiples países: Ecuador, Colombia, Venezuela y España. Coordinación internacional de incidencias y actualizaciones.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">SIR</span>
        <span class="timeline-tag">Soporte multisede</span>
      </div>
    </div>

    <!-- KFC Administración Ecuador -->
    <div class="timeline-item">
      <div class="timeline-dot past"></div>
      <p class="timeline-date">mar. 2020 — dic. 2021 · 1 año 10 meses · Ecuador</p>
      <h3 class="timeline-role">Administración de Aplicaciones</h3>
      <p class="timeline-company">Grupo KFC Ecuador</p>
      <p class="timeline-desc">
        Administración de aplicaciones corporativas. Gestión de base de datos, control de calidad y uso de Team Foundation Server para control de versiones y seguimiento de proyectos.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">QA</span>
        <span class="timeline-tag">TFS</span>
      </div>
    </div>

    <!-- KFC Desarrollador -->
    <div class="timeline-item">
      <div class="timeline-dot past"></div>
      <p class="timeline-date">mar. 2019 — mar. 2020 · 1 año 1 mes · Ecuador</p>
      <h3 class="timeline-role">Desarrollador de Software</h3>
      <p class="timeline-company">Grupo KFC Ecuador</p>
      <p class="timeline-desc">
        Desarrollo de software interno para el grupo. Primer rol dentro de KFC Ecuador, base de una trayectoria de casi 4 años en la empresa con crecimiento a roles de administración y soporte internacional.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">Desarrollo interno</span>
      </div>
    </div>

    <!-- GoApps -->
    <div class="timeline-item">
      <div class="timeline-dot past"></div>
      <p class="timeline-date">abr. 2020 — oct. 2021 · 1 año 7 meses · Ecuador</p>
      <h3 class="timeline-role">Software Developer</h3>
      <p class="timeline-company">GoApps CL · Contrato por obra o servicio</p>
      <p class="timeline-desc">
        Desarrollo de aplicación de delivery para restaurantes y plataformas digitales marketplace. Proyectos para distintos sectores: restauración, logística, agricultura y administración pública.
      </p>
      <div class="timeline-tags">
        <span class="timeline-tag">React Native</span>
        <span class="timeline-tag">Laravel</span>
        <span class="timeline-tag">Angular</span>
        <span class="timeline-tag">SQL Server</span>
        <span class="timeline-tag">Node.js</span>
      </div>
    </div>

  </div>
</section>

<hr class="sep"/>

<!-- EDUCATION -->
<section id="education">
  <div class="reveal">
    <p class="section-label">05 — Formación</p>
    <h2 class="section-title">Educación</h2>
    <div class="section-line"></div>
  </div>
  <div class="reveal">
    <div class="edu-card">
      <div class="edu-icon">🎓</div>
      <div>
        <p class="edu-title">Ingeniería en Sistemas</p>
        <p class="edu-sub">Universitario Rumiñahui · Ecuador</p>
        <p class="edu-date">feb. 2015 — dic. 2019</p>
      </div>
    </div>
  </div>
</section>

<hr class="sep"/>

<!-- CONTACT -->
<section id="contact">
  <div class="reveal">
    <p class="section-label">06 — Contacto</p>
    <h2 class="section-title">Hablemos</h2>
    <div class="section-line"></div>
  </div>
  <div class="contact-inner reveal">
    <div>
      <div class="contact-text">
        <p>
          ¿Tienes un proyecto interesante, una oportunidad o simplemente quieres hablar de tecnología, restauración o arquitectura de software? Escríbeme.
        </p>
      </div>
      <div class="contact-links">
        <a href="mailto:jeisoncaguana@gmail.com" class="contact-link">
          <span class="contact-link-icon">✉️</span>
          <div>
            <span class="contact-link-label">Email</span>
            <span class="contact-link-value">jeisoncaguana@gmail.com</span>
          </div>
        </a>
        <a href="https://linkedin.com/in/jeisoncaguana" target="_blank" class="contact-link">
          <span class="contact-link-icon">💼</span>
          <div>
            <span class="contact-link-label">LinkedIn</span>
            <span class="contact-link-value">linkedin.com/in/jeisoncaguana</span>
          </div>
        </a>
        <a href="https://github.com/jeisoncaguana" target="_blank" class="contact-link">
          <span class="contact-link-icon">🐙</span>
          <div>
            <span class="contact-link-label">GitHub</span>
            <span class="contact-link-value">github.com/jeisoncaguana</span>
          </div>
        </a>
        <a href="https://jeisoncaguana.com" target="_blank" class="contact-link">
          <span class="contact-link-icon">🌐</span>
          <div>
            <span class="contact-link-label">Web</span>
            <span class="contact-link-value">jeisoncaguana.com</span>
          </div>
        </a>
      </div>
    </div>
    <div class="contact-form">
      <div class="form-group">
        <label class="form-label">Nombre</label>
        <input type="text" class="form-input" placeholder="Tu nombre"/>
      </div>
      <div class="form-group">
        <label class="form-label">Email</label>
        <input type="email" class="form-input" placeholder="tu@email.com"/>
      </div>
      <div class="form-group">
        <label class="form-label">Mensaje</label>
        <textarea class="form-textarea" placeholder="Cuéntame sobre tu proyecto o propuesta..."></textarea>
      </div>
      <button class="btn-primary" style="width:100%; text-align:center;">Enviar mensaje</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<hr class="sep"/>
<footer>
  <p class="footer-copy">© 2026 <span>Jeison Caguana</span> — Hecho con código y café ☕</p>
  <div class="footer-links">
    <a href="https://linkedin.com/in/jeisoncaguana" target="_blank">LinkedIn</a>
    <a href="https://github.com/jeisoncaguana" target="_blank">GitHub</a>
    <a href="mailto:jeisoncaguana@gmail.com">Email</a>
  </div>
</footer>

<script>
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }
  });
}, { threshold: 0.08 });
reveals.forEach(r => observer.observe(r));
</script>
</body>
</html>
