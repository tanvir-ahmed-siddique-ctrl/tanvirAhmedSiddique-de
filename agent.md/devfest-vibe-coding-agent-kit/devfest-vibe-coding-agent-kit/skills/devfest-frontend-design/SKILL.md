---
name: devfest-frontend-design
description: Visual and interaction design guidance for the DevFest contest web app. Use when polishing, reviewing, or restyling the UI of a contest app after the main workflow and tests work, or when choosing a layout, typography, color tokens, states, or animations. Covers matching the UI to the problem type, bilingual-safe text, brief reduced-motion-aware animation, and avoiding generic AI-dashboard looks. Use it even if the person only says "make it look better" or "polish the UI" during the contest.
---

# DevFest Frontend Design

> Rebuilt for v3. The original file was not available when this kit was edited; the v2 patch additions are merged in.

Apply only **after** the core tests pass. Never polish while the main path is broken. Full detail: `../devfest-vibe-coding/references/FRONTEND_QUALITY.md` and `PRODUCT_STRATEGY.md`.

## Steps

1. **Match the UI to the problem type.** Simulator/tool = workspace + controls + result panel. Dashboard = only metrics that answer a real question. Form/workflow = validation, progress, confirmation. A tool needs no hero and no KPI cards.
2. **Set tokens** in CSS variables (background, surface, text, muted, border, primary, success, warning, danger, focus). One typeface family plus a Bangla-capable fallback. Contrast at least 4.5:1 for body text.
3. **Make the first action obvious.** One dominant primary action; the main answer visible without scrolling; useful empty state and a sample-data loader on first load.
4. **Never rely on color alone for state.** Add an icon, pattern, or text label.
5. **Animations** are brief (about 150–300 ms), non-blocking, animate transform/opacity, and respect `prefers-reduced-motion`. Compute first; animate after.
6. **Visual canvases** (maps, graphs, charts) compute scale from the data's min/max; thin clickable elements get a larger invisible hit area; provide a text alternative.
7. **Bilingual-safe layout.** Test the longest Bangla strings at narrow widths; no truncated buttons; no layout jump on language switch.
8. **Responsive** from about 360 px; wide content scrolls inside its own container.
9. **Re-run the tests and the judge path** after styling. Styling must not change behavior.

## Avoid

Generic centered hero with three cards, heavy gradients, glassmorphism everywhere, stock illustrations, many fonts, pill-shaped everything, animations that slow the primary action.
