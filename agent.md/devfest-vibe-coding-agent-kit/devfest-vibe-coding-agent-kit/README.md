# DevFest 2026 AI Vibe-Coding: Competition Agent Kit (v3)

A rules-first, correctness-first, speed-first instruction pack for the DIU CPC AI DevFest Vibe-Coding Contest (Solo), 6 October 2026.

## What this kit is

An **agent-instruction pack**, not a starter project and not a code template. It contains Markdown instructions, checklists, prompt patterns, and verification guidance for an AI coding agent.

It intentionally contains **no contest project source code, starter UI, reusable app template, old project code, or prebuilt assets**. The contest app must start from zero and be written during the contest.

## What changed in v3

- **Automatic Problem Pack ingest.** When you paste the statement and attach data/JSON, the agent saves them itself into `docs/problem/` (statement verbatim, data byte-identical) and derives `DATA_PROFILE.md`, `SAMPLE_CHECKS.md`, `LEDGER.md`. See `references/PROJECT_MEMORY.md` and `references/PROBLEM_INTAKE.md`.
- **Build log.** `docs/BUILD_LOG.md` records every commit point with the literal prompt, decisions, and bugs.
- **README generator.** The README is produced from those files and the real repo state, in a stranger-proof, judge-friendly format for a solo participant. See `FINAL_README_TEMPLATE.md` and `references/README_GENERATION.md`.
- **Reference README** (`REFERENCE_README_EXAMPLE.md`): style and structure example only. Never copy its text or architecture.
- Rebuilt the 12 files that were not uploaded when v2 was edited, with the v2 patches merged in.
- Prompt bank updated (ingest, mid-contest clarification, README generation, README stranger test).

## Structure

```text
devfest-vibe-coding-agent-kit/
├── README.md                          # this file
├── AGENTS.md                          # global operating policy (do not pre-load into the contest repo unless permitted)
├── CONTEST_RULES.md                   # summarized rulebook and hard constraints
├── SCORING_INFERENCE.md               # non-official judging strategy
├── SETUP_CHECKLIST.md                 # pre-contest readiness (now includes ingest readiness)
├── PROMPT_BANK.md                     # prompts to steer the agent under time pressure
├── FINAL_README_TEMPLATE.md           # judge-friendly README template (solo participant)
├── REFERENCE_README_EXAMPLE.md        # style reference only
├── ORGANIZER_QUESTIONS.md             # questions to clarify before / at T+0
├── SOURCES.md                         # research basis
├── MANIFEST.md                        # file list
└── skills/
    ├── devfest-vibe-coding/
    │   ├── SKILL.md                   # MASTER skill
    │   └── references/
    │       ├── TIMELINE.md
    │       ├── PRODUCT_STRATEGY.md
    │       ├── FRONTEND_QUALITY.md
    │       ├── BILINGUAL_UX.md
    │       ├── ROBUSTNESS.md
    │       ├── AI_FEATURE_POLICY.md
    │       ├── GIT_DEPLOY.md
    │       ├── JUDGE_EXPERIENCE.md
    │       ├── FINAL_AUDIT.md
    │       ├── PRESSURE_TESTS.md
    │       ├── PROBLEM_INTAKE.md      # ingest + ledger
    │       ├── PROJECT_MEMORY.md      # NEW: docs/ layout and templates
    │       ├── LOGIC_CORRECTNESS.md
    │       ├── DELIVERABLES.md
    │       └── README_GENERATION.md   # NEW: README from project memory
    ├── devfest-frontend-design/
    │   └── SKILL.md
    └── devfest-final-audit/
        └── SKILL.md
```

## What the agent writes into the contest repo (after T+0)

```text
docs/
  problem/
    STATEMENT.md  CLARIFICATIONS.md  DATA_PROFILE.md  SAMPLE_CHECKS.md  LEDGER.md
    samples/        # your JSON/CSV/etc., byte-identical
  BUILD_LOG.md
README.md           # generated from the above + real repo state
screenshots/        # only if the statement requires it (exact folder name from the statement)
```

## Quick start at T+0

1. Load the master skill (or paste its summary).
2. Paste the statement and attach the data files, then run **PROMPT_BANK #1** (ingest + intake). No app code yet. The agent creates `docs/problem/` on its own.
3. Ask the organizers only behavior-changing questions before T+15. If an answer arrives later, use **PROMPT_BANK #1b**.
4. Logic first (PROMPT_BANK #2), then UI. Commit about T+20, 45, 70, final 85 (optional docs commit at T+10). The agent appends to `docs/BUILD_LOG.md` each time.
5. At about T+65–72 take screenshots (if required) and run **PROMPT_BANK #7** to generate the README. At about T+75–85 run #7b and #8.
6. Stop all changes at T+90.

## Important compliance notes

- The rulebook prohibits pre-written contest code, old templates/projects, and participant-controlled persistent backends/databases. It does **not explicitly say whether pre-authored AI instruction files are allowed**. Get written organizer confirmation first, do not bring external storage, and see `ORGANIZER_QUESTIONS.md` and `SETUP_CHECKLIST.md`.
- Keep this kit and `REFERENCE_README_EXAMPLE.md` **out of the contest repository** unless organizers explicitly allow it. The `docs/` folder is created fresh from the real statement after T+0.
- The README must be honest about AI use. Never claim what was not done.

## Research basis

See `SOURCES.md`.

## North-star behavior

**ingest → ledger → logic + tests → main path → intentional polish → deliverables → README from facts → verify → deploy → freeze**

Never sacrifice rule compliance for visual polish. Never let an optional feature threaten a complete, correct main workflow.
