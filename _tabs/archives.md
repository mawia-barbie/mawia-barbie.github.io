---
title: Archives
icon: fas fa-archive
order: 3
layout: default
---

<div class="archives-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:820px; width:100%;">

    <div class="term-section-header" style="margin-bottom:36px;">
      <span class="term-section-badge">// history</span>
      <h1>Archive_Log.db</h1>
      <p class="term-section-desc">All posts and writeups organized by date. Browse the complete archive below.</p>
    </div>

    {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

    {% for year_group in posts_by_year %}
    <div class="archive-year-group">
      <div class="archive-year-header">
        <span class="archive-year-icon">📁</span>
        <h2 class="archive-year-title">{{ year_group.name }}</h2>
        <span class="archive-year-count">{{ year_group.items | size }} posts</span>
      </div>

      <div class="archive-post-list">
        {% for post in year_group.items %}
        <article class="archive-post-item">
          <time class="archive-post-date" datetime="{{ post.date | date: '%Y-%m-%d' }}">
            {{ post.date | date: '%b %d' }}
          </time>
          <div class="archive-post-body">
            <h3 class="archive-post-title">
              <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            {% if post.description %}
            <p class="archive-post-desc">{{ post.description }}</p>
            {% endif %}
            <div class="archive-post-tags">
              {% for tag in post.tags limit:4 %}
              <span class="archive-tag">{{ tag }}</span>
              {% endfor %}
              {% if post.tags.size > 4 %}
              <span class="archive-tag more">+{{ post.tags.size | minus: 4 }}</span>
              {% endif %}
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
    </div>
    {% endfor %}

    {% if site.posts.size == 0 %}
    <div class="archive-empty">
      <span class="material-symbols-outlined" style="font-size:48px;color:rgba(201,160,220,0.15);">inbox</span>
      <p>No posts yet. The archive is awaiting its first entry.</p>
    </div>
    {% endif %}

  </div>
</div>

<style>
.archives-root {
  width: 100%;
  background: transparent;
}

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

/* ── Year Group ── */
.archive-year-group {
  margin-bottom: 40px;
}

.archive-year-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 16px;
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(201, 160, 220, 0.06);
}
.archive-year-icon { font-size: 20px; }
.archive-year-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.2rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  letter-spacing: 1px;
}
.archive-year-count {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  margin-left: auto;
}

/* ── Post List ── */
.archive-post-list {
  display: flex;
  flex-direction: column;
}

.archive-post-item {
  display: flex;
  gap: 20px;
  padding: 14px 16px;
  border-radius: 8px;
  transition: background 0.2s ease;
  text-decoration: none !important;
}
.archive-post-item:hover {
  background: rgba(201, 160, 220, 0.03);
}

.archive-post-date {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: rgba(196, 176, 204, 0.4);
  min-width: 56px;
  padding-top: 2px;
  flex-shrink: 0;
}

.archive-post-body { flex: 1; }

.archive-post-title {
  margin: 0 0 4px 0;
  font-size: 15px;
  font-weight: 600;
}
.archive-post-title a {
  color: var(--mauve-light, #e6c8f0) !important;
  text-decoration: none !important;
  transition: color 0.2s;
}
.archive-post-title a:hover {
  color: var(--mauve, #c9a0dc) !important;
}

.archive-post-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  margin: 0 0 6px 0;
  line-height: 1.5;
}

.archive-post-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 4px;
}

.archive-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  padding: 2px 6px;
  border-radius: 3px;
  background: rgba(201, 160, 220, 0.04);
  border: 1px solid rgba(201, 160, 220, 0.06);
  color: rgba(196, 176, 204, 0.6);
  text-transform: uppercase;
  letter-spacing: 0.3px;
}
.archive-tag.more {
  background: rgba(201, 160, 220, 0.02);
  border-color: rgba(201, 160, 220, 0.04);
  color: rgba(196, 176, 204, 0.3);
}

/* ── Empty State ── */
.archive-empty {
  text-align: center;
  padding: 60px 20px;
}
.archive-empty p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: rgba(196, 176, 204, 0.4);
  margin-top: 16px;
}

@media (max-width: 600px) {
  .archive-post-item { flex-direction: column; gap: 6px; }
  .archive-post-date { min-width: auto; }
  .term-section-header h1 { font-size: 1.2rem; }
}
</style>
