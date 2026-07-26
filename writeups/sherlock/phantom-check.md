---
title: "Operation Blackout 2025: Phantom Check — Writeup"
layout: home
permalink: /writeups/sherlock/phantom-check/
---

<div class="writeup-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:900px; width:100%;">

    <div class="writeup-header" style="margin-bottom:40px;">
      <a href="/sherlock-labs/" class="writeup-back-btn">← Back to Sherlock Labs</a>
      <div class="term-section-header" style="margin-top:16px;">
        <span class="term-section-badge">// blue_team_forensics // writeup</span>
        <h1>Operation Blackout 2025: Phantom Check</h1>
      </div>
      <div class="writeup-meta">
        <span class="writeup-meta-tag">Difficulty: Hard</span>
        <span class="writeup-meta-tag">Category: Anti-Virtualization</span>
        <span class="writeup-meta-tag">Platform: HTB Sherlock</span>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Scenario</h2>
      <p>Talion suspects that the threat actor carried out anti-virtualization checks to avoid detection in sandboxed environments. The objective is to analyze the provided PowerShell event logs and identify the virtualization detection techniques employed by the attacker.</p>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 1</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which WMI class did the attacker use to retrieve model and manufacturer information for virtualization detection?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The PowerShell Operational logs revealed that the attacker queried the <strong>Win32_ComputerSystem</strong> WMI class. This class provides information about the system's hardware, including the manufacturer and model.</p>
      <p>These values are commonly used in virtualization detection because virtual machines often expose identifiable manufacturer or model names such as:</p>
      <ul>
        <li>VMware</li>
        <li>VirtualBox</li>
        <li>Microsoft Corporation</li>
        <li>Virtual Machine</li>
      </ul>
      <p>The attacker compared these values against known virtualization platforms to determine whether the script was executing inside a virtual environment.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Relevant Command</div>
        <pre><code>Get-WmiObject Win32_ComputerSystem</code></pre>
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>Win32_ComputerSystem</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 2</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which WMI query did the attacker execute to retrieve the current temperature value of the machine?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The attacker queried the <strong>MSAcpi_ThermalZoneTemperature</strong> WMI class.</p>
      <p>Many virtual machines either report unrealistic temperature values or do not expose thermal information at all. Malware commonly checks this class as an additional indicator of virtualization.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">WMI Query</div>
        <pre><code>SELECT * FROM MSAcpi_ThermalZoneTemperature</code></pre>
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>SELECT * FROM MSAcpi_ThermalZoneTemperature</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 3</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        The attacker loaded a PowerShell script to detect virtualization. What is the function name of the script?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>Reviewing the Script Block Logging events (Event ID 4104) revealed a custom PowerShell function responsible for performing virtualization checks.</p>
      <p>The function consolidated multiple techniques, including:</p>
      <ul>
        <li>WMI queries</li>
        <li>Registry enumeration</li>
        <li>Process discovery</li>
      </ul>

      <p>Function identified:</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Function</div>
        <pre><code>Check-VM</code></pre>
      </div>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>Check-VM</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 4</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        Which registry key did the above script query to retrieve service details for virtualization detection?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The PowerShell script queried the Windows Services registry hive to enumerate installed services and drivers associated with virtualization software.</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Registry Path</div>
        <pre><code>HKLM:\SYSTEM\ControlSet001\Services</code></pre>
      </div>

      <p>The script searched for virtualization-related services commonly installed by hypervisors, including VMware and VirtualBox components.</p>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>HKLM:\SYSTEM\ControlSet001\Services</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 5</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        The VM detection script can also identify VirtualBox. Which processes is it comparing to determine if the system is running VirtualBox?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>The script enumerated running processes and compared them against known VirtualBox Guest Additions processes.</p>
      <p>The presence of either process strongly indicates that the host is running inside a VirtualBox virtual machine.</p>

      <p>Processes identified:</p>
      <ul>
        <li><code>vboxservice.exe</code></li>
        <li><code>vboxtray.exe</code></li>
      </ul>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>vboxservice.exe, vboxtray.exe</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Task 6</h2>

      <h3 class="writeup-h3">Question</h3>
      <div class="writeup-quote">
        The VM detection script prints any detection with the prefix "This is a". Which two virtualization platforms did the script detect?
      </div>

      <h3 class="writeup-h3">Investigation</h3>
      <p>After completing the hardware, registry, and process checks, the script identified the virtualization platform and displayed the result using the format:</p>

      <div class="writeup-code-block">
        <div class="writeup-code-header">Output Format</div>
        <pre><code>This is a &lt;platform&gt;</code></pre>
      </div>

      <p>The script successfully detected:</p>
      <ul>
        <li>Hyper-V</li>
        <li>VMware</li>
      </ul>

      <div class="writeup-answer">
        <span class="writeup-answer-label">Answer:</span>
        <code>Hyper-V, VMware</code>
      </div>
    </div>

    <div class="writeup-card">
      <h2 class="writeup-h2">Summary of Anti-Virtualization Techniques</h2>
      <p>During the investigation, the attacker employed several anti-virtualization techniques to determine whether the malware was executing inside a virtual machine:</p>
      <ul>
        <li>Queried the <strong>Win32_ComputerSystem</strong> WMI class to obtain the system manufacturer and model.</li>
        <li>Queried <strong>MSAcpi_ThermalZoneTemperature</strong> to examine thermal sensor data.</li>
        <li>Enumerated services through the Windows registry.</li>
        <li>Searched for VirtualBox Guest Additions processes.</li>
        <li>Compared collected information against known virtualization indicators.</li>
        <li>Reported the detected virtualization platform before continuing execution.</li>
      </ul>
      <p>These checks allow malware to recognize analysis environments and alter or suppress malicious behavior to evade detection.</p>

      <h3 class="writeup-h3" style="margin-top:20px;">MITRE ATT&CK Mapping</h3>
      <div class="writeup-table">
        <table>
          <tr><th>Technique</th><th>ATT&CK ID</th></tr>
          <tr><td>Virtualization/Sandbox Evasion: System Checks</td><td>T1497.001</td></tr>
          <tr><td>System Information Discovery</td><td>T1082</td></tr>
          <tr><td>Query Registry</td><td>T1012</td></tr>
          <tr><td>Process Discovery</td><td>T1057</td></tr>
          <tr><td>Windows Management Instrumentation (WMI)</td><td>T1047</td></tr>
        </table>
      </div>

      <h3 class="writeup-h3" style="margin-top:20px;">Conclusion</h3>
      <p>This Sherlock demonstrates how attackers use layered anti-virtualization techniques to identify sandboxed or virtualized environments before executing malicious actions. By combining WMI queries, registry enumeration, and process discovery, the PowerShell script was able to detect virtualization platforms such as Hyper-V, VMware, and VirtualBox.</p>
      <p>The investigation also highlights the importance of PowerShell Script Block Logging (Event ID 4104), which provided valuable visibility into the attacker's PowerShell functions and enabled the reconstruction of the virtualization detection workflow.</p>
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
