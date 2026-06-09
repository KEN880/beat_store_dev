# KEN&BAJ — Stitch brief

Saved ideas + ready-to-run prompts for generating complementary pages in Stitch,
in the KEN&BAJ visual language. The single-file landing tour (`../beat-site.html`)
is NOT to be regenerated — Stitch would flatten its custom motion. Stitch is used
only to ADD pages the site doesn't have yet (catalog, beat detail, EPK, contact).

## Reuse these — do NOT recreate

- **Stitch project:** `KEN&BAJ — beats` → `projects/10018926955654513917`
- **Design system asset (canonical):** `assets/2253286526295227666` — "KEN&BAJ — catalog v2", full type + spacing scale. (Older `assets/7036924526014203361` superseded.)
- **NOTE:** `update_design_system` errors with "invalid argument" — use `create_design_system` to make a new asset instead, then point generation at it.
- **Rendered screens (catalog):** `b0ce04bc35704d9990efcc983bac322e` (v2, the keeper) · `dedf2ccd192c4bf7b13c26cb72c31d7f` (sparser draft). Generations time out at the tool layer but finish server-side — poll `list_screens`.
- **Device:** `DESKTOP` first; generate `MOBILE` variants only after a desktop screen is approved.
- **Model:** `GEMINI_3_1_PRO` for final passes, `GEMINI_3_FLASH` for quick drafts.

### How to run (when Stitch MCP is connected)
1. `generate_screen_from_text` with `projectId: 10018926955654513917`, `designSystem: assets/7036924526014203361`, `deviceType: DESKTOP`, and the prompt block below.
2. The call usually **times out at the tool layer but keeps rendering server-side** — don't assume failure.
3. Poll `get_project` (name `projects/10018926955654513917`); when a `screenInstances` entry appears, the screen is ready.
4. `get_screen` to pull the preview image + exported code.
5. Port the good parts into the real site by hand (Anton/Archivo/DM Serif/Space Mono, the genre-gradient seams, the sticky player).

## Design system (already encoded in Stitch)

> Canonical source: **`stitch-design-system.md`** (full design.md with structured type + spacing scale lifted from the live site). On reconnect, refresh Stitch from it via `create_design_system_from_design_md` / `update_design_system`, then re-point screens to the new asset.

- **Canvas:** ink `#0b0b0a`, text paper `#f5f2ec` (never pure black/white). Captions = paper 50%. Hairlines = paper 12% (0.5px), not boxes.
- **Genre accents (one per context):** trap red `#b5121b` (default) · emo/melodic pink `#ff4fa3` (+cyan `#46e0e0`) · rage bronze `#9c6b3d` · melancholy violet `#8a5cff`.
- **Type:** Anton (UPPERCASE display) · Chivo ≈ Archivo (lowercase body) · Space Mono (labels/meta/numbers). Rare italic serif (DM Serif Display) for one emphasized word.
- **Surface:** sharp/editorial, 4px radius, circular accent play buttons, optional ~7% film-grain overlay. Catalog numbering 001, 002… as mono eyebrows. Copy lowercase except Anton words.

## Screens to generate (ranked)

