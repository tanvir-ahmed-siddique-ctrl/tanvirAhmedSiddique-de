# Timeline (90-minute contest clock)

> Rebuilt for v3. The original file was not available when this kit was edited; the commit-point and skeleton-deploy rules from the v2 patch are merged in.

Targets, not a rigid script. Correctness and required deliverables come before polish; polish comes before bonuses.

## Commit points

About **T+10 (optional docs commit), T+20, T+45, T+70, and final T+85**. Never a gap above 25 minutes (the rulebook allows 30). At least 3 commits in total. Every message has a summary plus `Prompt: "<literal prompt>"` or `Manual edit`.

## Schedule

| Window | Goal | Output |
|---|---|---|
| T+0–5 | **Ingest**: save statement and data files into `docs/problem/` | `STATEMENT`, `samples/`, `DATA_PROFILE`, first `BUILD_LOG` entry |
| T+5–10 | Ledger, sample checks, hidden-test risks, ambiguities, plan | `LEDGER`, `SAMPLE_CHECKS`. Optional docs commit ~T+10 |
| T+10–15 | Ask the organizers behavior-changing questions (allowed until T+15) | `CLARIFICATIONS` |
| T+10–25 | Scaffold, pure logic module, tests from sample checks passing | **commit ~T+20** |
| T+25–30 | Connect hosting, push a **skeleton** (with skeleton README) and confirm the public HTTPS URL opens | live skeleton by ~T+30 |
| T+30–45 | Primary UI wired to the logic; sample data loader; empty state | **commit ~T+45** |
| T+45–65 | Validation/error/empty states, bilingual UI, responsive layout | ledger statuses updated |
| T+65–75 | Required animations, polish, **screenshots** (from the deployed site), **full README generation** | **commit ~T+70** |
| T+75–85 | Hidden-test audit, spec-fidelity pass, README refresh and stranger test, production build, deploy verify | **final commit ~T+85** |
| T+85–90 | **Buffer only**: confirm the deployment is built from the final commit, record the commit ID, fill and submit the form | nothing changes after T+90 |

T+90–95 is submission-only with a 10-mark penalty. Do not plan to use it.

## Docs time budget

Ingest about 5 minutes. Each build-log entry about 1 minute. README across the whole contest about 8 minutes. If any docs task grows beyond that, shrink it; never let documentation delay logic or deployment.

## If behind

1. At T+45 with tests not green: stop UI work, fix logic.
2. At T+55 with no deployed skeleton: deploy now, whatever state.
3. At T+60 with core path incomplete: cut every bonus and AI feature.
4. At T+70 with screenshots missing: capture them before any further polish.
5. At T+80: freeze scope. Only fixes for ledger MUST/STRING rows and deliverables.
6. If a push or deploy fails at T+86 or later: do not rewrite history. Re-push normally, or redeploy the same commit. Report to the organizers if the infrastructure is at fault.

## Self-check every 15 minutes

- Is the last commit older than 20 minutes? Commit.
- Are tests green?
- Does the live URL still open?
- Is the ledger status current?
