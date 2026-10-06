# Robustness

> Rebuilt for v3. The original file was not available when this kit was edited; the additions from the v2 patch are merged in.

Judges stress the app with data and actions you have not seen. Test the main journey against all of these.

## Hidden-test fixtures

Build small fixtures for: empty, minimal, maximum-size, duplicates, ties, disconnected/partial data, malformed input, differently scaled data (coordinates, dates, amounts), IDs that sort unexpectedly (`"10"` vs `"2"`, upper vs lower case). Prioritize the rules that `docs/problem/DATA_PROFILE.md` lists as *not exercised* by the sample. See LOGIC_CORRECTNESS.md.

## Input handling

- Validate the whole input, collect **all** errors with stable codes, show them in the active language.
- **Invalid import keeps the previous valid data.** Never replace good state with a failed load.
- Do not crash on unexpected types, missing keys, or extra keys. Do not trim or lowercase identifiers unless the statement says so.

## User actions

- Rapid repeated clicks and toggles produce the same final state as slow ones (no double-apply, no stale results).
- **Reset semantics** are defined (what is restored, what is kept such as the language) and match the statement; reset restores the originally loaded data exactly.
- Every change recalculates immediately; nothing requires reload or re-import.
- Refresh behavior is intentional: either state restores from browser storage or the app starts clean with the sample loader visible. Storage reads and writes are wrapped in try/catch and the app works if storage is empty or blocked.

## Environment

- Works at narrow widths and when zoomed.
- Works offline after load unless an optional external API is used.
- If an external API fails or is blocked, the main features still work and the user sees a clear message.
- No console errors in the tested path.

## Process

For every real bug found: add a failing test first, then fix. Fix only issues that materially affect correctness or the main journey. Never rewrite a working core late.
