---
title: "Operation Blackout 2025: Smoke & Mirrors — Writeup"
layout: home
permalink: /writeups/sherlock/smoke-and-mirrors/
---

<div class="writeup-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:900px; width:100%;">

    <div class="writeup-header" style="margin-bottom:40px;">
      <a href="/sherlock-labs/" class="writeup-back-btn">← Back to Sherlock Labs</a>
      <div class="term-section-header" style="margin-top:16px;">
        <span class="term-section-badge">// blue_team_forensics // writeup</span>
        <h1>Operation Blackout 2025: Smoke &amp; Mirrors</h1>
      </div>
      <div class="writeup-meta">
        <span class="writeup-meta-tag">Difficulty: Hard</span>
        <span class="writeup-meta-tag">Category: Defense Evasion</span>
        <span class="writeup-meta-tag">Platform: HTB Sherlock</span>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Scenario</h2>
      <p>Byte Doctor Reyes is investigating a stealthy post-breach attack in which expected security logs and Microsoft Defender alerts are missing. The objective is to analyze the provided PowerShell event logs and determine how the attacker impaired the system's security controls to evade detection.</p>
      <p>This investigation focuses on identifying defense evasion techniques through PowerShell Operational logs.</p>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 1: Identify the Registry Key Used to Disable LSA Protection</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        The attacker disabled LSA protection on the compromised host by modifying a registry key. What is the full path of that registry key?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>LSA (Local Security Authority) Protection helps prevent unauthorized access to the LSASS process, making credential dumping significantly more difficult.</p>
      <p>During the investigation, the attacker was found to have modified the registry key responsible for LSA Protection.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Registry Path</div>
        <pre><code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa</code></pre>
      </div>

      <p>The relevant registry value is <strong>RunAsPPL</strong>, which controls whether LSASS runs as a Protected Process Light (PPL).</p>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 2: PowerShell Command Used to Disable Windows Defender</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which PowerShell command did the attacker first execute to disable Windows Defender?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The PowerShell logs revealed that the attacker modified Microsoft Defender settings using the <strong>Set-MpPreference</strong> cmdlet.</p>
      <p>The command disables multiple Defender protections simultaneously:</p>
      <ul>
        <li>IOAV (Internet Download Protection)</li>
        <li>Email scanning</li>
        <li>Block-at-First-Seen cloud protection</li>
      </ul>

      <div class="writeup-code-block">
        <div class="writeup-code-header">PowerShell Command</div>
        <pre><code>Set-MpPreference -DisableIOAVProtection $true -DisableEmailScanning $true -DisableBlockAtFirstSeen $true</code></pre>
      </div>

      <div class="writeup-mitre">
        <strong>MITRE ATT&CK:</strong> T1562.001 — Impair Defenses: Disable or Modify Security Tools
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>Set-MpPreference -DisableIOAVProtection $true -DisableEmailScanning $true -DisableBlockAtFirstSeen $true</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 3: AMSI Bypass</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        The attacker loaded an AMSI patch written in PowerShell. Which function in the DLL is being patched?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>AMSI (Antimalware Scan Interface) allows security products such as Microsoft Defender to inspect scripts before execution.</p>
      <p>Rather than disabling AMSI directly, the attacker patched the <strong>AmsiScanBuffer</strong> function in memory.</p>
      <p>Once patched, PowerShell scripts can execute without being scanned by AMSI.</p>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Function Patched:</span>
        <code>AmsiScanBuffer</code>
      </div>

      <div class="writeup-mitre">
        <strong>MITRE ATT&CK:</strong> T1562.001 — Impair Defenses
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 4: Restarting into Safe Mode</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which command did the attacker use to restart the machine in Safe Mode?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The attacker modified the Boot Configuration Data (BCD) using <strong>bcdedit.exe</strong>.</p>
      <p>Booting into Safe Mode with Networking can reduce the number of security services that start automatically, making it easier to execute malicious activity.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Command</div>
        <pre><code>bcdedit.exe /set safeboot network</code></pre>
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>bcdedit.exe /set safeboot network</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 5: Disabling PowerShell Command History</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which PowerShell command did the attacker use to disable PowerShell command history logging?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>PowerShell uses <strong>PSReadLine</strong> to store interactive command history.</p>
      <p>The attacker configured PowerShell to stop saving command history by changing the history save style.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Command</div>
        <pre><code>Set-PSReadLineOption -HistorySaveStyle SaveNothing</code></pre>
      </div>

      <p>This prevents future interactive PowerShell commands from being written to the user's history file, reducing forensic evidence.</p>

      <div class="writeup-mitre">
        <strong>MITRE ATT&CK:</strong> T1070 — Indicator Removal on Host
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>Set-PSReadLineOption -HistorySaveStyle SaveNothing</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Conclusion</h2>
      <p>This investigation demonstrates several common defense evasion techniques used by attackers to reduce visibility and hinder forensic analysis. The attacker:</p>
      <ul>
        <li>Disabled LSA Protection to weaken credential security.</li>
        <li>Modified Microsoft Defender settings to reduce malware detection.</li>
        <li>Patched <strong>AmsiScanBuffer</strong> to bypass AMSI scanning.</li>
        <li>Configured the system to boot into Safe Mode with Networking.</li>
        <li>Disabled PowerShell command history logging to limit forensic artifacts.</li>
      </ul>
      <p>Together, these techniques significantly impaired the host's defensive capabilities and made post-compromise detection more difficult.</p>

      <h3 class="writeup-h3" style="margin-top:20px;">MITRE ATT&CK Mapping</h3>
      <div class="writeup-table">
        <table>
          <tr><th>Technique</th><th>ATT&CK ID</th></tr>
          <tr><td>Disable or Modify Security Tools</td><td>T1562.001</td></tr>
          <tr><td>Indicator Removal on Host</td><td>T1070</td></tr>
          <tr><td>Modify Registry</td><td>T1112</td></tr>
          <tr><td>Boot or Logon Autostart Modification (BCD)</td><td>T1547</td></tr>
        </table>
      </div>

      <h3 class="writeup-h3" style="margin-top:20px;">Key Takeaways</h3>
      <p>This Sherlock emphasizes the importance of PowerShell Operational logging during investigations. Even when attackers attempt to disable security controls, PowerShell logs can reveal registry modifications, AMSI bypasses, Defender configuration changes, and attempts to remove forensic artifacts, providing investigators with valuable evidence of defense evasion activity.</p>
    </div>

  </div>
