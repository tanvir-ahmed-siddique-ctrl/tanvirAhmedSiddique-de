# Build Log

## Intake and planning

- Prompt: "Start implementing the merged competition plan."
- Changed: preserved the official statement and sample pack, documented sample anomalies, acceptance checks, assumptions, and the requirements ledger.
- Verified: copied requirements JSON is byte-identical to the supplied file; both duplicate experience PDFs share the same SHA-256 digest.
- Deployment state: local repository has no configured remote.

## Core application and compliance engine

- Prompt: "Start implementing the merged competition plan and connect the supplied GitHub repository."
- Changed: React/TypeScript application shell, validated requirements loader, browser PDF inspection, thumbnails, SHA-256 duplicates, safe matching, expiry/status engine, bilingual UI, ordered PDF generation with a reserved footer strip, and automated sample-output generation.
- Verified: 12 compliance tests pass; production build succeeds; browser sample flow rejects the PNG and detects both duplicate experience PDFs.
- Decisions: auto-match only applies when exactly one non-duplicate file suggests a requirement; ambiguous Trade License and Experience candidates remain manual.

## Deliverables and release preparation

- Prompt: "Connect the supplied GitHub repository and continue the build without rewriting existing history."
- Changed: generated the required 16-page sample package, added the status screenshot, README, MIT license, exact upload-boundary tests, and GitHub Pages workflow.
- Verified: PDF pages 1, 2, 3, and 16 render without overlap; full Bangla switch works in the browser; required status screenshot is readable at desktop width.
- Pending: repository owner must enable GitHub Actions as the Pages source if it is not already enabled.

## Deployment runner compatibility

- Prompt: "Push the project to the supplied repository and verify the deployment."
- Changed: pinned the CI package manager to the locally verified pnpm release and explicitly allowed only `esbuild`'s required native install step.
- Verified: the GitHub failure was reproduced locally as `ERR_PNPM_IGNORED_BUILDS`; frozen-lock install, tests, and build are rerun after this targeted fix.

## Correct competition repository

- Prompt: "Move the verified project to the registration-number repository, commit all current work now, and use a polished faithful prompt in the commit."
- Changed: added participant identity and registration number, updated the Pages URL, and switched the Git remote to the correctly named competition repository.
- Verified: full test/build gate and the new remote push are checked before handoff.
