# AI Handoff — Finca Tariqa

*Update this document at the end of every substantial task. The next agent reads this first.*

---

## Current project state (2026-08-14)

The site is live at `finca-tariqa.com`. All recent changes are pushed to `main` and deployed via GitHub Pages. The site is a static HTML/CSS project — no build step, no framework.

---

## Last completed task

**Hero uniformity + text reduction + Camp Tariqa nav additions** (August 14, 2026)

All page heroes are now left-aligned with canonical values, except the homepage which intentionally remains centered. Nav has been updated sitewide. Excess text removed from seven pages. Glamping imagery and gatherings content added to camp.html. Volunteer build content merged into camp.html.

---

## Current task

**Shared AI infrastructure setup** (August 14, 2026)

Creating `docs/`, `skills/`, and `AGENTS.md` to establish shared context and conventions for multi-agent work. No website changes in this task.

---

## Files being modified (current task)

- `AGENTS.md` (new)
- `docs/project-context.md` (new)
- `docs/decisions.md` (new)
- `docs/ai-work-log.md` (new)
- `docs/ai-handoff.md` (this file, new)
- `docs/project-map.md` (new)
- `docs/ai-git-workflow.md` (new)
- `skills/tariqa-brand/SKILL.md` (new)
- `skills/tariqa-editorial/SKILL.md` (new)
- `skills/tariqa-engineering/SKILL.md` (new)

---

## Important context for the next agent

1. **Diana is a UX designer, not an engineer.** Communicate in plain language. Don't paste long code blocks unless asked. Give one clear action at a time when she's overloaded.

2. **The farm has no live payments yet.** `fund.html` looks like a functioning store but Stripe is not connected. Do not claim payments work.

3. **mission-v2.html is an unapproved draft.** It exists at the root but has never been approved by Diana. Do not promote it or link to it without confirmation.

4. **camp.html is the most active page.** It was substantially rebuilt in this session. Read it carefully before editing — it has many page-specific CSS classes and image containment patterns.

5. **The CMS is separate.** `tariqa-voice/` manages blog posts and audio. Do not touch blog HTML via CMS Publish for `heat-resilience-report.html`, `report.html`, or `blog/index.html` — these have custom markup the CMS overwrites.

6. **Audio files in `/audio/` may be tracked in git.** Check with `git ls-files audio/` before any git operation that might push large binary files.

7. **Grove Token ecosystem is not deployed.** `contracts/GroveToken.sol` and `tokens/` exist but are not live. Related HTML pages are disallowed in robots.txt.

---

## Known problems (don't fix without Diana's input)

- `mission-v2.html` — draft, needs approval or deletion
- `volunteers.html` — not in top nav, may be intentional
- `sitemap.xml` — missing `camp.html` and `volunteers.html`
- `blog/land-certificates.html` — exists but not in blog index or sitemap
- No live payment processing
- No real farm photography on the site

---

## Do not change

- `index.html` hero — intentionally centered, not left-aligned like other pages
- `blog/index.html` editorial list style — `border-bottom` separators only, no cards
- `blog/heat-resilience-report.html` audio player markup
- `report.html` custom layout
- Top nav order: Oranges · The Land · The Forest · Camp Tariqa · Our Mission · Journal · Support

---

## Recommended next step

**Review and resolve `mission-v2.html`**: Either approve it as the replacement for `mission.html` and update all links, or delete it. It has been sitting as an unapproved draft. Ask Diana before acting.
