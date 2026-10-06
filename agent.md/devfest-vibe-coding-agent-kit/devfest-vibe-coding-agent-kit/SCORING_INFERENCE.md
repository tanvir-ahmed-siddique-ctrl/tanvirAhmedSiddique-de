# Judging Strategy — Inference, Not Official Scoring

## Important

The supplied rulebook does **not publish a scoring rubric or marks breakdown**. Therefore the framework below is an evidence-based strategy, not an official claim about judge weighting.

The rulebook does explicitly say judges evaluate the submitted repository, final eligible commit, and required live deployment. That means compliance, working behavior, and the quality of the live experience are all directly exposed to judging.

## Evidence from the organizers' mock test (5 Oct 2026)

The practice problem (a graph-based route simulator) showed how the real contest is likely framed:

- Sample checks with exact expected results were published.
- The statement warned that judges use **unseen datasets**, equal-cost ties, disconnected cases, and invalid input, and that **hard-coded sample answers are not acceptable**.
- Exact status strings were quoted in the statement.
- Extra deliverables beyond the README were required (a screenshots folder).
- Required behaviors included subtle animations, two languages for statuses and errors, and immediate recalculation after every change.

Inference: the real contest will likely be spec-heavy, partly checkable by test cases, and judged on more than looks.

## Likely high-impact dimensions (ordered)

### 1. Correctness on unseen data and sample checks

Every explicit rule, tie-break, limit, and validation requirement. A half-correct engine under a beautiful UI loses to a correct engine under a plain UI.

### 2. Requirement and deliverable completeness

All MUST tasks, exact strings, required files/folders, README fields, MIT LICENSE, working live deployment that matches the final commit.

### 3. Usefulness to an organization

The problem statement will describe an organizational user. The app should solve a recognizable workflow, not merely display data.

### 4. UX clarity

A judge should understand who this is for, what problem it solves, what to do first, and what success looks like, without an explanation.

### 5. Visual polish and required motion

Distinctive, coherent, intentional design helps because many competitors converge on generic dashboards. Required animations are part of the spec, so keep them brief, readable, and non-blocking.

### 6. Robustness

Survive missing/empty/odd values, refreshes where appropriate, narrow viewports, language changes, rapid repeated actions, and optional API failure.

### 7. Engineering quality

Judges can read the repository and commit history. Clean structure, readable names, tests, and honest prompt-logged commits matter.

### 8. Deployment quality

The live site must match the final eligible commit and work on the judge's own Chrome without login or installation.

## Strategic objective

Optimize as if the judge has only a few minutes and may compare many submissions:

**spec-correct main flow → required deliverables → clarity → polish → resilience → bonus depth**

Do not spend scarce time on infrastructure that the rules forbid or on AI that the rules make optional.

## README as the first impression (inference)

A judge opens the repository before or alongside the live site. A README that answers "what is it, how do I open it, what should I see, what is done and what is not" in the first screens raises perceived clarity, completeness, and trust, and costs only a few minutes if it is generated from project memory (`docs/`) instead of written from scratch. A README with unverified claims does the opposite. See `skills/devfest-vibe-coding/references/README_GENERATION.md`.
