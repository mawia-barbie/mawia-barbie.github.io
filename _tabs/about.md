---
title: About
icon: fas fa-user
order: 1
layout: home
---

<div class="about-page-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="width:100%; max-width:980px;">

    <!-- ─── PROFESSIONAL SUMMARY (terminal style) ─── -->
    <section class="about-card" style="margin-bottom:28px;">
      <div class="about-card-inner">
        <div class="term-section-header">
          <span class="term-section-badge">// professional_summary</span>
          <h2>Summary.sys</h2>
        </div>

        <!-- Terminal-style identity output -->
        <div class="about-terminal-preview">
          <div class="about-term-line"><span class="mauve">┌──(grace㉿mawia)</span><span class="gray">-[~]</span></div>
          <div class="about-term-line"><span class="mauve">└─$</span> <span class="cmd">whoami</span></div>
          <div class="about-term-line"><span class="output">  → Grace Mawia</span></div>
          <div class="about-term-line"><span class="output">  → SOC Analyst &amp; DFIR Specialist</span></div>
          <div class="about-term-line"><span class="output">  → Threat Hunter &amp; CTF Competitor</span></div>
          <div class="about-term-line" style="margin-top:6px;"><span class="mauve">└─$</span> <span class="cmd">cat ~/mission.txt</span></div>
          <div class="about-term-line"><span class="output">  → "Hunt threats. Analyze evidence. Defend forward."</span></div>
        </div>

        <p class="about-text" style="margin-top:20px;">
          I'm Grace Mawia, a cybersecurity professional with a background in Computer Security and Forensics and a passion for protecting digital systems through security monitoring, incident response, and digital investigations.
        </p>

        <p class="about-text" style="margin-top:12px;">
          My interests span Security Operations (SOC), Digital Forensics, Threat Detection, and Ethical Hacking.
        </p>

        <div class="values-box">
          <div class="values-header">
            <span class="material-symbols-outlined values-icon">terminal</span>
            <span>Core Values:</span>
          </div>
          <ul>
            <li>Relentless Curiosity</li>
            <li>Technical Precision</li>
            <li>Continuous Skill-Pivoting</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- ─── CERTIFICATIONS ─── -->
    <section class="about-card" style="margin-bottom:28px;">
      <div class="about-card-inner">
        <div class="term-section-header">
          <span class="term-section-badge">// credentials</span>
          <h2>Credentials.cer</h2>
        </div>

        <div class="cert-list">

          <article class="cert-individual-card">
            <div class="cert-card-top">
              <span class="material-symbols-outlined cert-card-icon">verified</span>
              <div class="cert-card-badge">DFIR</div>
            </div>
            <h3 class="cert-card-title">Digital Forensics and Incident Response</h3>
            <p class="cert-card-org">Cybersafe Foundation</p>
            <p class="cert-card-desc">Hands-on training in forensic analysis, evidence handling and incident response workflows. Covers disk imaging, memory analysis, log correlation, and containment strategies.</p>
            <div class="cert-card-skills">
              <span>Forensics</span>
              <span>Incident Response</span>
              <span>Evidence Handling</span>
            </div>
          </article>

          <article class="cert-individual-card">
            <div class="cert-card-top">
              <span class="material-symbols-outlined cert-card-icon">verified</span>
              <div class="cert-card-badge">Ethical Hacking</div>
            </div>
            <h3 class="cert-card-title">Cisco Ethical Hacker</h3>
            <p class="cert-card-org">Cisco</p>
            <p class="cert-card-desc">Training focused on penetration testing fundamentals, web vulnerabilities and defensive controls. Includes reconnaissance, exploitation, and post-exploitation methodologies.</p>
            <div class="cert-card-skills">
              <span>Pen Testing</span>
              <span>Web Security</span>
              <span>Vulnerability Assessment</span>
            </div>
          </article>

        </div>
      </div>
    </section>

    <!-- ─── SKILLS & TOOLS ─── -->
    <section class="about-card" style="margin-bottom:28px;">
      <div class="about-card-inner">
        <div class="term-section-header">
          <span class="term-section-badge">// tool_kit</span>
          <h2>Tool_Kit.bin</h2>
        </div>
        <div class="skills-cloud">
          <span class="skill-tag">Splunk</span>
          <span class="skill-tag">Wireshark</span>
          <span class="skill-tag">Autopsy</span>
          <span class="skill-tag">Volatility</span>
          <span class="skill-tag">Nmap</span>
          <span class="skill-tag">Burp Suite</span>
          <span class="skill-tag">Linux</span>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Bash</span>
          <span class="skill-tag">Git</span>
          <span class="skill-tag">SIEM</span>
          <span class="skill-tag">YARA</span>
          <span class="skill-tag">Metasploit</span>
          <span class="skill-tag">TCPDump</span>
          <span class="skill-tag">Registry</span>
          <span class="skill-tag">Gobuster</span>
        </div>
      </div>
    </section>

    <!-- ─── Contact ─── -->
    <div class="about-contact-row">
      <a class="about-contact-btn" href="https://www.linkedin.com/in/grace-mawia-9b8340269/" aria-label="LinkedIn">
        <span class="material-symbols-outlined" style="font-size:18px;">link</span>
        LinkedIn
      </a>
      <a class="about-contact-btn" href="https://github.com/mawia-barbie" aria-label="GitHub">
        <span class="material-symbols-outlined" style="font-size:18px;">code</span>
        GitHub
      </a>
      <a class="about-contact-btn" href="mailto:mawiag411@gmail.com" aria-label="Email">
        <span class="material-symbols-outlined" style="font-size:18px;">mail</span>
        Email
      </a>
    </div>

  </div>
