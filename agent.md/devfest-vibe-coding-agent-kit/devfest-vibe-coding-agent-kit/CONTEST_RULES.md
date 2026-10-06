# Official Rule Constraints — DevFest 2026 AI Vibe-Coding Contest

Source: `AI DevFest Vibe-Coding Contest (Solo) Rulebook.pdf` supplied for this project. This file is a concise operational summary; the organizer's rulebook remains authoritative.

## Event and format

- Contest: AI DevFest Vibe-Coding Contest (Solo)
- Date: 6 October 2026, listed as :30 PM to 5:30 PM in the rulebook
- Venue: Daffodil International University
- Build/deploy window: T+0 to T+90
- Setup: 30 minutes before T+0, not part of contest time
- App: browser-only web app, frontend only
- Languages: Bangla + English
- Live public HTTPS deployment required by T+90
- GitHub repository required; source must be public
- License: MIT
- Organizer contact (rulebook 13.3): cpc@diu.edu.bd

## The problem statement adds mandatory requirements

The problem and sample data are given at T+0. Anything the statement requires (specific files or folders such as screenshots, exact status strings, input limits, sample checks, required animations) is mandatory in addition to the rulebook. Organizers may change rules before or during the event and tell everyone; a live clarification wins over this summary.

## Before T+0 / setup

Allowed during the 30-minute setup:

- Log in to GitHub and AI tools.
- Create a new public repository named `devfest-<registration-number>`.
- Confirm you can push code.
- Add a README and MIT LICENSE.

Do **not** commit any project code before T+0.

## Starting from zero

The contest app must be written during the contest. Do not reuse your own old code, old projects, personal templates, or another participant's code. Open-source libraries and official starter tools such as Vite remain allowed.

Interpretation notes (not official wording):

- Installing packages from npm/CDN is explicitly allowed.
- Copy-paste component registries (source code copied into your repo by a CLI) are a gray area under "anyone else's code". Default: avoid unless organizers confirm; ask before the contest.
- Pre-written AI instruction/skill files are not mentioned in the rulebook. Get written confirmation before relying on them.

## Frontend-only boundary

Not allowed:

- participant-controlled backend servers
- server code/serverless functions used by the app
- participant-controlled persistent databases
- participant-controlled persistent online storage such as Firebase, Supabase, or Appwrite for that purpose

Allowed:

- localStorage
- sessionStorage
- IndexedDB
- normal browser APIs
- static hosting
- browser-callable external/public HTTPS APIs subject to the rulebook

## External APIs

External APIs may be used when they work directly from the browser (CORS) and are not used as the participant's persistent backend/database/storage layer. If an external API stops working, the **main parts** of the app should still work.

## AI inside the app

Optional. If used:

- main features must still work without AI
- the user must type their own API key into the app
- never put an API key in source code, the repository, or the live site

## Bilingual requirement

The app must work in Bangla and English. A language switch is a strong default. All main labels, buttons, messages, and instructions must exist in both languages (this includes statuses and validation errors; dataset labels may stay as supplied).

## Live site

The deployed site must:

- be public HTTPS
- open on a judge's own device
- require no login or installation
- run the main features
- match the final eligible commit
- remain available through judging/results

## Git requirements

- New public repo name: `devfest-<registration-number>`
- At least one commit every 30 minutes, at least 3 commits total
- Every commit message must state what changed and the AI prompt used; use `Manual edit` for manual changes
- No force-push, rebase of pushed history, repository deletion, or history manipulation
- Final eligible commit must be created and pushed by T+90

## Deadline behavior

At T+90:

- stop coding
- stop committing
- stop pushing
- stop deployment changes
- submit the form

T+90 to T+95 is submission-only and carries a 10-mark penalty.

## Lab rules to remember

- Phone: authentication and backup hotspot only. No coding, AI tools, messaging, or calls on it.
- No talking/messaging anyone but organizers (no chat apps, email, social media, remote access).
- Unauthorized external storage devices are a disqualification trigger.
- Do not disable security software or touch other people's files/PCs.
- Log out of all accounts and close the browser when finished.
- Extra time is considered only for verified organizer-provided equipment/internet problems.

## README requirements

The final repository README must include:

- full name
- registration number
- public HTTPS live link
- how to run the app
- main features completed
- bonus features
- known problems
- AI tools used
- most useful prompt

plus anything the problem statement adds (for example a screenshots section).

## Submission files

The repository must contain:

- source code
- `README.md`
- any output files requested by the problem (for example required screenshots)
- an MIT `LICENSE` file

## Data and licensing

- For testing, use only sample data supplied by organizers.
- Do not use/upload real personal or private company data.
- Respect licenses of third-party libraries, fonts, images, and files.

## Disqualification triggers relevant to the agent

- pre-written/old project code or templates
- copied/shared participant code
- prohibited communication with others during the contest
- unauthorized storage devices
- prohibited participant-controlled backend/database/online persistence
- altered Git history
- post-T+90 code/commit/push/deployment changes presented as submission
- false identity/information
- disruptive/dishonest behavior

## Rulebook caveat

The rulebook says the organizers may modify rules and that organizer decisions are final. If a live organizer clarification conflicts with this summary, the live organizer clarification wins.

## Project docs inside the repository (interpretation, not official wording)

After T+0 the agent saves contest-provided material (statement text, sample data, organizer clarifications) and a build log under `docs/` in the contest repository. These are documentation and contest-provided data, not pre-written project code.

- Raw sample files are kept byte-identical to what organizers gave.
- Default: commit `docs/problem/`. If organizers say the statement or data must not be republished, keep `docs/problem/` out of Git (add it to `.gitignore`) and keep only what the app strictly needs.
- The README must be honest about AI use: list the AI tools used and, if an instruction kit was loaded with organizer permission, say so briefly.
- Do not include a pre-contest document from another project (for example an old README) in the repository.
