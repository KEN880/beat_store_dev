# KEN&BAJ — Build Spec v2: BROKEN CHANNEL
> Winner (judge consensus 9.2). Type IS the imagery; color IS signal state. Single static HTML file, no photos.

## Summary
Winner by judge consensus (9.2): BROKEN CHANNEL. Thesis — type IS the imagery, color IS signal state. Kill every clip-art prop (moon, skyline SVG, hearts/stars doodles, embers, falling stars, the 46vh "999", globe icon, glitch loops) and rebuild each beat as a full-bleed PRESS-SHEET POSTER. One signature device carries the whole site: THE SLICED COLOSSUS + OVERPRINT REGISTRATION — each title is one enormous Anton word sliced into 3 horizontal bands offset on a Swiss grid, with a mis-registered color outline ghost and a knockout copy, so one word becomes a 3-layer print object. The wow-moment is SCROLL-TUNED REGISTRATION: scrolling pulls the bands and color ghost out of register (torn/double-print look), and when a zone hits center it SNAPS into perfect register; if that beat is playing the monochrome floods to channel color in one 0.9s wash — scrolling literally feels like tuning a radio dial through static until each channel locks. The serif (DM Serif Display) finally gets a structural job: lyric/title-card voice, the entire "saint" title, an epigraph per beat, and the hero ampersand. Three loaded fonts become a real pairing SYSTEM (Anton=brutal mass, DM Serif=soft/lyric, Space Mono=transmission readout). GRAFTS: global grayscale→color flood on play (from Color-on-Play, the non-negotiable "signal locks" reward); reel-slate metadata folded into the CH.0x // BPM // KEY readout; exactly ONE redacted credit + ONE rotated registration sticker on hard zones (from AWGE, as tiny press marks not a sticker collage); VHS scanline ONLY on luv (from AWGE) as that channel's identity; the CH.01–CH.04 "channels" episodic spine (from Persona, persona-less). Everything ships in one static HTML file, two new Google fonts, no photos.

## Remove list
- luv: ALL the .doodle SVG (hearts, stars, sparkles, the cross, the two scattered hearts) — lines 267-276, the entire <svg class="doodle"> block
- luv: the continuous chromatic glitch loop (.z-emo .bt .c / .m animations glc/glm, lines 150-153, and the 3-span .c/.m/.w title markup) — replace with STATIC overprint
- midnight: the .moon div (line 243, 58-59) and the entire <svg class="sky"> skyline block (lines 245-254) and .horizon (line 244, 60) — re-express the city as negative-space notches cut from the colossus baseline
- midnight: the two .slash bars (lines 56-57, 255) — replace with a single 1px registration rule on the grid
- saint: the .big999 div (lines 86-87, 312), the .halo ring (lines 88-89, 311), the .stars falling-star system (lines 90-92, 313, JS 409-410), and the <i ti-world globe> icon (lines 93, 314)
- ash: the .embers ember system (lines 78-80, 297, JS 406-407), the .grid perspective SVG (lines 77, 287-296), and the .tape warning-tape (lines 158, 298) — replace tape with a single bold registration rule + crop marks
- intro: the .eqhero hero equalizer (lines 47-49, 237, JS 403-404) and the .stripe bars knocked through the wordmark (lines 46, JS 400-401)
- global: the perpetual Sequoia-zoom loops on decor (.z.playing .big999/.grid/.doodle, seqfar/seqnear keyframes lines 124-128) — decor is gone; keep ONLY the background color-flood on play
- global: ad-hoc tracking values everywhere (eleven different Space Mono letter-spacings) — collapse to 3 tokens
- global: positive letter-spacing on Anton (.bt .01em line 32, z-rage .04em line 81) — go negative
- the pb.on pulsing ring keyframe (pbpulse) stays conceptually but restyle play buttons as crop-mark crosshair triggers, not glossy circles

## New fonts
- Archivo Expanded — wide grotesque for the sub-deck (BPM/KEY/MOOD caps strips); wide-vs-condensed is the core tension against Anton. Add via Google Fonts: Archivo+Expanded:wght@600;700;800. (Fallback if unavailable: Archivo wght 800 + font-stretch:125% where supported.)
- Big Shoulders Display — variable ultra-condensed for the left rail + vertical channel labels, so rail type reads DISTINCT from Anton. Add: Big+Shoulders+Display:wght@500;700;900