</div>

<style>
.about-page-root { width: 100%; background: transparent; }

/* ── About Cards ── */
.about-card {
  background: rgba(13, 11, 20, 0.6);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  padding: 32px;
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
  position: relative;
  overflow: hidden;
}
.about-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 48px rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
}
.about-card-inner { position: relative; z-index: 2; }

/* ── Terminal Preview ── */
.about-terminal-preview {
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  line-height: 1.9;
  background: rgba(0,0,0,0.25);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 8px;
  padding: 16px 20px;
  margin-bottom: 8px;
}
.about-term-line .mauve { color: var(--mauve, #c9a0dc); }
.about-term-line .gray { color: rgba(196, 176, 204, 0.4); }
.about-term-line .cmd { color: #e6e1e5; }
.about-term-line .output { color: #c4b0cc; padding-left: 8px; }

/* ── Term Section Header ── */
.term-section-header { margin-bottom: 20px; }
.term-section-badge {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(201, 160, 220, 0.3);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.term-section-header h2 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 2px;
  border-left: 3px solid var(--mauve, #c9a0dc);
  padding-left: 14px;
}

/* ── Body Text ── */
.about-text {
  font-size: 14px;
  line-height: 1.7;
  color: var(--muted, #c4b0cc);
  margin: 0;
}

/* ── Values Box ── */
.values-box {
  background: rgba(201, 160, 220, 0.03);
  border: 1px solid rgba(201, 160, 220, 0.08);
  border-radius: 8px;
  padding: 16px 20px;
  margin-top: 16px;
}
.values-header {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--mauve);
  margin-bottom: 8px;
}
.values-icon { font-size: 16px !important; }
.values-box ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
.values-box li {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--mauve);
  padding: 3px 0;
}
.values-box li::before {
  content: '→ ';
  color: rgba(201, 160, 220, 0.4);
}

/* ── Individual Certification Cards ── */
.cert-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.cert-individual-card {
  background: rgba(201, 160, 220, 0.02);
  border: 1px solid rgba(201, 160, 220, 0.08);
  border-radius: 12px;
  padding: 24px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}
.cert-individual-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, var(--mauve, #c9a0dc), transparent);
  opacity: 0.3;
  transition: opacity 0.3s;
}
.cert-individual-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 48px rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
}
.cert-individual-card:hover::before { opacity: 0.8; }

.cert-card-top {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 14px;
}
.cert-card-icon {
  font-size: 28px !important;
  color: var(--mauve, #c9a0dc) !important;
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 9px;
  background: rgba(201, 160, 220, 0.04);
  flex-shrink: 0;
}
.cert-card-badge {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 3px 10px;
  border-radius: 4px;
  background: rgba(34, 211, 238, 0.06);
  border: 1px solid rgba(34, 211, 238, 0.15);
  color: #22d3ee;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.cert-card-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 4px 0;
  font-weight: 700;
}
.cert-card-org {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: #22d3ee;
  margin: 0 0 10px 0;
}
.cert-card-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  margin: 0 0 14px 0;
  line-height: 1.6;
}
.cert-card-skills {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}
.cert-card-skills span {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  padding: 3px 8px;
  border-radius: 4px;
  background: rgba(201, 160, 220, 0.04);
  border: 1px solid rgba(201, 160, 220, 0.08);
  color: rgba(196, 176, 204, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* ── Contact Row ── */
/* ── Skills Cloud ── */
.skills-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}
.skill-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  padding: 8px 18px;
  border-radius: 6px;
  background: rgba(201, 160, 220, 0.03);
  border: 1px solid rgba(201, 160, 220, 0.08);
  color: var(--mauve);
  text-transform: uppercase;
  letter-spacing: 1.5px;
  transition: all 0.25s ease;
  cursor: default;
}
.skill-tag:hover {
  background: rgba(201, 160, 220, 0.08);
  border-color: rgba(201, 160, 220, 0.2);
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(201, 160, 220, 0.04);
}

.about-contact-row {
  display: flex;
  justify-content: center;
  gap: 14px;
  margin-top: 4px;
  flex-wrap: wrap;
}
.about-contact-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  border-radius: 8px;
  border: 1px solid rgba(201, 160, 220, 0.12);
  color: var(--mauve, #c9a0dc) !important;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  text-decoration: none !important;
  background: rgba(201, 160, 220, 0.03);
  transition: all 0.25s ease;
}
.about-contact-btn:hover {
  background: rgba(201, 160, 220, 0.08);
  border-color: rgba(201, 160, 220, 0.25);
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(201, 160, 220, 0.06);
}

/* ── Responsive ── */
@media (max-width: 820px) {
  .about-card { padding: 20px; }
  .about-terminal-preview { font-size: 12px; padding: 12px 16px; }
  .term-section-header h2 { font-size: 1.1rem; }
  .cert-individual-card { padding: 18px; }
}
</style>
