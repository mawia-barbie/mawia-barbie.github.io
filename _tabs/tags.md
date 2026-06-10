---
title: Tags
icon: fas fa-tags
order: 4
layout: home
---

<div class="site-section" style="min-height:80vh; padding:60px 28px; display:flex; align-items:flex-start; justify-content:center; background:var(--bg-dark);">
  <div style="max-width:1100px; width:100%; color:var(--muted); text-align:center;">

    <h1 style="color:var(--neon-pink); margin-bottom:16px;">Tags</h1>
    <p style="color:var(--muted); margin-bottom:28px;">A quick view of topics and technologies.</p>

    <div style="display:flex; flex-wrap:wrap; justify-content:center; gap:12px;">
      {% for tag in site.tags %}
        <a href="/tags/{{ tag[0] | slugify }}/" class="tag-pill">{{ tag[0] }} ({{ tag[1].size }})</a>
      {% endfor %}
    </div>

  </div>
</div>

<style>
.tag-pill { display:inline-block; padding:10px 16px; border-radius:999px; background:linear-gradient(90deg, rgba(255,20,147,0.12), rgba(65,105,225,0.08)); color:var(--neon-pink); text-decoration:none; box-shadow: 0 0 14px rgba(255,105,180,0.06); border:1px solid rgba(255,105,180,0.06); }
.tag-pill:hover { transform:translateY(-3px); box-shadow:0 0 20px rgba(255,105,180,0.12); }
@media (max-width:820px){ .site-section { padding:30px 16px;} }
</style>