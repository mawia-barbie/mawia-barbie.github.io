---
title: Home SOC Lab
layout: home
permalink: /home-soc-lab/
---

<div class="soc-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div class="soc-container">

    <a href="/categories/" class="soc-back">← Back to Projects</a>

    <!-- ── HERO ── -->
    <header class="soc-hero">
      <div class="term-section-header" style="margin-bottom:18px;">
        <span class="term-section-badge">// blue_team_lab // soc</span>
        <h1>Home SOC Lab</h1>
      </div>

      <div class="soc-hero-meta">
        <span class="soc-status-badge"><span class="soc-status-dot" aria-hidden="true"></span> Active</span>
        <span class="soc-meta-tag">Wazuh</span>
        <span class="soc-meta-tag">Sysmon</span>
        <span class="soc-meta-tag">Atomic Red Team</span>
        <span class="soc-meta-tag">Windows 11</span>
        <span class="soc-meta-tag">Parrot OS</span>
        <span class="soc-meta-tag">MITRE ATT&CK</span>
      </div>

      <p class="soc-hero-intro">A self-built Security Operations Center (SOC) lab used to simulate cyber attacks, monitor endpoint activity, investigate security alerts, and strengthen hands-on detection and incident response skills using Wazuh, Sysmon, and Atomic Red Team.</p>
    </header>

    <!-- ── LAB OVERVIEW ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// about</span>
        <h2>Lab Overview</h2>
      </div>
      <div class="soc-card">
        <p>The Home SOC Lab is a hands-on detection engineering environment built to bridge the gap between theory and practice. It simulates realistic cyber attacks against a dedicated Windows 11 endpoint while collecting rich telemetry, so every phase of the attack lifecycle can be observed, analyzed, and investigated — end to end.</p>
        <p>Rather than relying on a commercial sandbox, the lab recreates a miniature enterprise detection stack on commodity hardware: a SIEM platform (Wazuh), endpoint instrumentation (Sysmon + Wazuh Agent), and an adversary simulator (Atomic Red Team). Every alert that fires is treated as a real investigation, reinforcing the SOC analyst workflow: triage, root cause analysis, MITRE ATT&CK mapping, and documentation.</p>
        <div class="soc-card-stats">
          <div class="soc-stat"><span class="soc-stat-num">3</span><span class="soc-stat-label">Lab nodes</span></div>
          <div class="soc-stat"><span class="soc-stat-num">8</span><span class="soc-stat-label">Workflow stages</span></div>
          <div class="soc-stat"><span class="soc-stat-num">∞</span><span class="soc-stat-label">Case studies</span></div>
        </div>
      </div>
    </section>

    <!-- ── LAB ARCHITECTURE ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// topology</span>
        <h2>Lab Architecture</h2>
      </div>

      <div class="arch-diagram">
        <div class="arch-node">
          <span class="material-symbols-outlined arch-node-icon" aria-hidden="true">desktop_windows</span>
          <h3>Windows 11 Laptop</h3>
          <p>Dedicated endpoint — Sysmon installed, Wazuh Agent installed, Atomic Red Team used to simulate attacks.</p>
          <span class="arch-node-tag">Endpoint</span>
        </div>

        <div class="arch-connector">
          <span class="material-symbols-outlined" aria-hidden="true">arrow_forward</span>
          <span class="arch-connector-label">telemetry</span>
        </div>

        <div class="arch-node core">
          <span class="material-symbols-outlined arch-node-icon" aria-hidden="true">monitoring</span>
          <h3>Wazuh Platform</h3>
          <p>Receives endpoint telemetry, generates security alerts, and supports investigation and analysis.</p>
          <span class="arch-node-tag">Detection</span>
        </div>

        <div class="arch-connector reverse">
          <span class="material-symbols-outlined" aria-hidden="true">arrow_back</span>
          <span class="arch-connector-label">investigate</span>
        </div>

        <div class="arch-node">
          <span class="material-symbols-outlined arch-node-icon" aria-hidden="true">laptop_mac</span>
          <h3>Parrot OS Laptop</h3>
          <p>Primary investigation workstation — used for administration, analysis, and documentation.</p>
          <span class="arch-node-tag">Investigation</span>
        </div>
      </div>
    </section>

    <!-- ── INVESTIGATION WORKFLOW ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// playbook</span>
        <h2>Investigation Workflow</h2>
      </div>

      <div class="workflow">
        <div class="wf-step"><span class="wf-num">01</span><span class="wf-label">Plan Attack</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">02</span><span class="wf-label">Execute Atomic Red Team Test</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">03</span><span class="wf-label">Sysmon Records Events</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">04</span><span class="wf-label">Wazuh Collects Logs</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">05</span><span class="wf-label">Alert Generated</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">06</span><span class="wf-label">Investigate</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">07</span><span class="wf-label">Map to MITRE ATT&CK</span></div>
        <span class="wf-arrow" aria-hidden="true">→</span>
        <div class="wf-step"><span class="wf-num">08</span><span class="wf-label">Document Findings</span></div>
      </div>
    </section>

    <!-- ── TECHNOLOGIES USED ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// stack</span>
        <h2>Technologies Used</h2>
      </div>

      <div class="tech-grid">
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">monitoring</span><span class="tech-card-name">Wazuh</span><span class="tech-card-role">SIEM · Detection</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">terminal</span><span class="tech-card-name">Sysmon</span><span class="tech-card-role">Endpoint Telemetry</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">desktop_windows</span><span class="tech-card-name">Windows 11</span><span class="tech-card-role">Target Endpoint</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">security</span><span class="tech-card-name">Parrot OS</span><span class="tech-card-role">Analysis OS</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">rocket_launch</span><span class="tech-card-name">Atomic Red Team</span><span class="tech-card-role">Adversary Simulator</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">code</span><span class="tech-card-name">PowerShell</span><span class="tech-card-role">Scripting</span></div>
        <div class="tech-card"><span class="material-symbols-outlined tech-card-icon" aria-hidden="true">track_changes</span><span class="tech-card-name">MITRE ATT&CK</span><span class="tech-card-role">Framing</span></div>
      </div>
    </section>

    <!-- ── LAB OBJECTIVES ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// objectives</span>
        <h2>Lab Objectives</h2>
      </div>

      <div class="objectives-grid">
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Simulate real-world attacks</span></div>
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Monitor endpoint activity</span></div>
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Analyze security alerts</span></div>
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Practice incident response</span></div>
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Improve detection engineering skills</span></div>
        <div class="objective-item"><span class="material-symbols-outlined objective-icon" aria-hidden="true">check_circle</span><span>Document investigations</span></div>
      </div>
    </section>

    <!-- ── INVESTIGATION LIBRARY ── -->
    <section class="soc-section">
      <div class="term-section-header" style="margin-bottom:20px;">
        <span class="term-section-badge">// case_studies</span>
        <h2>Investigation Library</h2>
      </div>
      <p class="soc-section-note">Full case studies completed inside the lab. New investigations are published here as they are documented.</p>

      <div class="investigation-grid">
        {% for inv in site.data.soc-investigations %}
        <article class="investigation-card{% unless inv.url %} pending{% endunless %}">
          <div class="investigation-card-top">
            <span class="material-symbols-outlined investigation-card-icon" aria-hidden="true">search_insights</span>
            <span class="investigation-num">#{{ inv.number }}</span>
          </div>
          <h3 class="investigation-card-title">{{ inv.title }}</h3>
          <p class="investigation-card-desc">{{ inv.description }}</p>
          <div class="investigation-card-foot">
            {% if inv.url %}
            <a href="{{ inv.url }}" class="investigation-link">Read Case Study →</a>
            {% else %}
            <span class="investigation-pending">⌛ Pending</span>
            {% endif %}
          </div>
        </article>
        {% endfor %}
      </div>
    </section>

    <footer class="soc-footer">
      <p>© {{ site.time | date: '%Y' }} Grace Mawia // CYBER_SENTINEL — Home SOC Lab</p>
    </footer>

  </div>
