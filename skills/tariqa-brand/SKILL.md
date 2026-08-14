# Skill: tariqa-brand

**Purpose:** Guide AI agents in preserving and applying the Finca Tariqa brand identity — voice, visual system, personality, and positioning.

**When to use:** When writing new copy, creating new sections, designing page layouts, choosing colours, selecting imagery, or evaluating whether existing content "feels right."

**Relationships with other skills:** Works alongside `tariqa-editorial` (word-level rules) and `tariqa-engineering` (implementation rules).

---

## Brand essence

A real farm doing real work, documented honestly. Not aspirational lifestyle content. Not environmental activism. Not tech startup. The farm has a specific ecology, a specific history, and a specific owner making specific decisions. All of this is present in the brand.

**One sentence:** An 80-million-year-old limestone hillside being farmed and restored by someone learning in public.

---

## Positioning

| What Finca Tariqa is | What it is not |
|---------------------|----------------|
| A working citrus farm converting to organic | An eco-luxury retreat |
| A forest restoration project with legal/scientific grounding | A charity or NGO |
| A first-generation farm figuring things out | A multigenerational heritage estate |
| A project building toward carbon credits and eco-tourism | A completed, polished product |
| Woman-owned, founder-run | Faceless brand |

---

## Personality

- **Direct** — states things plainly without hedging or overselling
- **Precise** — uses specific names, numbers, species, dates (Navelina, not "orange variety")
- **Unhurried** — does not rush to the CTA; trusts the reader to get there
- **Grounded in place** — Carcaixent, Puig Gros, 39.118°N / 0.438°W, Valencia Late
- **Honest about difficulty** — DANA flooding, bureaucratic obstacles, long timelines are present
- **Comfortable with uncertainty** — "expected 2029" not "will achieve in 2029"

---

## Visual identity

### Typography
- **Headings**: Lora (serif, Google Fonts) — weight 400–700, italic for occasional emphasis
- **Body / UI**: Plus Jakarta Sans — weight 300–700

### Colour system
Always use CSS variables, never hardcode hex values.

```
--earth-dark:  #141f16   nav, footers, dark section backgrounds
--earth-mid:   #253c29   stat strips, secondary dark surfaces
--earth-med:   #3a6645   borders, active states, eyebrow text on light
--earth-light: #5a8f68   eyebrows on dark backgrounds
--sand:        #f4efe6   primary light surface, text on dark
--sand-deep:   #e8dfc8   hover states, secondary light surface
--terracotta:  #c4622d   primary CTA buttons, active nav link
--gold:        #c9973a   Support nav link, Grove Token, secondary accent
--white:       #fafaf8   page background, card backgrounds
--ink:         #141208   body text on white/sand
--mid:         #3d3828   secondary body text
```

### Section rhythm
- Dark sections (`--earth-dark` bg): hero sections, footers, CTA blocks, dark narrative sections
- Sand sections (`--sand` bg): contrast sections, carbon data, featured content
- White sections (`--white` bg): default content sections
- Alternate dark/white/sand to create rhythm — never two adjacent dark sections

### Hero pattern (all pages except homepage)
```
padding: calc(var(--nav-height) + 4rem) clamp(1.25rem, 6vw, 6rem) clamp(4rem, 8vw, 6rem)
align-items: flex-end (text anchors to bottom-left)
background: gradient overlays on --earth-dark or --earth-mid
h1: clamp(2.8rem, 5.5vw, 4.8rem), line-height: 1.08
eyebrow → h1 → lead paragraph
```

Homepage hero is intentionally centered — do not change.

### Eyebrow pattern
```html
<span class="eyebrow">Section Label</span>
```
Always precedes an h2 or h1. Uppercase, tight tracking, 0.72rem. Creates entry point before the main claim.

### Images
- The site currently has no real farm photography — only Midjourney renders for Camp Tariqa
- When adding images: contain them within border-radius wrappers, never full-bleed outside normal page flow
- `object-fit: cover` + `object-position` for controlled cropping within fixed-height containers
- Images accent content — they do not replace it

---

## Tone by context

| Context | Tone |
|---------|------|
| Hero headlines | Short, declarative. One idea. No filler. |
| Body copy | Specific, informative. Reads like a field note or a well-researched email. |
| CTAs | Honest about what the action is. Not "Join the movement." More "Adopt a tree." |
| Legal / planning content | Plain statement of facts. No dramatisation. |
| Carbon / ecological claims | Precise, hedged where uncertain. Always distinguish verified from estimated. |
| Gatherings / events | Warmer, more sensory — but still grounded in the actual place |

---

## Things to avoid

- "Regenerative" as an adjective applied to everything (overused, becoming meaningless)
- Superlatives: "unique," "incredible," "world-class"
- Passive voice where active is possible
- Marketing speak: "journey," "ecosystem," "synergy," "impact"
- Invented ecological or agricultural claims
- Making the farm sound finished when it isn't
- Lifestyle imagery: sun-drenched tables, artisan hands, mason jars
- Urgency pressure: "limited time," "act now"

---

## Evaluation criteria

When reviewing copy or design, ask:
1. Does this feel like it was written by someone who actually farms this land?
2. Is every specific claim verifiable or clearly labelled as estimated/proposed?
3. Does it use the exact vocabulary of this project (Navelina, DIC, Quercus ilex, Puig Gros)?
4. Would a grant reviewer find this credible?
5. Would a literate adult feel respected, not manipulated?

---

## Expected outputs

- Headlines that state a specific fact or decision rather than a feeling
- Body copy that earns the reader's trust through precision
- Section structure that breathes — eyebrow → h2 → one or two focused paragraphs
- CTAs that describe the action honestly
