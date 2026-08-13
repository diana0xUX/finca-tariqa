# Finca Tariqa — Grove Token Collection
## Master Reference Document

---

## What it is

1,100 NFT tokens, each tied to a real, specific orange tree on an 80-million-year-old limestone hillside in Valencia, Spain. The NFT is a living certificate — it carries the tree's real traits, updates every season with actual harvest data, and accrues history the longer you hold it.

---

## Business model

- **Initial purchase**: fiat only (€ via PayPal or ETH/USDC equivalent). Customer pays an annual adoption fee and receives a **mystery tree NFT** — rarity is assigned randomly from the eligible pool for their tier, not chosen.
- **Secondary market**: crypto only (ETH, USDC). No fiat after the initial purchase. Holders can trade tokens on secondary markets; the token's value is determined by its rarity and history.
- **No per-rarity pricing at point of sale.** The marketplace is a gallery showing what exists and what rarity looks like — not a price list.

---

## Adoption tiers (fiat, initial sale)

These live on **adopt.html**. Three tiers, each unlocking access to a different rarity pool.

| Tier | Spanish name | Annual fee | Rarity pool | Physical benefit |
|------|-------------|-----------|-------------|-----------------|
| Friend of the Tree | Amigo del Árbol | €99 / year | Common · Uncommon | 25 kg oranges, 2 deliveries |
| Godparent of the Tree | Padrino del Árbol | €175 / year | Rare · Epic eligible | 50 kg, 3 deliveries, named plaque on tree, harvest video |
| Custodian of the Tree | Custodio del Árbol | €290 / year | Epic · Legendary eligible | 80 kg, 5 deliveries, GPS on-chain, governance vote |

All tiers include: ERC-721 NFT on Polygon (via OpenSea), digital adoption certificate, welcome letter + harvest photo, seasonal metadata updates, level-up each renewal.

---

## Rarity system

Five tiers, determined by the combination of a token's 11 traits.

| Rarity | Color | Distribution (approx) |
|--------|-------|----------------------|
| Common | `#aaa` (grey) | ~56% |
| Uncommon | `#7ed490` (green) | ~27% |
| Rare | `#88b8ff` (blue) | ~11% |
| Epic | `#c07aff` (purple) | ~5% |
| Legendary | `#e8b840` (gold) | ~1% (≈10 tokens total) |

### Rarity calculation logic

Each trait option has a rarity tag (`common`, `uncommon`, `rare`, `epic`, `legendary`). The combined token rarity is calculated from the average score:
- **Legendary**: 2+ legendary traits, OR 1 legendary + 2+ epic
- **Epic**: 1+ legendary, OR 2+ epic with avg score ≥ 2.5
- **Rare**: 1+ epic, OR avg score ≥ 2.0
- **Uncommon**: avg score ≥ 1.2
- **Common**: everything else

Score mapping: common=0, uncommon=1, rare=2, epic=3, legendary=4.

---

## The genome — 11 traits

Every token is built from 10 weighted-random traits. Weights (`w`) control rarity of each option.

### 1. Tree Age
| Option | Rarity | Weight | Notes |
|--------|--------|--------|-------|
| Seedling | Uncommon | 8 | Pot close-up — no landscape traits in prompt |
| Young Sapling | Common | 20 | Young tree in a black plastic nursery bag, ready to be transplanted — bag prompt, no landscape traits |
| Established | Common | 22 | |
| Mature Grove Tree | Common | 35 | |
| Ancient Patriarch | Rare | 15 | References the 1957 geological survey trees |

Seedling and Young Sapling use simplified pot prompts — no canopy shape, trunk, fruit load, or ground traits apply.

### 2. Canopy Shape
| Option | Rarity | Weight |
|--------|--------|--------|
| Round & Full | Common | 33 |
| Wide Spread | Common | 23 |
| Precision Trimmed | Uncommon | 15 |
| Tall & Twisted | Uncommon | 18 |
| Ancient Gnarled | Rare | 11 |
| Dragon Crown | Epic | 8 |

