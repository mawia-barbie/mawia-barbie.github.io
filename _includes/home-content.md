<!-- REVAMPED PORTFOLIO: MAUVE TERMINAL THEME -->
{% assign default_password = "hunt2025" %}
<div class="portfolio-root">
  <div class="container-terminal">

    <!-- ─── HERO: NAME + ROLES ─── -->
    <section class="hero-section" id="hero">
      <div class="hero-frame">
        <div class="hero-glow-orb hero-glow-orb--1" aria-hidden="true"></div>
        <div class="hero-glow-orb hero-glow-orb--2" aria-hidden="true"></div>
        <div class="hero-identity">
          <div class="hero-glitch-wrapper">
            <h1 class="hero-name" data-text="Grace Mawia">Grace Mawia</h1>
          </div>
          <div class="hero-status">
            <span class="hero-status-dot"></span>
            <span class="hero-status-text">Available for Opportunities</span>
          </div>
          <div class="hero-divider"><span></span><span class="hero-divider-dot"></span><span></span></div>
          <div class="hero-roles">
            <span class="hero-role-badge soc"><span class="hero-badge-icon">◈</span> SOC Analyst</span>
            <span class="hero-role-badge ctf"><span class="hero-badge-icon">◈</span> CTF Player</span>
            <span class="hero-role-badge dfir"><span class="hero-badge-icon">◈</span> DFIR Specialist</span>
          </div>
          <p class="hero-tagline">"Hunt threats. Analyze evidence. Defend forward."</p>
          <p class="hero-sub-summary">
            Focused on SOC operations, digital forensics, and threat detection.<br>
            Driven by curiosity, hands-on learning, and a passion for solving complex security challenges.
          </p>
          <div class="hero-cta-row">
            <a href="/categories/" class="hero-cta"><span class="hero-cta-arrow">→</span> View Projects</a>
            <a href="/about/" class="hero-cta hero-cta--ghost">About Me</a>
          </div>
        </div>
      </div>
    </section>

    <!-- ─── HTB ROOMS (directly below name) ─── -->
    <section class="section-block" id="htb-rooms">
      <div class="section-header">
        <span class="section-badge">// hack_the_box</span>
        <h2>HTB_Pwned.sys</h2>
      </div>
      <div class="htb-grid">

        <!-- Meow - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Meow</h4>
          <div class="htb-tags">
            <span>Telnet</span><span>Nmap</span><span>Enumeration</span>
          </div>
          <p>Basic network enumeration and remote access via Telnet to obtain the flag.</p>
        </div>

        <!-- Fawn - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Fawn</h4>
          <div class="htb-tags">
            <span>FTP</span><span>Anonymous</span><span>Enumeration</span>
          </div>
          <p>FTP anonymous authentication and information disclosure via misconfigured file sharing.</p>
        </div>

        <!-- Dancing - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Dancing</h4>
          <div class="htb-tags">
            <span>SMB</span><span>Windows</span><span>Share Discovery</span>
          </div>
          <p>SMB share enumeration and remote directory navigation to retrieve exposed data.</p>
        </div>

        <!-- Redeemer - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Redeemer</h4>
          <div class="htb-tags">
            <span>Redis</span><span>Database</span><span>Enumeration</span>
          </div>
          <p>Connected to an exposed Redis instance and extracted sensitive stored data.</p>
        </div>

        <!-- Appointment - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Appointment</h4>
          <div class="htb-tags">
            <span>SQLi</span><span>Web</span><span>Auth Bypass</span>
          </div>
          <p>SQL Injection in login form to bypass authentication and access restricted functionality.</p>
        </div>

        <!-- Sequel - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Sequel</h4>
          <div class="htb-tags">
            <span>MySQL</span><span>SQL</span><span>Enumeration</span>
          </div>
          <p>MySQL misconfiguration allowing unauthenticated database enumeration and flag retrieval.</p>
        </div>

        <!-- Crocodile - Released -->
        <div class="htb-card released">
          <div class="htb-card-head">
            <span class="htb-diff easy">Easy</span>
            <span class="htb-status released-label">Released</span>
          </div>
          <h4>Crocodile</h4>
          <div class="htb-tags">
            <span>FTP</span><span>Gobuster</span><span>Web</span>
          </div>
          <p>FTP anonymous login, credential discovery, directory fuzzing, and admin panel access.</p>
        </div>



      </div>
    </section>

    <!-- moved to about page -->

    <!-- ─── FOOTER ─── -->
    <footer class="portfolio-footer">
      <div class="footer-glow" aria-hidden="true"></div>
      <div class="footer-inner">
        <div class="footer-main">
          <span class="footer-copy"><span class="footer-prompt">❯</span> © 2025 Grace Mawia <span class="footer-sep">//</span> <span class="footer-highlight">CYBER_SENTINEL</span></span>
          <span class="footer-quote">"The only truly secure system is one that is powered off — and even then I have my doubts."</span>
        </div>
        <nav class="footer-nav">
          <a href="#" class="footer-link"><span class="footer-link-arrow">~</span> GitHub</a>
          <a href="#" class="footer-link"><span class="footer-link-arrow">~</span> LinkedIn</a>
          <a href="#" class="footer-link"><span class="footer-link-arrow">~</span> TryHackMe</a>
          <a href="#" class="footer-link"><span class="footer-link-arrow">~</span> HackTheBox</a>
        </nav>
      </div>
    </footer>

  </div>
