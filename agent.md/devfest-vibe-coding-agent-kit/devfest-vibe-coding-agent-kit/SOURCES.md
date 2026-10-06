# Research Basis

This kit is an original synthesis. It does not copy a competition app or promise any scoring outcome.

## OpenAI / Codex

- `openai/codex` — skill creator and Codex operating patterns
- `openai/skills` — skill packaging and discovery conventions
- OpenAI Developers, “Rethinking skills and prompts for GPT-6 Astra” — current guidance to keep skill descriptions focused, use progressive disclosure, avoid bloated context, and avoid overly prescriptive recipes

## Anthropic

- `anthropics/skills` — Agent Skills architecture and `frontend-design` skill
- Claude Agent Skills authoring best practices — concise `SKILL.md`, descriptive triggers, progressive disclosure, concrete examples, and verification

## Vercel

- `vercel-labs/skills` — open agent skills ecosystem and conventions
- `vercel-labs/open-agents` — concise `frontend-design` skill focused on distinctive, production-grade interfaces and avoiding generic AI aesthetics

## Superpowers

- `obra/superpowers` — composable engineering workflow, TDD discipline, and verification-before-completion
- `obra/superpowers-skills` — pressure-testing skills themselves with adversarial scenarios

## Organizers' mock test (5 Oct 2026)

- Practice problem statement, `README_START_HERE.txt`, and sample `building.json` supplied by the organizers. Lessons folded into the kit: requirements ledger, exact strings, required deliverables (screenshots), tests from sample checks, hidden-test mindset, earlier commit cadence, skeleton deploy by about T+30. The kit was deliberately kept problem-agnostic; nothing in it depends on that specific problem.

## Adaptation to this contest

The sources above are general agent/software-engineering systems. The contest-specific layer in this kit is derived from the supplied DIU CPC rulebook: 90-minute build, frontend-only, bilingual, no participant-controlled persistence/backend, optional user-supplied-key AI, public HTTPS deployment, Git cadence/prompt logging, final-commit/deployment matching, README requirements, and T+90 freeze.

## README reference (v3)

- `REFERENCE_README_EXAMPLE.md`: a README from a different, older project, supplied by the participant purely as a **style and clarity reference** (hero block, links, highlights, architecture and data flow, stack, run steps, structure, demo flow). Its content, names and architecture are not reused; the contest README is written fresh from `FINAL_README_TEMPLATE.md`.
