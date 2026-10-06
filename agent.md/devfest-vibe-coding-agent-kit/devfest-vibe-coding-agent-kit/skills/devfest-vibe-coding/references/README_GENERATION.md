# README Generation Protocol

The README is the first thing a judge opens and sometimes the only thing they read before the live site. It must let a stranger understand the project **without anyone explaining it**.

The agent writes it from project memory (`docs/`) and the real repository state, using [FINAL_README_TEMPLATE.md](../../../FINAL_README_TEMPLATE.md). It does not write it from recollection.

## 1. When

| Pass | When | What |
|---|---|---|
| Skeleton | first commits, skeleton deployed by ~T+30 | name, registration number, one-paragraph description, run steps; the live link is added as soon as the skeleton deploys |
| Full | ~T+65–72 (with screenshots) | every template section filled from facts |
| Refresh | ~T+80–85, after behavior is frozen | re-check every claim, status table, links, screenshots still match |

Keep each pass short. A good README never costs more than ~8 minutes in total across the contest.

## 2. Source of truth for each section

| README section | Take it from |
|---|---|
| Name, registration number | the person (ask once; never guess) |
| Live link | deployment dashboard / the actual opened URL |
| At a glance, The problem | `docs/problem/STATEMENT.md`, rewritten in plain words |
| 60-second judge tour | the real UI: click path you actually ran |
| Key features, Bonus features | `LEDGER.md` rows with Status = Done |
| Rules and edge cases handled | `LEDGER.md` RULE / LIMIT rows + test names |
| Bilingual support | the real i18n dictionary (copy 3–5 real strings) |
| Requirement coverage | `LEDGER.md` (Status + Evidence columns) |
| Tech stack, Run, Tests | `package.json` scripts and the commands you actually ran |
| Project structure | real `ls`/`tree` output, annotated |
| Screenshots | files that really exist in the folder the statement names |
| Assumptions and known problems | `BUILD_LOG.md` decisions + unresolved bugs |
| AI tools used, Most useful prompt | `BUILD_LOG.md` (literal prompts) |
| How this was built | `BUILD_LOG.md` |

## 3. Writing for a stranger

- First screen answers: what is it, who is it for, where do I open it, what do I click first.
- Plain words. Define a term the first time. No internal jargon in the README (no "ledger", "T+85", "phase", "skill", "kit").
- Short sentences. Tables for comparisons, numbered steps for actions, one idea per bullet.
- Name the **exact** buttons and labels as they appear in the UI (English labels; add the Bangla label where useful).
- Show the one result that proves it works (a sample input and the output the judge should see).
- Include a short Bangla summary at the top; the app is bilingual and so is the audience.
- Link, do not repeat: details live in `docs/`.

### Stranger test (before the final commit)

Imagine a reader who has only the README and 60 seconds. They must be able to answer:

1. What does this app do and for whom?
2. How do I open it, and what do I click first?
3. What should I see if it works?
4. Which parts are done, partial, or missing?
5. How do I run and test it locally?
6. Who made it, how was AI used, and what is the license?

If any answer needs scrolling past the third screen, restructure.

## 4. Using the reference README

`REFERENCE_README_EXAMPLE.md` shows the target level of clarity: hero block, links table, highlights, architecture and data flow, stack table, run steps, structure tree, demo flow, engineering notes.

Borrow: the **shape** and the habit of linking and tabulating.
Never borrow: sentences, names, links, badges, diagrams, or its architecture (that project used a backend, a bot and hosted services; this contest is frontend-only). Do not commit the reference file to the contest repository.

Adapt to this contest:

- It was a team; this is a solo participant: a **Participant** table instead of a team table.
- It listed backend endpoints; here describe **screens, controls and rules** instead of API routes.
- It had a roadmap; keep only honest, short *next steps* inside Known problems.

## 5. Diagram

Use a Mermaid block (GitHub renders it, no image tooling needed). Keep it to roughly 6–12 nodes: user → UI → logic module → result panel, plus sample data, language dictionary and browser storage if used. Draw only what exists. Do not draw a server.

## 6. Honesty rules

- Every claim is verified: if it was not run, do not write "tested". Do not write "all tests pass" unless you ran them in this state and saw them pass.
- Status words, not only icons: write "Done", "Partial", "Not done" next to any symbol.
- Do **not** put the repository's own final commit hash in the README (editing the README changes the hash). The commit ID goes in the submission form.
- AI disclosure: list the AI tools actually used. If an instruction kit (Markdown files only, no project code) was loaded and the organizers allowed it, say so in one plain sentence. Never claim a tool that was not used and never hide one that was.
- No fake metrics, fake users, fake screenshots, or marketing claims. Known problems are listed plainly.
- No secrets, no personal data, no real private company data.

## 7. Required fields checklist (rulebook plus statement)

- [ ] full name
- [ ] registration number
- [ ] public HTTPS live link (opened and checked)
- [ ] how to run the app
- [ ] main features completed
- [ ] bonus features
- [ ] known problems
- [ ] AI tools used
- [ ] most useful prompt
- [ ] any section the statement adds (for example screenshots, with the exact folder name)
- [ ] MIT `LICENSE` file exists

## 8. Final checks

- Open the README on the **repository page** (not the editor): headings render, Mermaid renders, tables align, every link and image opens.
- All `<!-- AGENT: ... -->` comments and `[placeholders]` are gone.
- Coverage table matches `LEDGER.md` and what the live site actually does.
- Screenshots match the final behavior.
