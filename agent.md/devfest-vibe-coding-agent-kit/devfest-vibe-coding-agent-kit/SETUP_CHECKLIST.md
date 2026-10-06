# 30-Minute Setup Checklist

This checklist is about environment readiness, not pre-building the contest app.

## Before contest day

- [ ] Written organizer confirmation that pre-authored AI instruction files (no project code) are allowed; screenshot or save it
- [ ] Decided how the kit reaches the lab PC (see below). **Do not carry a USB drive**: unauthorized external storage is a disqualification trigger
- [ ] Completed one timed 90-minute dry run with this kit (use the mock problem) and noted where the agent got stuck
- [ ] Phone charged, with authentication apps and hotspot ready (phone is for auth/hotspot only)
- [ ] ID card or registration confirmation ready

## Kit transport

Pick one and confirm it is permitted:

- [ ] Private GitHub repo (separate from the contest repo) or gist you can open after logging in during setup
- [ ] Instructions stored inside your AI tool's own cloud settings (project/custom instructions), loaded during setup
- [ ] Short master prompt typed or pasted at T+0 (smallest and safest fallback)

Keep the kit **out of the contest repository** before T+0. After T+0, add it only if organizers allow.

## Accounts

- [ ] GitHub login works
- [ ] GitHub 2FA/authentication is ready
- [ ] Codex/Claude/other AI tool login works
- [ ] Hosting account (Vercel/Netlify/Cloudflare Pages/GitHub Pages) login works, if the organizer permits preparation
- [ ] Browser can access required documentation/package registries

## Repository

- [ ] New public repo can be created
- [ ] Name format: `devfest-<registration-number>`
- [ ] Push access confirmed (git user name/email configured)
- [ ] README and MIT LICENSE added during setup, no project code
- [ ] Hosting can be connected to the repo for automatic deploy on push

## Machine

- [ ] Node.js/npm or chosen runtime available
- [ ] `npm install` works from the registry (test runner such as Vitest can be installed)
- [ ] Git available
- [ ] Browser opens the local development server
- [ ] Latest Chrome available for the final check
- [ ] You know the OS screenshot shortcut for required screenshots
- [ ] Network stable; backup connection available if using a personal laptop

## Ingest readiness (how the problem reaches the agent at T+0)

- [ ] You know how you will hand over the statement: copy text from the PDF/page and paste it, or attach the file(s) in your AI tool. Practise once with the mock problem
- [ ] You know how data files (JSON/CSV) get into the AI tool and into the repository folder without any external storage device
- [ ] The agent can read and write the repository folder and run `cp` and `git`
- [ ] You tried the T+0 prompt (PROMPT_BANK #1) on the mock problem and checked that `docs/problem/` was created with byte-identical sample files
- [ ] You have your full name and registration number ready to give to the agent for the README

## Do not pre-stage

- project source code
- previous app code
- starter template code
- reusable component library you authored yourself
- old local project copied into the contest repo
- secret/API credentials inside files
- a pre-filled README or `docs/` content for a problem you have not seen yet (the agent writes them from the real statement at T+0; the templates stay in the kit, outside the repo)

## Mental reset at T+0

Start a new timer. Treat the contest repository as disposable. The problem and sample data you receive at T+0 are the only product-specific truth. First action: intake and ledger (no code).
