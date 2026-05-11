# figr.design Instagram Carousel Templates — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build 3 self-contained HTML/CSS carousel template files (7 slides each, 1080×1080px) in figr.design's brand language for their UI/UX Instagram channel.

**Architecture:** Three standalone HTML files, each embedding Inter via Google Fonts CDN and all CSS inline via `<style>`. No build tools, no dependencies. Each file renders all 7 slides stacked vertically — screenshot each individually for posting.

**Tech Stack:** HTML5, CSS3 (custom properties, flexbox, absolute positioning), Google Fonts (Inter), inline SVG for diagrams (Template C)

---

## File Map

| File | Description |
|------|-------------|
| `template-a-manifesto.html` | Type-led editorial — dark hook/CTA, ghost numbers, cyan underline accent |
| `template-b-toolkit.html` | Structured card format — bordered cards, cyan numbered badges, ruled dividers |
| `template-c-diagram.html` | 50/50 split — left diagram panel, right text panel, inline SVG shapes |

---

## Task 1: Template A — Manifesto

**Files:**
- Create: `template-a-manifesto.html`

Sample topic: "5 signs your design system is failing"

- [ ] **Step 1: Create the file**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=1080">
<title>figr.design — Template A: Manifesto</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #FAFAFA;
    --surface: #FFFFFF;
    --ink: #0D0D0D;
    --ink-muted: #6B6B6B;
    --accent: #00C8B4;
    --accent-light: #E6FAF8;
    --border: #E8E8E8;
    --dark: #0D0D0D;
    --ghost: #EBEBEB;
  }

  body {
    font-family: 'Inter', sans-serif;
    background: #E0E0E0;
    padding: 40px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    align-items: center;
  }

  .slide {
    width: 1080px;
    height: 1080px;
    position: relative;
    overflow: hidden;
    flex-shrink: 0;
  }

  /* ── DARK SLIDES ── */
  .slide-dark {
    background: var(--dark);
  }

  .accent-bar {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 5px;
    height: 140px;
    background: var(--accent);
    border-radius: 0 3px 3px 0;
  }

  .slide-dark .content {
    position: absolute;
    left: 80px;
    top: 50%;
    transform: translateY(-50%);
    max-width: 860px;
  }

  .chip {
    display: inline-block;
    background: var(--accent);
    color: #fff;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 4px;
    margin-bottom: 28px;
  }

  .slide-dark h1 {
    font-size: 68px;
    font-weight: 700;
    color: #FFFFFF;
    line-height: 1.08;
    letter-spacing: -0.02em;
    margin-bottom: 20px;
  }

  .slide-dark .sub {
    font-size: 20px;
    font-weight: 400;
    color: #888888;
  }

  /* ── LIGHT SLIDES ── */
  .slide-light {
    background: var(--bg);
  }

  .ghost-number {
    position: absolute;
    top: -30px;
    right: -20px;
    font-size: 280px;
    font-weight: 700;
    color: var(--ghost);
    line-height: 1;
    user-select: none;
    pointer-events: none;
    letter-spacing: -0.05em;
  }

  .slide-light .content {
    position: absolute;
    left: 80px;
    top: 50%;
    transform: translateY(-50%);
    max-width: 800px;
    z-index: 1;
  }

  .slide-label {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 24px;
  }

  .slide-light h2 {
    font-size: 50px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.1;
    letter-spacing: -0.02em;
    margin-bottom: 20px;
  }

  .accent-line {
    width: 52px;
    height: 3px;
    background: var(--accent);
    border-radius: 2px;
    margin-bottom: 28px;
  }

  .slide-light .body {
    font-size: 19px;
    font-weight: 400;
    color: var(--ink-muted);
    line-height: 1.65;
    max-width: 680px;
  }

  /* ── CTA SLIDE ── */
  .slide-cta .content {
    position: absolute;
    left: 80px;
    top: 50%;
    transform: translateY(-50%);
    max-width: 860px;
  }

  .slide-cta .cta-label {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #555555;
    margin-bottom: 20px;
  }

  .slide-cta h2 {
    font-size: 72px;
    font-weight: 700;
    color: #FFFFFF;
    line-height: 1;
    letter-spacing: -0.03em;
    margin-bottom: 18px;
  }

  .slide-cta .cta-sub {
    font-size: 20px;
    font-weight: 400;
    color: #888888;
    margin-bottom: 32px;
  }

  .slide-cta .handle {
    font-size: 24px;
    font-weight: 600;
    color: var(--accent);
    letter-spacing: -0.01em;
  }

  /* ── BRAND MARK ── */
  .brand {
    position: absolute;
    bottom: 32px;
    right: 40px;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.02em;
  }

  .slide-dark .brand,
  .slide-cta .brand { color: #555555; }
  .slide-light .brand { color: var(--ink-muted); }

  /* ── SLIDE NUMBER LABEL (bottom-left on light slides) ── */
  .slide-num {
    position: absolute;
    bottom: 34px;
    left: 40px;
    font-size: 12px;
    font-weight: 500;
    color: #CCCCCC;
    letter-spacing: 0.06em;
  }
</style>
</head>
<body>

<!-- ══════════════════════════════════════════
     SLIDE 1 — HOOK (dark)
══════════════════════════════════════════ -->
<div class="slide slide-dark">
  <div class="accent-bar"></div>
  <div class="content">
    <div class="chip">Design Systems</div>
    <h1>Your design system<br>is lying to you.</h1>
    <p class="sub">5 signs it's quietly failing your team</p>
  </div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 2 — PROBLEM
══════════════════════════════════════════ -->
<div class="slide slide-light">
  <div class="ghost-number">01</div>
  <div class="content">
    <div class="slide-label">The Problem</div>
    <h2>Most design systems<br>die in silence.</h2>
    <div class="accent-line"></div>
    <p class="body">Teams stop using them. Components drift. No one calls it — until the codebase is three versions behind the design file.</p>
  </div>
  <div class="slide-num">02 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 3 — TIP 01
══════════════════════════════════════════ -->
<div class="slide slide-light">
  <div class="ghost-number">02</div>
  <div class="content">
    <div class="slide-label">Sign 01</div>
    <h2>Designers are<br>overriding tokens.</h2>
    <div class="accent-line"></div>
    <p class="body">If your team is manually typing hex values instead of using design tokens, the system doesn't reflect reality — and engineers will follow the file, not the spec.</p>
  </div>
  <div class="slide-num">03 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 4 — TIP 02
══════════════════════════════════════════ -->
<div class="slide slide-light">
  <div class="ghost-number">03</div>
  <div class="content">
    <div class="slide-label">Sign 02</div>
    <h2>No one owns<br>the changelog.</h2>
    <div class="accent-line"></div>
    <p class="body">A system without a changelog is a system no one trusts. If updates appear without notice, teams build their own copies — and you get five slightly different button components.</p>
  </div>
  <div class="slide-num">04 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 5 — TIP 03
══════════════════════════════════════════ -->
<div class="slide slide-light">
  <div class="ghost-number">04</div>
  <div class="content">
    <div class="slide-label">Sign 03</div>
    <h2>Adoption is tracked<br>by vibes, not data.</h2>
    <div class="accent-line"></div>
    <p class="body">If you don't know your component coverage rate, you don't know if the system is working. Measure coverage quarterly — it's the one metric that reveals real adoption vs. polite compliance.</p>
  </div>
  <div class="slide-num">05 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 6 — TIP 04
══════════════════════════════════════════ -->
<div class="slide slide-light">
  <div class="ghost-number">05</div>
  <div class="content">
    <div class="slide-label">Sign 04</div>
    <h2>The system lives<br>in Figma only.</h2>
    <div class="accent-line"></div>
    <p class="body">A design system that isn't in code is a style guide. If engineers are not co-owners — if there's no component library in the repo — the system will always lag two sprints behind.</p>
  </div>
  <div class="slide-num">06 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 7 — CTA (dark)
══════════════════════════════════════════ -->
<div class="slide slide-dark slide-cta">
  <div class="accent-bar"></div>
  <div class="content">
    <div class="cta-label">Save this for your next system audit</div>
    <h2>Save this.</h2>
    <p class="cta-sub">More frameworks for design leads, every week.</p>
    <div class="handle">@figr.design</div>
  </div>
  <div class="brand">figr.design</div>
</div>

</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Open `template-a-manifesto.html` in a browser. Check:
- All 7 slides render at exactly 1080px wide
- Slide 1 and 7: dark `#0D0D0D` background, white headline, cyan left bar, `figr.design` wordmark bottom-right in gray
- Slides 2–6: `#FAFAFA` background, large ghost number top-right in `#EBEBEB`, content left-aligned, cyan underline below headline, muted body text
- Inter font loaded (check Network tab if unsure)
- No overflow or clipping on any slide

- [ ] **Step 3: Commit**

```bash
git add template-a-manifesto.html
git commit -m "feat: add Template A Manifesto carousel (7 slides)"
```

---

## Task 2: Template B — Toolkit

**Files:**
- Create: `template-b-toolkit.html`

Sample topic: "How to run a 30-min design critique"

- [ ] **Step 1: Create the file**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=1080">
<title>figr.design — Template B: Toolkit</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #FAFAFA;
    --surface: #FFFFFF;
    --ink: #0D0D0D;
    --ink-muted: #6B6B6B;
    --accent: #00C8B4;
    --accent-light: #E6FAF8;
    --border: #E8E8E8;
  }

  body {
    font-family: 'Inter', sans-serif;
    background: #E0E0E0;
    padding: 40px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    align-items: center;
  }

  .slide {
    width: 1080px;
    height: 1080px;
    position: relative;
    overflow: hidden;
    flex-shrink: 0;
    background: var(--surface);
  }

  /* ── SLIDE 1: HOOK ── */
  .slide-hook {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 80px;
  }

  .chip-top {
    position: absolute;
    top: 52px;
    left: 52px;
    display: inline-block;
    background: var(--accent-light);
    color: var(--accent);
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 4px;
  }

  .hook-headline {
    font-size: 60px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.08;
    letter-spacing: -0.025em;
    max-width: 760px;
    margin-bottom: 20px;
  }

  .hook-sub {
    font-size: 20px;
    font-weight: 400;
    color: var(--ink-muted);
    max-width: 520px;
    line-height: 1.5;
  }

  .cyan-bar-bottom {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 4px;
    background: var(--accent);
  }

  /* ── SLIDES 2–6: CARD ── */
  .slide-card {
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .card {
    width: 880px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 60px 68px;
    position: relative;
  }

  .card-header {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 32px;
  }

  .badge {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: var(--accent);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    font-weight: 700;
    color: #fff;
    flex-shrink: 0;
  }

  .card-label {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--ink-muted);
  }

  .card h2 {
    font-size: 38px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.15;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
  }

  .card-rule {
    height: 1px;
    background: var(--border);
    margin-bottom: 24px;
  }

  .card-body {
    font-size: 18px;
    font-weight: 400;
    color: var(--ink-muted);
    line-height: 1.7;
    margin-bottom: 32px;
  }

  .tag-chip {
    display: inline-block;
    background: var(--accent-light);
    color: var(--accent);
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 5px 12px;
    border-radius: 4px;
  }

  /* ── SLIDE 7: CTA ── */
  .slide-cta {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 80px;
    background: var(--surface);
  }

  .cta-arrow {
    font-size: 72px;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 32px;
  }

  .cta-headline {
    font-size: 40px;
    font-weight: 700;
    color: var(--ink);
    letter-spacing: -0.02em;
    margin-bottom: 14px;
  }

  .cta-sub {
    font-size: 19px;
    font-weight: 400;
    color: var(--ink-muted);
    margin-bottom: 40px;
    max-width: 440px;
    line-height: 1.5;
  }

  .cta-btn {
    display: inline-block;
    border: 2px solid var(--accent);
    color: var(--accent);
    font-size: 16px;
    font-weight: 600;
    letter-spacing: 0.01em;
    padding: 14px 32px;
    border-radius: 10px;
  }

  /* ── BRAND MARK ── */
  .brand {
    position: absolute;
    bottom: 32px;
    right: 40px;
    font-size: 13px;
    font-weight: 500;
    color: var(--ink-muted);
    letter-spacing: 0.02em;
  }

  .slide-num {
    position: absolute;
    bottom: 34px;
    left: 40px;
    font-size: 12px;
    font-weight: 500;
    color: #CCCCCC;
    letter-spacing: 0.06em;
  }