</div>

<!-- ─── PASSWORD MODAL ─── -->
<div class="password-overlay" id="password-overlay" role="dialog" aria-modal="true" aria-label="Enter password to unlock writeup">
  <div class="password-modal">
    <div class="password-modal-header">
      <span class="material-symbols-outlined" aria-hidden="true">lock</span>
      <span>Restricted Writeup</span>
    </div>
    <p class="password-desc">This room is still active on HTB. Enter the shared password to access the writeup.</p>
    <div class="password-input-group">
      <label for="password-input" class="sr-only">Password</label>
      <input type="password" id="password-input" placeholder="Enter password..." autocomplete="off" />
      <button id="password-submit">Unlock</button>
    </div>
    <p class="password-error" id="password-error" role="alert">Incorrect password. Try again.</p>
    <button class="password-close" id="password-close">Cancel</button>
  </div>
</div>

<!-- ─── PASSWORD UNLOCK MODAL CONTENT (hidden, shown when unlocked) ─── -->
<div class="writeup-reveal" id="writeup-reveal" role="dialog" aria-modal="true" aria-label="Writeup unlocked">
  <div class="writeup-reveal-inner">
    <span class="material-symbols-outlined" style="color:var(--mauve);font-size:32px;" aria-hidden="true">lock_open</span>
    <h3>Writeup Unlocked</h3>
    <p id="writeup-reveal-text">You now have access to this writeup. Please don't share it publicly while the room is active.</p>
    <a href="#" id="writeup-reveal-link" class="writeup-link">Read Writeup →</a>
    <button class="writeup-close-btn" id="writeup-close-btn">Close</button>
  </div>
</div>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&family=JetBrains+Mono:wght@400;500;700&display=swap');

.portfolio-root {
  width: 100%;
  min-height: 100vh;
  background:
    radial-gradient(circle at 10% 10%, rgba(201,160,220,0.03), transparent 6%),
    radial-gradient(circle at 90% 90%, rgba(201,160,220,0.03), transparent 12%),
    linear-gradient(180deg, #07060b, var(--bg-dark, #0f0d1a));
}

.container-terminal {
  width: 100%;
  max-width: 1180px;
  margin: 0 auto;
  padding: 80px 36px 40px;
}

/* ── Hero Section ── */
.hero-section {
  margin-bottom: 48px;
}

.hero-frame {
  position: relative;
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 16px;
  padding: 48px 40px 40px;
  background:
    radial-gradient(ellipse at 30% 0%, rgba(201,160,220,0.06), transparent 60%),
    radial-gradient(ellipse at 70% 100%, rgba(34,211,238,0.03), transparent 50%),
    rgba(201, 160, 220, 0.02);
  overflow: hidden;
  animation: heroFramePulse 6s ease-in-out infinite;
}

@keyframes heroFramePulse {
  0%, 100% { border-color: rgba(201, 160, 220, 0.12); }
  50% { border-color: rgba(201, 160, 220, 0.25); }
}

.hero-glow-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  pointer-events: none;
  opacity: 0.5;
}
.hero-glow-orb--1 {
  width: 300px; height: 300px;
  top: -100px; left: -60px;
  background: radial-gradient(circle, rgba(201,160,220,0.15), transparent 70%);
  animation: orbFloat1 8s ease-in-out infinite;
}
.hero-glow-orb--2 {
  width: 250px; height: 250px;
  bottom: -80px; right: -40px;
  background: radial-gradient(circle, rgba(34,211,238,0.1), transparent 70%);
  animation: orbFloat2 10s ease-in-out infinite;
}

