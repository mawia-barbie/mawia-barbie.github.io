---
title: About
icon: fas fa-user
order: 1
layout: home
---

<!-- Vertically centered About content, nudged slightly lower -->
<div style="display:flex; align-items:center; justify-content:center; min-height:100vh; padding:20px 20px 60px;">
  <div style="max-width:920px; width:100%; text-align:center; margin-top:80px;">

    <h1 style="color:var(--neon-pink); margin:0 0 12px 0;">Hey, I’m Grace Mawia 👋</h1>

    <p style="color:var(--muted); font-size:1.06em; max-width:760px; margin:0 auto 22px auto;">
      I’m a <strong style="color:var(--neon-pink);">cybersecurity professional</strong> and Python tinkerer who loves building projects, hunting vulnerabilities, and solving challenging CTFs.
    </p>

    <!-- Skills & Tools side-by-side but without card backgrounds -->
    <div style="display:flex; justify-content:center; gap:40px; flex-wrap:wrap; margin-bottom:22px;">

      <div style="width:300px; text-align:center;">
        <h3 style="color:var(--neon-pink); margin:0 0 10px 0;">Skills</h3>
        <ul style="list-style:none; padding:0; margin:0; color:var(--muted); display:flex; flex-direction:column; gap:6px; align-items:center;">
          <li>Python 🐍</li>
          <li>Web Security 🔒</li>
          <li>Linux 🖥️</li>
          <li>Networking 🌐</li>
          <li>Threat Analysis 🕵️‍♂️</li>
        </ul>
      </div>

      <div style="width:300px; text-align:center;">
        <h3 style="color:var(--neon-pink); margin:0 0 10px 0;">Tools</h3>
        <ul style="list-style:none; padding:0; margin:0; color:var(--muted); display:flex; flex-direction:column; gap:6px; align-items:center;">
          <li>HTB Labs 🧩</li>
          <li>Burp Suite 🛠️</li>
          <li>Nmap 🌐</li>
          <li>Wireshark 📡</li>
          <li>John the Ripper 🔑</li>
        </ul>
      </div>

    </div>

    <!-- Connect Section (plain buttons remain) -->
    <div style="margin-top:8px;">
      <h2 style="color:var(--neon-pink); margin-bottom:10px;">Connect with Me</h2>
      <div style="display:flex; gap:12px; justify-content:center;">
        <a class="neon-btn" href="https://github.com/mawia">🐱 GitHub</a>
        <a class="neon-btn" href="https://linkedin.com/in/mawia">💼 LinkedIn</a>
        <a class="neon-btn" href="https://twitter.com/mawia">🐦 Twitter</a>
      </div>
    </div>

  </div>
</div>

<style>
@media (max-width: 820px) {
  div[style*="max-width:920px"] { padding:20px; margin-top:20px !important; }
}
</style>