# figr.design Instagram Carousel Templates — Design Spec

**Date:** 2026-05-11  
**Channel:** figr.design Instagram (UI/UX content)  
**Audience:** Design leads and managers  
**Output:** HTML/CSS files, 3 templates × 7 slides, screenshot-ready at 1080×1080px  

---

## Content Strategy

- **Topics:** Educational frameworks + practical how-tos for design leads
- **Narrative structure (all templates):** Hook → Problem → Tip 1 → Tip 2 → Tip 3 → Tip 4 → CTA
- **Tone:** Editorial, confident, direct — matches figr.design brand voice

---

## Shared Design System

### Canvas
- 1080×1080px per slide
- HTML/CSS divs rendered at exact pixel size
- One HTML file per template, slides stacked vertically

### Color Palette
| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#FAFAFA` | Page background |
| `--surface` | `#FFFFFF` | Card surfaces |
| `--ink` | `#0D0D0D` | Primary text |
| `--ink-muted` | `#6B6B6B` | Secondary/body text |
| `--accent` | `#00C8B4` | figr cyan — accent only |
| `--accent-light` | `#E6FAF8` | Cyan tint for chips/badges |
| `--border` | `#E8E8E8` | Subtle borders, dividers |
| `--dark` | `#0D0D0D` | Dark bg slides (hook/CTA) |

### Typography
- **Font:** Inter (Google Fonts, weights 400/500/600/700)
- **Display:** 700, 56–72px, line-height 1.1
- **Heading:** 600, 36–44px, line-height 1.2
- **Body:** 400, 16–18px, line-height 1.6
- **Label/chip:** 500, 11–12px, uppercase, letter-spacing 0.1em

### Brand Element
- `figr.design` wordmark, 13px, `--ink-muted` on light slides / white on dark slides
- Position: bottom-right corner, 32px from edge
- Thin 3px cyan bar or dot as visual anchor on each slide

---

## Template A — Manifesto

**Character:** Type-led editorial. No illustrations. Pure typographic hierarchy. Best for framework breakdowns and bold statements.

### Slide 1 — Hook (Dark)
- Background: `#0D0D0D`
- Left edge: 4px × 120px cyan vertical bar
- Center-left layout:
  - Label chip: cyan bg, "DESIGN LEADERSHIP" 11px uppercase
  - Headline: 68px, 700, white, max 2 lines
  - Sub-text: 18px, `#999999`, 1 line
- Bottom-right: `figr.design` wordmark in white

### Slides 2–6 — Problem + Tips 1–4 (Light)
- Background: `#FAFAFA`
- Ghost number: `01`–`05`, 220px, weight 700, color `#EBEBEB`, absolute positioned top-right, sits behind text
- Content positioned center-left:
  - Slide label: "PROBLEM" or "TIP 01"–"TIP 04", 11px uppercase cyan, letter-spaced
  - Tip title: 44px, 700, `#0D0D0D`, max 2 lines
  - Cyan underline: 3px solid, 48px wide, 12px below title
  - Body: 18px, `#6B6B6B`, max 3 lines
- Bottom-right: `figr.design` wordmark

### Slide 7 — CTA (Dark)
- Background: `#0D0D0D`
- Left edge: same 4px cyan bar
- "Save this." — 60px, 700, white
- Sub-line: "More frameworks for design leads →" 20px, `#999999`
- `@figr.design` in cyan, 22px, 500
- Bottom-right: `figr.design` wordmark in white

---

## Template B — Toolkit

**Character:** Structured card format. Systematic, tool-like. Matches figr's product positioning. Best for practical how-tos.

### Slide 1 — Hook (Light)
- Background: `#FFFFFF`
- Top-left: cyan chip label (e.g. `HOW TO`)
- Center: headline 58px, 700, `#0D0D0D`, max 2 lines
- Sub-text: 18px muted, 1 line
- Bottom: full-width 3px cyan bar
- Bottom-right: `figr.design` wordmark

### Slides 2–6 — Problem + Tips 1–4 (Light with card)
- Background: `#FAFAFA`
- Centered bordered card: 880px wide, border `1px solid #E8E8E8`, border-radius 20px, padding 56px
- Inside card:
  - Top: cyan numbered badge (36px circle, white number, 600 weight) + slide label right of badge
  - Tip title: 34px, 700, `#0D0D0D`, margin-top 24px
  - Horizontal rule: 1px `#E8E8E8`, margin 20px 0
  - Body: 17px, `#6B6B6B`, line-height 1.65, max 4 lines
  - Bottom of card: small tag chip (e.g. `DESIGN SYSTEMS`) in `--accent-light`
- Bottom-right: `figr.design` wordmark

### Slide 7 — CTA (Light)
- Background: `#FFFFFF`
- Center: large `↓` arrow, 64px, cyan
- "Follow figr.design" — 36px, 700, `#0D0D0D`
- "Weekly frameworks for design leads." — 18px muted
- Cyan outlined button: "Visit figr.design →" — 16px, 500, radius 8px
- Bottom: full-width 3px cyan bar

---

## Template C — Diagram

**Character:** 50/50 visual split. Left panel = simple diagram. Right panel = text. Best for showing relationships, comparisons, processes.

### Slide 1 — Hook (Light)
- Background: `#FFFFFF`
- Left-aligned layout (max-width 520px for text)
- Label chip: cyan, "FRAMEWORK" or "PROCESS"
- Headline: 62px, 700, `#0D0D0D`, max 2 lines
- Body: 18px muted, 2 lines
- Right side (decorative): 2-box diagram preview in `#E8E8E8` + cyan — teaser of content
- Bottom-right: `figr.design` wordmark

### Slides 2–6 — Problem + Tips 1–4 (Split layout)
- Left panel (540px): background `#FAFAFA`
  - Simple diagram centered in panel
  - Diagram types (vary per slide): 2-box flow with arrow, Venn (2 circles), comparison table (2 cols), step ladder, single box with labels
  - Diagram colors: `#0D0D0D` shapes, `#00C8B4` highlights, `#E8E8E8` fills
  - Diagram label: 12px, uppercase, muted
- Right panel (540px): background `#FFFFFF`, padding 48px
  - Slide label: "PROBLEM" or "TIP 01"–"TIP 04", 11px uppercase cyan
  - Tip title: 30px, 700, `#0D0D0D`, max 2 lines
  - Body: 17px, `#6B6B6B`, max 4 lines
  - Thin left border on right panel: 3px solid `#E8E8E8`
- Bottom-right of full slide: `figr.design` wordmark

### Slide 7 — CTA (Light)
- Background: `#FFFFFF`
- Center layout
- "Which one resonates?" — 44px, 700, `#0D0D0D`
- Sub-line: 18px muted
- Cyan filled CTA box (radius 10px): "Follow for more frameworks →" white text, 18px, 500
- Bottom-right: `figr.design` wordmark

---

## Sample Topics (one per template for the initial build)

| Template | Topic | Slide 1 Headline |
|----------|-------|-----------------|
| A — Manifesto | 5 signs your design system is failing | "Your design system is lying to you." |
| B — Toolkit | How to run a 30-min design critique | "Run better critiques in 30 minutes." |
| C — Diagram | UX debt vs. design debt | "These two are not the same thing." |

---

## File Structure

```
Carousel Set 1/
├── template-a-manifesto.html
├── template-b-toolkit.html
├── template-c-diagram.html
```

Each file: self-contained HTML, Google Fonts CDN, no external dependencies beyond fonts.
