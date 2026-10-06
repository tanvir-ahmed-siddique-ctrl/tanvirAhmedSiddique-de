# Git and Deployment

> Rebuilt for v3. The original file was not available when this kit was edited; the rules from the v2 patch are merged in.

## Git rules (rulebook)

- Public repository `devfest-<registration-number>`, MIT `LICENSE`, README from setup.
- At least 3 commits, one at least every 30 minutes. Internal cadence: ~T+20, ~T+45, ~T+70, final ~T+85 (optional docs commit ~T+10). No gap above 25 minutes.
- **Linear history only.** No force push, no rebase of pushed commits, no history edits, no repository deletion.
- Final eligible commit is created and pushed by T+90. Nothing changes after that.

## Commit message

```
<short summary of what changed>

Prompt: "<literal prompt used>"
```

- Use `Manual edit` when no AI was used. **Never invent or paraphrase a prompt.**
- If the prompt contained the pasted statement, write `[problem statement pasted]` in its place.
- Keep `docs/BUILD_LOG.md` in step with the commits.
- Commit often with working states; do not commit secrets, `node_modules`, or build output unless the hosting method needs it. Keep a correct `.gitignore`.

## Hosting

- Connect hosting to the repository early (if organizers allow it during setup) and deploy a **skeleton by about T+30**. Auto-deploy on push is fine, but nothing may change after T+90.
- Build command and output folder are set correctly (for Vite: `npm run build`, output `dist`).
- **GitHub Pages with a project path** (`https://user.github.io/repo/`): set the correct base path (for Vite, `base: '/<repo>/'`) or the site will be blank.
- **Client-side routing**: handle refresh on deep links (hash routing or rewrite rules), or use no routing at all.
- Check that assets load over HTTPS (no mixed content) and that the site works in a clean Chrome profile (no login, no extensions).

## Verification before submitting

1. Push the final commit; confirm it appears on the repository page.
2. Confirm the live site is **built from that exact commit** (hosting dashboard shows the commit).
3. Open the live URL in an incognito window and run the main journey and the language switch.
4. Confirm required deliverables (screenshots, `docs/`) open on the repository page.
5. Copy the final commit ID from the repository (full or first 7 characters).

Do not write the final commit hash into the README; editing it would change the hash. The hash goes in the submission form.

## If something fails late

- Push rejected: pull and re-push normally. Never force-push.
- Build fails on the host: fix the smallest cause, commit, push. Do not restructure.
- After T+90: stop. Tell the organizers if the infrastructure was at fault.
