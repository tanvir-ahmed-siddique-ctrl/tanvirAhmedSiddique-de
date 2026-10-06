# Final Audit

> Rebuilt for v3. The original file was not available when this kit was edited; the additions from the v2 patch are merged in.

Run this before the final claim, around T+75–85. Report results as pass/fail with evidence. Fix highest-impact failures first. No new features.

## Checklist

**Build and tests**
- [ ] Production build succeeds
- [ ] Automated tests pass
- [ ] Every sample check passes (from `docs/problem/SAMPLE_CHECKS.md`)
- [ ] Adversarial fixtures behave (no crash, correct error code, all errors collected)

**Spec fidelity**
- [ ] Re-read `STATEMENT.md` and `CLARIFICATIONS.md` line by line against `LEDGER.md`
- [ ] Every MUST/RULE/LIMIT row works; ledger Status and Evidence are current
- [ ] Exact strings appear **verbatim** in English mode
- [ ] Tie-breaks, ordering, and limits behave as stated

**Deliverables**
- [ ] Required deliverables (for example the screenshots folder) exist **in the final commit** and open on the repository page
- [ ] `docs/problem/` holds the untouched statement and byte-identical sample files; `docs/BUILD_LOG.md` is complete
- [ ] MIT `LICENSE` present

**UX**
- [ ] Core journey works from a cold start on the live site
- [ ] Bangla/English switch changes every label, status, and error
- [ ] Responsive at narrow width; no console errors
- [ ] State never conveyed by color alone; required animations are brief and reduced-motion aware

**README**
- [ ] Generated from project memory; passes the stranger test (README_GENERATION.md)
- [ ] All rulebook fields present; statement-required sections present
- [ ] Every claim verified; coverage table matches reality; no AGENT comments or placeholders remain
- [ ] Links and images open on the repository page; no own-commit hash in the README

**Compliance**
- [ ] No backend, serverless functions, or participant-controlled persistence
- [ ] No secrets in the working tree or in history; no real private data
- [ ] Optional AI (if any) works only with a user-typed key; core works without it
- [ ] Linear Git history; at least 3 commits with prompts or `Manual edit`; gap never above 30 minutes

**Release**
- [ ] Final commit pushed (by T+90, ideally ~T+85)
- [ ] Live HTTPS site is built from the final commit and opens in clean Chrome
- [ ] Form fields ready: name, registration number, repo URL, final commit ID (copied from the repository), live URL

## Output format

```
PASS/FAIL per group, evidence, blocking issues, final commit ID, live URL.
```