### 0 — TOUR landing (Stitch mockup of the real site) `[todo — auth pending]`
Goal: a Stitch mockup of the actual beat-tour (the live `beat-site.html`), NOT a catalog/list. Static only — no JS motion. Use `GEMINI_3_FLASH` (tall page renders more reliably).
```
A single tall, immersive, full-screen vertical SCROLL "tour" landing page for music producer KEN&BAJ — NOT a list, NOT a playlist, NOT a table of beats. Six full-viewport-height sections, each its own atmospheric world. Copy lowercase except huge ANTON display words. Subtle film grain over everything. KEY: section backgrounds form ONE continuous gradient — bottom color of each section = top color of the next (sunset into night).

1 INTRO (dark, radial #1a1a18→#0b0b0a): centered giant ANTON "KEN&BAJ" with 3 thin horizontal dark stripes; Space Mono "a tour through the sound — scroll"; "scroll ↓" cue. Minimal fixed nav (KEN&BAJ left, contact + volume right).
2 TRAP / "midnight" (#0b0b0a): one red #b5121b diagonal slash; eyebrow "001 — trap / dark"; huge ANTON "MIDNIGHT" with "night" in italic serif red; meta "140 bpm · f min · menace"; red circular play.
3 EMO / "luv" (sunset #0a0810→#241043→#7a1f63→#cf4f4a→#e8843c): white doodles (sparkles/stars/squiggle); vertical japanese "ビート · 音" left; eyebrow "002 — emo / melodic"; huge ANTON "LUV" with cyan #46e0e0 + magenta #ff4fa3 glitch offset; meta "88 bpm · d min · rage era"; pink circular play.
4 RAGE / "ash" (#e8843c→#7a4a20→#1e1308→#0b0805): faint bronze grid; tag top-right "utopia // 002—rage"; eyebrow "003 — rage / dystopian"; huge ANTON "ASH"; meta "150 bpm · e min · distorted"; bronze #9c6b3d circular play.
5 MELANCHOLY / "saint" (purple radial over #0b0807→#3a1f73→#0c0816): giant faint "999" watermark; small globe icon; eyebrow "004 — melancholy"; huge ANTON "SAINT"; meta "70 bpm · bb min · late night"; violet #8a5cff circular play.
6 CONTACT (fades to #0b0b0a): eyebrow "inquiries"; big ANTON mailto "kenmusic888@gmail.com" red underline; Space Mono socials (instagram/youtube/soundcloud/spotify).
Footer: barcode motif, "cat. no. 001 — the tour", "KEN&BAJ © 2026". Pinned sticky player bar (circular red play, mono "midnight — trap", red progress, "0:00"). Right-edge vertical dot nav (one per section).
```

## Screens to generate (ranked) — aux pages

