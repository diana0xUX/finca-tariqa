# Finca Tariqa — Project Context

*Shared context for AI agents. Last updated: 2026-08-14.*

---

## Project overview

Finca Tariqa is a first-generation, woman-owned regenerative citrus farm and forest restoration project on an 80-million-year-old limestone hillside in Carcaixent, Valencia, Spain. Founded ~2022 by Diana.

The website is the primary public face of the project. It serves as: a funding platform (tree adoption), a journal, a place to recruit volunteers and collaborators, and a long-term record of the ecological project.

**What the site is trying to accomplish:**
1. Convert visitors into tree adopters (recurring revenue)
2. Build credibility for grant applications (Ma Earth, carbon certification)
3. Attract skilled volunteers and builders for Camp Tariqa
4. Document the ecological transition for long-term legitimacy

---

## Current state (August 2026)

The site is live at `https://finca-tariqa.com`. Deployed automatically from the `main` branch of `diana0xUX/finca-tariqa` via GitHub Pages.

The farm is in Year 1 of its public campaign (€10,000 goal). Organic certification is in progress (CAECV registration, full organic status expected 2029). No Stripe integration is live yet — the "Support" page is a soft launch / signal-gathering stage. Camp Tariqa is in early planning — DIC (Declaración de Interés Comunitario) application has not yet been filed.

---

## Brand

### Essence
A working farm that is honest about what it is and where it's going. Not a fantasy of rural life — a real ecological transition with real costs, timelines, and bureaucratic obstacles.

### Positioning
- Not: eco-luxury retreat, charity project, hobbyist smallholding
- Yes: serious long-term ecological and agricultural project, first-gen owner learning publicly

### Personality
- Direct, unhurried, precise
- Grounded in place (limestone, Valencia, specific varieties)
- Comfortable with complexity and uncertainty
- Never boosterish, never apologetic

### Visual identity (CONFIRMED)
- **Typefaces**: Lora (serif, headings) + Plus Jakarta Sans (sans-serif, body/UI)
- **Colour palette** (CSS variables):
  - `--earth-dark: #141f16` — deepest forest green, used for nav, footers, dark sections
  - `--earth-mid: #253c29` — mid forest, stat strips
  - `--earth-med: #3a6645` — active green, borders
  - `--earth-light: #5a8f68` — lighter green, eyebrows on dark
  - `--sand: #f4efe6` — warm cream, primary light text
  - `--sand-deep: #e8dfc8` — deeper cream, hover states
  - `--terracotta: #c4622d` — primary CTA, active nav state
  - `--gold: #c9973a` — secondary accent, Support nav highlight, Grove Token
  - `--white: #fafaf8` — page background, card backgrounds
  - `--ink: #141208` — body text
  - `--mid: #3d3828` — secondary text
- **Border radii**: sm 4px / md 8px / lg 16px / xl 24px
- **Transition**: 0.22s ease

### Things that make Tariqa distinctive
- Specific geology (80M-year limestone, Puig Gros)
- Named orange varieties with real harvest windows
- DANA flood recovery as part of the story
- Carbon baseline work as economic future, not greenwashing
- Grove Tokens (NFTs with real tree metadata) — unusual combination
- F5-TTS narrated journal posts

### Things to avoid
- Generic "sustainable farm" language
- Stock photography aesthetic (no site has actual photos yet — art direction TBD)
- Carbon credit boosterism without caveats
- Inventing environmental credentials not yet earned
- SaaS-style UI patterns (gradients, cards, carousels for their own sake)

---

## Stories currently on the site

1. **Founder story** — bought a farm, had never farmed, learning in public (`blog/we-bought-a-farm-wed-never-farmed.html`)
2. **Heat resilience** — research on citrus stress physiology at 42°C, five case studies (`blog/heat-resilience-report.html`)
3. **Geology** — full geological and hydrological survey of the limestone formation (`report.html`)
4. **Forest transition** — Aleppo pine → Quercus ilex (holm oak) over 15 years (`forest.html`)
5. **Land** — 80M-year limestone formation, how geology shapes the fruit (`land.html`)
6. **Camp Tariqa** — plans for eco-venue, agro-tourism, glamping, volunteer basecamp (`camp.html`)

