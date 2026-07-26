---
title: Sherlock Labs
layout: home
permalink: /sherlock-labs/
---

<div class="sherlock-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:1100px; width:100%;">

    <div class="term-section-header" style="margin-bottom:36px;">
      <span class="term-section-badge">// blue_team_forensics</span>
      <h1>Sherlock_Labs.db</h1>
      <p class="term-section-desc">In-depth investigation write-ups for complex blue-team scenarios — host-based forensics, threat hunting, and incident response.</p>
    </div>

    <div class="sherlock-grid">

      <!-- Brutus (Password Protected) -->
      <article class="sherlock-card locked">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">Brutus <span class="sherlock-lock-badge">🔒</span></h3>
        <p class="sherlock-card-desc">Forensic investigation of a brute-force attack scenario. Analyze authentication logs, identify compromised accounts, and trace the attacker's foothold.</p>
        <div class="sherlock-tags">
          <span>Log Analysis</span><span>Auth Logs</span><span>Brute Force</span>
        </div>
        <button class="sherlock-unlock-btn" data-lab="brutus">🔑 Unlock Writeup</button>
      </article>

      <!-- FortySeven-1 -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">FortySeven-1</h3>
        <p class="sherlock-card-desc">Digital forensics case involving file recovery and metadata analysis. Recover deleted artifacts and piece together user activity from disk images.</p>
        <div class="sherlock-tags">
          <span>File Recovery</span><span>Metadata</span><span>Disk Forensics</span>
        </div>
        <a href="#" class="sherlock-link">Read Writeup →</a>
      </article>

      <!-- Vantage -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">Vantage</h3>
        <p class="sherlock-card-desc">Investigate network traffic to identify abuse of the OpenStack API. Analyze packet captures to discern misconfigurations and unauthorized access attempts. Trace API interactions and pinpoint the technical vulnerabilities that allowed the breach.</p>
        <div class="sherlock-tags">
          <span>OpenStack API</span><span>Packet Capture</span><span>Cloud Security</span><span>API Abuse</span>
        </div>
        <a href="#" class="sherlock-link">Read Writeup →</a>
      </article>

      <!-- Telly -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">Telly</h3>
        <p class="sherlock-card-desc">Analyze network traffic to find evidence of exploitation of CVE-2026-24061 against the telnet protocol, allowing root remote access without any credentials or prior access.</p>
        <div class="sherlock-tags">
          <span>Telnet</span><span>CVE-2026-24061</span><span>Network Traffic</span><span>Remote Access</span>
        </div>
        <a href="#" class="sherlock-link">Read Writeup →</a>
      </article>

      <!-- MangoBleed -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">MangoBleed</h3>
        <p class="sherlock-card-desc">Advanced memory forensics challenge. Analyze memory dumps to identify malicious processes, injected code, and persistence mechanisms used by the adversary.</p>
        <div class="sherlock-tags">
          <span>Memory Forensics</span><span>Volatility</span><span>Malware Analysis</span>
        </div>
        <a href="/writeups/sherlock/mangobleed/" class="sherlock-link">Read Writeup →</a>
      </article>

      <!-- Operation Blackout 2025: Phantom Check -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">Operation Blackout 2025: Phantom Check</h3>
        <p class="sherlock-card-desc">A Sherlock challenge showcasing common virtualization detection techniques used by attackers. Gain the ability to create detection rules by identifying specific WMI queries, comparing processes for VM detection, and analyzing registry keys or file paths associated with virtual environments.</p>
        <div class="sherlock-tags">
          <span>VM Detection</span><span>WMI Queries</span><span>Registry Analysis</span><span>Detection Rules</span>
        </div><a href="/writeups/sherlock/phantom-check/" class="sherlock-link">Read Writeup →</a>
      </article>

        <!-- Operation Blackout 2025: Smoke & Mirrors -->
      <article class="sherlock-card">
        <div class="sherlock-card-top">
          <span class="material-symbols-outlined sherlock-card-icon">search_insights</span>
        </div>
        <h3 class="sherlock-card-title">Operation Blackout 2025: Smoke &amp; Mirrors</h3>
        <p class="sherlock-card-desc">Analyze event logs and forensic artifacts to uncover how the attacker disabled or altered security features. Identify the tools, commands, or scripts used to reduce visibility and reconstruct the methods the attacker used to operate undetected.</p>
        <div class="sherlock-tags">
          <span>Event Logs</span><span>Defense Evasion</span><span>Security Features</span><span>Forensic Artifacts</span>
        </div>
        <a href="/writeups/sherlock/smoke-and-mirrors/" class="sherlock-link">Read Writeup →</a>
      </article>

    </div>

  </div>