## Design tokens

### colors
ROLES (silent/base state, ink-on-paper press sheet):
--ink:#0c0c0b (near-black, replaces old #0b0b0a — warmer black)
--paper:#efe9dd (newsprint warm paper, replaces #f5f2ec — more press-sheet)
--hair:rgba(239,233,221,.10) (1px registration rules / hairlines on ink)
--hair-ink:rgba(12,12,11,.14) (hairlines on paper zones)
--micro:rgba(239,233,221,.46) (mono micro text on ink)
--micro-ink:rgba(12,12,11,.52) (mono micro text on paper)

CHANNEL COLORS — each has [solid], [ghost/overprint], [shadow-hue]. Color floods ONLY on .playing:
CH.01 midnight: --c1:#d11425 (blood red) | --c1-ghost:#7a0b14 (deep maroon outline) | bg-ink near-black #0c0c0b
CH.02 luv: --c2:#ff3d9a (hot magenta, solid core) | --c2-cy:#18e0e0 (cyan offset-left) | --c2-mg:#ff3d9a (magenta offset-right) — CMYK mis-register pair
CH.03 ash: --c3:#ff5b1e (molten orange) | --c3-ghost:#c2702f (scorched bronze outline) | scorched 2-stop bg #2a1408→#0c0805
CH.04 saint: --c4:#7b5cff (ultraviolet) | --c4-soft:#b9a6ff (soft lilac glow) | deep violet-ink bg
CH.00 intro + contact: red --c1 accent on deep ink

RULES: in SILENT state every zone renders in ink/paper monochrome (the colossus is paper-on-ink or ink-on-paper, the overprint ghost is a desaturated near-gray). On .playing the channel hue saturates in via filter + the ghost outline takes its true color. Color = signal, never decoration.

### typeScale
FAMILIES: Anton (brutal display mass), DM Serif Display italic (lyric/title-card/soft), Space Mono (transmission readout/data), Archivo Expanded (wide sub-deck), Big Shoulders Display (rail/vertical labels). Archivo (existing) stays only for body/nav fallback.

TRACKING TOKENS (collapse all mono spacing to three):
--track-label:.30em (uppercase eyebrows / status / stamps)
--track-data:.10em (timecode / credits / coords / sub-deck / footer)
--track-micro:.02em (nav, player title)
LEADING TOKENS: --lh-colossus:0.80 (multi-line stacked lockups) / --lh-single:1.0 (single-word colossus) / --lh-data:1.45 (mono micro-blocks, REPLACES the old 1.7) / --lh-serif:1.18 (epigraphs)

LEVELS:
L0 COLOSSUS (Anton): the giant beat/email word. font:Anton; size:clamp(120px,34vw,560px); weight:400; line-height:1.0 single / 0.80 stacked; letter-spacing:-0.03em; font-feature-settings:'kern' 1,'liga' 0; text-transform:uppercase. Negative optical margin: margin-left:-0.04em (left-set) so flat Anton stems align to the small mono labels not the CSS box.
L0b HERO WORDMARK (Anton + serif &): KEN / BAJ in Anton clamp(70px,17vw,210px), letter-spacing:-0.045em; the & in DM Serif Display italic at ~0.70× cap-height, optically centered, channel-red.
L1 EPIGRAPH (DM Serif Display italic): one lyric line per beat. font:DM Serif Display; font-style:italic; size:clamp(20px,2.6vw,40px); weight:400; line-height:1.18; letter-spacing:0. SAINT title uses THIS family at clamp(44px,8vw,110px) instead of Anton.
L2 SUB-DECK (Archivo Expanded): bpm/key/mood wide-caps strip. font:Archivo Expanded; size:clamp(15px,1.6vw,22px); weight:700; line-height:1.1; letter-spacing:.06em; text-transform:uppercase.
L3 STATUS EYEBROW (Space Mono): channel/status line. font:Space Mono; size:clamp(11px,1vw,13px); weight:700; line-height:1.45; letter-spacing:var(--track-label); uppercase.
L4 DATA/CREDIT (Space Mono): coords, credits, timecode, footer. size:11px–12px; weight:400; line-height:var(--lh-data); letter-spacing:var(--track-data); uppercase for credits, mixed for coords.
L5 RAIL/VERTICAL LABEL (Big Shoulders Display): font:Big Shoulders Display; weight:700; size:12px (number) / 11px (name); line-height:1; letter-spacing:.14em; uppercase; vertical channel tag writing-mode:vertical-rl.
L6 NAV/PLAYER (Space Mono): size:12px; weight:400; letter-spacing:var(--track-micro); uppercase.
MODULAR SCALE per zone = min 4 visible steps (L3 eyebrow → L1/L2 mid → L0 colossus → L4 data), arranged DIFFERENTLY per world.