</div>

<style>
.soc-root { width: 100%; background: transparent; }

.soc-container { max-width: 960px; width: 100%; }

.soc-back {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: #22d3ee !important;
  text-decoration: none !important;
  transition: all 0.2s;
  margin-bottom: 28px;
}
.soc-back:hover { padding-left: 4px; opacity: 0.85; }

/* ── Section header ── */
.term-section-header { margin-bottom: 24px; }
.term-section-badge {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(201, 160, 220, 0.3);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.term-section-header h1, .term-section-header h2 {
  font-family: 'JetBrains Mono', monospace;
  font-weight: 700;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 2px;
  border-left: 3px solid var(--mauve, #c9a0dc);
  padding-left: 16px;
}
.term-section-header h1 { font-size: 1.7rem; }
.term-section-header h2 { font-size: 1.3rem; }

/* ── Hero ── */
.soc-hero { margin-bottom: 44px; }
.soc-hero-meta {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
}
.soc-status-badge {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #27c93f;
  background: rgba(39, 201, 63, 0.06);
  border: 1px solid rgba(39, 201, 63, 0.2);
  padding: 4px 12px;
  border-radius: 999px;
  margin-right: 4px;
}
.soc-status-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #27c93f;
  animation: socPulse 2s ease-in-out infinite;
}
@keyframes socPulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(39, 201, 63, 0.4); }
  50% { box-shadow: 0 0 10px 2px rgba(39, 201, 63, 0.35); }
}
.soc-meta-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 4px 10px;
  border-radius: 4px;
  background: rgba(34, 211, 238, 0.04);
  border: 1px solid rgba(34, 211, 238, 0.1);
  color: rgba(196, 176, 204, 0.75);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}