</div>

<!-- ─── PASSWORD MODAL ─── -->
<div class="sherlock-password-overlay" id="sherlock-password-overlay" role="dialog" aria-modal="true" aria-label="Enter password to unlock writeup">
  <div class="sherlock-password-modal">
    <div class="sherlock-password-modal-header">
      <span class="material-symbols-outlined" aria-hidden="true">lock</span>
      <span>Restricted Writeup</span>
    </div>
    <p class="sherlock-password-desc">This lab is still active. Enter the shared password to access the writeup.</p>
    <div class="sherlock-password-input-group">
      <label for="sherlock-password-input" class="sr-only">Password</label>
      <input type="password" id="sherlock-password-input" placeholder="Enter password..." autocomplete="off" />
      <button id="sherlock-password-submit">Unlock</button>
    </div>
    <p class="sherlock-password-error" id="sherlock-password-error" role="alert">Incorrect password. Try again.</p>
    <button class="sherlock-password-close" id="sherlock-password-close">Cancel</button>
  </div>
</div>

<!-- ─── WRITEUP REVEAL MODAL ─── -->
<div class="sherlock-writeup-reveal" id="sherlock-writeup-reveal" role="dialog" aria-modal="true" aria-label="Writeup unlocked">
  <div class="sherlock-writeup-reveal-inner">
    <span class="material-symbols-outlined" style="color:var(--mauve);font-size:32px;" aria-hidden="true">lock_open</span>
    <h3>Writeup Unlocked</h3>
    <p id="sherlock-writeup-reveal-text">You now have access to this writeup. Please don't share it publicly while the lab is active.</p>
    <a href="#" id="sherlock-writeup-reveal-link" class="sherlock-writeup-link">Read Writeup →</a>
    <button class="sherlock-writeup-close-btn" id="sherlock-writeup-close-btn">Close</button>
  </div>
</div>

<style>
.sherlock-root { width: 100%; background: transparent; }

.term-section-header { margin-bottom: 36px; }
.term-section-badge {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(201, 160, 220, 0.3);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.term-section-header h1 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.6rem;
  font-weight: 700;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  text-transform: uppercase;
  letter-spacing: 2px;
  border-left: 3px solid var(--mauve, #c9a0dc);
  padding-left: 16px;
}
.term-section-desc {
  font-size: 14px;
  color: var(--muted, #c4b0cc);
  margin-top: 12px;
  margin-bottom: 0;
}

/* ── Sherlock Grid ── */
.sherlock-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.sherlock-card {
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  padding: 24px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.sherlock-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, #22d3ee, transparent);
  opacity: 0.2;
  transition: opacity 0.3s;
}
.sherlock-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 60px rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
}
.sherlock-card:hover::before { opacity: 0.8; }

.sherlock-card-top {
  display: flex;
  align-items: center;
  margin-bottom: 14px;
}

.sherlock-card-icon {
  font-size: 28px !important;
  color: #22d3ee !important;
}

.sherlock-card-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.05rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 10px 0;
}

.sherlock-card-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  margin: 0 0 14px 0;
  line-height: 1.6;
  flex: 1;
}