### spacingGrid
GRID: every .z becomes display:grid; grid-template-columns:repeat(12,1fr); grid-template-rows:repeat(8,1fr); gap:0; padding:clamp(20px,5vw,80px); position:relative; overflow:hidden (clip the bleeding colossus). Replaces the universal centered flex column. Each zone PLACES its elements into named grid cells (grid-column / grid-row) so all six compositions are distinct.
SPACING SCALE (8px base): --s1:8px --s2:16px --s3:24px --s4:40px --s5:64px --s6:96px. Use these for all gaps/margins between type levels.
GUTTER/PAD: --pad:clamp(20px,5vw,80px) (keep). Left rail reserves a ~150px lane on desktop (existing midnight padding-left logic generalizes to a --rail-lane:150px the grid accounts for).
RADIUS: --r:0 everywhere (press sheet = sharp). The ONLY rounded element is the player play/pause control (keep 50% on .pp). Crop-mark targets use stroke circles (visual round, not border-radius). Everything else square — radius:0 on cards, buttons, stamps.
EDGE TENSION: the colossus is allowed to bleed past the viewport edge (overflow clipped at section). A word that fully fits = heading; a word cropped by the margin = print. Mandatory bleed in midnight (left), ash (right), contact (both).

### radius


### textureRecipes
1) FILM GRAIN (two-layer, replaces single .07 layer). Layer A fine: SVG feTurbulence baseFrequency 0.9 numOctaves 2, mix-blend-mode:screen, opacity .06. Layer B coarse paper tooth: feTurbulence baseFrequency 0.35 numOctaves 1, mix-blend-mode:multiply, opacity .04. Both position:fixed inset:0 pointer-events:none z-index:80. CSS: .grain-fine::after{background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='200'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/></filter><rect width='100%25' height='100%25' filter='url(%23n)'/></svg>");opacity:.06;mix-blend-mode:screen} and a sibling .grain-coarse at baseFrequency 0.35 opacity .04 mix-blend-mode:multiply.
2) HALFTONE DOT FILL inside the colossus letters. repeating-radial-gradient(circle at 0 0, currentColor 0 1.1px, transparent 1.1px 6px); applied as a background on a background-clip:text copy of the colossus so the giant letters read as printed dots, not flat ink. Dot pitch per zone: ash coarse (gradient stop 9px), saint fine (4px), midnight/luv medium (6px). On ash, mask the halftone copy with a linear-gradient alpha so the LOWER half of the letters dissolves into dots (ash = burning up).
3) DUOTONE BAND backgrounds = 2-stop HARD gradient (no soft blend), e.g. background:linear-gradient(180deg,#2a1408 0 55%,#0c0805 55% 100%); the seam between zones is a hard 1px registration rule + corner crop marks, NOT a soft fade.
4) RISO MIS-REGISTER overprint = the ghost layer. A duplicate absolutely-positioned colossus with -webkit-text-stroke:1.5px var(--channel-ghost); color:transparent; mix-blend-mode:multiply (paper zones) / screen (ink zones); transform:translate(var(--ghost-x,5px),var(--ghost-y,5px)). On luv use TWO ghosts: cyan offset translate(-6px,0) + magenta offset translate(6px,0) around the ink core.
5) SCANLINE (luv only): repeating-linear-gradient(0deg, transparent 0 1px, rgba(0,0,0,.18) 1px 3px); position absolute over the zone, opacity .5, pointer-events none.
6) CROP MARKS + REGISTRATION TARGETS in all four corners of every zone: tiny SVG L-marks (two 14px strokes) + one crosshair-in-circle target, stroke currentColor at --micro opacity, 1px. Pure inline SVG via a reusable .cropmarks component absolutely positioned in each .z. Costs nothing, says 'press sheet'.

