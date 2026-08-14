# AI Git Workflow — Finca Tariqa

Safe git workflow for Claude Code, OpenAI Codex, and any future AI agents.

---

## Before starting any task

```bash
# Check current state — never assume it's clean
git status
git log --oneline -10

# Check for large binary files that might be tracked
git ls-files audio/
git ls-files images/
```

Do not assume uncommitted changes are yours. Inspect before touching.

---

## Standard task workflow

1. **Pull latest before starting substantial work**
   ```bash
   git pull origin main
   ```

2. **Inspect current changes**
   ```bash
   git status
   git diff
   ```

3. **Work on the task**
   - Read files before editing (use Read tool, not cat)
   - Make focused, reviewable changes
   - Test locally: `python3 -m http.server 8765` → `http://localhost:8765/<page>.html`

4. **Review the diff before committing**
   ```bash
   git diff
   ```
   Make sure the diff matches intent. No accidental rewrites, no leftover debug code.

5. **Update documentation if the task was substantial**
   - Add entry to `docs/ai-work-log.md`
   - Update `docs/ai-handoff.md`
   - Record decisions in `docs/decisions.md` if any were made

6. **Stage specific files — never `git add -A` without inspecting**
   ```bash
   git add index.html oranges.html  # list files explicitly
   # or, if changes are all intentional:
   git diff --name-only  # see what changed
   git add <specific files>
   ```

7. **Commit with a clear message**
   ```bash
   git commit -m "short description of what changed and why"
   ```
   Good: `"camp: contain glamping image within section padding"`
   Bad: `"updates"`, `"fix"`

8. **Push to main**
   ```bash
   git push
   ```
   GitHub Pages deploys automatically. There is no staging environment.

---

## Branch strategy

This is a small solo project with no formal branch strategy. The default is to work directly on `main`.

Use a branch only when:
- Making large experimental changes (e.g., adding a new page with uncertain design)
- A task will span multiple sessions and needs review before going live

Branch naming if used: `feature/short-description` or `fix/short-description`

---

## Commit message conventions

```
<scope>: <what changed>
```

Scope (optional but helpful):
- `camp`, `fund`, `mission`, `forest`, `oranges`, `land` — specific page
- `nav` — navigation changes across all pages
- `style` — style.css changes
- `blog` — blog directory changes
- `docs` — documentation only (no website changes)
- `seo` — robots, sitemap, meta tags

Examples from this project's history:
- `camp: contain glamping image within section padding`
- `nav: move Full Report to footer only`
- `blog: fix broken cover image link`
- `docs: add AI collaboration infrastructure`

---

## Things never to do

- `git push --force` — never on main, never without explicit approval
- `git reset --hard` — only if you know exactly what you're discarding
- `git add .` or `git add -A` — too risky; always list files explicitly
- `git commit --amend` on a pushed commit — rewrites public history
- Commit `.env`, `KNOWLEDGE.md`, API keys, passwords, or secrets
- Skip pre-commit hooks with `--no-verify`

---

## Verifying a push worked

GitHub Pages usually deploys within 1–2 minutes of a push to main.

To check:
1. Go to `https://finca-tariqa.com/<page>.html` after ~2 minutes
2. Or check the GitHub Actions / Pages tab on `diana0xUX/finca-tariqa`

If something breaks after a push, the last working commit is visible in `git log`. Revert if needed:
```bash
git revert HEAD  # creates a new commit that undoes the last one — safe
```

---

## Uncommitted work from another agent

If you find uncommitted changes on startup that you didn't make:
1. Run `git status` and `git diff` to understand what changed
2. Do not `git checkout .` or `git restore .` — you may discard the other agent's work
3. Ask Diana what to do before proceeding
