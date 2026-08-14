# Skill: tariqa-editorial

**Purpose:** Guide AI agents in writing and editing copy that matches the Finca Tariqa editorial standard — word-level precision, audio-readability, and content discipline.

**When to use:** When writing new page copy, editing existing copy, trimming text, writing blog posts, or preparing content that will be narrated by F5-TTS.

**Relationships with other skills:** Works alongside `tariqa-brand` (voice and positioning) and `tariqa-engineering` (audio player technical rules).

---

## Core principle

Every sentence must earn its place. If removing it doesn't change the meaning or weaken the argument, it shouldn't be there.

---

## Sentence-level rules

- **Specific over general**: "Navelina, Navel Lane Late, Valencia Late" not "several orange varieties"
- **Active over passive**: "The pine canopy blocks regeneration" not "Regeneration is blocked by the pine canopy"
- **Short on dark backgrounds**: Hero text and dark section copy reads better in short sentences. Use them.
- **Long where complexity warrants it**: Body copy in white sections can carry more detail — don't artificially break every thought into fragments
- **Numbers as numbers**: 1.7 hectares, 800 plants per hectare, €10,000 — not "approximately one point seven" (except for audio, see below)
- **No filler transitions**: "Additionally," "Furthermore," "It is worth noting that" — delete these

---

## Vocabulary to use

- **Varieties**: Navelina, Navel Lane Late, Valencia Late (always full names)
- **Species**: Quercus ilex, Aleppo pine, Pinus halepensis (scientific names when the context warrants it, otherwise holm oak / alzina)
- **Place**: Carcaixent, Puig Gros, Valencia, the limestone hillside, the grove, the upper zone / lower zone
- **Legal**: DIC (Declaración de Interés Comunitario), PTGFS (Plan Tècnic de Gestió Forestal Sostenible), CAECV, GVA, suelo no urbanizable
- **Carbon**: CRCF, Verra VCS VM0042, baseline, sequestration — not "carbon footprint," not "offsetting"
- **Camp**: glamping, demountable structures, agro-tourism rooms, event venue, basecamp — not "eco-lodge," not "retreat centre"

---

## What to trim (with care)

These patterns often appear and can usually be cut:
- Sentences that restate what was just said
- Throat-clearing intros: "The farm is committed to..." "We believe that..."
- Vague qualifiers: "quite," "very," "a bit," "somewhat"
- Tautological phrases: "natural and organic," "real and authentic"
- Aspirational claims that aren't grounded: "transforming the landscape" without specifics

**Warning**: Before cutting, read the surrounding paragraph. Some sentences that look like filler actually anchor a transition or carry a legal/factual caveat. Remove with intent, not with a macro.

---

## Audio narration rules

Blog posts and some page content is narrated by F5-TTS via the tariqa-voice CMS. Write for the ear in these contexts.

**Spell out in source HTML** (the TTS normaliser is a fallback, not a guarantee):
- Numbers: "thirty to eighty euros" not "€30–80"
- Units: "per tonne" not "/t", "hectares" not "ha"
- Chemical names: "calcium carbonate" not "CaCO₃", "carbon dioxide" not "CO₂"
- Species: "Quercus ilex" reads correctly as two words — keep it; "Pinus halepensis" likewise
- Abbreviations: "CAECV" is fine as-is (reads as letters); "CRCF" similarly. When in doubt, spell it out in a parenthetical on first use.
- Percentages: "forty percent" not "40%"
- Dates: "two thousand and twenty-six" is handled by the normaliser, but "twenty-twenty-six" is cleaner

**Sentence rhythm for audio**: Vary sentence length. Three short sentences followed by a longer one. Avoid three-clause sentences with multiple subclauses — they're hard to follow when listened to.

**Paragraph length for audio**: Keep paragraphs to 3–4 sentences. Longer paragraphs lose listeners.

---

## Blog post structure

Finca Tariqa blog posts are long-form field notes with research depth. Standard structure:

1. **Opening**: Place the reader in a specific moment or observation. No "In this article, we will..."
2. **The problem or question**: What is being investigated or reported
3. **Evidence and specifics**: Numbers, species, case studies, legal instruments — the meat
4. **What this means for the farm**: Connect back to Tariqa specifically
5. **What comes next**: Honest about uncertainty; don't round off to a tidy conclusion that isn't true

---

## Content that must not be invented

- Scientific/ecological measurements (carbon sequestration rates, soil pH, Brix levels)
- Regulatory timelines (DIC approval, CAECV certification, EU CRCF operational date)
- Financial figures (adoption pricing, grant amounts, carbon credit prices)
- Historical claims (Franco reforestation programme dates, DANA flood event details)

If you don't have a source, label the claim ASSUMPTION or NEEDS VERIFICATION. Don't write it as fact.

---

## Evaluation criteria

1. Could you remove any sentence without losing meaning? If yes, consider it.
2. Is there a vague claim that should be specific?
3. If narrated aloud, would any phrase sound unnatural?
4. Has any assumption been presented as a confirmed fact?
5. Does the copy use the vocabulary of the project or generic "sustainability" language?