## Global systems
"NAV (fixed top): keep mix-blend-mode:difference + scroll-hide. Left = logo 'KEN&BAJ' Space Mono 12px var(--track-micro) uppercase. Right = mono 'CH.0x' current-channel indicator (driven by zo observer) + 'CONTACT' text link + small Tabler volume icon. 0.5px --hair bottom border on scroll. No icon-only nav.\n\nLEFT RAIL (fixed, vertical center, mix-blend-mode:difference) = CHANNEL TUNER. Items in Big Shoulders Display: number '00 INTRO' / 'CH.01'-'CH.04' / 'END', a 14px bar growing to 34px when active, a vertical channel name expanding on active/hover (keep max-width transition). Active driven by existing zo IntersectionObserver. Thin 1px vertical signal line behind items; active marker is a tiny crop-mark crosshair, not a plain dot. Hidden under 680px.\n\nSTICKY PLAYER (fixed bottom): keep play/pause + mini-EQ + title + scrubber + time. Restyle press-sheet: bg rgba(12,12,11,.92) backdrop-blur; .pp filled circle in current --channel color (the only rounded element); title Space Mono var(--track-micro); scrubber fill channel color; timecode mono var(--track-data); EQ animates on body.isplaying (keep eqp). ADD left mono readout 'CH.0x // BPM // KEY' (reel-slate graft) updated by setBeat().\n\nTEXTURE LAYER (global): two fixed full-viewport grain layers (.grain-fine screen .06 baseFreq .9 + .grain-coarse multiply .04 baseFreq .35) at z-80, below cursor (z-9999). Reusable .cropmarks SVG (4 corner L-marks + 1 registration target) injected into every .z. The halftone-fill copy + overprint-ghost copy travel with each colossus component.\n\nGRID OVERLAY (dev aid, ship hidden): .gridlines::before drawing 12-col guides at low opacity, toggled by body.debug — off in production, documented so placement can be verified during build.\n\nCURSOR: keep dot + lerp ring + difference blend, hidden on touch. On play-button hover the ring morphs into a small crop-mark CROSSHAIR (border-radius:50% → two pseudo-element strokes forming a +).\n\nCOLOR STATE ENGINE: default monochrome. setBeat(i) sets :root --channel/--channel-ghost; applyParallax() toggles .playing on active+playing zone → grayscale→color flood + ghost offset settle. Silence = colorless."

## Motion system
"NAMED EASINGS: --ease-snap:cubic-bezier(.16,1,.3,1) (register snap, reveals); --ease-flood:cubic-bezier(.7,0,.3,1) (color flood on play); linear (scroll-tied slice parallax only — a print shifting, not a spring).\n\nNAMED KEYFRAMES: @keyframes assemble-slice (hero/colossus bands slide from ±18px → 0 + opacity 0→1, stagger 60ms); @keyframes flood-in (filter grayscale(1) saturate(.3) → grayscale(0) saturate(1) over .9s --ease-flood, paired ghost 12px→5px); @keyframes eqp (keep, player EQ 3px↔16px); @keyframes target-spin (active-zone corner registration target 0→360deg over 18s linear, the ONLY ambient loop allowed). DELETED loops: pbpulse, eqb, glc/glm, ember, fall, seqfar, seqnear, seqzoom.\n\nSCROLL BEHAVIORS (extend existing rAF/scroll listener, one handler): (1) SLICE PARALLAX — per zone p=(sectionCenter-viewportCenter)/viewportHeight clamped; set --slice=p; 3 bands translateX top +5%*p / mid -5%*p / bottom +5%*p, easing linear; p→0 at center = REGISTERED. (2) REGISTER SNAP — when |p| drops below threshold add .registered ~0.5s with --ease-snap so lock-in is crisp. (3) OVERPRINT GHOST — translate 12px→5px as |p|→0; on .playing ghost takes channel color. (4) COLOR FLOOD ON PLAY — .playing zone runs flood-in; the only color event, the reward. (5) REGISTER-IN REVEAL on first entry (replaces generic .reveal) — colossus bands assemble, epigraph fine 6px slide, mono lines clip-path inset 100%→0; 1s --ease-snap, gated by existing io. (6) HERO LOAD — KEN&BAJ assembles letter-by-letter from vertical slices, serif & settles last. (7) MICRO — contact email hover = register-snap + red underline wipe scaleX 0→1.\n\nPERFORMANCE: throttle rAF to one transform write/frame; will-change:transform on bands only during active scroll; suppress the 90px bg blur while --slice!=0 (swap to static gradient). prefers-reduced-motion: disable slice parallax/flood/assemble/target-spin; render every zone REGISTERED, full color if playing, no loops."