</style>
</head>
<body>

<!-- ══════════════════════════════════════════
     SLIDE 1 — HOOK
══════════════════════════════════════════ -->
<div class="slide slide-hook">
  <div class="chip-top">How To</div>
  <h1 class="hook-headline">Run better design<br>critiques in 30 min.</h1>
  <p class="hook-sub">A repeatable format that actually improves work — without the circular feedback loops.</p>
  <div class="cyan-bar-bottom"></div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 2 — PROBLEM
══════════════════════════════════════════ -->
<div class="slide slide-card">
  <div class="card">
    <div class="card-header">
      <div class="badge">!</div>
      <span class="card-label">The Problem</span>
    </div>
    <h2>Most critiques are<br>just opinion contests.</h2>
    <div class="card-rule"></div>
    <p class="card-body">Without structure, design critiques devolve into whoever speaks loudest wins. Good work gets killed. Weak work ships. And designers leave feeling less confident than when they walked in.</p>
    <span class="tag-chip">Design Process</span>
  </div>
  <div class="slide-num">02 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 3 — TIP 01
══════════════════════════════════════════ -->
<div class="slide slide-card">
  <div class="card">
    <div class="card-header">
      <div class="badge">1</div>
      <span class="card-label">Step 01 — 0–5 min</span>
    </div>
    <h2>State the goal<br>before anything else.</h2>
    <div class="card-rule"></div>
    <p class="card-body">The designer presents in 60 seconds: what is this screen trying to do, and what specific question needs feedback? Everything said after that gets filtered through that lens — not personal taste.</p>
    <span class="tag-chip">Facilitation</span>
  </div>
  <div class="slide-num">03 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 4 — TIP 02