### 3. Canopy Colour
| Option | Rarity | Weight |
|--------|--------|--------|
| Deep Teal | Common | 28 |
| Forest Green | Common | 23 |
| Midsummer Flush | Uncommon | 16 |
| Midnight Moss | Uncommon | 16 |
| Autumn Bronze | Rare | 10 |
| Storm Silver | Epic | 7 |
| Golden Sage | Legendary | 7 |

### 4. Trunk Character
| Option | Rarity | Weight | Notes |
|--------|--------|--------|-------|
| Straight Ancient | Common | 30 | |
| Double Twist | Uncommon | 22 | |
| Dragon Curl | Uncommon | 18 | |
| Grafted Union | Uncommon | 14 | Visible graft knob where bitter orange rootstock meets sweet orange scion; bark texture changes at union |
| Heritage Graft | Rare | 8 | 50+ year old graft scar, swollen knotted, dramatic rootstock flare |
| Spirit Root | Rare | 10 | |
| Celestial Spire | Epic | 6 | |

### 5. Fruit Load
| Option | Rarity | Weight |
|--------|--------|--------|
| Heavy Laden | Common | 30 |
| Full Harvest | Common | 25 |
| Medium | Uncommon | 20 |
| Sparse | Rare | 15 |
| First Blossom | Epic | 10 |

### 6. Fruit Character
| Option | Rarity | Weight | Notes |
|--------|--------|--------|-------|
| Standard Orange | Common | 35 | Classic round ripe oranges — no extra prompt |
| Navel | Common | 25 | Large distinctive navel oranges |
| Blood Orange | Uncommon | 16 | Deep crimson skin, split to show ruby-red flesh |
| Green-Skinned | Uncommon | 12 | Fully ripe but jade-green skinned |
| Buddha's Hand | Rare | 8 | Tentacle-like yellow fingers like golden octopuses clinging to branches |
| Twin Fused | Rare | 6 | Pairs of citrus fused together at the skin |
| Albino Citrus | Epic | 5 | Pale ghostly white-skinned, almost translucent |
| Violet-Skinned | Epic | 4 | Deep purple-violet skin, otherworldly |
| Crystal Citrus | Legendary | 3 | Semi-translucent crystalline, internal structure faintly glowing |
| Golden Orb | Legendary | 2 | Metallic gold-skinned, emits warm luminescence |

Fruit Load (quantity) and Fruit Character (type/appearance) are separate traits — they combine in the prompt. Seedling and Young Sapling skip both.

### 7. Sky
| Option | Rarity | Weight |
|--------|--------|--------|
| Sunset Ember | Common | 25 |
| Storm Dramatic | Common | 20 |
| Dawn Rose | Uncommon | 18 |
| Deep Night | Uncommon | 15 |
| Golden Noon | Rare | 10 |
| Mystical Teal | Epic | 8 |
| Blood Moon | Legendary | 4 |

### 8. Ground
| Option | Rarity | Weight |
|--------|--------|--------|
| Limestone Terrace | Common | 35 |
| Rolling Hills | Common | 30 |
| Exposed Roots | Rare | 22 |
| Sacred Stone | Epic | 13 |

### 9. Atmosphere
| Option | Rarity | Weight |
|--------|--------|--------|
| Clear Dramatic | Common | 30 |
| Golden Pollen | Uncommon | 25 |
| Rain Mist | Uncommon | 20 |
| Spirit Wisps | Rare | 15 |
| Storm Coming | Epic | 10 |

### 10. Special Trait
| Option | Rarity | Weight |
|--------|--------|--------|
| None | Common | 28 |
| Glowing Fruit | Uncommon | 12 |
| Ancient Face | Rare | 10 |
| Bee Swarm | Rare | 8 |
| Root Wisps | Epic | 7 |
| Lightning Scar | Epic | 6 |
| Cyberpunk Glitch | Epic | 6 |
| Laser Scaffold | Epic | 5 |
| Golden Branch | Legendary | 4 |
| Crown of Light | Legendary | 3 |
| Neural Root | Legendary | 4 |
| Virus Bloom | Legendary | 4 |