## Per-zone

### intro
PRESS-SHEET TITLE CARD (deep ink + paper type, cinematic open). Grid: top row (row 1) Space Mono status 'TRANSMISSION 001 // KEN&BAJ BROADCAST' col 1-6, --track-label. Row 2: DM Serif Display italic title-card line 'four channels, one signal' col 2-9, clamp(22px,3vw,40px) — the serif voice pays off immediately. Rows 3-5: HERO WORDMARK col 2-11 = Anton 'KEN' + DM Serif italic red '&' (0.7x cap height, optically centered) + Anton 'BAJ', assembling from vertical slices on load. Bottom-left (row 8, col 1-3): 'EST. 2026 · PROD.' mono readout. Bottom-right (row 8, col 10-12): 'SCROLL TO TUNE ↓' mono. Crop marks all four corners + one rotating registration target bottom-right. NO eqhero, NO stripe bars through the wordmark.

### midnight
CH.01 / BLOOD RED. Colossus 'MIDNIGHT' (or stacked MID/NIGHT line-height .80) LEFT-SET, grid col 1-8 rows 4-7, bleeding off the LEFT edge so the 'M' is half-cropped (edge tension). The CITY is negative space: the colossus baseline is notched (clip-path or a masked rect strip) into a torn skyline silhouette — buildings are cut FROM the letters, not a separate SVG. Overprint ghost in --c1-ghost offset down-left; halftone fill COARSE-medium (6px) inside letters. Top-right credit stack (col 9-12 row 2-3) Space Mono var(--track-data): 'PROD. KEN&BAJ // CAT.001' with exactly ONE redacted word (blacked-out bar). DM Serif italic epigraph 'it only moves after dark' col 7-9 row 6. ONE rotated registration-target sticker (replaces 'AWGE//TESTING' stamp) top area, small. Single 1px registration rule across row 4 (replaces the two slashes). Sub-deck Archivo Expanded '140 BPM · F MIN · MENACE' under credit.

### luv
CH.02 / MAGENTA + CYAN VHS CHANNEL. Colossus 'LUV' centered col 2-11 but MIXED-BASELINE: 'L' large and low, 'U' medium raised, 'V' largest — three sizes/three baselines, locked together by -0.04em tracking (poster jitter, not animation). Heaviest CMYK mis-registration of the site, done STATIC: cyan #18e0e0 outline ghost offset translate(-6px,0), magenta #ff3d9a outline ghost offset translate(6px,0), ink/paper core centered → riso double-print. Scanline overlay (luv ONLY) at opacity .5. DM Serif italic epigraph 'i wrote this about you' lower-left (col 1-4 row 7), tender against the loud type. Vertical Space Mono channel tag 'チャンネル02' on the right edge (col 12), thin transmission label not decoration. Sub-deck '88 BPM · D MIN · TENDER'. NO floating hearts/stars/sparkles/cross.

### ash
CH.03 / MOLTEN ORANGE. Colossus 'ASH' RIGHT-SET + skewX(-7deg) with transform-origin + small translateX so the lowest baseline glyph kisses the optical right margin (skew corrected, tight -0.01em tracking, NO loose .04em). Grid col 5-12 rows 2-6, bleeding off the RIGHT. SECOND large type mass bottom-left (col 1-5 rows 6-8): a Space Mono coordinate/telemetry block set BIG — clamp(14px,2vw,28px), var(--track-data), line-height 1.45 (NOT 1.7): '34°03′N 118°15′W / LEVEL 03 — RAGE / SIGNAL: DISTORTED'. Two type masses fight across the diagonal. Halftone fill COARSE (9px) inside letters, masked so the LOWER half dissolves into dots (ash = burning up). Scorched 2-stop hard duotone bg #2a1408→#0c0805. Warning tape REMOVED → single bold registration rule + crop-mark corners. Sub-deck Archivo Expanded '150 BPM · E MIN · DISTORTED'. ONE redacted credit + ONE rotated target sticker (hard-zone marks).

