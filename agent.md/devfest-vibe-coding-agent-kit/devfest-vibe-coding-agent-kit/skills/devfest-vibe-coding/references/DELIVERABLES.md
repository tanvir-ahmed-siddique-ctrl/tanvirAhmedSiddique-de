# Deliverables Protocol

The README and LICENSE are never the only deliverables. The problem statement may require more (for example screenshots of specific states, exported files, sample outputs). Missing a required deliverable can cost marks even when the app is perfect.

## 1. List deliverables at T+0

From the problem statement and rulebook, write the full list:

- repository: source code, `README.md` (required fields), `LICENSE` (MIT)
- problem-specific files/folders (names exactly as stated)
- project docs the agent maintains: `docs/problem/` (statement, sample data, ledger) and `docs/BUILD_LOG.md`
- the generated, stranger-proof README (see README_GENERATION.md)
- submission form fields: full name, registration number, repo URL, final commit ID, public HTTPS live URL

## 2. Screenshots (when required)

- Capture from the **deployed** site (or the production build) in Chrome using the OS screenshot tool. It is faster and more reliable than automation.
- Show exactly the states the statement names. Save with clear names, for example `01-baseline.png`, `02-rerouted-after-hazard.png`.
- Put them in the exact folder name the statement requires.
- Reference them from the README.

## 3. Schedule

- Capture screenshots around **T+65–72**, then commit them together with README updates (the ~T+70 commit).
- If code changes after screenshots, check that the screenshots still match the final behavior.
- A deliverable that is not in the final eligible commit does not exist for the judges.

## 4. Verify in the repository

On the repository page (not your local folder):

- required folders/files are present in the final commit (including `docs/problem/` and `docs/BUILD_LOG.md`)
- images open
- README renders and lists identity, live link, run instructions, main features, bonus features, known problems, AI tools used, most useful prompt (plus any extra sections the statement requires)

## 5. Form checklist (before T+90)

- name and registration number correct
- repo URL opens without login
- final commit ID copied from the repository (full or first 7 characters)
- live URL opens in a clean Chrome profile without login
- the live site matches the final commit
