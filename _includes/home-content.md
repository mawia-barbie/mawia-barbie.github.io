<!-- FUTURISTIC CYBERPUNK HOMEPAGE -->
<div class="home-viewport" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding-top:48px; padding-bottom:80px; position:relative;">
  <div class="home-inner" style="width:100%; max-width:1180px; padding:36px;">

    <!-- HERO -->
    <header class="hero" style="text-align:center; position:relative; padding:48px 18px 36px;">
      <div class="hero-bg" aria-hidden="true"></div>

      <h1 class="hero-name" style="font-size:3.2rem; line-height:1.05; margin:0 0 10px;">
        Grace Mawia
      </h1>

      <p class="hero-roles" style="margin:0 0 14px; font-weight:600;">
        SOC Analyst • Digital Forensics • Threat Intelligence • CTF Competitor
      </p>

      <p class="hero-tagline" style="max-width:880px; margin:0 auto 18px; font-size:1.05rem;">
        Passionate about investigating threats, analyzing security incidents, and strengthening cyber defenses through practical hands-on experience.
      </p>

      <div style="display:flex; gap:14px; justify-content:center; margin-top:18px;">
        <a id="view-projects-cta" class="cta-btn primary" href="/categories/">View Projects</a>
        <a class="cta-btn" href="/about/">Contact Me</a>
      </div>

      <div class="term-accent" aria-hidden="true" style="margin-top:22px; opacity:0.08; font-family:'Share Tech Mono', monospace; color:var(--neon-pink);">
        $ sudo tail -f /var/log/security.log
      </div>
    </header>

    <!-- FEATURED PROJECTS -->
    <section id="projects" class="featured-projects" style="margin-top:28px;">
      <h2 style="color:var(--neon-pink); margin:0 0 12px; text-align:left;">
        Featured Projects
      </h2>

      <p style="color:var(--muted); margin:0 0 18px; text-align:left;">
        Selected investigations, research and practical security work.
      </p>

      <div class="project-grid" style="display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:20px;">

        <!-- HTB Room: Meow -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Meow — Starting Point (HTB)</h3>

            <p class="project-desc">Introduced basic network enumeration and remote access concepts. Identified open services with Nmap and connected using Telnet to obtain the user flag. Reinforced securing exposed services.</p>

            <p class="project-skills">Skills: Telnet · Nmap · Service Enumeration · Linux Fundamentals</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Fawn -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Fawn — Starting Point (HTB)</h3>

            <p class="project-desc">Explored FTP and anonymous authentication; enumerated accessible files and retrieved sensitive information from a misconfigured FTP service. Demonstrated how insecure file-sharing leads to information disclosure.</p>

            <p class="project-skills">Skills: FTP · Anonymous Login · Enumeration · Information Gathering</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Dancing -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Dancing — Starting Point (HTB)</h3>

            <p class="project-desc">Investigated SMB network shares, enumerated available shares and accessed exposed files. Used SMB tools to navigate remote directories and retrieve flags, gaining hands-on experience with Windows file-sharing services.</p>

            <p class="project-skills">Skills: SMB Enumeration · Windows Networking · SMBclient · Share Discovery</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Redeemer -->
        <article class="project-card coming-soon">
          <div class="project-inner">
            <div class="coming-badge">Redeemer</div>

            <h3 class="project-title">Redeemer — Starting Point (HTB)</h3>

            <p class="project-desc">Worked with a Redis in-memory database service: connected to an exposed Redis instance, enumerated stored data and extracted information. Learned risks of publicly accessible database services.</p>

            <p class="project-skills">Skills: Redis · Database Enumeration · Service Discovery · Information Extraction</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Appointment -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Appointment — Starting Point (HTB)</h3>

            <p class="project-desc">Assessed a web application's authentication mechanism and exploited a SQL Injection in the login form to bypass controls. Gained access to restricted functionality and learned the impact of improper input validation.</p>

            <p class="project-skills">Skills: SQL Injection · Web Security Testing · Authentication Bypass · Input Validation</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Sequel -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Sequel — Starting Point (HTB)</h3>

            <p class="project-desc">Enumerated a vulnerable MySQL service, identified a misconfiguration allowing unauthenticated access, and executed SQL queries to explore the database and retrieve the flag. Practiced database enumeration and SQL usage.</p>

            <p class="project-skills">Skills: MySQL · SQL · Database Enumeration · Information Gathering · Linux</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

        <!-- HTB Room: Crocodile -->
        <article class="project-card">
          <div class="project-inner">
            <h3 class="project-title">Crocodile — Starting Point (HTB)</h3>

            <p class="project-desc">Enumerated a misconfigured FTP service allowing anonymous login, discovered sensitive files with cleartext credentials, performed web enumeration and directory fuzzing to find an admin login, and used discovered credentials to gain access.</p>

            <p class="project-skills">Skills: FTP Enumeration · Anonymous FTP · Credential Discovery · Directory Fuzzing · Gobuster · Web Enumeration · Authentication Testing</p>

            <div style="display:flex; gap:10px; margin-top:14px; align-items:center;">
              <a class="ghost-btn muted" href="#" aria-disabled="true">Writeup (coming)</a>
            </div>
          </div>
        </article>

      </div>
    </section>

  </div>