### saint
CH.04 / ULTRAVIOLET — the ONE calm, serif-led, breathing zone (contrast to all brutal zones). Title 'saint' set ENTIRELY in DM Serif Display italic (NOT Anton — soft world = serif, the structural payoff), small-to-medium clamp(44px,8vw,110px), centered col 4-9 rows 4-5, with MASSIVE leading and surrounding whitespace. Faint ultraviolet glow via text-shadow only (0 0 46px var(--c4-soft) at low alpha). Thin cinematic letterbox bars top/bottom (keep, but slim ~5% + crop marks on them). Mono epigraph below in var(--track-data): 'RECORDED ALONE, 4AM'. Negative space does the work. REMOVE the 999, halo, falling stars, globe — replace ambient with a single faint OUTLINED serif ampersand watermark (col 7-10, -webkit-text-stroke, very low opacity) tying back to the hero. Sub-deck '70 BPM · BB MIN · LATE NIGHT'.

### contact
OUTRO / SIGNAL SIGN-OFF. The EMAIL becomes the colossus: 'KENMUSIC888@GMAIL.COM' set in Anton, SLICED into 3 bands + overprint ghost like the beat titles, spanning full width col 1-12 rows 3-6, bleeding both edges. Hover triggers the register-snap (bands lock to 0 + red underline wipes scaleX 0→1). Top row mono 'END OF TRANSMISSION // CAT.001' col 1-6, var(--track-label). DM Serif italic closing line 'until the next reel' col 8-11 row 2. Socials as MONO TEXT LINKS (INSTAGRAM / YOUTUBE / SOUNDCLOUD / SPOTIFY) with var(--track-label), row 7, not bare icons. Footer barcode reframed as a 'BROADCAST FREQUENCY' strip with the timecode. Crop marks frame the whole final press sheet.