Cyberpunk specials (Glitch, Scaffold, Neural Root, Virus Bloom) introduce digital/sci-fi aesthetics — neon scan lines, laser lattices, bioluminescent data conduits, toxic spore eruptions.

### 11. Background World
| Option | Rarity | Weight | Notes |
|--------|--------|--------|-------|
| Natural Grove | Common | 45 | No extra background prompt |
| Industrial Collapse | Rare | 12 | Collapsed brutalist ruins, rusting iron, crumbling concrete engulfed by nature |
| End of World Sky | Rare | 10 | Apocalyptic burning horizon, massive storm wall, crimson ash clouds |
| Overgrown Ruins | Rare | 7 | Ancient overgrown temple ruins, stone split by roots, jungle consuming civilisation |
| Flooded City | Epic | 8 | Drowned city, submerged buildings beneath water, the tree the only living thing |
| Cyberpunk Megacity | Epic | 7 | Towering cyberpunk skyline, holographic billboards, neon-lit skyscrapers, flying vehicles |
| Nuclear Winter | Epic | 6 | Ashen grey snowfall, dead frozen earth, pale grey light, the tree impossibly alive |
| Space Void | Legendary | 5 | Cosmic void, stars and nebulae, tree floating in deep space with roots trailing into darkness |

---

## AI image generation

Images are generated via **fal.ai FLUX** API.

- **Model options**:
  - `fal-ai/flux/schnell` — fast, €0.003/image (4 inference steps)
  - `fal-ai/flux/dev` — quality, €0.025/image (28 inference steps)
- **Full collection cost**: ~€28 on Dev, ~€3.30 on Schnell (1,100 images)
- **API key**: stored in browser `localStorage` under key `fal_key`. Never hardcoded. Set via browser console: `localStorage.setItem('fal_key','your-key')`
- **Image size**: `square_hd` (1024×1024)
- **Output format**: JPEG

### Style anchor (appended to every prompt)
```
painterly digital fantasy art, rich jewel-tone color palette, cinematic warm directional sunlight with dramatic ambient occlusion, deep atmospheric background, Unreal Engine 5 painterly render quality, NFT collectible series, highly detailed illustration
```

### Prompt structure

Age-aware branching:
- **Seedling**: `{treeAge.prompt}, {sky.prompt}, {atmosphere.prompt}, {special if any}, {background if any}, {STYLE_ANCHOR}`
- **Young Sapling**: `{treeAge.prompt}, {canopyColor.prompt} fresh foliage, {sky.prompt}, {atmosphere.prompt}, {special if any}, {background if any}, {STYLE_ANCHOR}`
- **Established / Mature Grove Tree / Ancient Patriarch**: `{treeAge.prompt}, centered full-frame composition, {canopyShape.prompt} {canopyColor.prompt} canopy, {fruitLoad.prompt}, {trunkType.prompt} trunk with deeply textured ridged bark, {ground.prompt}, {sky.prompt}, {atmosphere.prompt}, {special if any}, {background if any}, {STYLE_ANCHOR}`

No Midjourney parameters (`--ar`, `--v`, `--stylize`) — those are MJ-only and break fal.ai prompts.

---

## Special mechanics

### Dutch auction (Legendary tokens)
The ~10 Legendary tokens do not sell at a fixed price. Each opens at **€500** and drops **€10/day** until claimed. The buyer decides when the price is right.

### Seasonal metadata updates
At the end of each harvest season, token metadata is updated on-chain with:
- Fruit yield from that tree
- Organic certification progress stage
- Soil carbon measurement change
- Season number / level title

Older tokens become more interesting — a tree held for 4 seasons has 4 seasons of real data.

### Level system
Each season a holder renews, their token levels up. Level titles escalate over time (Seedling → Sapling → Grove → etc.).

