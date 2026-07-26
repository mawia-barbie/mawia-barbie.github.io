---
title: Categories
icon: fas fa-th-large
order: 2
layout: home
---

<div class="categories-root" style="min-height:100vh; display:flex; align-items:flex-start; justify-content:center; padding:80px 20px 40px; width:100%;">
  <div style="max-width:1100px; width:100%;">

    <div class="term-section-header" style="margin-bottom:36px;">
      <span class="term-section-badge">// archives</span>
      <h1>Project_Archive.db</h1>
      <p class="term-section-desc">Projects and writeups grouped by category. Select a category to explore.</p>
    </div>

    <div class="cats-grid">

      <!-- Sherlock Rooms -->
      <div class="cat-panel">
        <div class="cat-panel-head">
          <span class="material-symbols-outlined cat-panel-icon">search_insights</span>
          <span class="cat-panel-num">01</span>
        </div>
        <h3 class="cat-panel-title">Sherlock Rooms</h3>
        <p class="cat-panel-desc">In-depth investigation write-ups for complex blue-team scenarios focusing on host-based forensics and threat hunting.</p>
        <div class="cat-panel-meta">
          <span class="cat-tag">DFIR</span>
          <span class="cat-tag">Blue Team</span>
          <span class="cat-tag">Host Forensics</span>
        </div>
        <a href="/sherlock-labs/" class="cat-panel-link">View Cases →</a>
      </div>

      <!-- Python Tools -->
      <div class="cat-panel">
        <div class="cat-panel-head">
          <span class="material-symbols-outlined cat-panel-icon">code</span>
          <span class="cat-panel-num">02</span>
        </div>
        <h3 class="cat-panel-title">Python Tools</h3>
        <p class="cat-panel-desc">Custom security tooling for log analysis, network scanning, packet manipulation, and automation.</p>
        <div class="cat-panel-meta">
          <span class="cat-tag">Python</span>
          <span class="cat-tag">Scripting</span>
          <span class="cat-tag">Automation</span>
        </div>
        <a href="https://github.com/mawia-barbie/portscanner_with-_nmap" class="cat-panel-link">View on GitHub →</a>
      </div>

    </div>

  </div>
</div>

<style>
.categories-root {
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

/* ── Category Grid ── */
.cats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.cat-panel {
  background: rgba(13, 11, 20, 0.5);
  border: 1px solid rgba(201, 160, 220, 0.06);
  border-radius: 12px;
  padding: 28px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.cat-panel::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, var(--mauve, #c9a0dc), transparent);
  opacity: 0.2;
  transition: opacity 0.3s;
}
.cat-panel:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 60px rgba(201, 160, 220, 0.06);
  border-color: rgba(201, 160, 220, 0.15);
}
.cat-panel:hover::before { opacity: 0.8; }

.cat-panel-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}
.cat-panel-icon {
  font-size: 32px !important;
  color: var(--mauve, #c9a0dc) !important;
}
.cat-panel-num {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: rgba(201, 160, 220, 0.2);
}

.cat-panel-title {
  font-family: 'JetBrains Mono', monospace;
  font-size: 1.1rem;
  color: var(--mauve-light, #e6c8f0) !important;
  margin: 0 0 10px 0;
}

.cat-panel-desc {
  font-size: 13px;
  color: var(--muted, #c4b0cc);
  margin: 0 0 16px 0;
  line-height: 1.6;
  flex: 1;
}

.cat-panel-meta {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 18px;
}
.cat-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  padding: 3px 8px;
  border-radius: 4px;
  background: rgba(201, 160, 220, 0.04);
  border: 1px solid rgba(201, 160, 220, 0.08);
  color: rgba(196, 176, 204, 0.7);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.cat-panel-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--mauve, #c9a0dc) !important;
  text-decoration: none !important;
  transition: all 0.2s;
  margin-top: auto;
}
.cat-panel-link:hover {
  color: var(--mauve-light, #e6c8f0) !important;
  padding-left: 4px;
}

@media (max-width: 820px) {
  .cats-grid { grid-template-columns: 1fr; }
  .term-section-header h1 { font-size: 1.2rem; }
  .cat-panel { padding: 20px; }
}
</style>
