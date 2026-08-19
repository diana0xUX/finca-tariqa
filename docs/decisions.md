# Decision Log — Finca Tariqa

Shared record of important decisions. AI agents should read this before changing anything that might conflict with a prior decision.

Format: Date · Title · Decision · Reason · Status · Source

---

## 2026-08-14 — Homepage hero remains centered

**Decision:** `index.html` hero uses `text-align: center`, `align-items: center`, `justify-content: center`. It does not follow the left-aligned hero standard applied to all other pages.

**Reason:** Diana explicitly requested this after the hero was changed to left-aligned. "Leave home page as it was." The centered layout is intentional for the homepage as the primary brand statement.

**Status:** Accepted

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — Hero canonical values for all pages except index.html

**Decision:** All non-homepage page heroes use:
```css
padding: calc(var(--nav-height) + 4rem) clamp(1.25rem, 6vw, 6rem) clamp(4rem, 8vw, 6rem);
align-items: flex-end;
h1: clamp(2.8rem, 5.5vw, 4.8rem), line-height: 1.08;
lead: clamp(1rem, 1.6vw, 1.1rem), line-height: 1.75;
```

**Reason:** Uniformity across pages. Diana requested same padding, font sizes, and left-aligned layout on all tabs.

**Status:** Accepted

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — Top nav order

**Decision:** Top navigation order is: Oranges · The Land · The Forest · Camp Tariqa · Our Mission · Journal · Support

**Reason:** Camp Tariqa moved before Our Mission. Full Report removed from top nav (moved to footer only).

**Status:** Accepted

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — Images contained within page flow (no full-bleed)

**Decision:** Images must be inside `.section-inner` padding containers, with `border-radius`, `max-height`, `object-fit: cover`, and `object-position` for cropping. No full-bleed image divs outside normal page flow.

**Reason:** Diana complained multiple times about images overlapping text and appearing too large. Full-bleed divs outside the flow caused visual chaos on camp.html.

**Status:** Accepted

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — Full Report in footer only

**Decision:** `report.html` link appears only in the footer, not in the top navigation.

**Reason:** Diana requested it removed from top nav. It's too detailed / specialist for primary navigation.

**Status:** Accepted

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — volunteers.html not in top nav

**Decision:** `volunteers.html` is accessible via footer only, not in the top nav.

**Reason:** Volunteer programme content was merged into `camp.html`. The standalone page still exists but isn't a primary nav destination.

**Status:** Accepted (but see open question — may be worth reconsidering)

**Source:** Diana (session 2026-08-14)

---

## 2026-08-14 — blog/index.html editorial list style

**Decision:** `blog/index.html` uses an editorial list style: `border-bottom` line separators only, no card boxes, no white backgrounds on list items, no box shadows.

**Reason:** Enforced by Diana and documented in `tariqa-voice/CLAUDE.md`. This style is also enforced in `_regenerate_index()` in server.py — both must stay in sync.

**Status:** Accepted

**Source:** tariqa-voice/CLAUDE.md

---

## 2026-08-13 — CMS cannot publish custom-styled posts

**Decision:** These files must never be published via the tariqa-voice CMS Publish button — edit directly in HTML only:
- `blog/heat-resilience-report.html`
- `report.html`
- `blog/index.html`

**Reason:** `_generate_post_html()` strips all custom markup. These files have audio players with timing arrays, custom stat boxes, and layout structures that cannot survive CMS regeneration.

**Status:** Accepted

**Source:** CLAUDE.md + tariqa-voice/CLAUDE.md

---

## 2026-08-13 — KNOWLEDGE.md gitignored (moved to private repo)

**Decision:** `KNOWLEDGE.md` is gitignored in this repo. Sensitive project facts live in `/Users/diana/Documents/finca-tariqa-private/KNOWLEDGE.md` (private repo `diana0xUX/tariqa-private`).

**Reason:** Security — KNOWLEDGE.md may contain sensitive financial or personal information.

**Status:** Accepted

**Source:** git commit 4b358fd

---

## 2026-08-14 — Audio files — partial git tracking (confirmed)

**Decision:** Two audio files are tracked in git (`audio/founder-story.mp3`, `audio/heat-resilience-report.mp3`). Two others are untracked (`audio/we-bought-a-farm-wed-never-farmed.mp3`, `audio/what-is-a-blockchain-certificate-for-regenerating-land.mp3`). This is an inconsistent state.

**Reason:** Audio files were committed for the two earliest posts before a policy was established. Newer audio files were not added. No explicit gitignore rule exists for audio.

**Status:** Accepted (as-is for now). Action needed: decide whether to gitignore `/audio/` entirely (and untrack existing) or commit all audio files. Ask Diana before changing this.

**Source:** `git ls-files audio/` audit 2026-08-14

---

## PROPOSED — Stripe integration on fund.html

**Decision:** Stripe will be integrated directly into `fund.html` for tree adoption payments.

**Reason:** Simplest path for a static site. No server required for Stripe Checkout redirect flow.

**Status:** Proposed (not yet built)

**Source:** Project context / Diana

---

## PROPOSED — DIC application Q4 2026

**Decision:** File Declaración de Interés Comunitario (DIC) application for Camp Tariqa development on suelo no urbanizable.

**Reason:** Required legal instrument to operate rural agro-tourism and event venue on non-urban classified land in Valencia.

**Status:** Proposed

**Source:** camp.html legal track section

---

## 2026-08-19 — Wallet addresses in fund.html added before domain launch

**Decision:** The placeholder wallet addresses (ETH, BTC, PayPal) in `fund.html` will be filled in before the site moves to its permanent domain. Do not flag them as bugs or prompt Diana to add them during pre-launch work sessions.

**Status:** Accepted — deferred to domain launch

**Source:** Diana (session 2026-08-19)