### Grafting
Two Season 3+ holders can "graft" their trees together. A real cutting is taken from each tree, a new sapling is planted on the hillside, and a new Grove Token is minted. The new token inherits one visible trait from each parent, plus one new trait of its own. **Maximum 100 graftings ever.**

### Badges
Non-transferable. Awarded to wallets for:
- First 30 adopters (any tier)
- Owning a DANA storm survivor tree
- Custodio tier during first holm oak planting season
- Collect all 3 orange varieties → Grove Master
- Collect all 5 rarity tiers → Full Spectrum
- Hold tokens across all 4 season frames → Year Round

---

## Technology stack

| Layer | Tech | Status |
|-------|------|--------|
| Blockchain | Polygon (OpenSea supported) | Planned — see note |
| Token standard | ERC-721 via OpenSea shared contract (lazy mint) | Planned |
| Metadata storage | OpenSea handles metadata on lazy mint | No Pinata/IPFS needed for launch |
| Future storage | Codex (IFT) — ZK-audited, economic repair incentives | Migrates from OpenSea storage when Codex reaches production (~2027) |
| Notifications | Waku (IFT) | Padrino+ tier |
| Minting | OpenSea lazy mint — NFT goes on-chain only at point of sale | No upfront gas cost |
| Secondary market | OpenSea native (collection already lives there) | |

**Chain note**: OpenSea does not support Linea. Options are Ethereum, Polygon, Base, Optimism, Arbitrum. **Polygon recommended** — lowest gas fees, native OpenSea support, transparent to non-crypto buyers.

---

## Orange tree varieties at Finca Tariqa

Three varieties on the land, each with different characteristics that feed into NFT traits:

| Variety | Notes |
|---------|-------|
| Clemenules | — |
| Navelina | — |
| Lane-Late | Longest-keeping navel variety; upper terrace |

Trees range from ~32 to 70+ years old. The oldest (documented in the 1957 geological survey) are Legendary-tier eligible.

---

## Files in this project

| File | Purpose |
|------|---------|
| `adopt.html` | Customer-facing adoption page — tiers, pricing, how it works |
| `marketplace.html` | NFT gallery browser — shows all rarity types, links to adopt.html. No prices (secondary crypto market) |
| `grove-ai-generator.html` | Internal tool — generates token art via fal.ai FLUX. Saves history to localStorage (`grove_generated`) |
| `grove-collection.html` | Design system — full genome, rarity weights, Midjourney prompt builder |
| `grove-generator.html` | SVG card preview — instant browser-side tree art, no API needed |
| `featured-tokens.html` | Showcase — 3 real AI-generated token cards with full trait breakdown |
| `tokens/` | Folder of saved AI-generated token images |
| `tokens/token-01-rare-bee-swarm.jpg` | Rare · Bee Swarm · Mystical Teal sky |
| `tokens/token-02-common-sunset.jpg` | Common · Full Harvest · Sunset Ember sky |
| `tokens/token-03-legendary-sacred-portal.jpg` | Legendary · Crown of Light · Blood Moon sky |
| `fund.html` | Funding page — ETH/BTC/PayPal (wallet addresses still placeholder) |
| `admin.html` | Internal dashboard — links to all tools and pages |
| `sitemap.html` | Visual site hierarchy |
| `KNOWLEDGE.md` | This file |

---

## Journal writing rules — audio-friendly text

Blog posts are narrated by the voiceover engine (F5-TTS). The engine reads what it sees. If the text says `CO2` the model guesses how to pronounce an ambiguous letter sequence and usually gets it wrong. Write for the ear, not the screen.

### Numbers

| Instead of | Write |
|-----------|-------|
| 42°C | forty-two degrees Celsius |
| 38°F | thirty-eight degrees Fahrenheit |
| 1,100 | eleven hundred (or one thousand one hundred) |
| 80 | eighty (for numbers under one hundred, spell them out) |
| 4th | fourth |
| 1st, 2nd, 3rd | first, second, third |
| 15–20% | fifteen to twenty percent |
| 35% | thirty-five percent |