.sherlock-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 16px;
}
.sherlock-tags span {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  padding: 3px 8px;
  border-radius: 4px;
  background: rgba(34, 211, 238, 0.04);
  border: 1px solid rgba(34, 211, 238, 0.08);
  color: rgba(196, 176, 204, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.sherlock-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: #22d3ee !important;
  text-decoration: none !important;
  transition: all 0.2s;
  margin-top: auto;
}
.sherlock-link:hover {
  color: #67e8f9 !important;
  padding-left: 4px;
}

/* ── Locked Card ── */
.sherlock-card.locked {
  border-color: rgba(255, 189, 46, 0.08);
}
.sherlock-card.locked::before {
  background: linear-gradient(90deg, #ffbd2e, transparent);
}

.sherlock-lock-badge {
  font-size: 14px;
  margin-left: 4px;
}

.sherlock-unlock-btn {
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
  margin-top: auto;
  width: 100%;
}
.sherlock-unlock-btn:hover {
  background: rgba(255, 189, 46, 0.1);
  border-color: rgba(255, 189, 46, 0.4);
  box-shadow: 0 0 20px rgba(255, 189, 46, 0.06);
}

/* ── Password Modal ── */
.sherlock-password-overlay {
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
.sherlock-password-overlay.active {
  opacity: 1;
  visibility: visible;
}

.sherlock-password-modal {
  background: #13101a;
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 12px;
  padding: 32px;
  width: min(400px, 90vw);
  box-shadow: 0 0 60px rgba(201, 160, 220, 0.06);
  text-align: center;
}

.sherlock-password-modal-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  color: #ffbd2e;
  margin-bottom: 12px;
}
.sherlock-password-modal-header span:first-child { font-size: 20px !important; }

.sherlock-password-desc {
  font-size: 13px;
  color: rgba(196, 176, 204, 0.6);
  margin-bottom: 20px;
  line-height: 1.5;
}

.sherlock-password-input-group {
  display: flex;
  gap: 8px;
  margin-bottom: 12px;
}
.sherlock-password-input-group input {
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
.sherlock-password-input-group input:focus {
  border-color: rgba(201, 160, 220, 0.3);
}
.sherlock-password-input-group input::placeholder {
  color: rgba(196, 176, 204, 0.3);
}
.sherlock-password-input-group button {
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
.sherlock-password-input-group button:hover {
  background: rgba(201, 160, 220, 0.12);
  border-color: rgba(201, 160, 220, 0.3);
}

.sherlock-password-error {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #ff5f56;
  display: none;
  margin: 8px 0;
}
.sherlock-password-error.show { display: block; }

.sherlock-password-close {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  background: none;
  border: none;
  cursor: pointer;
  margin-top: 8px;
  transition: color 0.2s;
}
.sherlock-password-close:hover { color: var(--muted); }

/* ── Writeup Reveal Modal ── */
.sherlock-writeup-reveal {
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
.sherlock-writeup-reveal.active {
  opacity: 1;
  visibility: visible;
}

.sherlock-writeup-reveal-inner {
  background: #13101a;
  border: 1px solid rgba(201, 160, 220, 0.12);
  border-radius: 12px;
  padding: 36px;
  width: min(400px, 90vw);
  box-shadow: 0 0 60px rgba(201, 160, 220, 0.06);
  text-align: center;
}
.sherlock-writeup-reveal-inner h3 {
  font-family: 'JetBrains Mono', monospace;
  color: var(--mauve-light) !important;
  margin: 12px 0 8px;
  font-size: 1.1rem;
}
.sherlock-writeup-reveal-inner p {
  font-size: 13px;
  color: rgba(196, 176, 204, 0.6);
  margin-bottom: 20px;
  line-height: 1.5;
}

.sherlock-writeup-link {
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
.sherlock-writeup-link:hover {
  background: rgba(201, 160, 220, 0.15);
  box-shadow: 0 0 24px rgba(201, 160, 220, 0.06);
}

.sherlock-writeup-close-btn {
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
.sherlock-writeup-close-btn:hover {
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

@media (max-width: 820px) {
  .sherlock-grid { grid-template-columns: 1fr; }
  .term-section-header h1 { font-size: 1.2rem; }
  .sherlock-card { padding: 18px; }
}
</style>

<script>
(function() {
  'use strict';

  const DEFAULT_PASSWORD = 'defense@blue';

  const passwordOverlay = document.getElementById('sherlock-password-overlay');
  const passwordInput = document.getElementById('sherlock-password-input');
  const passwordSubmit = document.getElementById('sherlock-password-submit');
  const passwordError = document.getElementById('sherlock-password-error');
  const passwordClose = document.getElementById('sherlock-password-close');
  const writeupReveal = document.getElementById('sherlock-writeup-reveal');
  const writeupCloseBtn = document.getElementById('sherlock-writeup-close-btn');

  let currentLab = '';

  document.querySelectorAll('.sherlock-unlock-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      currentLab = btn.dataset.lab || 'unknown';
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
        var textEl = document.getElementById('sherlock-writeup-reveal-text');
        if (textEl) {
          textEl.textContent = currentLab.charAt(0).toUpperCase() + currentLab.slice(1) + ' writeup unlocked! Please keep this confidential while the lab is active.';
        }
        var linkEl = document.getElementById('sherlock-writeup-reveal-link');
        if (linkEl) {
          linkEl.href = '/writeups/sherlock/' + currentLab + '/';
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