---

## Audience

**CONFIRMED:** Tree adopters — European urban professionals interested in sustainability, connection to food origin, and place-based projects. Likely 30–55. Gift purchasers (tree adoption as a gift).

**CONFIRMED:** Grant bodies — Ma Earth (Round 4, April 2027), EU carbon credit scheme (~2028), Spanish agricultural subsidies.

**CONFIRMED:** Skilled volunteers and builders — people who want to contribute time + skills in exchange for accommodation, food, and learning.

**ASSUMPTION:** Retreat / gathering attendees — people interested in cacao ceremonies, sound healing, bodywork, nature-based gatherings. Camp Tariqa section addresses this but the venue doesn't exist yet.

**ASSUMPTION:** NFT / crypto-adjacent audience for Grove Tokens — this audience has not been tested and may overlap minimally with tree adopter audience.

---

## Business model

### Existing (soft launch only — no live payments yet)
- **Tree adoption subscriptions**: Amigo €99/yr (3 kg), Padrino €175/yr (10 kg), Custodio €290/yr (25 kg + harvest day). Founding adopter pricing locked 3 years.
- **One-time donations**: Any amount, linked from Support page

### Planned (within 12 months)
- **Stripe integration** on `fund.html` — not yet live
- **Grove Tokens**: ERC-721 NFTs on Polygon, one per adopted tree, seasonal metadata updates. Smart contract (`contracts/GroveToken.sol`) exists but is not deployed. Token imagery exists (`tokens/`).
- **Eco-tourism / Camp Tariqa**: Rural event venue, agro-tourism rooms, glamping terraces. Dependent on DIC approval (application not yet filed, targeted Q4 2026).

### Speculative (2028+)
- **Carbon credits**: Soil carbon baseline in progress with IVIA-accredited lab. Verra VCS VM0042 pathway planned. EU CRCF Framework operational ~2028. Target 1–5 t/ha/yr at €30–80/tonne.
- **Grove Token secondary market**: Depends on tree adoption adoption rate.

---

## Website

### Navigation (confirmed current state)
Top nav (all pages except blog subdir): Oranges · The Land · The Forest · Camp Tariqa · Our Mission · Journal · Support
Footer: Oranges · Land · Forest · Mission · Full Report · Journal · Support · Our Plans

Blog subdirectory (`blog/`) uses `../` prefix links and a slightly different nav style.

### Pages

| File | Purpose | Status |
|------|---------|--------|
| `index.html` | Homepage — overview, mission, adoption CTA | Live |
| `oranges.html` | Three citrus varieties, terroir, harvest windows | Live |
| `land.html` | Geology, hydrology, soil chemistry | Live |
| `forest.html` | Holm oak restoration, timeline, carbon connection | Live |
| `camp.html` | Camp Tariqa — venue, glamping, gatherings, volunteer build | Live |
| `volunteers.html` | Volunteer programme detail (footer only, not in top nav) | Live |
| `mission.html` | Four revenue streams, grant application context | Live |
| `fund.html` | Tree adoption tiers, how-it-works, Stripe (pending) | Live |
| `campaign-2026.html` | Itemised €10,000 Year 1 budget breakdown | Live |
| `report.html` | Full geological survey — custom layout, long-form | Live (footer only) |
| `roadmap.html` | Project plans and timeline | Live (footer only) |
| `sitemap.html` | HTML sitemap | Live |
| `blog/index.html` | Journal index — editorial list style | Live |
| `blog/we-bought-a-farm-wed-never-farmed.html` | Founder story with audio | Live |
| `blog/heat-resilience-report.html` | Heat research with audio | Live |
| `blog/land-certificates.html` | Land certificate article | Live |
| `mission-v2.html` | Draft redesign of mission.html | DRAFT — not approved |
| `grove-ai-generator.html` | AI grove generator tool | Not public (robots.txt disallowed) |
| `grove-collection.html` | Grove Token collection | Not public |
| `grove-generator.html` | Grove Token generator | Not public |
| `grove-map.html` | Interactive grove map | Not public (assumed) |
| `marketplace.html` | Token marketplace | Not public (assumed) |
| `featured-tokens.html` | Featured tokens display | Not public (assumed) |

