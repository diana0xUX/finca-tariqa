# Skill: tariqa-engineering

**Purpose:** Guide AI agents through the technical conventions of the Finca Tariqa static site — CSS architecture, HTML patterns, image handling, blog rules, and safe change practices.

**When to use:** Before editing any HTML or CSS file. Before working with images or audio. Before touching blog posts.

**Relationships with other skills:** Works alongside `tariqa-brand` (design constraints) and `tariqa-editorial` (content constraints).

---

## Architecture overview

- Pure static HTML + CSS + vanilla JS
- No build step, no npm, no framework
- Single shared stylesheet: `style.css` (root)
- Page-specific CSS: `<style>` blocks inside each HTML `<head>`
- Fonts: Google Fonts CDN (Lora + Plus Jakarta Sans)
- Hosting: GitHub Pages, auto-deploy from `main` branch
- Local preview: `python3 -m http.server 8765` → `http://localhost:8765/<page>.html`

---

## CSS architecture

### What goes where

| Location | Contents |
|----------|----------|
| `style.css` | CSS variables, reset, typography, nav, buttons, footer, `.section`, `.hero`, utility classes, responsive breakpoints |
| `<style>` in `<head>` | Page-specific layout, section-specific components, hero variants for that page only |

**Never** move page-specific styles into `style.css`. **Never** put reusable utilities in page `<style>` blocks.

### CSS variables — always use, never hardcode

```css
/* Colours */
--earth-dark, --earth-mid, --earth-med, --earth-light
--sand, --sand-deep, --terracotta, --gold, --white, --ink, --mid

/* Layout */
--nav-height: 68px
--radius-sm: 4px  --radius-md: 8px  --radius-lg: 16px  --radius-xl: 24px
--transition: 0.22s ease
```

### Responsive breakpoints (in style.css)
- 900px: grid-3 → 1 col; why-grid / carbon-grid on forest.html collapse
- 700px: grid-2 → 1 col; mobile nav activates (hamburger toggle)
- 480px: grid-4 → 1 col; stat-strip stacks vertically

Every new grid or multi-column layout needs a mobile collapse at 700px at minimum.

---

## HTML patterns

### Page structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title — Finca Tariqa</title>
  <!-- OG / Twitter meta -->
  <link rel="canonical" href="...">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link rel="stylesheet" href="style.css">  <!-- or ../style.css in blog/ -->
  <style>/* page-specific CSS */</style>
</head>
<body>
  <!-- Navigation (copy from existing page, update active class) -->
  <!-- Hero section -->
  <!-- Content sections -->
  <!-- Footer (copy from existing page) -->
</body>
</html>
```

### Navigation — current canonical state
```html
<nav class="nav">
  <a href="index.html" class="nav-logo">Finca Tariqa</a>
  <ul class="nav-links" id="main-nav">
    <li><a href="oranges.html">Oranges</a></li>
    <li><a href="land.html">The Land</a></li>
    <li><a href="forest.html">The Forest</a></li>
    <li><a href="camp.html">Camp Tariqa</a></li>
    <li><a href="mission.html">Our Mission</a></li>
    <li><a href="blog/index.html">Journal</a></li>
    <li><a href="fund.html" class="nav-highlight">Support</a></li>
  </ul>
  <div class="nav-toggle" role="button" tabindex="0" aria-label="Open navigation" onclick="document.getElementById('main-nav').classList.toggle('open')">
    <span></span><span></span><span></span>
  </div>
</nav>
```
Add `class="active"` to the link for the current page. Blog subdirectory pages prefix hrefs with `../`.

### Footer — current canonical state
```html
<footer class="site-footer">
  <div class="footer-inner">
    <div class="footer-brand">
      Finca Tariqa<br>Carcaixent, Valencia<br>Spain
    </div>
    <ul class="footer-links">
      <li><a href="oranges.html">Oranges</a></li>
      <li><a href="land.html">Land</a></li>
      <li><a href="forest.html">Forest</a></li>
      <li><a href="mission.html">Mission</a></li>
      <li><a href="report.html">Full Report</a></li>
      <li><a href="blog/index.html">Journal</a></li>
      <li><a href="fund.html">Support</a></li>
      <li><a href="roadmap.html">Our Plans</a></li>
    </ul>
  </div>
  <div class="footer-bottom">Last updated August 2026</div>