@keyframes orbFloat1 {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(20px, 15px); }
}
@keyframes orbFloat2 {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(-15px, -20px); }
}

.hero-identity {
  text-align: center;
  position: relative;
  z-index: 2;
}

/* Status pill */
.hero-status {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
  padding: 6px 18px;
  border-radius: 100px;
  border: 1px solid rgba(39, 201, 63, 0.2);
  background: rgba(39, 201, 63, 0.05);
  margin: 16px auto 0;
  width: fit-content;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #27c93f;
  letter-spacing: 1.5px;
  text-transform: uppercase;
}
.hero-status-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #27c93f;
  animation: statusPulse 2s ease-in-out infinite;
  box-shadow: 0 0 8px rgba(39, 201, 63, 0.5);
}
@keyframes statusPulse {
  0%, 100% { opacity: 1; box-shadow: 0 0 8px rgba(39, 201, 63, 0.5); }
  50% { opacity: 0.4; box-shadow: 0 0 2px rgba(39, 201, 63, 0.2); }
}
.hero-status-text {
  font-weight: 500;
}

/* Glitch name */
.hero-glitch-wrapper {
  position: relative;
  display: inline-block;
}

.hero-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 4.2rem;
  font-weight: 800;
  color: var(--mauve-light, #e6c8f0);
  margin: 0;
  letter-spacing: 6px;
  text-transform: uppercase;
  text-shadow:
    0 0 10px rgba(201, 160, 220, 0.5),
    0 0 30px rgba(201, 160, 220, 0.3),
    0 0 80px rgba(201, 160, 220, 0.15),
    0 0 120px rgba(201, 160, 220, 0.05);
  position: relative;
}

.hero-name::before,
.hero-name::after {
  content: attr(data-text);
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  opacity: 0;
}
.hero-name::before {
  color: #22d3ee;
  clip-path: inset(20% 0 60% 0);
}
.hero-name::after {
  color: #ff5f56;
  clip-path: inset(60% 0 10% 0);
}

@media (prefers-reduced-motion: no-preference) {
  .hero-name {
    animation: heroGlitch 4s infinite;
  }
  .hero-name::before {
    animation: heroGlitchShift 3s infinite;
  }
  .hero-name::after {
    animation: heroGlitchShift 2.5s infinite reverse;
  }
}

@keyframes heroGlitch {
  0%, 90%, 100% { transform: translate(0); }
  91% { transform: translate(-2px, 1px); }
  92% { transform: translate(2px, -1px); }
  93% { transform: translate(-1px, 2px); }
  94% { transform: translate(0); }
}
@keyframes heroGlitchShift {
  0%, 7%, 100% { opacity: 0; }
  4% { opacity: 0.6; }
  5% { opacity: 0.3; }
  6% { opacity: 0.7; }
}

/* Role title */
.hero-role-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 15px;
  font-weight: 500;
  color: rgba(196, 176, 204, 0.6);
  margin: 8px 0 0;
  letter-spacing: 4px;
  text-transform: uppercase;
}

/* Divider */
.hero-divider {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin: 20px 0;
}
.hero-divider span:first-child,
.hero-divider span:last-child {
  width: 60px;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(201,160,220,0.3), transparent);
}
.hero-divider-dot {
  width: 5px; height: 5px;
  border-radius: 50%;
  background: var(--mauve);
  opacity: 0.5;
}

/* Role badges */
.hero-roles {
  display: flex;
  justify-content: center;
  gap: 14px;
  margin-top: 0;
  flex-wrap: wrap;
}

