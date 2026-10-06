# Frontend Quality Standard

> Rebuilt for v3. The original file was not available when this kit was edited; the rules from the v2 patch are merged in.

## Visual system (decide in the first 5 minutes of UI work)

- One typeface family for the interface plus a Bangla-capable font in the fallback stack. Two weights are usually enough.
- A small token set in CSS variables: background, surface, text, muted text, border, primary, success, warning, danger, focus ring. Use tokens everywhere.
- Spacing scale (4/8/12/16/24/32). Consistent radius. Few shadows.
- Contrast: body text at least 4.5:1, large text and UI borders at least 3:1.

## Layout and hierarchy

- Obvious purpose in 5 seconds: page title, one line of context, the primary action.
- Fit the shape to the problem (see PRODUCT_STRATEGY.md). Result panel shows the main answer without scrolling.
- Responsive from about 360 px wide to desktop. Wide content (tables, canvases) scrolls inside its own container, never the whole page sideways.
- Touch targets at least 40 px.

## State and feedback

- **Never rely on color alone to show state.** Pair color with an icon, pattern, shape, or text label (for example "Blocked" with a symbol, not just red).
- Every async or heavy action has a visible state: idle, working, success, error.
- Useful **empty state on first load** with the next action and a way to load the provided sample data.
- Error messages say what is wrong, where, and how to fix it, in the active language.
- Use `aria-live` (polite) for status text that changes after an action.

## Motion

- Required animations are brief (about 150–300 ms), non-blocking, and respect `prefers-reduced-motion` (disable or shrink them).
- Computation finishes first; animation only illustrates the result. Never delay a result for an animation. Never block input during one.
- Animate transform and opacity, not layout.

## Visual canvases (maps, graphs, charts)

- Compute scale from the data's min/max every time; never assume the sample's size or coordinate range.
- Give thin clickable elements (edges, lines, small nodes) a larger invisible hit area.
- Label things that matter; provide a text alternative or table for the same information.
- Test with a much larger and a much smaller dataset than the sample.

## Accessibility basics

- Real `<button>`, `<label>`, `<table>` elements. Visible focus outline. Everything usable with the keyboard.
- `lang` attribute on `<html>` follows the selected language.
- Images and screenshots have alt text.

## Fonts and assets

- Prefer fonts bundled through npm (for example a Bangla font package under an open license) so the site works without external requests; always keep a system fallback.
- Respect licenses of fonts, icons, and images and list them in the README.
- No stock images. Simple SVG/CSS is fine.

## Console and polish

- No console errors or warnings in the tested path.
- No layout jump on language switch; test the longest Bangla strings in narrow layouts.
- Favicon and page title set.