.soc-hero-intro {
  font-size: 15px;
  color: var(--muted, #c4b0cc);
  line-height: 1.75;
  margin: 0;
  max-width: 760px;
}

/* ── Cards ── */
.soc-card {
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  padding: 28px;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}
.soc-card:hover {
  border-color: rgba(201, 160, 220, 0.14);
  box-shadow: 0 12px 40px rgba(201, 160, 220, 0.05);
}
.soc-card p {
  font-size: 14px;
  color: var(--muted, #c4b0cc);
  line-height: 1.75;
  margin: 0 0 14px 0;
}
.soc-card p:last-of-type { margin-bottom: 22px; }

.soc-card-stats {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
  border-top: 1px solid rgba(201, 160, 220, 0.06);
  padding-top: 18px;
}
.soc-stat {
  display: flex;
  flex-direction: column;
  gap: 2px;
  padding: 10px 18px;
  border-radius: 8px;
  background: rgba(201, 160, 220, 0.03);
  border: 1px solid rgba(201, 160, 220, 0.07);
}
.soc-stat-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--mauve-light, #e6c8f0);
}
.soc-stat-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: rgba(196, 176, 204, 0.45);
}

/* ── Architecture diagram ── */
.arch-diagram {
  display: flex;
  align-items: stretch;
  gap: 0;
  margin: 8px 0 4px;
}
.arch-node {
  flex: 1 1 0;
  min-width: 0;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.08);
  border-radius: 12px;
  padding: 22px 18px;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
  animation: socFadeIn 0.5s ease both;
}
.arch-node::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, var(--mauve, #c9a0dc), transparent);
  opacity: 0.25;
  transition: opacity 0.3s;
}
.arch-node:hover {
  transform: translateY(-4px);
  border-color: rgba(201, 160, 220, 0.18);
  box-shadow: 0 14px 40px rgba(201, 160, 220, 0.06);
}
.arch-node:hover::before { opacity: 0.9; }
.arch-node.core {
  border-color: rgba(34, 211, 238, 0.16);
}
.arch-node.core::before {
  background: linear-gradient(90deg, #22d3ee, var(--mauve, #c9a0dc), transparent);
  opacity: 0.7;
}
@keyframes socFadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: none; }
}
.arch-node-icon {
  font-size: 34px !important;
  color: var(--mauve, #c9a0dc) !important;
  margin-bottom: 12px;
}
.arch-node.core .arch-node-icon { color: #22d3ee !important; }
.arch-node h3 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 10px 0;
  letter-spacing: 0.5px;
}
.arch-node p {
  font-size: 12.5px;
  color: var(--muted, #c4b0cc);
  line-height: 1.6;
  margin: 0 0 14px 0;
}
.arch-node-tag {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 3px 10px;
  border-radius: 999px;
  background: rgba(201, 160, 220, 0.05);
  border: 1px solid rgba(201, 160, 220, 0.1);
  color: rgba(196, 176, 204, 0.6);
}
.arch-node.core .arch-node-tag {
  background: rgba(34, 211, 238, 0.05);
  border-color: rgba(34, 211, 238, 0.14);
  color: #22d3ee;
}
.arch-connector {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4px;
  width: 74px;
  flex-shrink: 0;
  color: rgba(34, 211, 238, 0.6);
}
.arch-connector .material-symbols-outlined {
  font-size: 22px !important;
  animation: socArrowPulse 2s ease-in-out infinite;
}
@keyframes socArrowPulse {
  0%, 100% { transform: translateX(0); opacity: 0.5; }
  50% { transform: translateX(4px); opacity: 1; }
}
.arch-connector.reverse .material-symbols-outlined {
  animation-name: socArrowPulseBack;
}
@keyframes socArrowPulseBack {
  0%, 100% { transform: translateX(0); opacity: 0.5; }
  50% { transform: translateX(-4px); opacity: 1; }
}
.arch-connector-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: rgba(196, 176, 204, 0.35);
  white-space: nowrap;
}

/* ── Workflow ── */
.workflow {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 10px;
}
.wf-step {
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 14px 16px;
  border-radius: 10px;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.08);
  transition: all 0.25s ease;
}
.wf-step:hover {
  border-color: rgba(34, 211, 238, 0.25);
  transform: translateY(-3px);
  box-shadow: 0 10px 28px rgba(201, 160, 220, 0.05);
}
.wf-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: #22d3ee;
  letter-spacing: 1px;
}
.wf-label {
  font-size: 12.5px;
  font-weight: 600;
  color: var(--mauve-light, #e6c8f0);
  white-space: nowrap;
}
.wf-arrow {
  font-family: 'JetBrains Mono', monospace;
  font-size: 15px;
  color: rgba(34, 211, 238, 0.5);
}

/* ── Tech grid ── */
.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 12px;
}
.tech-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  padding: 20px 12px;
  border-radius: 10px;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.07);
  text-align: center;
  transition: all 0.25s ease;
}
.tech-card:hover {
  transform: translateY(-4px);
  border-color: rgba(201, 160, 220, 0.2);
  box-shadow: 0 12px 32px rgba(201, 160, 220, 0.06);
}
.tech-card-icon {
  font-size: 28px !important;
  color: var(--mauve, #c9a0dc) !important;
}
.tech-card-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12.5px;
  font-weight: 700;
  color: var(--mauve-light, #e6c8f0);
}
.tech-card-role {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  letter-spacing: 0.8px;
  text-transform: uppercase;
  color: rgba(196, 176, 204, 0.4);
}

/* ── Objectives ── */
.objectives-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 12px;
}
.objective-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 14px 16px;
  border-radius: 10px;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.07);
  font-size: 13.5px;
  color: var(--muted, #c4b0cc);
  transition: all 0.25s ease;
}
.objective-item:hover {
  border-color: rgba(201, 160, 220, 0.16);
  transform: translateX(3px);
}
.objective-icon {
  font-size: 20px !important;
  color: #27c93f !important;
  flex-shrink: 0;
}

