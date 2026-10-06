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
- Pending: repository owner must supply the registration number and enable GitHub Actions as the Pages source if it is not already enabled.
