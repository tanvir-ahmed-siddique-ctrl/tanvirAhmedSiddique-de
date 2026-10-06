# Judge Experience

> Rebuilt for v3. The original file was not available when this kit was edited; the additions from the v2 patch are merged in.

A judge sees many submissions, with limited time, on their own device and Chrome. Design the first two minutes.

## The cold-start test

Within seconds the judge should know: what is this, who is it for, what do I click first, what result do I get, how do I switch language.

## First load

- Clear next action on screen. A one-line purpose statement.
- A visible way to **load the provided sample data** (if the problem supplies it).
- Never look empty or broken. No spinner that never ends. No console errors.

## Result visibility

- The main answer is visible **without scrolling**.
- Show the **exact status strings from the statement** (English mode), and the Bangla equivalents in Bangla mode.
- Every change updates the result immediately.
- Errors are specific and bilingual.

## Judge path

Walk it yourself on the live site as if you had never seen it: load sample, see the result, change one thing, see the update, switch language, trigger one validation error, press reset. This same path becomes the README's **60-second judge tour**.

## Repository view

The judge also opens the repository: README first, then `docs/problem/`, screenshots, commit history. The README must make sense on its own (see README_GENERATION.md). Commit messages are readable and carry prompts.

## Avoid

Login walls, install prompts, cookie banners, auto-playing animation that blocks input, hidden controls, tiny text, jargon in labels.
