---
name: KEN&BAJ — beat catalog
colors:
  ink: '#0b0b0a'
  paper: '#f5f2ec'
  muted: 'rgba(245,242,236,0.5)'
  hair: 'rgba(245,242,236,0.12)'
  background: '#0b0b0a'
  on-background: '#f5f2ec'
  surface: '#0f0f0e'
  surface-container: '#141413'
  on-surface: '#f5f2ec'
  on-surface-variant: 'rgba(245,242,236,0.5)'
  outline: 'rgba(245,242,236,0.12)'
  primary: '#b5121b'
  on-primary: '#0b0b0a'
  secondary: '#ff4fa3'
  on-secondary: '#0b0b0a'
  tertiary: '#8a5cff'
  on-tertiary: '#0b0b0a'
  acc-trap: '#b5121b'
  acc-emo: '#ff4fa3'
  acc-cyan: '#46e0e0'
  acc-rage: '#9c6b3d'
  acc-mel: '#8a5cff'
  error: '#ff5a4d'
typography:
  display-hero:
    fontFamily: Anton
    fontSize: clamp(70px, 17vw, 200px)
    fontWeight: '400'
    lineHeight: '0.8'
    letterSpacing: 0.01em
  display-lg:
    fontFamily: Anton
    fontSize: clamp(56px, 13vw, 168px)
    fontWeight: '400'
    lineHeight: '0.82'
    letterSpacing: 0.01em
  display-md:
    fontFamily: Anton
    fontSize: clamp(34px, 9vw, 104px)
    fontWeight: '400'
    lineHeight: '0.88'
  headline:
    fontFamily: Anton
    fontSize: 28px
    fontWeight: '400'
    lineHeight: '1.0'
  body-lg:
    fontFamily: Chivo
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Chivo
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.55'
  body-sm:
    fontFamily: Chivo
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.5'
  eyebrow:
    fontFamily: Space Mono
    fontSize: 11px
    fontWeight: '400'
    lineHeight: '1.0'
    letterSpacing: 0.32em
  meta:
    fontFamily: Space Mono
    fontSize: 12px
    fontWeight: '400'
    lineHeight: '1.2'
    letterSpacing: 0.08em
  label-sm:
    fontFamily: Space Mono
    fontSize: 11px
    fontWeight: '700'
    lineHeight: '1.0'
    letterSpacing: 0.04em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  full: 9999px
spacing:
  base: 8px
  pad: clamp(20px, 5vw, 80px)
  container-max: 1240px
  gutter: 24px
  section-v-padding: 90px
  margin-desktop: 80px
  margin-mobile: 20px
---

# KEN&BAJ — Design System

Dark, atmospheric, underground beat-producer catalog for **KEN&BAJ** (trap, emo/melodic, rage, melancholy). Contact: kenmusic888@gmail.com. NOT a busy BeatStars marketplace — it is an editorial, almost record-label "catalogue" (cat. no. 001). Calm, confident, lots of negative space, type-driven. Tokens above are lifted directly from the live landing tour (`../beat-site.html`).

## Mood
Underground tape/zine meets premium music-label press kit. Near-black canvas, warm off-white ink, ONE genre-accent per context. Subtle film-grain overlay on large surfaces. Everything lowercase except ANTON display words. Mono metadata everywhere (bpm, key, cat no).

## Color
- Canvas ink `#0b0b0a`, text paper `#f5f2ec`. Never pure white/black.
- Captions / secondary text: paper at 50% (`muted`). Hairlines & dividers: paper at ~12% (`hair`), 0.5px — not boxes.
- ONE accent per zone/genre, used sparingly (play state, active marker, key numbers):
  - trap = red `#b5121b` (default / `primary`)
  - emo/melodic = pink `#ff4fa3` (`secondary`) + cyan `#46e0e0` glitch secondary
  - rage = bronze `#9c6b3d`
  - melancholy = violet `#8a5cff` (`tertiary`)
- Note: Stitch only seeds 3 override colors + neutral, so `primary/secondary/tertiary` = red/pink/violet. Bronze and cyan are documented here for manual use; apply them by hand on rage/emo screens.

## Typography
Real fonts in production: **Anton** (display), **Archivo** (body — Stitch stand-in is **Chivo**, closest grotesk), **Space Mono** (labels/meta/numbers), **DM Serif Display** italic (rare accent word).
- Display/headline: Anton, UPPERCASE, huge, line-height 0.8–0.88, tight tracking. Hero name, beat titles, section heads. Scale: `display-hero` (hero wordmark) → `display-lg` (beat titles) → `display-md` (mail / section heads) → `headline`.
- Body: Chivo/Archivo, 400–600, lowercase, calm. `body-lg` / `body-md` / `body-sm`.
- Labels/meta/numbers: Space Mono, UPPERCASE. `eyebrow` (.32em tracking — section eyebrows like "cat. no. 001"), `meta` (.08em — bpm·key·vibe lines), `label-sm` (player/timestamps).
- Catalog numbering 001, 002… set as `eyebrow`.
- Accent emphasis: a single word inside a title in DM Serif Display italic (e.g. mid<em>night</em>).

## Shape & surface
- Sharp, editorial — radius 4px (`DEFAULT`) on most things; `sm` 2px for chips/inputs.
- Play buttons are perfect CIRCLES (`full`) filled with the genre accent, dark glyph.
- Separators are thin hairlines, not heavy cards. Let the dark canvas do the separating.
- Optional grain overlay (SVG fractal noise, ~7% opacity, screen blend) on big sections.

## Spacing & layout
- Side padding `pad` = `clamp(20px, 5vw, 80px)` (mirrors the site's `--pad`).
- Container max 1240px, gutter 24px. Section vertical padding ~90px.
- 8px base rhythm. Mobile margins 20px, desktop 80px.

## Components
- **Beat row/card**: Anton title, Space Mono `meta` (genre · bpm · key · vibe), circular accent play button, waveform/barcode motif (thin vertical bars). Hover: accent hairline + slight lift.
- **Sticky bottom player**: slim bar pinned to viewport bottom — circular play, mono track title, thin progress track (accent fill), mono timestamp (`label-sm`).
- **Buttons**: ghost (paper hairline border, fills paper on hover) or solid accent. 4px or pill.
- **License tiers**: editorial hairline-separated table — tier name (small Anton), what's included (body), formats + price (Space Mono), select button. Recommended tier gets a subtle accent hairline.
- **Filter chips**: Space Mono uppercase; active chip uses the red accent.
- **Barcode/waveform motif**: thin vertical bars as decorative rhythm (footer + waveforms).

## Motion (reference only — Stitch won't reproduce it)
- Slow, cinematic. Scroll-reveal fades (y 24→0). Accent changes by context. Landing tour uses a macOS-Sequoia-style slow zoom on backgrounds while a beat plays. Avoid bouncy motion. Reduce-motion friendly.

## Copy tone
- lowercase, terse, confident. mono metadata. "inquiries", "cat. no. 001", "the tour". Email as a big Anton link in contact.

---

### Theme config (for `create_design_system` / `update_design_system`)
- colorMode: `DARK`
- colorVariant: `FIDELITY`
- customColor / overridePrimaryColor: `#b5121b`
- overrideSecondaryColor: `#ff4fa3`
- overrideTertiaryColor: `#8a5cff`
- overrideNeutralColor: `#6b6862` (warm grey)
- headlineFont: `ANTON` · bodyFont: `CHIVO` · labelFont: `SPACE_MONO`
- roundness: `ROUND_FOUR`
- Project to apply to: `projects/10018926955654513917` · current asset: `assets/7036924526014203361`
