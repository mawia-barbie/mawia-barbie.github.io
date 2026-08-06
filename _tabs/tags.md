---
title: Tags
icon: fas fa-tag
order: 4
layout: default
---

<div class="tags-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:860px; width:100%;">

    <div class="term-section-header" style="margin-bottom:36px;">
      <span class="term-section-badge">// taxonomy</span>
      <h1>Tag_Index.idx</h1>
      <p class="term-section-desc">Browse the knowledge base by topic. Every post is indexed under its tags — add a <code>tags:</code> list to any post's front matter and it appears here automatically.</p>
    </div>

    {% assign tags = site.tags | sort %}
    {% if tags.size > 0 %}
    {% assign tagged_posts = site.posts | where_exp: "p", "p.tags.size > 0" %}

    <!-- ── Controls: search + sort ── -->
    <div class="tag-controls">
      <div class="tag-search-wrap" role="search">
        <span class="material-symbols-outlined tag-search-icon" aria-hidden="true">search</span>
        <input
          type="search"
          id="tag-search"
          class="tag-search-input"
          placeholder="Filter tags &amp; posts… e.g. wazuh, sysmon, sherlock"
          aria-label="Search tags and posts"
          autocomplete="off"
          spellcheck="false"
        />
        <button class="tag-search-clear" id="tag-search-clear" aria-label="Clear search">✕</button>
      </div>

      <div class="tag-sort" role="group" aria-label="Sort tags">
        <button class="tag-sort-btn active" id="tag-sort-name" type="button" data-sort="name" aria-pressed="true">A–Z</button>
        <button class="tag-sort-btn" id="tag-sort-count" type="button" data-sort="count" aria-pressed="false">By posts</button>
      </div>
    </div>

    <div class="tag-stats" aria-live="polite">
      <span id="tag-stats-text">{{ tags.size }} tag{% if tags.size != 1 %}s{% endif %} · {{ tagged_posts.size }} post{% if tagged_posts.size != 1 %}s{% endif %}</span>
    </div>

    <!-- ── Quick-jump cloud ── -->
    <div class="tag-cloud" id="tag-cloud" aria-label="Quick jump to a tag">
      {% for tag in tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_size = tag | last | size %}
      <button class="tag-cloud-item" type="button" data-tag-target="tag-{{ tag_name | slugify }}">
        <span class="tag-cloud-name">{{ tag_name }}</span>
        <span class="tag-cloud-count">{{ tag_size }}</span>
      </button>
      {% endfor %}
    </div>

    <!-- ── Tag groups ── -->
    <div class="tag-list" id="tag-groups">
      {% for tag in tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_posts = tag | last | sort: 'date' | reverse %}
      <section class="tag-group" id="tag-{{ tag_name | slugify }}" data-tag-count="{{ tag_posts.size }}">
        <div class="tag-group-header" role="button" tabindex="0" aria-expanded="true" aria-controls="tag-posts-{{ tag_name | slugify }}">
          <span class="material-symbols-outlined tag-group-icon" aria-hidden="true">sell</span>
          <h2 class="tag-group-title">{{ tag_name }}</h2>
          <span class="tag-group-count" aria-label="{{ tag_posts.size }} post{% if tag_posts.size != 1 %}s{% endif %}">{{ tag_posts.size }}</span>
          <span class="material-symbols-outlined tag-group-chevron" aria-hidden="true">expand_more</span>
        </div>

        <div class="tag-post-list" id="tag-posts-{{ tag_name | slugify }}">
          <div class="tag-post-list-inner">
            {% for post in tag_posts %}
            <article class="tag-post-item">
              <time class="tag-post-date" datetime="{{ post.date | date: '%Y-%m-%d' }}">
                {{ post.date | date: '%b %d, %Y' }}
              </time>
              <div class="tag-post-body">
                <h3 class="tag-post-title">
                  <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
                </h3>
                {% if post.description %}
                <p class="tag-post-desc">{{ post.description }}</p>
                {% endif %}
              </div>
            </article>
            {% endfor %}
          </div>
        </div>
      </section>
      {% endfor %}
    </div>

    <!-- ── No search results ── -->
    <div class="tag-no-results" id="tag-no-results" style="display:none;">
      <span class="material-symbols-outlined" aria-hidden="true">search_off</span>
      <p>No tags match “<span id="tag-no-results-query"></span>”.</p>
    </div>

    {% else %}

    <!-- ── Empty state ── -->
    <div class="tag-empty">
      <span class="material-symbols-outlined" aria-hidden="true">sell</span>
      <h2>Tag index is empty</h2>
      <p>No tags have been indexed yet. Add a <code>tags:</code> list to any post's front matter — e.g. <code>tags: [sherlock, dfir, threat-hunting]</code> — and it will be grouped and searchable here automatically.</p>
    </div>

    {% endif %}

  </div>