.hero-role-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  padding: 8px 20px;
  border-radius: 8px;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  font-weight: 600;
  transition: all 0.3s ease;
  cursor: default;
}
.hero-badge-icon {
  font-size: 10px;
  opacity: 0.7;
}

.hero-role-badge.soc {
  color: #22d3ee;
  border: 1px solid rgba(34, 211, 238, 0.25);
  background: rgba(34, 211, 238, 0.06);
  box-shadow: 0 0 20px rgba(34, 211, 238, 0.05);
}
.hero-role-badge.soc:hover {
  background: rgba(34, 211, 238, 0.12);
  border-color: rgba(34, 211, 238, 0.5);
  box-shadow: 0 0 30px rgba(34, 211, 238, 0.12);
  transform: translateY(-3px);
}

.hero-role-badge.ctf {
  color: #27c93f;
  border: 1px solid rgba(39, 201, 63, 0.25);
  background: rgba(39, 201, 63, 0.06);
  box-shadow: 0 0 20px rgba(39, 201, 63, 0.05);
}
.hero-role-badge.ctf:hover {
  background: rgba(39, 201, 63, 0.12);
  border-color: rgba(39, 201, 63, 0.5);
  box-shadow: 0 0 30px rgba(39, 201, 63, 0.12);
  transform: translateY(-3px);
}

.hero-role-badge.dfir {
  color: var(--mauve, #c9a0dc);
  border: 1px solid rgba(201, 160, 220, 0.25);
  background: rgba(201, 160, 220, 0.06);
  box-shadow: 0 0 20px rgba(201, 160, 220, 0.05);
}
.hero-role-badge.dfir:hover {
  background: rgba(201, 160, 220, 0.12);
  border-color: rgba(201, 160, 220, 0.5);
  box-shadow: 0 0 30px rgba(201, 160, 220, 0.12);
  transform: translateY(-3px);
}

.hero-tagline {
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  color: rgba(196, 176, 204, 0.6);
  margin-top: 24px;
  font-style: italic;
  letter-spacing: 0.5px;
}

.hero-sub-summary {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  font-size: 15px;
  line-height: 1.8;
  color: rgba(196, 176, 204, 0.7);
  margin: 20px auto 0;
  max-width: 560px;
  text-align: center;
}

/* CTA buttons */
.hero-cta-row {
  display: flex;
  justify-content: center;
  gap: 14px;
  margin-top: 28px;
}
.hero-cta {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  font-weight: 600;
  padding: 12px 28px;
  border-radius: 8px;
  text-decoration: none !important;
  letter-spacing: 1px;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
.hero-cta-arrow {
  transition: transform 0.3s ease;
}
.hero-cta:hover .hero-cta-arrow {
  transform: translateX(4px);
}

/* Primary CTA */
.hero-cta:not(.hero-cta--ghost) {
  color: #0d0b14 !important;
  background: linear-gradient(135deg, var(--mauve), var(--mauve-light));
  border: 1px solid var(--mauve);
  box-shadow: 0 0 24px rgba(201, 160, 220, 0.2), 0 4px 16px rgba(201, 160, 220, 0.15);
}
.hero-cta:not(.hero-cta--ghost):hover {
  box-shadow: 0 0 40px rgba(201, 160, 220, 0.35), 0 8px 32px rgba(201, 160, 220, 0.2);
  transform: translateY(-3px);
}

/* Ghost CTA */
.hero-cta--ghost {
  color: var(--mauve) !important;
  background: transparent;
  border: 1px solid rgba(201, 160, 220, 0.25);
}
.hero-cta--ghost:hover {
  background: rgba(201, 160, 220, 0.08);
  border-color: rgba(201, 160, 220, 0.5);
  box-shadow: 0 0 24px rgba(201, 160, 220, 0.1);
  transform: translateY(-3px);
}

/* ── Section Block ── */
.section-block {
  margin-bottom: 60px;
}

.section-header {
  margin-bottom: 28px;
}
.section-badge {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(201, 160, 220, 0.3);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.section-header h2 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.6rem;
  font-weight: 700;
  color: var(--mauve-light) !important;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 2px;
  border-left: 3px solid var(--mauve);
  padding-left: 16px;
}

/* ── HTB Cards ── */
.htb-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 18px;
}

.htb-card {
  background: rgba(201, 160, 220, 0.02);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 10px;
  padding: 20px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}
.htb-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 3px;
  height: 100%;
  background: var(--mauve);
  opacity: 0.3;
  transition: opacity 0.3s;
}
.htb-card:hover::before { opacity: 0.8; }
.htb-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 48px rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
}

