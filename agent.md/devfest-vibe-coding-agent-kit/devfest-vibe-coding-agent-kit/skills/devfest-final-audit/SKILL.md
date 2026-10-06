---
name: devfest-final-audit
description: Final verification pass for a DevFest contest submission before claiming it is done. Use at about T+75-85, or whenever the person says final check, audit, ready to submit, verify, or deadline, even if they do not name this skill. Runs tests and the production build, verifies exact strings, required deliverables in the final commit, README accuracy, bilingual coverage, rule compliance, and that the live deployment matches the final commit, then records the commit ID.
---

# DevFest Final Audit

> Rebuilt for v3. The original file was not available when this kit was edited; the v2 patch additions are merged in.

Full checklist: `../devfest-vibe-coding/references/FINAL_AUDIT.md`. Be a strict judge. Report pass/fail with evidence. No new features.

## Steps

1. **Run the automated tests** and the production build. Record the real results.
2. **Re-read** `docs/problem/STATEMENT.md` and `CLARIFICATIONS.md` against `LEDGER.md`, row by row. Update Status and Evidence.
3. **Verify exact strings** appear verbatim in English mode; check the Bangla equivalents and that errors are bilingual.
4. **Verify sample checks and adversarial fixtures** (empty, ties, invalid, boundary, unseen-scale data).
5. **Verify deliverables are in the final commit** and open on the **repository page** (for example `screenshots/`, `docs/problem/`, `docs/BUILD_LOG.md`, `LICENSE`).
6. **Verify the README**: generated from project memory, passes the stranger test, every claim verified, rulebook fields and statement-required sections present, no placeholders or AGENT comments, no own-commit hash, links and images open.
7. **Check compliance**: no backend or participant-controlled persistence, no secrets in the tree or history, optional AI only with a user-typed key, linear Git history, at least 3 commits with prompts or `Manual edit`.
8. **Verify the live deployment** is built from the final commit and works in clean Chrome (no login, no install), including the language switch.
9. **Record the final commit ID** (copied from the repository) and prepare the form fields: name, registration number, repo URL, commit ID, live URL.
10. **Stop at T+90.** No code, Git, or deployment changes after that.

## Output

```
PASS/FAIL per group, evidence, blocking issues, final commit ID, live URL.
```
