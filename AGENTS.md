# AGENTS.md — Finca Tariqa

Operational instructions for AI coding agents (Claude Code, OpenAI Codex, and others).
Read this before touching anything. Full project context is in `docs/project-context.md`.

---

## Project identity

Finca Tariqa is a regenerative citrus farm and forest restoration project in Carcaixent, Valencia, Spain. The website is the public face of a real, ongoing ecological and agricultural project. It is not a design portfolio or a startup landing page.

The site is a static HTML/CSS site deployed on GitHub Pages. No build system. No framework. No npm. One shared stylesheet (`style.css`). Page-specific styles live in `<style>` blocks inside each HTML file.

---

## Source of truth hierarchy

When sources conflict, follow this order:

1. Current session instructions from Diana (highest authority)
2. Explicit recorded decisions in `docs/decisions.md`
3. This file (AGENTS.md)
4. `docs/project-context.md` and other docs
5. What already exists in the code
6. Agent assumptions (lowest — flag these, don't act on them silently)

When you detect a conflict between sources: state it, don't silently choose.

---

## Working principles

- **Preserve the project's distinctive identity.** This farm has a specific voice. Keep it.
- **Inspect before editing.** Read the file. Understand the surrounding context. Then change only what needs changing.
- **Prefer small, reviewable changes.** One thing per commit. The diff should be obvious.
- **Do not invent facts.** Especially ecological, scientific, agricultural, financial, or legal claims. Label anything uncertain. See "Fact discipline" below.
- **Do not make strategic decisions without approval.** Page structure, information architecture, business model copy, CTA wording — ask Diana.
- **Match the existing code style.** No reformatting unrelated code. No introducing patterns that don't already exist in the codebase.
- **No feature creep.** Don't add what wasn't asked for. A bug fix doesn't need a refactor. A text edit doesn't need new classes.

---

## Technical rules

### Editing pages
- Always `Read` the file before editing
- Page-specific CSS lives in `<style>` blocks in each HTML `<head>` — do not move it to `style.css`
- `style.css` contains only shared, reusable rules — nav, footer, buttons, sections, typography, utilities
- CSS variables are defined in `style.css :root` — use them, don't hardcode colours
- Local preview: `cd /Users/diana/Documents/finca-tariqa && python3 -m http.server 8765`, then open `http://localhost:8765/<page>.html`

### Navigation rules
- Top nav order: Oranges · The Land · The Forest · Camp Tariqa · Our Mission · Journal · Support
- "Support" uses class `nav-highlight` (renders in gold)
- Active page link uses class `active` (renders in terracotta)
- Blog subdirectory pages (`blog/*.html`) use `../` prefix on all href links
- Do not add or remove nav items without Diana's approval

### CSS variables (never hardcode these values)
```
--earth-dark: #141f16    --sand: #f4efe6
--earth-mid:  #253c29    --sand-deep: #e8dfc8
--earth-med:  #3a6645    --terracotta: #c4622d
--earth-light: #5a8f68   --gold: #c9973a
--white: #fafaf8         --ink: #141208
--mid: #3d3828
```

### Files that must never be auto-published via CMS
Edit these HTML files directly — the CMS (`tariqa-voice`) will overwrite custom markup:
- `blog/heat-resilience-report.html` — custom audio player with timing array
- `report.html` — geological report with custom layout and section markers
- `blog/index.html` — editorial list style enforced manually

### Hero block canonical values (all pages except index.html)
```css
padding: calc(var(--nav-height) + 4rem) clamp(1.25rem, 6vw, 6rem) clamp(4rem, 8vw, 6rem);
align-items: flex-end;
h1: clamp(2.8rem, 5.5vw, 4.8rem), line-height: 1.08;
lead: clamp(1rem, 1.6vw, 1.1rem), line-height: 1.75;
```
`index.html` hero is intentionally centered (text-align: center, align-items: center). Do not touch it.

### Security
- Never store passwords, API keys, or secrets in any file in this repo
- `fincatariqa@gmail.com` is the only sensitive datum permitted in repo files (it is in KNOWLEDGE.md which is gitignored)
- Stripe secret key must never appear in any file

---

## Design rules

- **Typography**: Lora (serif) for headings / display; Plus Jakarta Sans for body, UI, eyebrows, labels
- **Eyebrow pattern**: `<span class="eyebrow">Section Label</span>` — uppercase, tight tracking, 0.72rem
- **Lead paragraph**: class `lead` — larger, lighter weight, max 60ch
- **Dark sections**: `background: var(--earth-dark)` with `color: var(--sand)` text
- **Sand sections**: `background: var(--sand)` with `color: var(--ink)` text
- **White sections**: `background: var(--white)` — default page background
- **Images**: Use `object-fit: cover` + `object-position` when cropping. Always contain images within `border-radius` wrappers — never full-bleed outside the normal flow
- **Gradients**: Radial gradients using CSS — no image overlays
- **No stock photo aesthetic**: The visual language is quiet and typographic. Images accent, not dominate.

---

## Content rules

- Write for a literate adult who can tolerate complexity
- Specific beats vague: "Navelina, Navel Lane Late, Valencia Late" not "various orange varieties"
- Short sentences on dark backgrounds (they scan better)
- Do not invent narrative detail — if something is speculative, say so or omit it
- Audio narration style: spell out numbers, units, and chemical names in source HTML (e.g. "calcium carbonate" not "CaCO₃", "thirty to eighty euros per tonne" not "€30–80/t"). The TTS normaliser is a fallback.
- Do not remove copy without reading it in context — what looks like "excess text" often carries meaning

---

## Fact discipline

For all scientific, ecological, agricultural, geological, financial, and legal claims:

- **VERIFIED** — confirmed by published source or Diana
- **NEEDS VERIFICATION** — plausible but unconfirmed
- **ASSUMPTION** — reasonable inference, treat with caution
- **PROPOSED** — stated as future plan, not current fact

Do not convert an assumption into a fact in copy or documentation. If you are unsure of the status of a claim, label it rather than asserting it.

Examples of known VERIFIED facts:
- Location: Partida Puig Gros 34, Carcaixent, 46740, Valencia (39.118°N, 0.438°W)
- Area: 4.5 ha total (2.8 ha groves, 1.7 ha pine/oak forest)
- Trees: ~1,100 orange trees, aged 32–70+ years
- Varieties: Navelina, Navel Lane Late, Valencia Late
- Carbon market: EU CRCF (Regulation 2024/3012), operational ~2028

Examples of ASSUMPTION or PROPOSED:
- Carbon sequestration: "1–5 t/ha/yr" — range from literature, not measured on this land
- Carbon price: "€30–80/tonne" — market range, not a commitment
- DIC application timeline: Q4 2026 — Diana's plan, not confirmed by authorities

---

## Safety rules — agents must not

- Delete files without explicit approval
- Rewrite brand voice or page copy substantially without approval
- Add pages to the top navigation without approval
- Introduce unsupported scientific or environmental claims
- Replace the existing design system with a different one
- Make large architectural changes (moving CSS to a framework, adding npm, etc.) without explaining and getting approval
- Commit secrets, passwords, or API keys
- Force-push or destructively reset git history
- Run the CMS Publish action on custom-styled posts

---

## Where to find things

| What | Where |
|------|-------|
| Full project context | `docs/project-context.md` |
| Decision log | `docs/decisions.md` |
| AI work log | `docs/ai-work-log.md` |
| Current handoff | `docs/ai-handoff.md` |
| Repository map | `docs/project-map.md` |
| Git workflow | `docs/ai-git-workflow.md` |
| Brand skill | `skills/tariqa-brand/SKILL.md` |
| Editorial skill | `skills/tariqa-editorial/SKILL.md` |
| Engineering skill | `skills/tariqa-engineering/SKILL.md` |
| Project behaviour rules | `CLAUDE.md` |
| Private project facts | `/Users/diana/Documents/finca-tariqa-private/KNOWLEDGE.md` (not in this repo) |
| CMS rules | `/Users/diana/Documents/tariqa-voice/CLAUDE.md` (separate repo) |
