---
title: Tags
icon: fas fa-tag
order: 4
layout: default
---

<div class="tags-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:820px; width:100%;">

    <div class="term-section-header" style="margin-bottom:36px;">
      <span class="term-section-badge">// taxonomy</span>
      <h1>Tag_Index.idx</h1>
      <p class="term-section-desc">Browse content by topic. Each tag groups related posts and writeups together.</p>
    </div>

    {% assign tags = site.tags | sort %}
    {% if tags.size > 0 %}

    <div class="tag-cloud">
      {% for tag in tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_size = tag | last | size %}
      {% assign font_size = tag_size | times: 2 | plus: 80 %}
      {% if font_size > 160 %}{% assign font_size = 160 %}{% endif %}
      <a href="/tags/{{ tag_name | slugify }}/" class="tag-cloud-item" style="font-size: {{ font_size }}%" data-count="{{ tag_size }}">
        <span class="tag-cloud-name">{{ tag_name }}</span>
        <span class="tag-cloud-count">{{ tag_size }}</span>
      </a>
      {% endfor %}
    </div>

    <div class="tag-list">
      {% for tag in tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_posts = tag | last %}
      <div class="tag-group" id="tag-{{ tag_name | slugify }}">
        <div class="tag-group-header">
          <span class="material-symbols-outlined tag-group-icon">sell</span>
          <h2 class="tag-group-title">{{ tag_name }}</h2>
          <span class="tag-group-count">{{ tag_posts.size }} post{% if tag_posts.size > 1 %}s{% endif %}</span>
        </div>

        <div class="tag-post-list">
          {% for post in tag_posts %}
          <article class="tag-post-item">
            <time class="tag-post-date" datetime="{{ post.date | date: '%Y-%m-%d' }}">
              {{ post.date | date: '%b %d, %Y' }}
            </time>
            <h3 class="tag-post-title">
              <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            {% if post.description %}
            <p class="tag-post-desc">{{ post.description }}</p>
            {% endif %}
          </article>
          {% endfor %}
        </div>
      </div>
      {% endfor %}
    </div>

    {% else %}

    <div class="tag-empty">
      <span class="material-symbols-outlined" style="font-size:48px;color:rgba(201,160,220,0.15);">sell</span>
      <p>No tags found. Content hasn't been tagged yet.</p>
    </div>

    {% endif %}

  </div>
</div>

<style>
.tags-root {
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

/* ── Tag Cloud ── */
.tag-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
  padding: 24px;
  background: rgba(13, 11, 20, 0.4);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  margin-bottom: 48px;
}

.tag-cloud-item {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 16px;
  border-radius: 8px;
  background: rgba(201, 160, 220, 0.03);
  border: 1px solid rgba(201, 160, 220, 0.06);
  text-decoration: none !important;
  transition: all 0.25s ease;
  font-family: 'JetBrains Mono', monospace;
}
.tag-cloud-item:hover {
  background: rgba(201, 160, 220, 0.08);
  border-color: rgba(201, 160, 220, 0.2);
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(201, 160, 220, 0.06);
}

.tag-cloud-name {
  color: var(--mauve, #c9a0dc) !important;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.tag-cloud-count {
  font-size: 10px;
  color: rgba(196, 176, 204, 0.4);
  background: rgba(201, 160, 220, 0.04);
  padding: 1px 6px;
  border-radius: 4px;
}

/* ── Tag Groups ── */
.tag-group {
  margin-bottom: 36px;
}

.tag-group-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 16px;
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(201, 160, 220, 0.06);
}
.tag-group-icon {
  font-size: 20px !important;
  color: var(--mauve, #c9a0dc) !important;
}
.tag-group-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  letter-spacing: 1px;
}
.tag-group-count {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  margin-left: auto;
}

/* ── Tag Post List ── */
.tag-post-list {
  display: flex;
  flex-direction: column;
}

.tag-post-item {
  padding: 12px 16px;
  border-radius: 8px;
  transition: background 0.2s ease;
}
.tag-post-item:hover {
  background: rgba(201, 160, 220, 0.03);
}

.tag-post-date {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
}

.tag-post-title {
  margin: 2px 0 4px 0;
  font-size: 15px;
  font-weight: 600;
}
.tag-post-title a {
  color: var(--mauve-light, #e6c8f0) !important;
  text-decoration: none !important;
  transition: color 0.2s;
}
.tag-post-title a:hover {
  color: var(--mauve, #c9a0dc) !important;
}

.tag-post-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  margin: 0;
  line-height: 1.5;
}

/* ── Empty State ── */
.tag-empty {
  text-align: center;
  padding: 60px 20px;
}
.tag-empty p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: rgba(196, 176, 204, 0.4);
  margin-top: 16px;
}

@media (max-width: 600px) {
  .term-section-header h1 { font-size: 1.2rem; }
  .tag-cloud { padding: 16px; gap: 6px; }
  .tag-cloud-item { padding: 6px 12px; }
}
</style>