## Build steps
1. 1. Add the two Google Fonts to the existing <link>: append Archivo+Expanded:wght@600;700;800 and Big+Shoulders+Display:wght@500;700;900 to the css2 query (keep Anton, DM Serif Display ital, Space Mono, Archivo).
2. 2. Update :root tokens: change --ink to #0c0c0b, --paper to #efe9dd; add tracking tokens (--track-label .30em, --track-data .10em, --track-micro .02em), leading tokens (--lh-colossus .80, --lh-single 1.0, --lh-data 1.45, --lh-serif 1.18), spacing scale (--s1..--s6), --r 0, --ease-snap, --ease-flood, per-channel color vars (--c1..--c4 + ghosts).
3. 3. Replace .z flex with CSS grid: display:grid; grid-template-columns:repeat(12,1fr); grid-template-rows:repeat(8,1fr); overflow:hidden; remove align-items:center/text-align:center defaults. Add per-zone grid-column/grid-row placement per the perZone spec.
4. 4. Set Anton baseline: .bt letter-spacing:-0.03em, font-feature-settings:'kern' 1,'liga' 0; remove the +.04em on z-rage; hero wordmark -0.045em. Add optical negative margins to display titles (margin-left:-0.04em left-set; skew correction translateX on ash).
5. 5. Build the COLOSSUS component (reusable): one word rendered as 3 stacked spans of the SAME word, each in a div with clip-path inset (top inset(0 0 66% 0) / mid inset(33% 0 33% 0) / bottom inset(66% 0 0 0)) and translateX driven by --slice. Add a halftone-fill copy (background-clip:text + repeating-radial-gradient) and an overprint-ghost copy (-webkit-text-stroke + transparent fill + mix-blend-mode + translate(--ghost-x,--ghost-y)).
6. 6. Build texture layers: replace single .grain::after with two fixed layers (.grain-fine screen .06 baseFreq .9, .grain-coarse multiply .04 baseFreq .35). Add reusable .cropmarks SVG component injected into every .z's four corners + one registration target.
7. 7. Markup edits per zone — DELETE everything in the removeList: moon/skyline/horizon/slashes (midnight), all doodles + glitch spans (luv), 999/halo/stars/globe (saint), embers/grid/tape (ash), eqhero + stripes (intro). Replace each zone's .inner with grid-placed elements (status eyebrow L3, epigraph L1, sub-deck L2, colossus L0, data L4).
8. 8. Hero wordmark: split into Anton 'KEN' + DM Serif italic red '&' (0.7x, optically centered) + Anton 'BAJ'; wire the on-load slice-assemble animation.
9. 9. saint title: switch from Anton to DM Serif Display italic at clamp(44px,8vw,110px); add the outlined serif ampersand watermark.
10. 10. luv: implement static CMYK overprint (cyan ghost translate(-6px,0), magenta ghost translate(6px,0), ink core) + mixed-baseline L/U/V sizing + scanline overlay (luv only). Remove glc/glm animation.
11. 11. ash: skewX(-7deg) optically corrected + the big Space Mono telemetry block as a second mass + halftone lower-half dissolve mask.
12. 12. Restyle nav (CH.0x indicator + text links), left rail (Big Shoulders CH.01-04 tuner + crosshair active dot), player (add CH.0x//BPM//KEY readout, channel-color fill).
13. 13. Motion: rewrite keyframes — delete pbpulse/eqb/glc/glm/ember/fall/seqfar/seqnear/seqzoom; add assemble-slice, flood-in, target-spin (subtle). Keep eqp.
14. 14. Extend the rAF scroll handler: compute per-zone progress p, write --slice (band translateX top +5%/mid -5%/bottom +5%) and --ghost offset (12px→5px), add .registered snap class near center with --ease-snap. Suppress bg blur while --slice != 0.
15. 15. Color state: setBeat(i) sets :root --channel/--channel-ghost; applyParallax() toggles .playing → flood-in (grayscale→color + ghost settle). Default all zones monochrome.
16. 16. Replace generic .reveal with register-in reveal (colossus assemble, epigraph 6px slide, mono clip-reveal) gated by existing io observer.
17. 17. Update prefers-reduced-motion block: disable slice parallax, flood, assemble, target-spin; show registered final state.
18. 18. Mobile (<=680px): hide rail; simplify colossus to single un-sliced word (no 3-band parallax), reduce bleed, drop mix-blend ghosts to a single light offset; keep flood-on-play.
19. 19. Cursor: morph ring → crop-mark crosshair on play-button hover.
20. 20. Extract the <script> and run node --check; fix any errors.
21. 21. Verify in browser: scroll-tuned registration reads as intentional print (offsets snap clean at center, 4-8px rest), flood fires on play, no jank from blend-modes/blur.
22. 22. Per CLAUDE.md: keep beat-site.html as the source of truth, then cp beat-site.html index.html.

## Risks
"MEDIUM overall. (1) The premium/amateur line is craft-thin: mis-registration must read as INTENTIONAL print — keep rest offsets tight (4-8px) and SNAP clean to 0 at center; if offsets drift or never resolve it reads as 'broken/buggy'. (2) Performance: mix-blend-mode + large -webkit-text-stroke text + 90px-blur radial bg + scroll-driven transforms can jank on mid laptops — throttle the rAF, suppress the bg blur during slice motion, will-change only on active bands. (3) All-type thesis means a weak compositional hand yields a wall of headings; saint's calm serif zone is the safety valve but brutal zones need real 12-col grid discipline (place into named cells, don't re-center). (4) Mobile: 34vw bleeding colossi + blend modes need a simpler fallback (single un-sliced word, light single offset, keep flood). (5) -webkit-text-stroke is webkit-prefixed; provide a Firefox fallback (text-stroke / or a duplicate offset text-shadow outline). (6) background-clip:text needs -webkit- prefix + color:transparent; verify the halftone fill renders. (7) Hero letter-by-letter slice on load must not block FCP — animate after fonts load (document.fonts.ready). (8) node --check the extracted script and cp beat-site.html index.html per CLAUDE.md before shipping."