/* ── Investigation library ── */
.soc-section-note {
  font-size: 13px;
  color: rgba(196, 176, 204, 0.5);
  margin: -8px 0 16px 0;
}
.investigation-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 14px;
}
.investigation-card {
  display: flex;
  flex-direction: column;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.07);
  border-radius: 12px;
  padding: 20px;
  position: relative;
  overflow: hidden;
  transition: all 0.28s ease;
}
.investigation-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, #22d3ee, transparent);
  opacity: 0.3;
  transition: opacity 0.3s;
}
.investigation-card:hover {
  transform: translateY(-4px);
  border-color: rgba(201, 160, 220, 0.18);
  box-shadow: 0 14px 40px rgba(201, 160, 220, 0.06);
}
.investigation-card:hover::before { opacity: 0.9; }
.investigation-card.pending { opacity: 0.75; }
.investigation-card.pending::before {
  background: linear-gradient(90deg, #ffbd2e, transparent);
  opacity: 0.5;
}
.investigation-card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 12px;
}
.investigation-card-icon {
  font-size: 24px !important;
  color: #22d3ee !important;
}
.investigation-card.pending .investigation-card-icon { color: #ffbd2e !important; }
.investigation-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(201, 160, 220, 0.4);
  letter-spacing: 1px;
}
.investigation-card-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 8px 0;
}
.investigation-card-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  line-height: 1.6;
  margin: 0 0 16px 0;
  flex: 1;
}
.investigation-card-foot { margin-top: auto; }
.investigation-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: #22d3ee !important;
  text-decoration: none !important;
  transition: all 0.2s;
}
.investigation-link:hover { padding-left: 4px; color: #67e8f9 !important; }
.investigation-pending {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #ffbd2e;
  background: rgba(255, 189, 46, 0.05);
  border: 1px solid rgba(255, 189, 46, 0.16);
  padding: 3px 10px;
  border-radius: 999px;
}

/* ── Footer ── */
.soc-footer {
  margin-top: 48px;
  padding-top: 20px;
  border-top: 1px solid rgba(201, 160, 220, 0.06);
  text-align: center;
}
.soc-footer p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.35);
  margin: 0;
}