══════════════════════════════════════════ -->
<div class="slide slide-card">
  <div class="card">
    <div class="card-header">
      <div class="badge">2</div>
      <span class="card-label">Step 02 — 5–10 min</span>
    </div>
    <h2>Silent review first.<br>No talking.</h2>
    <div class="card-rule"></div>
    <p class="card-body">Everyone looks at the design independently for 3 minutes and writes sticky notes — what works, what doesn't, what's unclear. This prevents anchoring bias where the loudest voice in the room shapes everyone else's opinion.</p>
    <span class="tag-chip">Bias Reduction</span>
  </div>
  <div class="slide-num">04 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 5 — TIP 03
══════════════════════════════════════════ -->
<div class="slide slide-card">
  <div class="card">
    <div class="card-header">
      <div class="badge">3</div>
      <span class="card-label">Step 03 — 10–22 min</span>
    </div>
    <h2>Feedback must reference<br>the goal, not taste.</h2>
    <div class="card-rule"></div>
    <p class="card-body">Enforce one rule: every critique starts with "Given the goal of X…". "I don't like this font" is noise. "Given the goal of quick scanning, this hierarchy makes the CTA hard to find" is signal. Your job is to train that reflex.</p>
    <span class="tag-chip">Feedback Quality</span>
  </div>
  <div class="slide-num">05 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 6 — TIP 04