</div>

<style>
.tags-root {
  width: 100%;
  background: transparent;
}

/* ── Section Header ── */
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
.term-section-desc code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--mauve-light, #e6c8f0);
  background: rgba(201, 160, 220, 0.06);
  border: 1px solid rgba(201, 160, 220, 0.12);
  padding: 1px 6px;
  border-radius: 4px;
}

/* ── Controls ── */
.tag-controls {
  display: flex;
  align-items: stretch;
  gap: 12px;
  flex-wrap: wrap;
  margin-bottom: 14px;
}

.tag-search-wrap {
  position: relative;
  flex: 1 1 300px;
  min-width: 220px;
}
.tag-search-icon {
  position: absolute;
  left: 14px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 18px !important;
  color: rgba(196, 176, 204, 0.35);
  pointer-events: none;
  transition: color 0.2s;
}
.tag-search-wrap:focus-within .tag-search-icon {
  color: var(--mauve, #c9a0dc);
}
.tag-search-input {
  width: 100%;
  box-sizing: border-box;
  background: rgba(13, 11, 20, 0.6);
  border: 1px solid rgba(201, 160, 220, 0.1);
  border-radius: 8px;
  padding: 11px 42px 11px 42px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  color: var(--mauve-light, #e6c8f0);
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s, background 0.2s;
}
.tag-search-input::placeholder {
  color: rgba(196, 176, 204, 0.3);
}
.tag-search-input:focus {
  border-color: rgba(201, 160, 220, 0.35);
  background: rgba(13, 11, 20, 0.8);
  box-shadow: 0 0 0 3px rgba(201, 160, 220, 0.06), 0 0 24px rgba(201, 160, 220, 0.05);
}
.tag-search-input::-webkit-search-cancel-button {
  -webkit-appearance: none;
  appearance: none;
}
.tag-search-clear {
  position: absolute;
  right: 8px;
  top: 50%;
  transform: translateY(-50%);
  width: 26px;
  height: 26px;
  border-radius: 6px;
  border: none;
  background: transparent;
  color: rgba(196, 176, 204, 0.4);
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  line-height: 1;
  cursor: pointer;
  opacity: 0;
  pointer-events: none;
  transition: all 0.15s;
}
.tag-search-clear.visible {
  opacity: 1;
  pointer-events: auto;
}
.tag-search-clear:hover {
  color: var(--mauve-light, #e6c8f0);
  background: rgba(201, 160, 220, 0.08);
}

/* ── Sort toggle ── */
.tag-sort {
  display: inline-flex;
  gap: 4px;
  padding: 4px;
  background: rgba(13, 11, 20, 0.6);
  border: 1px solid rgba(201, 160, 220, 0.1);
  border-radius: 8px;
  align-self: center;
}
.tag-sort-btn {
  padding: 8px 14px;
  border-radius: 6px;
  border: none;
  background: transparent;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  color: rgba(196, 176, 204, 0.5);
  cursor: pointer;
  transition: all 0.18s;
}
.tag-sort-btn:hover {
  color: var(--mauve-light, #e6c8f0);
}
.tag-sort-btn.active {
  background: rgba(201, 160, 220, 0.1);
  color: var(--mauve-light, #e6c8f0);
  box-shadow: inset 0 0 0 1px rgba(201, 160, 220, 0.25);
}

/* ── Stats line ── */
.tag-stats {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.35);
  letter-spacing: 1px;
  text-transform: uppercase;
  margin: 0 2px 18px;
}

/* ── Tag cloud ── */
.tag-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 18px;
  margin-bottom: 32px;
  background: rgba(13, 11, 20, 0.4);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
}
.tag-cloud-item {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 7px 12px;
  border-radius: 6px;
  border: 1px solid rgba(201, 160, 220, 0.08);
  background: rgba(201, 160, 220, 0.03);
  color: var(--mauve, #c9a0dc) !important;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  cursor: pointer;
  transition: all 0.2s;
}
.tag-cloud-item:hover {
  background: rgba(201, 160, 220, 0.1);
  border-color: rgba(201, 160, 220, 0.25);
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(201, 160, 220, 0.08);
}
.tag-cloud-item.dimmed {
  opacity: 0.3;
}
.tag-cloud-count {
  font-size: 9px;
  padding: 1px 6px;
  border-radius: 4px;
  background: rgba(201, 160, 220, 0.06);
  color: rgba(196, 176, 204, 0.5);
}

/* ── Tag group cards ── */
.tag-group {
  margin-bottom: 16px;
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  overflow: hidden;
  position: relative;
  transition: border-color 0.25s, box-shadow 0.25s, transform 0.25s;
  animation: tagFadeIn 0.4s ease both;
}
.tag-group::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, var(--mauve, #c9a0dc), transparent);
  opacity: 0.15;
  transition: opacity 0.3s;
}
.tag-group:hover {
  transform: translateY(-3px);
  border-color: rgba(201, 160, 220, 0.14);
  box-shadow: 0 14px 40px rgba(201, 160, 220, 0.05);
}
.tag-group:hover::before { opacity: 0.7; }

@keyframes tagFadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to { opacity: 1; transform: none; }
}

/* Jump-flash highlight after clicking a cloud chip */
@keyframes tagFlash {
  0%   { box-shadow: 0 0 0 1px rgba(201, 160, 220, 0.5), 0 0 34px rgba(201, 160, 220, 0.16); }
  100% { box-shadow: 0 0 0 1px rgba(201, 160, 220, 0), 0 0 0 rgba(201, 160, 220, 0); }
}
.tag-group.flash {
  animation: tagFlash 1.2s ease;
}

/* ── Group header ── */
.tag-group-header {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 16px 20px;
  cursor: pointer;
  user-select: none;
  outline: none;
  transition: background 0.2s;
}
.tag-group-header:hover {
  background: rgba(201, 160, 220, 0.03);
}
.tag-group-header:focus-visible {
  box-shadow: inset 0 0 0 2px rgba(201, 160, 220, 0.3);
  border-radius: 12px 12px 0 0;
}
.tag-group-icon {
  font-size: 18px !important;
  color: var(--mauve, #c9a0dc) !important;
}
.tag-group-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.05rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0;
  letter-spacing: 1px;
}
.tag-group-count {
  margin-left: auto;
  min-width: 28px;
  text-align: center;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--mauve-light, #e6c8f0);
  background: rgba(201, 160, 220, 0.08);
  border: 1px solid rgba(201, 160, 220, 0.14);
  padding: 2px 9px;
  border-radius: 999px;
}
.tag-group-chevron {
  font-size: 18px !important;
  color: rgba(196, 176, 204, 0.3);
  transition: transform 0.25s ease;
}
.tag-group.collapsed .tag-group-chevron {
  transform: rotate(-90deg);
}

/* ── Collapse animation ── */
.tag-post-list {
  display: grid;
  grid-template-rows: 1fr;
  transition: grid-template-rows 0.3s ease;
}
.tag-post-list-inner {
  overflow: hidden;
  min-height: 0;
  visibility: visible;
  transition: visibility 0s;
}
.tag-group.collapsed .tag-post-list {
  grid-template-rows: 0fr;
}
/* Hide after the collapse animation finishes so links leave the tab order */
.tag-group.collapsed .tag-post-list-inner {
  visibility: hidden;
  transition: visibility 0s 0.3s;
}

/* ── Post items ── */
.tag-post-item {
  display: flex;
  gap: 18px;
  align-items: baseline;
  padding: 12px 20px;
  border-top: 1px solid rgba(201, 160, 220, 0.04);
  transition: background 0.18s;
}
.tag-post-item:hover {
  background: rgba(201, 160, 220, 0.03);
}
.tag-post-date {
  flex-shrink: 0;
  min-width: 96px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: rgba(196, 176, 204, 0.4);
  padding-top: 2px;
}
.tag-post-body {
  flex: 1;
  min-width: 0;
}
.tag-post-title {
  margin: 0 0 3px 0;
  font-size: 14.5px;
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

/* ── No search results ── */
.tag-no-results {
  text-align: center;
  padding: 48px 20px;
  border: 1px dashed rgba(201, 160, 220, 0.12);
  border-radius: 12px;
}
.tag-no-results .material-symbols-outlined {
  font-size: 40px !important;
  color: rgba(201, 160, 220, 0.15);
}
.tag-no-results p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: rgba(196, 176, 204, 0.45);
  margin: 12px 0 0;
}

/* ── Empty state ── */
.tag-empty {
  text-align: center;
  padding: 64px 24px;
  background: rgba(13, 11, 20, 0.5);
  border: 1px dashed rgba(201, 160, 220, 0.14);
  border-radius: 12px;
}
.tag-empty .material-symbols-outlined {
  font-size: 44px !important;
  color: rgba(201, 160, 220, 0.15);
}
.tag-empty h2 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 14px 0 8px;
  letter-spacing: 1px;
}
.tag-empty p {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12.5px;
  color: rgba(196, 176, 204, 0.5);
  line-height: 1.7;
  max-width: 480px;
  margin: 0 auto;
}
.tag-empty code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11.5px;
  color: var(--mauve-light, #e6c8f0);
  background: rgba(201, 160, 220, 0.06);
  border: 1px solid rgba(201, 160, 220, 0.12);
  padding: 1px 6px;
  border-radius: 4px;
}

/* ── Reduced motion ── */
@media (prefers-reduced-motion: reduce) {
  .tag-group { animation: none; }
  .tag-group.flash { animation: none; }
  .tag-group:hover { transform: none; }
  .tag-cloud-item:hover { transform: none; }
  .tag-post-list, .tag-post-list-inner { transition: none; }
  .tag-group-chevron { transition: none; }
  html { scroll-behavior: auto; }
}

/* ── Responsive ── */
@media (max-width: 640px) {
  .term-section-header h1 { font-size: 1.2rem; }
  .tag-controls { flex-direction: column; }
  .tag-sort { align-self: stretch; justify-content: center; }
  .tag-sort-btn { flex: 1; }
  .tag-post-item { flex-direction: column; gap: 4px; align-items: flex-start; }
  .tag-post-date { min-width: 0; }
  .tag-cloud { padding: 12px; }
  .tag-group-header { padding: 14px 16px; }
  .tag-post-item { padding: 10px 16px; }
}
</style>

<script>
(function () {
  'use strict';

  var searchInput = document.getElementById('tag-search');
  var searchClear = document.getElementById('tag-search-clear');
  var sortNameBtn = document.getElementById('tag-sort-name');
  var sortCountBtn = document.getElementById('tag-sort-count');
  var groupsWrap = document.getElementById('tag-groups');
  var noResults = document.getElementById('tag-no-results');
  var noResultsQuery = document.getElementById('tag-no-results-query');
  var statsText = document.getElementById('tag-stats-text');
  var cloud = document.getElementById('tag-cloud');

  // No tag groups rendered (empty index) — nothing to wire up.
  if (!groupsWrap) return;

  var groups = Array.prototype.slice.call(groupsWrap.querySelectorAll('.tag-group'));
  var cloudItems = cloud
    ? Array.prototype.slice.call(cloud.querySelectorAll('.tag-cloud-item'))
    : [];

  var sortMode = 'name';
  var query = '';

  function normalize(s) {
    return (s || '').toLowerCase().replace(/\s+/g, ' ').trim();
  }

  function tagNameOf(group) {
    var title = group.querySelector('.tag-group-title');
    return normalize(title ? title.textContent : '');
  }

  function applyFilter() {
    var q = normalize(query);
    var visible = 0;

    groups.forEach(function (g) {
      var tagMatches = q === '' || tagNameOf(g).indexOf(q) !== -1;
      var items = Array.prototype.slice.call(g.querySelectorAll('.tag-post-item'));
      var anyPost = false;

      items.forEach(function (it) {
        var match = tagMatches || normalize(it.textContent).indexOf(q) !== -1;
        it.style.display = match ? '' : 'none';
        if (match) anyPost = true;
      });

      var show = q === '' || tagMatches || anyPost;
      g.style.display = show ? '' : 'none';
      if (show) visible++;
    });

    if (cloud) {
      cloudItems.forEach(function (chip) {
        var target = chip.getAttribute('data-tag-target');
        var g = document.getElementById(target);
        chip.classList.toggle('dimmed', !!g && g.style.display === 'none');
      });
    }

    if (noResults) {
      noResults.style.display = visible === 0 ? '' : 'none';
      if (noResultsQuery) noResultsQuery.textContent = query;
    }
    if (statsText) {
      var total = groups.length;
      var plural = total === 1 ? 'tag' : 'tags';
      statsText.textContent =
        visible === total
          ? total + ' ' + plural
          : 'showing ' + visible + ' of ' + total + ' ' + plural;
    }
  }

  function applySort() {
    var sorted = groups.slice().sort(function (a, b) {
      var cmp;
      if (sortMode === 'count') {
        cmp = (parseInt(b.getAttribute('data-tag-count'), 10) || 0) -
              (parseInt(a.getAttribute('data-tag-count'), 10) || 0);
        if (cmp === 0) cmp = tagNameOf(a).localeCompare(tagNameOf(b));
      } else {
        cmp = tagNameOf(a).localeCompare(tagNameOf(b));
      }
      return cmp;
    });
    sorted.forEach(function (g) { groupsWrap.appendChild(g); });
    applyFilter();
  }

  function setSort(mode) {
    sortMode = mode;
    sortNameBtn.classList.toggle('active', mode === 'name');
    sortCountBtn.classList.toggle('active', mode === 'count');
    if (sortNameBtn) sortNameBtn.setAttribute('aria-pressed', mode === 'name' ? 'true' : 'false');
    if (sortCountBtn) sortCountBtn.setAttribute('aria-pressed', mode === 'count' ? 'true' : 'false');
    applySort();
  }

  function toggleGroup(g) {
    var collapsed = g.classList.toggle('collapsed');
    var header = g.querySelector('.tag-group-header');
    if (header) header.setAttribute('aria-expanded', collapsed ? 'false' : 'true');
  }

  // ── Search ──
  if (searchInput) {
    searchInput.addEventListener('input', function () {
      query = searchInput.value;
      if (searchClear) searchClear.classList.toggle('visible', query.length > 0);
      applyFilter();
    });
  }

  if (searchClear) {
    searchClear.addEventListener('click', function () {
      query = '';
      searchInput.value = '';
      searchClear.classList.remove('visible');
      applyFilter();
      searchInput.focus();
    });
  }

  // ── Sort ──
  if (sortNameBtn) {
    sortNameBtn.addEventListener('click', function () { setSort('name'); });
  }
  if (sortCountBtn) {
    sortCountBtn.addEventListener('click', function () { setSort('count'); });
  }

  // ── Collapsible groups ──
  groupsWrap.addEventListener('click', function (e) {
    var header = e.target.closest('.tag-group-header');
    if (header) toggleGroup(header.parentElement);
  });
  groupsWrap.addEventListener('keydown', function (e) {
    var header = e.target.closest('.tag-group-header');
    if (header && (e.key === 'Enter' || e.key === ' ')) {
      e.preventDefault();
      toggleGroup(header.parentElement);
    }
  });

  // ── Cloud chips: jump to section ──
  if (cloud) {
    cloud.addEventListener('click', function (e) {
      var chip = e.target.closest('.tag-cloud-item');
      if (!chip) return;
      var g = document.getElementById(chip.getAttribute('data-tag-target'));
      if (!g) return;
      if (g.classList.contains('collapsed')) toggleGroup(g);
      g.classList.remove('flash');
      void g.offsetWidth; // restart animation
      g.classList.add('flash');
      var reduceMotion =
        window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
      g.scrollIntoView({ behavior: reduceMotion ? 'auto' : 'smooth', block: 'start' });
    });
  }

  // ── "/" focuses the search box ──
  document.addEventListener('keydown', function (e) {
    if (e.key !== '/' || e.metaKey || e.ctrlKey || e.altKey) return;
    var tag = (e.target.tagName || '').toLowerCase();
    var typing = tag === 'input' || tag === 'textarea' || tag === 'select' || e.target.isContentEditable;
    if (!typing) {
      e.preventDefault();
      if (searchInput) {
        searchInput.focus();
        searchInput.select();
      }
    }
  });

  // Initial render (alphabetical by default)
  applySort();
})();
</script>