**Rule**: spell out numbers below one hundred; use digits for larger numbers only if they appear alongside a spelled-out unit (e.g. "400 million years").

### Units of measurement

| Instead of | Write |
|-----------|-------|
| 15 kg | fifteen kilograms |
| 8 mg/L | eight milligrams per litre |
| 200 ppm | two hundred parts per million |
| 5 ha | five hectares |
| 2.5 cm | two and a half centimetres |
| pH 6.5 | a pH of six point five |

### Chemical compounds and scientific terms

| Instead of | Write |
|-----------|-------|
| CO2 | carbon dioxide |
| H2O | water |
| CaCO3 | calcium carbonate |
| Ca(HCO3)2 | calcium bicarbonate |
| K2O | potassium oxide |
| SiO2 | silica |
| Fe2O3 | iron oxide |
| NH4 | ammonium |
| NO3 | nitrate |
| pH | p-H (with a hyphen, so it reads as two letters) |
| N-P-K | nitrogen, phosphorus, potassium |

**Rule**: always use the common English name for a compound, not the formula. If you need the formula for scientific precision, put it in parentheses after the name — the engine will stumble on the formula but at least the spoken name is already there.

> Example: "The bedrock is almost pure calcium carbonate (CaCO3), laid down…"

### Ranges and ratios

| Instead of | Write |
|-----------|-------|
| 10:1 | ten to one |
| 3–5 days | three to five days |
| 15-15-15 fertiliser | fifteen fifteen fifteen fertiliser |
| 80M years | eighty million years |

### What the auto-normalizer already handles (no need to fix in text)

The server-side normalizer rewrites these automatically before passing text to the engine. You don't have to fix them manually in the HTML, but spelling them out in the source is still better practice:
- `°C` / `°F` → degrees Celsius / Fahrenheit
- `%` → percent
- Unicode subscripts (`₂`, `₃`) and superscripts → plain digits
- Common compounds from the lookup table above

---

## Open tasks

- [ ] Generate full 1,100 token images (~€28 Dev / ~€3.30 Schnell)
- [ ] Replace placeholder wallet addresses in `fund.html` (ETH, BTC, PayPal)
- [ ] Connect waitlist form to email service (Tally.so, Mailchimp, or Buttondown)
- [ ] Call CAECV re: organic certification — **96 253 82 41**
- [ ] Awaiting replies: Exagro (cooperative) and José Antonio Iranzo Albelda (previous owner) re: treatment history

---

## Key decisions log

| Decision | Rationale |
|----------|-----------|
| Fiat for initial purchase only | Simpler onboarding; no crypto wallet required to adopt |
| No per-rarity marketplace pricing | Rarity is assigned randomly; marketplace is a gallery, not a shop |
| Mystery tree model | Customer pays tier fee, gets random tree from eligible pool — aligns incentives and builds excitement |
| fal.ai FLUX over Midjourney | API access, no Discord required, cost-effective, batch-generatable |
| STYLE_ANCHOR constant | Locks visual style across all 1,100 generated images for a coherent collection |
| localStorage for generator history | Images persist across sessions; history visible in marketplace after generation |
| OpenSea lazy mint (not custom contract) | No smart contract to deploy; OpenSea handles minting at point of sale; simpler and faster to launch |
| Polygon over Linea | OpenSea does not support Linea; Polygon has lowest gas fees of supported chains |
| Codex as future storage layer | IFT's own protocol; stronger durability guarantees than IPFS |
| Cyberpunk + Background World traits | Expands artistic range beyond realistic grove scenes — dystopian, sci-fi, and cosmic settings create collector excitement and visual variety within the same style anchor |
| Pot prompt for Seedling / Young Sapling | These ages have no canopy shape, trunk, fruit load, or ground traits — buildPrompt() branches on age to avoid nonsensical prompts |