══════════════════════════════════════════ -->
<div class="slide slide-card">
  <div class="card">
    <div class="card-header">
      <div class="badge">4</div>
      <span class="card-label">Step 04 — 22–30 min</span>
    </div>
    <h2>Designer closes with<br>a decision, not a list.</h2>
    <div class="card-rule"></div>
    <p class="card-body">The designer says what they'll change, what they'll ignore, and why — out loud, in the room. This closes the loop, builds their decision-making muscle, and signals to the team that critique is a tool, not a verdict.</p>
    <span class="tag-chip">Ownership</span>
  </div>
  <div class="slide-num">06 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 7 — CTA
══════════════════════════════════════════ -->
<div class="slide slide-cta">
  <div class="cta-arrow">↓</div>
  <h2 class="cta-headline">Follow figr.design</h2>
  <p class="cta-sub">Weekly frameworks for design leads who want to ship better work.</p>
  <div class="cta-btn">Visit figr.design →</div>
  <div class="cyan-bar-bottom"></div>
  <div class="brand">figr.design</div>
</div>

</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Open `template-b-toolkit.html` in a browser. Check:
- Slide 1: white bg, cyan chip top-left, centered headline, cyan bar at very bottom
- Slides 2–6: `#FAFAFA` bg, centered card with `1px #E8E8E8` border and `20px` radius, cyan numbered badge (circle), horizontal rule, muted body, colored tag chip at bottom
- Slide 7: white bg, large cyan `↓`, outlined cyan button
- All slides exactly 1080×1080px, no overflow

