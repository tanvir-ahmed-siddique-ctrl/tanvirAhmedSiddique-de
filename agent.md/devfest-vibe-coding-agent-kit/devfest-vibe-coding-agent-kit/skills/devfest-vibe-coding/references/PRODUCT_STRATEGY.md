# Product Strategy

> Rebuilt for v3. The original file was not available when this kit was edited; the product-type rules from the v2 patch are merged in.

## Purpose first

The problem statement describes an organizational user and a workflow. Name them in one sentence before designing: "[who] uses this to [do what] so that [result]". That sentence becomes the README's first lines and the app's page title.

## Pick the UI shape from the problem type

| Problem type | Shape | Do not add |
|---|---|---|
| Simulator / visual tool (graph, map, calculator, scheduler) | Workspace + control panel + result panel. Direct manipulation, clear state legend | KPI cards, hero, marketing copy |
| Dashboard / data explorer | Only metrics that answer a real question, useful filters, strong empty state | Decorative KPIs, filler charts |
| Form / workflow | Validation, progress, confirmation, undo where cheap | Multi-step wizards with no reason |
| Rule engine / checker | Input area, run/recalculate, per-rule results with reasons | Hidden scoring |

A tool does not need KPI cards or a hero.

## One excellent workflow

- Define the **primary action** (the one thing a judge will click first) and make it dominant.
- The main answer is visible without scrolling.
- Secondary features live behind clear but quieter controls.
- Every control on screen does something; remove dead buttons.

## Feature priority

1. Every MUST, STRING, LIMIT, RULE row in the ledger
2. Required deliverables (files, screenshots)
3. Clear first-use experience (empty state, sample data loader)
4. Bilingual completeness
5. Required animations
6. Resilience (invalid input, refresh, reset)
7. Bonus features that are cheap and obviously useful
8. Optional AI (last, only if everything above is done and time remains)

## Anti-patterns

Generic SaaS hero with three cards, decorative gradients, stock illustrations, lorem ipsum, fake numbers, "AI-powered" labels with nothing behind them, features that only exist to look impressive.

## Cut list when time is short

Optional AI, extra charts, themes, export formats not requested, settings pages, onboarding tours, animations beyond the required ones.
