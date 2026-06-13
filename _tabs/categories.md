---
title: Categories
icon: fas fa-th-large
order: 2
layout: home
---

<div class="site-section" style="min-height:100vh; padding:60px 28px; display:flex; align-items:flex-start; justify-content:center; background:var(--bg-dark);">
  <div style="max-width:1100px; width:100%; color:var(--muted);">
    <h1 style="color:var(--neon-pink); text-align:center; margin-bottom:18px;">Categories</h1>
    <p style="text-align:center; color:var(--muted); margin-bottom:32px;">Projects and writeups grouped by topic. Click to explore.</p>

    <div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:24px;">

      <div class="hud-panel">
        <h3 style="color:var(--neon-pink); margin-bottom:8px;">HTB Walkthroughs</h3>
        <p style="color:var(--muted);">Step-by-step walkthroughs and reports for HTB labs and CTF writeups.</p>
        <p style="margin-top:12px;"><a class="neon-btn" href="/categories/htb-walkthroughs/">Explore</a></p>
      </div>

      <div class="hud-panel">
        <h3 style="color:var(--neon-blue); margin-bottom:8px;">Python Tools</h3>
        <p style="color:var(--muted);">Scripts and tools for automation, scanning, and exploitation.</p>
        <p style="margin-top:12px;"><a class="neon-btn" href="https://github.com/mawia-barbie/portscanner_with-_nmap">Explore</a></p>
      </div>

      <div class="hud-panel">
        <h3 style="color:var(--neon-purple); margin-bottom:8px;">Other Projects</h3>
        <p style="color:var(--muted);">Miscellaneous experiments and small apps.</p>
        <p style="margin-top:12px;"><a class="neon-btn" href="/categories/other-projects/">Explore</a></p>
      </div>

    </div>

  </div>
</div>


<style>
.hud-panel { background: rgba(6,8,12,0.6); padding:20px; border-radius:12px; box-shadow: 0 0 22px rgba(255,105,180,0.06); border:1px solid rgba(255,105,180,0.06); backdrop-filter: blur(6px); }
.hud-panel h3 { text-shadow: 0 0 8px rgba(255,105,180,0.12); }
.site-section a.neon-btn { margin:0; }
@media (max-width:820px){ .site-section { padding:30px 16px;} }
</style>