### Major user journeys
1. Homepage → fund.html (adopt a tree)
2. Homepage → blog/ (read, build trust)
3. camp.html → contact (volunteer / collaborate)
4. mission.html → fund.html (grant credibility → adoption)

### Key CTAs
- "Adopt a tree" (fund.html) — primary conversion
- "Get in touch" (camp.html) — volunteer enquiries
- "Support the campaign" (campaign-2026.html) — one-time donation
- "Read the Journal" (blog/) — engagement

---

## Technical architecture

### Framework
None. Pure static HTML + CSS + vanilla JS. No build system, no bundler, no npm.

### Hosting & deployment
- GitHub Pages, auto-deploy from `main` branch
- Repo: `diana0xUX/finca-tariqa`
- Domain: `finca-tariqa.com`
- Local path: `/Users/diana/Documents/finca-tariqa/`

### Stylesheets
Single shared stylesheet: `style.css` in root. All pages `<link rel="stylesheet" href="style.css">` (blog pages use `../style.css`). Page-specific CSS is in `<style>` blocks in each HTML file.

### Fonts
Google Fonts CDN: Lora (serif) + Plus Jakarta Sans (sans). Loaded via `<link rel="preconnect">` + `<link rel="stylesheet">` in each page head.

### JavaScript
Vanilla JS, inline `<script>` blocks only. No external JS libraries. Used for: mobile nav toggle, blog audio player timing, scroll interactions.

### CMS
Separate project: `/Users/diana/Documents/tariqa-voice/` — Flask app on port 5173. Manages blog post drafts, triggers F5-TTS audio generation, and regenerates blog index HTML. **Not part of this repository.**

### Audio
Narrated blog posts use F5-TTS via tariqa-voice. Audio files stored in `/audio/` (root, gitignored via KNOWLEDGE.md). Blog audio: `blog/images/real/` subdirectory (not fully audited).

### NFT / Blockchain
Smart contract: `contracts/GroveToken.sol` (ERC-721 on Polygon). Not yet deployed. Token imagery in `tokens/` (JPG stills + MP4 videos). Token-related pages are not public (robots.txt disallowed).

### Dependencies
- No npm / package.json
- No server-side rendering
- No database
- No API endpoints (Stripe integration planned but not built)

### SEO
- `robots.txt` — allows AI assistants (GPTBot, ClaudeBot, etc.), disallows training crawlers (CCBot, Google-Extended)
- `sitemap.xml` — 12 URLs
- `llms.txt` — structured summary for AI agents
- Per-page Open Graph + Twitter Card meta
- Schema.org JSON-LD on homepage (Organization + WebSite)

---

## Known problems

1. **No live payments** — fund.html has adoption tiers but no Stripe integration. The page is aspirational.
2. **No actual photos** — all hero sections use CSS gradient backgrounds. No real photography of the farm exists on the site yet. Glamping imagery is Midjourney renders.
3. **mission-v2.html** exists as an unapproved draft — should be reviewed and either published (replacing mission.html) or deleted.
4. **Grove Token ecosystem not deployed** — contract, collection pages, and marketplace exist as code but nothing is live on-chain.
5. **camp.html content load** — the page is 46KB, the heaviest of the main pages. Worth monitoring as sections grow.
6. **volunteers.html not in top nav** — only reachable from footer. May be intentional or may be an oversight.
7. **sitemap.xml doesn't include camp.html or volunteers.html** — incomplete.
8. **blog/land-certificates.html** — exists in blog directory but not listed in blog index and not in sitemap. Status unclear.
9. **Audio files** — `audio/` directory exists but is not in `.gitignore` (only `KNOWLEDGE.md` and `.env` are gitignored). Large binary audio files may be tracked in git. Verify before any git operations.

---

## Open questions (require Diana's input)

1. Is `mission-v2.html` ready to replace `mission.html`?
2. Should `volunteers.html` be in the top nav?
3. Which admin console was meant in "upload tariqa camp plan in admin console"?
4. Is Stripe going to be integrated directly in `fund.html` or via a separate checkout flow?
5. Should Grove Token pages eventually go public, or remain dev-only?
6. Are audio files tracked in git? (Check `git ls-files audio/` before pushing large commits.)
