# Bilingual UX (Bangla + English)

> Rebuilt for v3. The original file was not available when this kit was edited; the rules from the v2 patch are merged in.

The rulebook requires the app to work in Bangla and English. All main labels, buttons, statuses, errors, instructions, and empty states must exist in both languages.

## Architecture

- A typed dictionary per language, keyed by stable message keys, in one module. A tiny `t(key, params)` helper. No heavy i18n library needed.
- **Logic returns error/status codes, never display strings.** The UI maps codes to Bangla/English. This keeps validation errors bilingual.
- Language state lives at the top of the app, is saved in `localStorage` (with try/catch), and sets `<html lang="bn|en">`.
- Switching language never resets the user's work, results, or scroll position.

## Content rules

- Use quoted status/error strings from the problem statement **verbatim** in English mode (check `docs/problem/LEDGER.md` STRING rows).
- Write a natural Bangla equivalent for each; do not machine-translate word by word. Keep it short and clear.
- Keep dataset IDs, labels, and numeric values as supplied unless the statement says otherwise (Latin digits by default).
- Do not build sentences by concatenating fragments; word order differs. Use full-sentence templates with placeholders.
- Plurals and units: keep wording neutral or provide both forms.
- Button and heading labels must not truncate in Bangla; Bangla text is often longer.

## Typography

- Bangla-capable font in the stack with comfortable line height (about 1.5–1.7). Test conjuncts and long strings.
- Avoid letter-spacing on Bangla text.

## Tests

- A test that both dictionaries have **exactly the same keys** and no empty values.
- A test that every error/status code the logic can return has a message in both languages.
- A manual pass: toggle language mid-flow on every screen, including error and empty states.
- Narrow viewport check with the longest Bangla strings.

## README

Include a short Bangla summary and a small table of real English/Bangla strings in the README (see FINAL_README_TEMPLATE.md).
