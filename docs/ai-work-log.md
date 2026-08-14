# AI Work Log — Finca Tariqa

Lightweight communication channel between AI agents. Record significant tasks here after completion.
Do not record every tiny edit. Record things the next agent needs to know.

---

## 2026-08-14 — Claude Code — Shared AI infrastructure setup

**Agent:** Claude Code (claude-sonnet-4-6)

**Task:** Establish shared documentation and collaboration infrastructure for multi-agent work (Claude Code + OpenAI Codex).

**Changes:**
- Created `docs/` directory
- Created `docs/project-context.md` — full project context document
- Created `docs/decisions.md` — decision log (seeded with all decisions from this session and earlier)
- Created `docs/ai-work-log.md` — this file
- Created `docs/ai-handoff.md` — handoff document
- Created `docs/project-map.md` — repository map
- Created `docs/ai-git-workflow.md` — git workflow for AI agents
- Created `AGENTS.md` — concise operational instructions (root level, readable by Claude and Codex)
- Created `skills/tariqa-brand/SKILL.md` — brand identity skill
- Created `skills/tariqa-editorial/SKILL.md` — editorial style skill
- Created `skills/tariqa-engineering/SKILL.md` — engineering conventions skill

**Decisions:**
- Created three skills only (brand, editorial, engineering) — sufficient for current project complexity; did not create speculative skills (growth, science-fact-check, business) that would have no immediate use
- Stored all decisions from the August 14 session in `docs/decisions.md`

**Open questions:**
- Is `mission-v2.html` ready to replace `mission.html`? It exists as a draft, was never approved.
- Should `volunteers.html` be in the top nav?
- Are audio files in `/audio/` tracked in git? (Run `git ls-files audio/` to check)
- Which admin console did Diana mean by "upload tariqa camp plan in admin console"?

**Files affected:**
- All new files under `docs/` and `skills/`
- `AGENTS.md` (new, root level)

**Next suggested action:**
Review `docs/decisions.md` for any decisions that need Diana's confirmation, particularly: `mission-v2.html` status, `volunteers.html` nav placement, and audio file git tracking.

---

## 2026-08-14 — Claude Code — Hero uniformity + text edits

**Agent:** Claude Code (claude-sonnet-4-6)

**Task:** Make first blocks uniform across all pages (same padding, font sizes, left-aligned). Remove excess text.

**Changes:**
- Applied canonical hero values (padding, h1 size, align-items: flex-end) to: oranges.html, land.html, forest.html, mission.html, fund.html, camp.html, volunteers.html
- Reverted index.html hero to original centered layout (Diana's instruction: "leave home page as it was")
- Removed excess text from: oranges.html, land.html, forest.html, mission.html, fund.html, camp.html, volunteers.html
- Removed "Full Report" from top nav on all pages (kept in footer)
- Added "Camp Tariqa" to top nav on all pages
- Swapped Camp Tariqa and Our Mission order in nav

**Files affected:**
- index.html, oranges.html, land.html, forest.html, mission.html, fund.html, camp.html, volunteers.html

---

## 2026-08-14 — Claude Code — Camp Tariqa + glamping content

**Agent:** Claude Code (claude-sonnet-4-6)

**Task:** Add glamping images and gatherings section to camp.html; merge volunteer build content from volunteers.html into camp.html below #phases.

**Changes:**
- Added `images/glamping-hillside-1.png`, `images/glamping-hillside-2.png`, `images/venue-gatherings.png`
- Added glamping gallery section to camp.html (single image, contained with border-radius)
- Added gatherings text section (cacao ceremonies, sound healing, bodywork) to camp.html
- Added "First, we build the camp" section (build list), "Builders. Learners. Both." (who-cards), "The exchange" (3-grid) below #phases in camp.html
- Multiple rounds of image size/containment fixes after user complaints about overlap

**Files affected:**
- camp.html, volunteers.html, images/ (3 new files)