</div>

<style>
:root {
  --neon-pink: var(--neon-pink, #f5a9c5);
  --neon-blue: var(--neon-blue, #22d3ee);
  --muted: var(--muted, #8b949e);
}

/* Ensure all text inside the home content uses the neon pink by default */
.home-inner { color: var(--neon-pink) !important; }

.home-viewport {
  background:
    radial-gradient(circle at 10% 10%, rgba(139,92,246,0.03), transparent 6%),
    radial-gradient(circle at 90% 90%, rgba(245,169,197,0.03), transparent 12%),
    linear-gradient(180deg,#07070b, var(--bg-dark));
}

/* Hero */
.hero {
  /* Use the neon pink for primary hero text so it matches About */
  color: var(--neon-pink);
}

.hero-bg {
  position:absolute;
  inset:0;
  border-radius:14px;
  pointer-events:none;
  opacity:0.03;
  background: repeating-linear-gradient(
    45deg,
    rgba(255,255,255,0.01) 0 1px,
    transparent 1px 12px
  );
  mix-blend-mode:overlay;
}

.hero-name {
  color:var(--neon-pink);
  font-weight:800;
  text-shadow:0 6px 30px rgba(245,169,197,0.08);
}

.cta-btn {
  display:inline-block !important;
  padding:10px 16px;
  border-radius:8px;
  border:1px solid rgba(245,169,197,0.08);
  color:var(--neon-pink) !important;
  text-decoration:none !important;
  background:transparent !important;
  box-shadow:0 8px 30px rgba(245,169,197,0.03) !important;
  transition:transform 180ms, box-shadow 180ms;
  opacity:1 !important;
  visibility:visible !important;
  z-index:80 !important;
}

#view-projects-cta { position:relative; z-index:90 !important; }

.cta-btn.primary {
  background:linear-gradient(
    90deg,
    rgba(245,169,197,0.06),
    rgba(139,92,246,0.04)
  );
}

.cta-btn:hover {
  transform:translateY(-4px);
  box-shadow:0 18px 50px rgba(245,169,197,0.1);
}

.term-accent {
  font-size:0.95rem;
}

/* Projects */
.project-card {
  position:relative; border-radius:12px; background:linear-gradient(
    180deg,
    rgba(255,255,255,0.02),
    rgba(255,255,255,0.01)
  );
  padding:18px;
  color:var(--neon-pink);
  border:1px solid rgba(245,169,197,0.04);
  box-shadow:0 8px 36px rgba(11,15,25,0.6);
  backdrop-filter:blur(8px) saturate(120%);
  transition:
    transform 260ms cubic-bezier(.2,.9,.2,1),
    box-shadow 260ms,
    border-color 260ms;
  overflow:hidden;
}

.project-card:hover {
  transform:translateY(-8px);
  box-shadow:0 26px 80px rgba(245,169,197,0.12);
  border-color:rgba(245,169,197,0.14);
}

.project-card .project-title {
  margin:0 0 8px;
  color:var(--neon-pink);
  font-size:1.05rem;
}

.project-desc {
  color:var(--neon-pink);
  margin:0 0 10px;
}

.project-skills {
  color:var(--neon-blue);
  font-size:0.92rem;
  margin:0;
}

.project-inner {
  position:relative;
  z-index:2;
}

.coming-badge {
  display:inline-block;
  padding:6px 10px;
  font-size:0.8rem;
  color:#0b0f19;
  background:var(--neon-pink);
  border-radius:999px;
  font-weight:700;
  margin-bottom:8px;
}

.ghost-btn {
  display:inline-block;
  padding:8px 12px;
  border-radius:8px;
  background:transparent;
  border:1px solid rgba(139,92,246,0.06);
  color:var(--neon-pink);
  text-decoration:none;
  transition:transform 160ms, box-shadow 160ms;
}

.ghost-btn:hover {
  transform:translateY(-4px);
  box-shadow:0 14px 40px rgba(139,92,246,0.08);
}

.ghost-btn.muted {
  opacity:0.32;
  pointer-events:none;
}

.project-card::after {
  content:'';
  position:absolute;
  inset:0;
  background:
    linear-gradient(
      90deg,
      rgba(255,255,255,0.002),
      transparent 1px
    );
  pointer-events:none;
  mix-blend-mode:overlay;
}

@media (max-width:820px) {
  .hero-name {
    font-size:1.8rem;
  }

  .project-card {
    padding:14px;
  }

  .home-inner {
    padding:18px;
  }
}

/* Force home content text to use the same neon-pink as the About page */
.home-inner, .home-inner *:not(.coming-badge) {
  color: var(--neon-pink) !important;
}

/* Keep badges and small UI accents as designed */
.coming-badge { color: #0b0f19 !important; }
</style>