</footer>
```

### Hero block (non-homepage)
```html
<section class="page-hero">  <!-- class name varies by page -->
  <div class="page-hero-inner">
    <span class="eyebrow">Section Label</span>
    <h1>Headline.</h1>
    <p class="lead">Lead paragraph text.</p>
  </div>
</section>
```
CSS:
```css
.page-hero {
  background: var(--earth-dark);  /* or --earth-mid */
  position: relative;
  overflow: hidden;
  min-height: 100vh;
  min-height: 100svh;
  display: flex;
  align-items: flex-end;
  padding: calc(var(--nav-height) + 4rem) clamp(1.25rem, 6vw, 6rem) clamp(4rem, 8vw, 6rem);
}
.page-hero-inner { position: relative; z-index: 1; max-width: 740px; }
.page-hero h1 { font-size: clamp(2.8rem, 5.5vw, 4.8rem); line-height: 1.08; }
.page-hero .lead { font-size: clamp(1rem, 1.6vw, 1.1rem); line-height: 1.75; }
```

---

## Image handling

### Containment rule
Images must always be inside the normal page flow, inside a `.section-inner` container. Never create a full-bleed image div outside the flow — it causes text overlap.

```html
<div class="my-img-wrap">
  <img src="images/filename.png" alt="Descriptive alt text">
</div>
```
```css
.my-img-wrap {
  border-radius: var(--radius-lg);
  overflow: hidden;
  max-height: 340px;
}
.my-img-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 65%;  /* adjust for focal point */
}
```

### File paths
- From root pages: `src="images/filename.png"`
- From blog subdirectory: `src="../images/filename.png"`

### Alt text
Always descriptive. Describe what's in the image, not the page section. Include location context where relevant.

---

## Blog — special rules

### Files that must never be CMS-published (edit HTML directly)
- `blog/heat-resilience-report.html` — has custom audio player with 59-entry `TIMING` array and `data-para` attributes on every paragraph for click-to-seek. The CMS `_generate_post_html()` function strips all of this.
- `report.html` — geological report with custom section layout. Same risk.
- `blog/index.html` — editorial list style enforced manually. `_regenerate_index()` in server.py may drift from this style.

### Audio player (heat-resilience-report.html)
- `const TIMING = [...]` in the `<script>` block — 59 entries mapping paragraph index to audio timestamp
- `data-para="N"` attributes on `<p>` tags — enable click-to-seek and highlight sync
- Speed slider: min 0.5×, max 2×, step 0.1
- The server auto-patches `const TIMING` after audio regeneration — do not manually edit the TIMING array unless you understand this mechanism

### Audio files
- Stored in `/audio/` (root directory)
- Generated by tariqa-voice CMS (F5-TTS)
- May or may not be tracked in git — verify with `git ls-files audio/` before pushing

---

## Working with the blog CMS (tariqa-voice)

The CMS runs on `http://127.0.0.1:5173`. It is a separate Flask app in `/Users/diana/Documents/tariqa-voice/`.

Start it with:
```bash
cd /Users/diana/Documents/tariqa-voice
source venv/bin/activate && python server.py
```

Restart after editing server.py:
```bash
pkill -f "python.*server.py"
cd /Users/diana/Documents/tariqa-voice
source venv/bin/activate && python server.py &
```

Verify it's running: `curl -s http://127.0.0.1:5173/api/posts | python3 -c "import sys,json; d=json.load(sys.stdin); print(len(d), 'posts')"`

---

## Local preview

Always use the local HTTP server — never `file://` protocol (causes CSS rendering issues).

```bash
cd /Users/diana/Documents/finca-tariqa
python3 -m http.server 8765
```

Then open: `http://localhost:8765/<page>.html`

---

## Before committing

```bash
git status          # what changed?
git diff            # what specifically changed?
git ls-files audio/ # are audio binaries tracked?
```

Stage specific files. Never `git add -A` without inspecting first.

---

## Evaluation criteria

Before marking a task complete:
1. Does the page render correctly in the local HTTP server?
2. Is the nav consistent with the canonical order?
3. Are all images contained (no overlap with text)?
4. Are CSS variables used (no hardcoded hex values)?
5. Is the diff clean — only what was intended changed?
6. Are audio narration files still referenced correctly if the blog was touched?
