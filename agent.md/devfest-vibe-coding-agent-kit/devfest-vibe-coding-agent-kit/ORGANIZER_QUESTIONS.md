# Questions to Clarify With Organizers

Ask only questions that materially affect compliance or interpretation. The rulebook says participant questions are allowed only during T+0 to T+15; resolve everything you can **before** the contest (rulebook contact: cpc@diu.edu.bd). Keep the written answer.

## A. Before contest day (highest priority)

> Are pre-authored AI instruction files such as `SKILL.md` / `AGENTS.md` allowed to be loaded by our AI coding agent, provided they contain no project source code, old templates, components, or reusable assets?

> If allowed, how may we access them on the lab PC? (We will not bring any external storage device.) Is a private GitHub repo or our AI tool's cloud settings acceptable during the 30-minute setup?

> Is it acceptable to install open-source UI packages from npm during the contest, and is copy-paste source from component registries (installed via a CLI) considered "anyone else's code"?

> Is it acceptable to connect our hosting account (Vercel/Netlify/Cloudflare Pages) to the empty repository during setup so that the final commit deploys automatically?

> May we save the problem statement text, the provided sample data files, and a build log under `docs/` in our repository, and mention in the README which AI tools (and any instruction files containing no project code) we used?

## B. Other useful clarifications

> If we use a public browser-callable API for an optional enhancement, is it acceptable to cache only the current session's response in `sessionStorage` or `localStorage`?

> Are pre-existing personal UI design-system documents or prompt documents allowed, provided they contain no source code or app template?

> Does a static deployment through a service such as Vercel/Netlify/Cloudflare Pages count as compliant when it is deployed from the final public GitHub commit?

> Which exact browser version/build will judges use, if known?

> Are the provided sample data files expected to be bundled in the repository, or only used to construct in-app local sample state?

> Are third-party fonts, icons, and images acceptable if their licenses allow it (listed in the README)?

## C. T+0 to T+15 protocol

Ask at most 3–5 questions. Make each one answerable with yes/no and state your default.

Typical ambiguity types worth asking (pick only those the statement leaves open):

- Does an empty/duplicate/extra field count as invalid or is it tolerated?
- What does **Reset** restore, and does it also clear the user's current selection?
- When two results tie, is the order in the statement complete, or is there another tie-break?
- Must statuses/errors use the exact English strings in the statement, and what Bangla wording is acceptable?
- Should numbers and dataset labels stay as supplied in Bangla mode?
- Which files or folders must be in the repository besides the README and LICENSE?
- Is saving progress/state expected, or bonus only?

If the answer matters to everyone, organizers will announce it to all. Record your default for anything unanswered in the README.