### 1 — Beats catalog `[probe / in progress]`
Goal: browse all beats as an editorial list (the page the tour landing can't be).
```
Beats catalog page for music producer KEN&BAJ. Dark near-black canvas (#0b0b0a), warm off-white text (#f5f2ec). Editorial record-label "catalogue" feel (cat. no. 001) — NOT a busy marketplace. Calm, type-driven, lots of negative space. Subtle film-grain overlay. Sharp 4px corners. Copy lowercase except ANTON display words.

Fixed minimal top nav: wordmark "KEN&BAJ" left; links "catalog / about / contact" right in Space Mono uppercase.

Header: Space Mono uppercase eyebrow "cat. no. 001 — the catalogue", huge ANTON uppercase title "BEATS", one lowercase Chivo subtitle. A row of genre filter chips in Space Mono uppercase: all · trap · emo · rage · melancholy (active chip = red accent).

Main: a vertical LIST of beat rows (not a grid), divided by thin hairlines (paper 12% opacity). Each row left→right: circular play button filled with the beat's genre accent + dark play glyph; beat title in ANTON uppercase; genre tag + Space Mono mono-meta "bpm · key · vibe"; a small waveform/barcode motif (thin vertical bars); duration in Space Mono; price + small ghost "license" button (paper hairline border). Beats with per-row accents: MIDNIGHT (trap, red #b5121b, "140 bpm · f min · menace"), LUV (emo, pink #ff4fa3, "88 bpm · d min · rage era"), ASH (rage, bronze #9c6b3d, "150 bpm · e min · distorted"), SAINT (melancholy, violet #8a5cff, "70 bpm · bb min · late night"), plus 3 more invented beats. Row hover = accent hairline.

Pinned bottom: slim sticky PLAYER bar — circular red play button, Space Mono track title "midnight — trap", thin progress track with red fill, Space Mono timestamp "0:00".

Footer above player: small barcode motif, "cat. no. 001 — the catalogue", "KEN&BAJ © 2026" in Space Mono.
```

### 2 — Beat detail + licensing `[todo]`
Goal: single-beat page with a real licensing table — the conversion page.
```
Single beat detail page for producer KEN&BAJ. Dark near-black canvas (#0b0b0a), warm off-white text (#f5f2ec), editorial, sharp 4px corners, subtle film grain, lowercase copy except ANTON words. This beat is "MIDNIGHT" — trap, accent red #b5121b.

Top: same minimal nav (KEN&BAJ wordmark, Space Mono links).

Hero: Space Mono eyebrow "cat. no. 001 / 01 — trap", giant ANTON title "MIDNIGHT", mono meta line "140 bpm · f min · menace · 2:48". A big circular red play button. A full-width waveform (thin vertical bars, red played portion / muted unplayed). Tags as Space Mono chips: trap, dark, menace.

Licensing: an editorial table of tiers (not bulky cards) separated by hairlines. Columns: tier name (small ANTON), what you get (Chivo body), file formats (Space Mono), price (Space Mono), a select button. Tiers:
- MP3 LEASE — $29.99 — mp3, 5k streams, non-exclusive
- WAV LEASE — $49.99 — wav + mp3, 10k streams
- TRACKOUT — $99.99 — wav + mp3 + stems, 100k streams
- EXCLUSIVE — $499 — full ownership transfer, unlimited
The recommended tier (TRACKOUT) gets a subtle red hairline accent. A primary red "add to cart" button.

Below: "more like this" — 3 small beat rows (LUV, ASH, SAINT) with their genre accents.

Pinned bottom: slim sticky player bar (circular red play, mono title "midnight — trap", red progress, "0:00").
```

### 3 — Press kit / EPK `[todo]`
Goal: one-page electronic press kit for labels/artists/sync.
```
Electronic press kit (EPK) one-page for music producer KEN&BAJ (trap, emo/melodic, rage, melancholy). Dark near-black canvas (#0b0b0a), warm off-white text (#f5f2ec), editorial magazine feel, sharp 4px corners, subtle film grain, lowercase copy except ANTON display words. Single accent: red #b5121b, used sparingly.

Header: Space Mono eyebrow "press kit — 2026", giant ANTON "KEN&BAJ", one-line lowercase Chivo positioning statement.

Bio block: a short 2-paragraph Chivo bio next to a portrait photo placeholder (4:3, slight desaturation).

Stats row: 3–4 big numbers in ANTON with Space Mono uppercase labels (e.g. monthly listeners, placements, beats released, years active). Separated by hairlines.

Selected work / placements: an editorial list (hairline-separated rows) — artist/track, role, year — all Space Mono meta with ANTON titles.

Genres: 4 chips with their accents (trap red, emo pink #ff4fa3, rage bronze #9c6b3d, melancholy violet #8a5cff).

Contact strip: big ANTON mailto "kenmusic888@gmail.com", Space Mono social row (instagram / youtube / soundcloud / spotify), and a "download press assets" ghost button.

Footer: barcode motif, "KEN&BAJ © 2026" in Space Mono.
```

### 4 — Contact / inquiries `[todo]`
Goal: simple booking/inquiry page.
```
Contact / inquiries page for producer KEN&BAJ. Dark near-black canvas (#0b0b0a), warm off-white text (#f5f2ec), lots of negative space, editorial, sharp 4px corners, subtle film grain, lowercase copy except ANTON words. Accent red #b5121b.

Minimal nav top. Center block: Space Mono eyebrow "inquiries", a giant ANTON mailto link "kenmusic888@gmail.com" with a red underline-on-hover.

Below, two columns: left = a short Chivo note ("for custom beats, mixing, sync & licensing — reach out"); right = a minimal form (name, email, subject dropdown [custom beat / licensing / mixing / other], message) — fields are underline-only (no boxes), floating Space Mono labels, focus underline turns red, full-width red submit button.

A Space Mono social row at the bottom (instagram / youtube / soundcloud / spotify). Footer: "KEN&BAJ © 2026".
```

### 5 — About / the tour `[todo]`
Goal: narrative page tying to the landing-tour concept (4 genre worlds).
```
About page for producer KEN&BAJ, themed as "the tour" — a journey through four sonic worlds. Dark near-black canvas (#0b0b0a), warm off-white text (#f5f2ec), editorial, sharp 4px corners, subtle film grain, lowercase copy except ANTON display words.

Header: Space Mono eyebrow "the tour — cat. no. 001", giant ANTON "ABOUT", a lowercase Chivo lead paragraph.

Four stacked full-width genre blocks, each with its own accent and a numbered Space Mono eyebrow: 001 TRAP (red #b5121b, "midnight / menace"), 002 EMO (pink #ff4fa3 + cyan #46e0e0, "luv / rage era"), 003 RAGE (bronze #9c6b3d, "ash / distorted"), 004 MELANCHOLY (violet #8a5cff, "saint / late night"). Each block: big ANTON genre word, a 2-line Chivo description, a Space Mono meta line. Blocks separated by hairlines.

Contact strip at the end: ANTON mailto, Space Mono socials. Footer "KEN&BAJ © 2026".
```

## Backlog (after the above)
- Cart / checkout (license summary, totals in Space Mono).
- Licensing FAQ (accordion, hairline-separated).
- Mobile variants of approved screens.
- Tie the catalog's sticky player visual back into `beat-site.html`'s real player.
