---
title: Archives
icon: fas fa-archive
order: 3
layout: home
---

<div class="site-section" style="min-height:100vh; padding:60px 28px; display:flex; align-items:flex-start; justify-content:center; background:var(--bg-dark);">
  <div style="max-width:1100px; width:100%; color:var(--muted);">
    <h1 style="color:var(--neon-pink); text-align:center; margin-bottom:12px;">Archives</h1>
    <p style="text-align:center; color:var(--muted); margin-bottom:28px;">Browse posts grouped by year.</p>

    <div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:20px;">
      {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
      {% for year_group in posts_by_year %}
      <div class="hud-panel">
        <h3 style="color:var(--neon-pink); margin-bottom:10px;">{{ year_group.name }}</h3>
        <ul style="list-style:none; padding:0; margin:0; color:var(--muted); display:flex; flex-direction:column; gap:8px;">
          {% for post in year_group.items %}
            <li><a href="{{ post.url }}" style="color:var(--muted); text-decoration:none;">• {{ post.title }}</a></li>
          {% endfor %}
        </ul>
      </div>
      {% endfor %}
    </div>

  </div>
</div>

<style>
.hud-panel { background: rgba(6,8,12,0.6); padding:18px; border-radius:12px; box-shadow: 0 0 22px rgba(255,105,180,0.06); border:1px solid rgba(255,105,180,0.06); backdrop-filter: blur(6px); }
.hud-panel a:hover { color:var(--neon-pink); text-decoration:underline; }
@media (max-width:820px){ .site-section { padding:30px 16px;} }
</style>