/* ── Responsive ── */
@media (max-width: 820px) {
  .term-section-header h1 { font-size: 1.3rem; }
  .term-section-header h2 { font-size: 1.1rem; }
  .soc-card { padding: 20px; }
  .arch-diagram { flex-direction: column; }
  .arch-connector {
    width: 100%;
    height: 44px;
    flex-direction: row;
    justify-content: center;
  }
  .arch-connector .material-symbols-outlined {
    transform: rotate(90deg);
    animation: none !important;
  }
  .arch-connector.reverse .material-symbols-outlined {
    transform: rotate(-90deg);
  }
  .workflow { gap: 8px; }
  .wf-step { padding: 11px 13px; }
  .wf-label { white-space: normal; }
}
@media (max-width: 480px) {
  .soc-hero-intro { font-size: 14px; }
  .tech-grid { grid-template-columns: repeat(auto-fill, minmax(120px, 1fr)); }
  .objectives-grid { grid-template-columns: 1fr; }
  .investigation-grid { grid-template-columns: 1fr; }
}

@media (prefers-reduced-motion: reduce) {
  .soc-status-dot, .arch-connector .material-symbols-outlined,
  .arch-node, .wf-step, .tech-card, .objective-item, .investigation-card { animation: none !important; }
  .arch-node:hover, .wf-step:hover, .tech-card:hover, .objective-item:hover,
  .investigation-card:hover { transform: none; }
}
</style>
