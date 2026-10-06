# Problem Intake Protocol (T+0–T+10)

Goal: turn the problem material into saved files and a checkable ledger **before writing app code**, so nothing mandatory is missed and every rule has a test.

Budget: about 8–10 minutes. Do not write app code during intake. Writing the `docs/` files is part of intake.

## 0. Ingest (automatic, first action)

Trigger: the person pastes a statement, attaches files (PDF, image, JSON, CSV, a "start here" note), or relays an organizer announcement. Do this immediately, without asking.

1. Create `docs/problem/` and `docs/problem/samples/` (layout and templates: [PROJECT_MEMORY.md](PROJECT_MEMORY.md)).
2. Save the statement verbatim to `STATEMENT.md`.
3. Copy every provided data file byte-for-byte into `samples/` (use `cp`, never re-save).
4. Inspect each data file with a throwaway command (do not commit it) and write `DATA_PROFILE.md`: shape, counts, ID format and ordering, value ranges, relationships, rules exercised, rules **not** exercised, anomalies.
5. Create an empty `CLARIFICATIONS.md`.
6. Start `docs/BUILD_LOG.md`.
7. Continue with sections 1 to 7 below.

When new material arrives later (an extra file, an organizer clarification): save it the same way, update `CLARIFICATIONS.md` and the affected ledger rows, and tell the person in one line what changed.

## 1. Read twice

1. Read once for the app: who uses it, what workflow, what output.
2. Read again for traps: exact strings, limits, tie-breaks, validation rules, required files/folders, required animations/languages, "must not" statements.

## 2. Requirements Ledger (`docs/problem/LEDGER.md`)

| ID | Requirement | Type | Source | How verified | Status | Evidence |
|---|---|---|---|---|---|---|
| R1 | (one atomic requirement) | MUST / BONUS / STRING / DELIVERABLE / LIMIT / RULE / UX | section or page | test / manual step | Not started | |

Rules for the ledger:

- One atomic requirement per row.
- Types: `MUST`, `BONUS`, `STRING` (exact text), `DELIVERABLE` (file/folder/artifact), `LIMIT` (numeric bounds), `RULE` (determinism, ordering, validation), `UX` (animation, language, states).
- Every `MUST`, `STRING`, `LIMIT`, and `RULE` row needs a verification (automated test where possible).
- Update `Status` and `Evidence` as work lands. The README coverage table is generated from this file, so never mark a row Done without evidence.

## 3. Extract these categories explicitly

- **Exact strings:** status/error texts quoted in the statement. Use verbatim in English mode.
- **Deliverables:** files/folders beyond the README (for example a `screenshots/` folder showing specific states, exported files, sample outputs).
- **Sample checks:** every scenario/expected-result pair goes to `SAMPLE_CHECKS.md` and becomes an automated test.
- **Input rules:** required fields, types, ranges, uniqueness, allowed values, cross-references, size limits, what counts as invalid.
- **Determinism rules:** tie-breaks, sort order, rounding, units.
- **Limits:** counts, sizes, ranges. Test at and just beyond each boundary.
- **Required UX:** languages, animations, visual states, accessibility items, what must update immediately.
- **Forbidden:** things the statement or rulebook says not to do (backend, hard-coding, secrets).

## 4. Hidden-test risks

Judges may use data you have not seen. List how they could stress each rule, for example:

- empty, minimal, and maximum-size inputs
- duplicates, ties, boundary values
- malformed or inconsistent input
- disconnected/partial/missing data
- IDs or names that sort or compare unexpectedly (`"10"` vs `"2"`, uppercase vs lowercase)
- different value ranges than the sample (coordinates, dates, amounts); use the *"not exercised"* list from `DATA_PROFILE.md`
- repeated or rapid user actions, reset, refresh, language switch mid-flow

## 5. Ambiguities → questions (T+0–T+15 only)

Ask only questions that change behavior. Maximum 3–5. Phrase them as yes/no with your default.

Good: "If initial state lists the same ID twice, should we accept it? Default: accept and de-duplicate."
Bad: "What should the UI look like?"

For anything unanswered, keep the default, log it in `BUILD_LOG.md`, and write it under **Assumptions / Known problems** in the README.

## 6. Plan

Write a one-screen plan: build order, test list, deliverables, commit points (optional ~T+10 docs commit, then ~T+20, 45, 70, final 85), and what gets cut first if behind.

## 7. Spec-fidelity pass (T+75)

Re-read the original problem statement (`docs/problem/STATEMENT.md`) and `CLARIFICATIONS.md` line by line against the ledger. Tick each row. Fix gaps before any further polish.