.htb-card-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.htb-diff {
  padding: 2px 8px;
  border-radius: 4px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 1px;
  border: 1px solid;
}
.htb-diff.easy {
  color: #27c93f;
  border-color: rgba(39, 201, 63, 0.3);
  background: rgba(39, 201, 63, 0.06);
}

.htb-status {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.htb-status.released-label { color: rgba(39, 201, 63, 0.6); }
.htb-status.locked-label { color: #ffbd2e; }

.htb-card h4 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.1rem;
  color: var(--mauve-light) !important;
  margin: 0 0 10px 0;
}

.htb-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  margin-bottom: 10px;
}
.htb-tags span {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  padding: 2px 7px;
  border-radius: 4px;
  background: rgba(201, 160, 220, 0.05);
  border: 1px solid rgba(201, 160, 220, 0.08);
  color: rgba(196, 176, 204, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.htb-card p {
  font-size: 13px;
  color: var(--muted);
  margin: 0 0 14px 0;
  line-height: 1.5;
}

.htb-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--mauve) !important;
  text-decoration: none !important;
  transition: all 0.2s;
}
.htb-link:hover {
  color: var(--mauve-light) !important;
  padding-left: 4px;
}

.htb-unlock-btn {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  padding: 8px 14px;
  border-radius: 6px;
  border: 1px solid rgba(255, 189, 46, 0.2);
  background: rgba(255, 189, 46, 0.04);
  color: #ffbd2e;
  cursor: pointer;
  transition: all 0.2s ease;
  letter-spacing: 0.5px;
}
.htb-unlock-btn:hover {
  background: rgba(255, 189, 46, 0.1);
  border-color: rgba(255, 189, 46, 0.4);
  box-shadow: 0 0 20px rgba(255, 189, 46, 0.06);
}

.htb-card.locked {
  border-color: rgba(255, 189, 46, 0.08);
}
.htb-card.locked::before {
  background: #ffbd2e;
}

/* ── Footer ── */
.portfolio-footer {
  margin-top: 60px;
  padding: 40px 0 24px;
  border-top: 1px solid rgba(201, 160, 220, 0.08);
  position: relative;
  overflow: hidden;
}

.footer-glow {
  position: absolute;
  top: -60px;
  left: 50%;
  transform: translateX(-50%);
  width: 80%;
  max-width: 600px;
  height: 120px;
  background: radial-gradient(ellipse, rgba(201, 160, 220, 0.04), transparent 70%);
  pointer-events: none;
}

.footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 20px;
  position: relative;
  z-index: 2;
}