- [ ] **Step 3: Commit**

```bash
git add template-b-toolkit.html
git commit -m "feat: add Template B Toolkit carousel (7 slides)"
```

---

## Task 3: Template C — Diagram

**Files:**
- Create: `template-c-diagram.html`

Sample topic: "UX debt vs. design debt — these two are not the same thing"

- [ ] **Step 1: Create the file**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=1080">
<title>figr.design — Template C: Diagram</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #FAFAFA;
    --surface: #FFFFFF;
    --ink: #0D0D0D;
    --ink-muted: #6B6B6B;
    --accent: #00C8B4;
    --accent-light: #E6FAF8;
    --border: #E8E8E8;
  }

  body {
    font-family: 'Inter', sans-serif;
    background: #E0E0E0;
    padding: 40px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    align-items: center;
  }

  .slide {
    width: 1080px;
    height: 1080px;
    position: relative;
    overflow: hidden;
    flex-shrink: 0;
    background: var(--surface);
  }

  /* ── SLIDE 1: HOOK ── */
  .slide-hook {
    display: flex;
    align-items: stretch;
  }

  .hook-left {
    flex: 0 0 560px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 80px 60px 80px 80px;
  }

  .chip {
    display: inline-block;
    background: var(--accent-light);
    color: var(--accent);
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 4px;
    margin-bottom: 28px;
    width: fit-content;
  }

  .hook-left h1 {
    font-size: 58px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.08;
    letter-spacing: -0.025em;
    margin-bottom: 22px;
  }

  .hook-left p {
    font-size: 19px;
    font-weight: 400;
    color: var(--ink-muted);
    line-height: 1.6;
    max-width: 400px;
  }

  .hook-right {
    flex: 1;
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    border-left: 1px solid var(--border);
  }

  /* ── SPLIT SLIDES (2–6) ── */
  .slide-split {
    display: flex;
    align-items: stretch;
  }

  .panel-diagram {
    flex: 0 0 540px;
    background: var(--bg);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 60px;
    gap: 24px;
  }

  .diagram-label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #BBBBBB;
    align-self: flex-start;
  }

  .panel-text {
    flex: 1;
    background: var(--surface);
    border-left: 3px solid var(--border);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 60px 64px;
  }

  .slide-label {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
  }

  .panel-text h2 {
    font-size: 32px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.2;
    letter-spacing: -0.02em;
    margin-bottom: 20px;
  }

  .panel-text p {
    font-size: 17px;
    font-weight: 400;
    color: var(--ink-muted);
    line-height: 1.7;
  }

  /* ── CTA SLIDE ── */
  .slide-cta {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 80px;
  }

  .cta-headline {
    font-size: 50px;
    font-weight: 700;
    color: var(--ink);
    letter-spacing: -0.025em;
    margin-bottom: 16px;
  }

  .cta-sub {
    font-size: 19px;
    color: var(--ink-muted);
    margin-bottom: 48px;
    max-width: 480px;
    line-height: 1.55;
  }

  .cta-btn {
    display: inline-block;
    background: var(--accent);
    color: #fff;
    font-size: 18px;
    font-weight: 600;
    padding: 18px 40px;
    border-radius: 10px;
    letter-spacing: 0.01em;
  }

  /* ── BRAND MARK ── */
  .brand {
    position: absolute;
    bottom: 32px;
    right: 40px;
    font-size: 13px;
    font-weight: 500;
    color: var(--ink-muted);
    letter-spacing: 0.02em;
  }

  .slide-num {
    position: absolute;
    bottom: 34px;
    left: 40px;
    font-size: 12px;
    font-weight: 500;
    color: #CCCCCC;
    letter-spacing: 0.06em;
  }

  /* ══════════════════════
     DIAGRAM COMPONENTS
  ══════════════════════ */

  /* Two-box flow */
  .flow-diagram {
    display: flex;
    align-items: center;
    gap: 0;
    width: 100%;
    max-width: 380px;
  }
  .flow-box {
    flex: 1;
    border: 2px solid var(--border);
    border-radius: 12px;
    padding: 20px 16px;
    text-align: center;
    background: var(--surface);
  }
  .flow-box.accent {
    border-color: var(--accent);
    background: var(--accent-light);
  }
  .flow-box-title {
    font-size: 15px;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 6px;
  }
  .flow-box-sub {
    font-size: 12px;
    color: var(--ink-muted);
    line-height: 1.4;
  }
  .flow-box.accent .flow-box-title { color: var(--accent); }
  .flow-arrow {
    font-size: 24px;
    color: var(--accent);
    padding: 0 12px;
    flex-shrink: 0;
  }

  /* Comparison table */
  .compare-table {
    width: 100%;
    max-width: 400px;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--border);
  }
  .compare-header {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  .compare-col-head {
    padding: 14px 16px;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    text-align: center;
    background: var(--bg);
    border-bottom: 1px solid var(--border);
  }
  .compare-col-head.accent { background: var(--accent); color: #fff; }
  .compare-col-head:last-child { border-left: 1px solid var(--border); }
  .compare-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    border-bottom: 1px solid var(--border);
  }
  .compare-row:last-child { border-bottom: none; }
  .compare-cell {
    padding: 12px 16px;
    font-size: 13px;
    color: var(--ink-muted);
    background: var(--surface);
    line-height: 1.4;
  }
  .compare-cell.accent-cell {
    background: var(--accent-light);
    color: var(--ink);
    font-weight: 500;
  }
  .compare-cell:last-child { border-left: 1px solid var(--border); }

  /* Venn circles */
  .venn {
    position: relative;
    width: 340px;
    height: 220px;
  }
  .venn-circle {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    top: 10px;
  }
  .venn-left {
    left: 0;
    background: rgba(0,200,180,0.15);
    border: 2px solid var(--accent);
  }
  .venn-right {
    right: 0;
    background: rgba(13,13,13,0.07);
    border: 2px solid var(--ink);
  }
  .venn-label {
    position: absolute;
    font-size: 12px;
    font-weight: 600;
    text-align: center;
    width: 100px;
    line-height: 1.3;
  }
  .venn-label.left { left: 10px; top: 88px; color: var(--accent); }
  .venn-label.right { right: 10px; top: 88px; color: var(--ink); }
  .venn-label.center {
    left: 50%;
    top: 88px;
    transform: translateX(-50%);
    color: var(--ink-muted);
    font-size: 11px;
    width: 80px;
  }

  /* Step ladder */
  .steps {
    display: flex;
    flex-direction: column;
    gap: 12px;
    width: 100%;
    max-width: 380px;
  }
  .step-item {
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .step-dot {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: var(--bg);
    border: 2px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 13px;
    font-weight: 700;
    color: var(--ink-muted);
    flex-shrink: 0;
  }
  .step-dot.active {
    background: var(--accent);
    border-color: var(--accent);
    color: #fff;
  }
  .step-text {
    font-size: 14px;
    font-weight: 500;
    color: var(--ink);
    line-height: 1.3;
  }
  .step-text.muted { color: var(--ink-muted); font-weight: 400; }

  /* Teaser preview (slide 1 right panel) */
  .teaser {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 16px;
    opacity: 0.6;
  }
  .teaser-box {
    width: 160px;
    height: 56px;
    border: 2px solid var(--border);
    border-radius: 10px;
    background: var(--surface);
  }
  .teaser-box.t-accent {
    border-color: var(--accent);
    background: var(--accent-light);
  }
  .teaser-arrow-small {
    font-size: 20px;
    color: var(--accent);
  }
</style>
</head>
<body>

<!-- ══════════════════════════════════════════
     SLIDE 1 — HOOK
══════════════════════════════════════════ -->
<div class="slide slide-hook">
  <div class="hook-left">
    <div class="chip">Framework</div>
    <h1>These two are not<br>the same thing.</h1>
    <p>UX debt and design debt feel identical — but they compound differently and need different fixes.</p>
  </div>
  <div class="hook-right">
    <div class="teaser">
      <div class="teaser-box t-accent"></div>
      <div class="teaser-arrow-small">↕</div>
      <div class="teaser-box"></div>
    </div>
  </div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 2 — PROBLEM
══════════════════════════════════════════ -->
<div class="slide slide-split">
  <div class="panel-diagram">
    <div class="diagram-label">The confusion</div>
    <div class="venn">
      <div class="venn-circle venn-left"></div>
      <div class="venn-circle venn-right"></div>
      <div class="venn-label left">UX<br>Debt</div>
      <div class="venn-label right">Design<br>Debt</div>
      <div class="venn-label center">Looks<br>the same</div>
    </div>
  </div>
  <div class="panel-text">
    <div class="slide-label">The Problem</div>
    <h2>Teams treat them<br>the same — and fix<br>neither properly.</h2>
    <p>Design debt is about inconsistency in the system. UX debt is about friction in the experience. Conflating them leads to design sprints that don't move user metrics — and vice versa.</p>
  </div>
  <div class="slide-num">02 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 3 — TIP 01
══════════════════════════════════════════ -->
<div class="slide slide-split">
  <div class="panel-diagram">
    <div class="diagram-label">Definition</div>
    <div class="flow-diagram" style="flex-direction: column; gap: 12px; align-items: stretch;">
      <div class="flow-box accent">
        <div class="flow-box-title">UX Debt</div>
        <div class="flow-box-sub">Friction the user feels</div>
      </div>
      <div style="text-align:center; font-size: 20px; color: var(--accent);">↕</div>
      <div class="flow-box">
        <div class="flow-box-title">Design Debt</div>
        <div class="flow-box-sub">Inconsistency the system carries</div>
      </div>
    </div>
  </div>
  <div class="panel-text">
    <div class="slide-label">Tip 01</div>
    <h2>Define them<br>separately — always.</h2>
    <p>UX debt lives in the product: confusing flows, missing states, unresolved edge cases. Design debt lives in the system: mismatched components, undocumented patterns, token drift. Different causes, different owners, different fixes.</p>
  </div>
  <div class="slide-num">03 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 4 — TIP 02
══════════════════════════════════════════ -->
<div class="slide slide-split">
  <div class="panel-diagram">
    <div class="diagram-label">How to spot it</div>
    <div class="compare-table">
      <div class="compare-header">
        <div class="compare-col-head accent">UX Debt</div>
        <div class="compare-col-head">Design Debt</div>
      </div>
      <div class="compare-row">
        <div class="compare-cell accent-cell">Users struggle</div>
        <div class="compare-cell">Team struggles</div>
      </div>
      <div class="compare-row">
        <div class="compare-cell accent-cell">Found in analytics</div>
        <div class="compare-cell">Found in audits</div>
      </div>
      <div class="compare-row">
        <div class="compare-cell accent-cell">Hurts conversion</div>
        <div class="compare-cell">Hurts velocity</div>
      </div>
    </div>
  </div>
  <div class="panel-text">
    <div class="slide-label">Tip 02</div>
    <h2>Use different signals<br>to surface each type.</h2>
    <p>UX debt shows up in session recordings, drop-off rates, and support tickets. Design debt shows up in design reviews, hand-off friction, and onboarding time for new designers. Stop using the same audit for both.</p>
  </div>
  <div class="slide-num">04 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 5 — TIP 03
══════════════════════════════════════════ -->
<div class="slide slide-split">
  <div class="panel-diagram">
    <div class="diagram-label">Priority matrix</div>
    <div class="flow-diagram" style="flex-direction: column; gap: 0; width: 100%; max-width: 380px;">
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px;">
        <div class="flow-box accent" style="text-align: left; padding: 16px;">
          <div class="flow-box-title" style="font-size:13px;">Fix first</div>
          <div class="flow-box-sub">High friction + visible to users</div>
        </div>
        <div class="flow-box" style="text-align: left; padding: 16px;">
          <div class="flow-box-title" style="font-size:13px;">Schedule</div>
          <div class="flow-box-sub">System inconsistency blocking velocity</div>
        </div>
        <div class="flow-box" style="text-align: left; padding: 16px; opacity: 0.7;">
          <div class="flow-box-title" style="font-size:13px;">Monitor</div>
          <div class="flow-box-sub">Low-impact UX edge cases</div>
        </div>
        <div class="flow-box" style="text-align: left; padding: 16px; opacity: 0.7;">
          <div class="flow-box-title" style="font-size:13px;">Backlog</div>
          <div class="flow-box-sub">Cosmetic design inconsistency</div>
        </div>
      </div>
    </div>
  </div>
  <div class="panel-text">
    <div class="slide-label">Tip 03</div>
    <h2>Prioritize by user<br>impact, not visibility.</h2>
    <p>A misaligned button radius is embarrassing. A checkout flow that loses users at step 3 is a revenue problem. Rank debt by the blast radius — how many users hit it, how often, with what consequence.</p>
  </div>
  <div class="slide-num">05 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 6 — TIP 04
══════════════════════════════════════════ -->
<div class="slide slide-split">
  <div class="panel-diagram">
    <div class="diagram-label">The fix cycle</div>
    <div class="steps">
      <div class="step-item">
        <div class="step-dot active">1</div>
        <div class="step-text">Audit and categorize (UX vs. design)</div>
      </div>
      <div class="step-item">
        <div class="step-dot active">2</div>
        <div class="step-text">Assign owners — product owns UX, system team owns design</div>
      </div>
      <div class="step-item">
        <div class="step-dot active">3</div>
        <div class="step-text">Dedicate 20% of sprint capacity to debt</div>
      </div>
      <div class="step-item">
        <div class="step-dot">4</div>
        <div class="step-text muted">Measure: coverage rate + task success rate</div>
      </div>
    </div>
  </div>
  <div class="panel-text">
    <div class="slide-label">Tip 04</div>
    <h2>Give each type<br>its own owner<br>and cadence.</h2>
    <p>Don't put UX debt and design debt in the same backlog. They need different owners, different success metrics, and different review cycles. Mixing them is why both stay unresolved for quarters.</p>
  </div>
  <div class="slide-num">06 / 07</div>
  <div class="brand">figr.design</div>
</div>

<!-- ══════════════════════════════════════════
     SLIDE 7 — CTA
══════════════════════════════════════════ -->
<div class="slide slide-cta">
  <h2 class="cta-headline">Which one does<br>your team confuse most?</h2>
  <p class="cta-sub">Follow figr.design for weekly frameworks that make design leadership less ambiguous.</p>
  <div class="cta-btn">Follow for more frameworks →</div>
  <div class="brand">figr.design</div>
</div>

</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Open `template-c-diagram.html` in a browser. Check:
- Slide 1: left-aligned text (560px), right panel with teaser diagram shapes on `#FAFAFA` bg
- Slides 2–6: strict 50/50 split — left `#FAFAFA` with diagram, right `#FFFFFF` with text, `3px #E8E8E8` left border on text panel
- Diagram types vary per slide: Venn circles (slide 2), vertical two-box flow (slide 3), comparison table (slide 4), 2×2 grid (slide 5), step ladder (slide 6)
- Slide 7: centered, filled cyan button, no split
- All slides exactly 1080×1080px

- [ ] **Step 3: Commit**

```bash
git add template-c-diagram.html
git commit -m "feat: add Template C Diagram carousel (7 slides)"
```

---

## Self-Review

**Spec coverage:**
- ✅ 3 templates built
- ✅ 7 slides each (Hook → Problem → Tips 1–4 → CTA)
- ✅ 1080×1080px canvas
- ✅ figr.design palette (cyan `#00C8B4`, near-black `#0D0D0D`, off-white `#FAFAFA`)
- ✅ Inter font
- ✅ `figr.design` brand mark bottom-right on all slides
- ✅ Light mode editorial (dark only on Template A hook/CTA slides)
- ✅ Audience-appropriate content (design leads — critique frameworks, design debt, system health)
- ✅ Template A: type-led, ghost numbers, dark hook/CTA
- ✅ Template B: card format, numbered badges, ruled dividers, tag chips
- ✅ Template C: 50/50 split, varying diagram types per slide, inline SVG-free (CSS only)

**Placeholder scan:** No TBDs, no "add appropriate X", all content is real and specific.

**Type consistency:** CSS class names consistent throughout each file. No cross-file dependencies.
