# finca-tariqa — Claude behaviour rules

## What this project is
Static site published via GitHub Pages from `diana0xUX/finca-tariqa`.
Local path: `/Users/diana/Documents/finca-tariqa/`
CMS lives in a separate project: `/Users/diana/Documents/tariqa-voice/` (Flask, port 5173).

**Private notes** (KNOWLEDGE.md, sensitive documents) → `diana0xUX/tariqa-private` (private repo)
Local path: `/Users/diana/Documents/finca-tariqa-private/KNOWLEDGE.md`

## Journal index style

`blog/index.html` uses a full-bleed layout:
- **Hero**: full-viewport cover image with transparent nav overlay, title + excerpt over dark gradient, "Read the story →" button bottom-right
- **Below fold**: horizontal story rows (280px thumbnail left, text right) with greyscale→colour hover
- **CTA strip**: dark green block before footer
- Cover image: `blog/images/cover-founder-story.jpg` (most recent / featured post)
- Secondary images: `blog/images/cover-*.png` per post

`_regenerate_index()` in tariqa-voice/server.py still generates the old editorial list style — do NOT run Publish for index from the CMS, edit `blog/index.html` directly.

## Audio player — heat-resilience-report.html

The audio player is embedded directly in the HTML (not CMS-generated).
- Audio bar HTML is before `<footer>`
- `const TIMING = [...]` in the `<script>` block has 59 entries (0.0s – 1314.572s)
- `data-para="N"` attributes on `<p>` tags enable click-to-seek and highlight sync
- Speed slider: min 0.5×, max 2×, step 0.1
- The server auto-patches `const TIMING` after audio regeneration via regex in `_run_generation()`

Do not run Publish from the CMS editor for this file — it would overwrite all custom markup.

## Custom-styled posts — edit directly, never via CMS Publish

These posts have custom CSS/HTML that the CMS cannot reproduce:
- `blog/heat-resilience-report.html` — case studies, stat boxes, audio player
- `report.html` — geological report with custom layout

For these files: edit HTML directly, set status in JSON manually, push with git.

## Commit and push workflow

```bash
cd /Users/diana/Documents/finca-tariqa
git add <files>
git commit -m "short description"
git push
```
GitHub Pages deploys automatically on push to main.

## Writing rules for audio narration

Blog posts are narrated by F5-TTS. Write for the ear.
Full rules in `/Users/diana/Documents/finca-tariqa-private/KNOWLEDGE.md` under "Journal writing rules — audio-friendly text".
Short version: spell out numbers, units, and chemical names in the source HTML.
The server-side normaliser is a fallback — good source text always wins.