.footer-main {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.footer-copy {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--muted, #c4b0cc);
  letter-spacing: 0.5px;
}

.footer-prompt {
  color: var(--mauve, #c9a0dc);
  margin-right: 4px;
}

.footer-sep {
  color: rgba(196, 176, 204, 0.25);
  margin: 0 4px;
}

.footer-highlight {
  color: var(--mauve-light, #e6c8f0);
  font-weight: 600;
}

.footer-quote {
  font-size: 12px;
  font-style: italic;
  color: rgba(196, 176, 204, 0.35);
  max-width: 420px;
  line-height: 1.5;
}

.footer-nav {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.footer-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.5) !important;
  text-decoration: none !important;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  padding: 6px 14px;
  border-radius: 6px;
  border: 1px solid rgba(201, 160, 220, 0.06);
  background: rgba(201, 160, 220, 0.02);
  transition: all 0.25s ease;
}

.footer-link:hover {
  color: var(--mauve-light, #e6c8f0) !important;
  background: rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(201, 160, 220, 0.06);
  letter-spacing: 2px;
}

.footer-link-arrow {
  color: var(--mauve, #c9a0dc);
  margin-right: 3px;
  opacity: 0.6;
}

.footer-link:hover .footer-link-arrow {
  opacity: 1;
}

/* ── Password Modal ── */
.password-overlay {
  position: fixed;
  inset: 0;
  z-index: 9000;
  background: rgba(7, 6, 11, 0.85);
  backdrop-filter: blur(8px);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}
.password-overlay.active {
  opacity: 1;
  visibility: visible;
}

.password-modal {
  background: #13101a;
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 12px;
  padding: 32px;
  width: min(400px, 90vw);
  box-shadow: 0 0 60px rgba(201, 160, 220, 0.06);
  text-align: center;
}

.password-modal-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  color: #ffbd2e;
  margin-bottom: 12px;
}
.password-modal-header span:first-child { font-size: 20px !important; }

.password-desc {
  font-size: 13px;
  color: rgba(196, 176, 204, 0.6);
  margin-bottom: 20px;
  line-height: 1.5;
}

.password-input-group {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
}
.password-input-group input {
  flex: 1;
  background: rgba(201, 160, 220, 0.04);
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 6px;
  padding: 10px 14px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: #e6e1e5;
  outline: none;
  transition: border-color 0.2s;
}
.password-input-group input:focus {
  border-color: rgba(201, 160, 220, 0.3);
}
.password-input-group input::placeholder {
  color: rgba(196, 176, 204, 0.3);
}
.password-input-group button {
  padding: 10px 18px;
  border-radius: 6px;
  border: 1px solid rgba(201, 160, 220, 0.15);
  background: rgba(201, 160, 220, 0.06);
  color: var(--mauve);
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  cursor: pointer;
  transition: all 0.2s;
}
.password-input-group button:hover {
  background: rgba(201, 160, 220, 0.12);
  border-color: rgba(201, 160, 220, 0.3);
}

.password-error {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #ff5f56;
  display: none;
  margin: 8px 0;
}
.password-error.show { display: block; }

.password-close {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  background: none;
  border: none;
  cursor: pointer;
  margin-top: 8px;
  transition: color 0.2s;
}
.password-close:hover { color: var(--muted); }

/* ── Writeup Reveal Modal ── */
.writeup-reveal {
  position: fixed;
  inset: 0;
  z-index: 9001;
  background: rgba(7, 6, 11, 0.85);
  backdrop-filter: blur(8px);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}
.writeup-reveal.active {
  opacity: 1;
  visibility: visible;
}

.writeup-reveal-inner {
  background: #13101a;
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 12px;
  padding: 36px;
  width: min(400px, 90vw);
  box-shadow: 0 0 60px rgba(201, 160, 220, 0.06);
  text-align: center;
}
.writeup-reveal-inner h3 {
  font-family: 'JetBrains Mono', monospace;
  color: var(--mauve-light) !important;
  margin: 12px 0 8px;
  font-size: 1.1rem;
}
.writeup-reveal-inner p {
  font-size: 13px;
  color: rgba(196, 176, 204, 0.6);
  margin-bottom: 20px;
  line-height: 1.5;
}

.writeup-link {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  padding: 10px 24px;
  border-radius: 6px;
  background: rgba(201, 160, 220, 0.08);
  border: 1px solid rgba(201, 160, 220, 0.15);
  color: var(--mauve) !important;
  text-decoration: none !important;
  transition: all 0.2s;
  margin-bottom: 12px;
}
.writeup-link:hover {
  background: rgba(201, 160, 220, 0.15);
  box-shadow: 0 0 24px rgba(201, 160, 220, 0.06);
}

.writeup-close-btn {
  display: block;
  width: 100%;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  background: none;
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 6px;
  padding: 8px;
  cursor: pointer;
  transition: all 0.2s;
}
.writeup-close-btn:hover {
  background: rgba(201, 160, 220, 0.04);
  color: var(--muted);
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  white-space: nowrap;
  border: 0;
}

/* ── Responsive ── */
@media (max-width: 820px) {
  .container-terminal { padding: 80px 16px 20px; }
  .hero-frame { padding: 36px 24px 32px; }
  .hero-name { font-size: 2.6rem; letter-spacing: 3px; }
  .hero-role-title { font-size: 13px; letter-spacing: 3px; }
  .hero-role-badge { font-size: 11px; padding: 7px 16px; }
  .hero-tagline { font-size: 12px; }
  .hero-sub-summary { font-size: 13px; }
  .hero-cta { font-size: 12px; padding: 10px 22px; }
  .section-header h2 { font-size: 1.2rem; }
  .footer-inner { flex-direction: column; text-align: center; align-items: center; }
  .footer-nav { justify-content: center; }
}

@media (max-width: 480px) {
  .hero-frame { padding: 28px 16px 24px; }
  .hero-name { font-size: 1.8rem; letter-spacing: 1px; }
  .hero-role-title { font-size: 11px; letter-spacing: 2px; }
  .hero-roles { gap: 8px; }
  .hero-role-badge { font-size: 9px; padding: 5px 12px; letter-spacing: 1px; }
  .hero-cta-row { flex-direction: column; align-items: center; gap: 10px; }
  .hero-cta { width: 100%; max-width: 240px; justify-content: center; }
  .hero-status { font-size: 10px; padding: 5px 14px; }
}
</style>

<script>
(function() {
  'use strict';

  const DEFAULT_PASSWORD = '{{ default_password }}';

  // ── Password Protection ──
  const passwordOverlay = document.getElementById('password-overlay');
  const passwordInput = document.getElementById('password-input');
  const passwordSubmit = document.getElementById('password-submit');
  const passwordError = document.getElementById('password-error');
  const passwordClose = document.getElementById('password-close');
  const writeupReveal = document.getElementById('writeup-reveal');
  const writeupCloseBtn = document.getElementById('writeup-close-btn');

  let currentRoom = '';

  // Unlock buttons
  document.querySelectorAll('.htb-unlock-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      currentRoom = btn.dataset.room || 'unknown';
      if (passwordOverlay) {
        passwordOverlay.classList.add('active');
        if (passwordInput) {
          passwordInput.value = '';
          passwordInput.focus();
        }
        if (passwordError) passwordError.classList.remove('show');
      }
    });
  });

  function checkPassword() {
    var entered = passwordInput ? passwordInput.value : '';
    if (entered === DEFAULT_PASSWORD) {
      if (passwordOverlay) passwordOverlay.classList.remove('active');
      if (passwordError) passwordError.classList.remove('show');
      if (writeupReveal) {
        writeupReveal.classList.add('active');
        var textEl = document.getElementById('writeup-reveal-text');
        if (textEl) {
          textEl.textContent = currentRoom.charAt(0).toUpperCase() + currentRoom.slice(1) + ' writeup unlocked! Please keep this confidential while the room is active on HTB.';
        }
        var linkEl = document.getElementById('writeup-reveal-link');
        if (linkEl) {
          linkEl.href = '/writeups/htb/' + currentRoom + '/';
        }
      }
    } else {
      if (passwordError) passwordError.classList.add('show');
      if (passwordInput) {
        passwordInput.value = '';
        passwordInput.focus();
      }
    }
  }

  if (passwordSubmit) {
    passwordSubmit.addEventListener('click', checkPassword);
  }
  if (passwordInput) {
    passwordInput.addEventListener('keydown', function(e) {
      if (e.key === 'Enter') checkPassword();
    });
  }
  if (passwordClose) {
    passwordClose.addEventListener('click', function() {
      if (passwordOverlay) passwordOverlay.classList.remove('active');
      if (passwordError) passwordError.classList.remove('show');
    });
  }
  if (writeupCloseBtn) {
    writeupCloseBtn.addEventListener('click', function() {
      if (writeupReveal) writeupReveal.classList.remove('active');
    });
  }

  if (passwordOverlay) {
    passwordOverlay.addEventListener('click', function(e) {
      if (e.target === passwordOverlay) {
        passwordOverlay.classList.remove('active');
        if (passwordError) passwordError.classList.remove('show');
      }
    });
  }
  if (writeupReveal) {
    writeupReveal.addEventListener('click', function(e) {
      if (e.target === writeupReveal) {
        writeupReveal.classList.remove('active');
      }
    });
  }

})();
</script>