</div>

<style>
.writeup-root { width: 100%; background: transparent; }

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

.writeup-back-btn {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: #22d3ee !important;
  text-decoration: none !important;
  transition: all 0.2s;
}
.writeup-back-btn:hover {
  padding-left: 4px;
  opacity: 0.8;
}

.writeup-meta {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-top: 12px;
}
.writeup-meta-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 4px 10px;
  border-radius: 4px;
  background: rgba(34, 211, 238, 0.04);
  border: 1px solid rgba(34, 211, 238, 0.1);
  color: rgba(196, 176, 204, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* ── Writeup Cards ── */
.writeup-card {
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  padding: 28px;
  margin-bottom: 24px;
  transition: all 0.3s ease;
}
.writeup-card:hover {
  border-color: rgba(201, 160, 220, 0.12);
  box-shadow: 0 8px 32px rgba(201, 160, 220, 0.04);
}

.writeup-h2 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.15rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 16px 0;
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(201, 160, 220, 0.06);
}

.writeup-h3 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.9rem;
  color: var(--mauve, #c9a0dc) !important;
  margin: 16px 0 8px 0;
}

.writeup-card p, .writeup-card li {
  font-size: 14px;
  line-height: 1.7;
  color: var(--muted, #c4b0cc);
}

.writeup-card ul {
  padding-left: 20px;
}
.writeup-card li {
  margin-bottom: 4px;
}

.writeup-quote {
  background: rgba(201, 160, 220, 0.03);
  border-left: 3px solid var(--mauve, #c9a0dc);
  border-radius: 0 6px 6px 0;
  padding: 12px 16px;
  font-size: 13px;
  font-style: italic;
  color: rgba(196, 176, 204, 0.7);
  margin: 10px 0;
  line-height: 1.5;
}

.writeup-code-block {
  background: rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 8px;
  margin: 12px 0;
  overflow: hidden;
}
.writeup-code-header {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 6px 14px;
  background: rgba(201, 160, 220, 0.03);
  border-bottom: 1px solid rgba(201, 160, 220, 0.04);
  color: rgba(196, 176, 204, 0.4);
  text-transform: uppercase;
  letter-spacing: 1px;
}
.writeup-code-block pre {
  margin: 0;
  padding: 14px 16px;
  overflow-x: auto;
}
.writeup-code-block code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: #22d3ee;
  line-height: 1.6;
}

.writeup-answer {
  background: rgba(39, 201, 63, 0.03);
  border: 1px solid rgba(39, 201, 63, 0.1);
  border-radius: 8px;
  padding: 12px 16px;
  margin-top: 14px;
}
.writeup-answer-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #27c93f;
  text-transform: uppercase;
  letter-spacing: 1px;
  display: block;
  margin-bottom: 6px;
}
.writeup-answer code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: #27c93f;
  word-break: break-all;
}

.writeup-mitre {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #ffbd2e;
  background: rgba(255, 189, 46, 0.03);
  border: 1px solid rgba(255, 189, 46, 0.08);
  border-radius: 6px;
  padding: 8px 14px;
  margin-top: 12px;
}

.writeup-table {
  overflow-x: auto;
  margin: 12px 0;
}
.writeup-table table {
  width: 100%;
  border-collapse: collapse;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
}
.writeup-table th, .writeup-table td {
  padding: 8px 14px;
  text-align: left;
  border: 1px solid rgba(201, 160, 220, 0.06);
}
.writeup-table th {
  color: var(--mauve-light, #e6c8f0);
  background: rgba(201, 160, 220, 0.03);
}
.writeup-table td {
  color: var(--muted, #c4b0cc);
}

@media (max-width: 820px) {
  .writeup-card { padding: 20px; }
  .term-section-header h1 { font-size: 1.2rem; }
  .writeup-code-block code { font-size: 11px; }
}
</style>
