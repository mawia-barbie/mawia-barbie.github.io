---
title: About
icon: fas fa-user
order: 1
layout: home
---

<!-- Futuristic cyberpunk About section: three stacked glass cards, vertically centered -->
<div style="display:flex; align-items:center; justify-content:center; min-height:100vh; padding:36px 20px;">
  <div style="width:100%; max-width:980px; text-align:center;">

    <!-- Section 1: Introduction Card -->
    <section class="glass-card" aria-label="Introduction" style="margin-bottom:28px;">
      <div class="card-inner">
        <div class="digital-motif" aria-hidden="true">⚡</div>
        <h1 class="name">Grace Mawia</h1>
        <p class="roles">SOC Analyst • Digital Forensics • Threat Intelligence • CTF Player</p>
        <p class="location"> Based in Nairobi, Kenya</p>
      </div>
    </section>

    <!-- Section 2: Professional Summary Card -->
    <section class="glass-card large" aria-label="Professional Summary" style="margin-bottom:28px;">
      <div class="card-inner">
        <h2 class="card-title">Professional Summary</h2>
        <p class="summary">I am a Cybersecurity professional with a passion for Security Operations, Digital Forensics, and Threat Intelligence. Experienced in monitoring security events, investigating incidents, analyzing threats, and supporting defensive security operations. Dedicated to continuous learning through hands-on labs and Capture The Flag competitions. Passionate about understanding attacker methodologies, improving detection capabilities, and helping organizations strengthen their security posture against evolving cyber threats.</p>
      </div>
    </section>

    <!-- Section 3: Certifications -->
    <section class="glass-card" aria-label="Certifications" style="margin-bottom:20px;">
      <div class="card-inner">
        <h2 class="card-title">Certifications</h2>

        <div class="cert-grid">
          <article class="cert-card">
            <div class="cert-icon">🛡️</div>
            <div class="cert-body">
              <h3 class="cert-name">Digital Forensics and Incident Response</h3>
              <p class="cert-org">Cybersafe Foundation</p>
              <p class="cert-desc">Hands-on training in forensic analysis, evidence handling and incident response workflows.</p>
            </div>
          </article>

          <article class="cert-card">
            <div class="cert-icon">🌐</div>
            <div class="cert-body">
              <h3 class="cert-name">Cisco Ethical Hacker</h3>
              <p class="cert-org">Cisco</p>
              <p class="cert-desc">Training focused on penetration testing fundamentals, web vulnerabilities and defensive controls.</p>
            </div>
          </article>

          <!-- Add more certification cards here if needed -->

        </div>

      </div>
    </section>

    <!-- Contact area -->
    <div style="margin-top:18px; display:flex; justify-content:center; gap:12px;">
      <a class="contact-btn" href="https://www.linkedin.com/in/grace-mawia-9b8340269/" aria-label="LinkedIn">LinkedIn</a>
      <a class="contact-btn" href="https://github.com/mawia-barbie" aria-label="GitHub">GitHub</a>
      <a class="contact-btn" href="mailto:mawiag411@gmai.com" aria-label="Email">Email</a>
    </div>

  </div>
</div>

<style>
/* Use shared layout variables so About matches the rest of the site */

.glass-card {
  position:relative;
  background: rgba(11,15,25,0.65); /* darker glass to match HUD panels */
  border: 1px solid rgba(245,169,197,0.06);
  border-radius: 14px;
  padding: 26px;
  color: var(--muted);
  box-shadow: 0 8px 40px rgba(11,15,25,0.6);
  backdrop-filter: blur(10px) saturate(120%);
  overflow: hidden;
  transition: transform 260ms cubic-bezier(.2,.9,.2,1), box-shadow 260ms;
}

.glass-card.large { padding:34px; }
.glass-card:hover { transform: translateY(-6px); box-shadow: 0 18px 60px rgba(139,92,246,0.12); }

.card-inner { position:relative; z-index:2; }
.digital-motif { position:absolute; left:18px; top:18px; font-size:22px; opacity:0.06; filter:drop-shadow(0 0 8px rgba(139,92,246,0.06)); }

/* animated glowing border */
.glass-card::before {
  content:'';
  position:absolute; inset:-1px; border-radius:15px;
  background: linear-gradient(90deg, rgba(245,169,197,0.06), rgba(139,92,246,0.05), rgba(34,211,238,0.03));
  z-index:1; opacity:0; transform:scale(0.98);
  transition: opacity 360ms, transform 360ms;
}
.glass-card:hover::before { opacity:1; transform:scale(1); }

/* Typography and colors aligned with the site */
.name { font-size:2.05rem; margin:8px 0 8px 0; color:var(--neon-pink); text-shadow:0 0 26px rgba(245,169,197,0.18); }
.roles { color:var(--muted); margin:6px 0; }
.location { color:var(--neon-pink); margin:6px 0 0 0; }

.card-title { font-size:1.15rem; color:var(--neon-pink); margin-bottom:8px; }
.summary { color:var(--muted); line-height:1.5; text-align:left; max-width:860px; margin:0 auto; }

/* Certifications grid */
.cert-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:14px; margin-top:16px; }
.cert-card { display:flex; gap:12px; align-items:flex-start; padding:12px; border-radius:10px; background:rgba(11,15,25,0.5); border:1px solid rgba(245,169,197,0.04); box-shadow:0 6px 18px rgba(139,92,246,0.04); transition:transform 220ms, box-shadow 220ms, border-color 220ms; }
.cert-card:hover { transform:translateY(-6px); box-shadow:0 20px 50px rgba(245,169,197,0.08); border-color:rgba(245,169,197,0.18); }
.cert-icon { font-size:28px; width:44px; height:44px; display:flex; align-items:center; justify-content:center; border-radius:9px; background: linear-gradient(180deg, rgba(245,169,197,0.04), rgba(139,92,246,0.03)); color:var(--neon-pink); box-shadow: 0 6px 18px rgba(245,169,197,0.03); }
.cert-name { color:var(--neon-pink); margin:0 0 4px 0; font-weight:700; font-size:1rem; }
.cert-org { color:var(--neon-blue); font-size:0.9rem; margin:0 0 6px 0; }
.cert-desc { color:var(--muted); margin:0; font-size:0.92rem; }

/* Contact buttons */
.contact-btn { display:inline-block; padding:10px 14px; border-radius:8px; border:1px solid rgba(245,169,197,0.08); color:var(--neon-pink); background:transparent; text-decoration:none; box-shadow:0 8px 28px rgba(245,169,197,0.03); transition:transform 200ms, box-shadow 200ms; }
.contact-btn:hover { transform:translateY(-4px); box-shadow:0 18px 48px rgba(245,169,197,0.12); }

/* Make sure this page inherits layout fonts and spacing */
.site-viewport > :not(.top-nav) { font-family: inherit; }

/* Responsive tweaks */
@media (max-width:900px){ .glass-card { padding:18px; border-radius:12px; } .name { font-size:1.5rem; } .summary { text-align:left; padding:0 6px; } }

</style>