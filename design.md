---
version: alpha
name: mm-ppt
description: >
  mm-ppt is the MiniMax AI large-model brand presentation system, reverse-engineered from the
  company master template and expressed in a fixed-stage HTML model. Its identity is a
  single saturated coral-red (#FF604A) field carrying every brand moment, a gold/amber growth accent
  (#FFD388), and a disciplined ink/slate text ladder on warm-white content surfaces. Display + body
  type is MiSans (Normal/Medium/Semibold/Demibold); every numeral and Latin word is Outfit. Brand
  motifs — an angular M/X letterform, an AI head-circuit icon, a gold zig-zag growth arrow, concentric
  radar/sonar rings, a chat speech-bubble and a search-input bar — live in the background art, not in
  the content. Content surfaces use white-on-#F3F4F7 rounded cards with no hard borders. Every slide
  except the cover carries a footer logo bar. The aesthetic is confident, geometric, tech-forward AI
  brand — energetic where it is coral, calm and legible where it is white.

# ---------- COLOR TOKENS ----------
colors:
  # signature
  coral: "#FF604A"            # PRIMARY. Brand field, accent, highlights, stat numerals, dots, CTAs.
  coral-deep: "#F33318"       # Deeper red-orange. TOC numbers, section divider field, intense accent.
  red-dark: "#DD1B00"         # Deepest red. Chart series, shadow facets on coral fields.
  coral-light: "#FF9E9A"      # Light coral. Decorative rings, chart series, soft fills.
  coral-wash: "#FFDBDA"       # Palest coral. Radar-ring washes, tint backgrounds.
  # secondary accent
  gold: "#FFD388"             # Amber/gold. Growth arrow, gold highlights, secondary accent only.
  gold-bright: "#FFE15A"      # Brighter gold, sparing.
  # text ladder
  ink: "#000000"              # Headlines + primary body on light surfaces. Pure black (template uses it).
  slate: "#6D7B89"            # Secondary body, captions, descriptions. The muted voice.
  slate-light: "#ACAFB4"      # Tertiary: axis labels, hairline meta.
  slate-blue: "#AFBBCD"       # Muted bar fills, neutral data tracks.
  gray-deep: "#454545"        # Dark-gray competitor/neutral labels.
  white: "#FFFFFF"            # Text on coral/red fields; inner card fill.
  # surfaces
  panel: "#F3F4F7"            # Outer card panel / section ground. Cool near-white.
  paper: "#FFFFFF"            # Default light content canvas (decor lives in corners).
  # optional secondary palette (the template ships a blue variant)
  blue: "#2F6BFF"             # Alt accent for the blue theme variant.
  blue-light: "#9BCDFF"       # Alt light ring.

# ---------- TYPOGRAPHY ----------
# Authored at the 1920x1080 stage. px values = original PowerPoint pt x 2.667
# (native 960x540 canvas = 720pt wide; stage is 2x native). Origin pt kept for traceability.
typography:
  font-display: "'MiSans','PingFang SC','Noto Sans SC',system-ui,sans-serif"   # CJK display + body (MiSans)
  font-num: "'Outfit','MiSans','PingFang SC',sans-serif"                       # 标题字体 Outfit — numerals + Latin headings
  font-body: "'DM Sans','MiSans','PingFang SC',sans-serif"                     # 正文字体 DM Sans — Latin body / captions
  scale:
    section-number:  { px: 160, pt: 60,  family: num,     weight: 600, use: "Chapter number on section page (Outfit)" }
    metric-xl:       { px: 144, pt: 54,  family: num,     weight: 500, use: "Hero stat numeral (Outfit Medium)" }
    display:         { px: 128, pt: 48,  family: display, weight: 600, use: "Cover title / section title (MiSans Semibold)" }
    quote:           { px: 107, pt: 40,  family: display, weight: 700, use: "金句 statement / big headline (MiSans Demibold)" }
    page-title:      { px: 80,  pt: 30,  family: display, weight: 700, use: "正文页 page title (MiSans Demibold)" }
    metric-md:       { px: 80,  pt: 30,  family: num,     weight: 500, use: "Secondary big stat (Outfit)" }
    h2:              { px: 53,  pt: 20,  family: display, weight: 500, use: "Lead statement / subhead (MiSans Medium)" }
    toc-number:      { px: 53,  pt: 20,  family: num,     weight: 500, use: "Agenda/TOC index number (Outfit, coral-deep)" }
    h3:              { px: 48,  pt: 18,  family: display, weight: 600, use: "Section subhead (MiSans Semibold)" }
    eyebrow:         { px: 37,  pt: 14,  family: display, weight: 700, use: "Eyebrow/label + card subhead (MiSans Demibold, coral)" }
    subtitle:        { px: 37,  pt: 14,  family: display, weight: 400, use: "Cover subtitle / lead caption (MiSans Regular)" }
    body:            { px: 28,  pt: 10.5, family: display, weight: 400, use: "Standard body / list (MiSans Regular)" }
    body-sm:         { px: 24,  pt: 9,   family: display, weight: 400, use: "Dense body (MiSans Regular)" }
    caption:         { px: 21,  pt: 8,   family: display, weight: 400, use: "Caption / placeholder body (MiSans Regular, often slate)" }
    micro:           { px: 18,  pt: 6.75, family: display, weight: 400, use: "Micro caption, footnote (slate)" }
    axis:            { px: 16,  pt: 6,   family: num,     weight: 400, use: "Chart axis ticks (Outfit, slate-light)" }
  rules:
    - "Every numeral, %, and pure-Latin word is Outfit. Every CJK run is MiSans. Never cross."
    - "CJK letter-spacing: 0. Outfit numerals/labels may use tracking; small Latin labels may be UPPERCASE."
    - "CJK line-height: 1.25 display, 1.6-1.75 body. Latin numerals line-height 1.0-1.1."
    - "Headlines are ink (#000) on light, white on coral. Coral is for eyebrows/numerals/highlights, never the headline body."
    - "Insert a space between CJK and Latin/number (盘古之白): '生成式 AI'，'M2 的 Agent 能力'."

# ---------- SPACING (px @ 1920x1080 stage) ----------
spacing:
  margin-x: 80          # Left/right content margin (~4.2%). The spine of every layout.
  margin-top: 64        # Top margin for page-title block.
  title-gap: 16         # Eyebrow -> title gap.
  block-gap: 40         # Between major blocks.
  card-gap: 28          # Between cards in a row.
  card-pad: 40          # Card internal padding.
  panel-pad: 48         # Outer panel internal padding.
  footer-y: 980         # Footer logo bar baseline (~93.8% of 1080 -> bar centered near 980-1010).
  footer-h: 56          # Footer logo bar height.

canvas:
  width: 1920
  height: 1080
  default-bg: "{colors.paper}"

radii:
  panel: 28             # Outer card panel (圆角矩形).
  card: 20              # Inner content card.
  chip: 12              # Small tag/badge.
  pill: 999             # Pill button / eyebrow capsule.
  dot: 50%              # Bullet dots, icon dots.

# ---------- BRAND ASSETS (in ./assets) ----------
assets:
  bg-cover-coral.png:    "Cover background. Coral field + M/X letterform + AI head-circuit + gold growth arrow. Title page (标题页)."
  bg-section-red.png:    "Section divider background. Clean deep-red + gold up-arrow + diagonal facets. Section page (章节页)."
  bg-coral-cta.png:      "Coral field + chat speech-bubble + white search-input bar. Transition page (过渡页) / closing CTA."
  bg-light-rings-red.png: "Light + coral radar rings (corners). 正文页 body / content (card layouts). [replaces old bg-light-rings.png]"
  bg-light-mark.png:     "=slide 7. Light + M/X brand mark top-right. 金句页 quote (statement in left ~60%)."
  bg-light-content.png:  "Light + soft gold radar rings. Warm 正文 content variant."
  bg-light-arc.png:      "=slide 21/22. Light + single minimal arc. Dense / data / TOC pages."
  bg-light-rings-yellow.png: "Gold/amber radar-ring canvas (warm variant of -red)."
  bg-light-rings-blue.png:  "Blue radar-ring canvas (optional blue-theme variant)."
  logo-white.png:        "White MiniMax WORDMARK (mark + MiniMax, no tagline). Footer-left on dark; compact chrome."
  logo-black.png:        "Black MiniMax wordmark. Footer-left on light surfaces."
  logo-colorful.png:     "Colored MiniMax wordmark (coral mark + dark text). Optional, on light surfaces."
  logo-and-tagline-white.png: "FULL white lockup — mark + MiniMax + 'Intelligence with Everyone'. Big-logo moments: cover / closing / transition."
  wordmark-tagline-white.png: "'Intelligence with Everyone' tagline, white. Footer-right on dark."
  wordmark-tagline-black.png: "'Intelligence with Everyone' tagline, black. Footer-right on light."
  wordmark-tagline.png:  "'Intelligence with Everyone' tagline, colored (purple W + orange dot). Optional, light surfaces."

# ---------- COMPONENTS ----------
components:
  eyebrow:
    spec: "MiSans Demibold 37px in {colors.coral}, optional 8px coral dot before it. CJK: no uppercase, no tracking."
    use: "Sits above every page title and section subhead. The universal section opener."
  tag-pill:
    spec: "Pill (radius 999) {colors.panel} bg, {colors.ink} or {colors.coral} text, ~14/28px padding. Small label top-right of header."
  card:
    spec: "Inner white card on {colors.panel} ground, radius 20, padding 40, NO hard border. Optional 8px coral icon-dot top-left. Subhead = eyebrow weight in ink; body = {colors.slate}."
  card-panel:
    spec: "Outer {colors.panel} rounded panel (radius 28) that holds a row of white cards. The deck's signature 'tray' depth — tint + radius, never shadow."
  metric:
    spec: "Big Outfit numeral (metric-xl 144px or metric-md 80px) in {colors.coral} (or ink with coral %), MiSans label below in {colors.ink}, optional slate sub-line. % sign in ink while the number is coral."
  footer-bar:
    spec: "Bottom chrome on every non-cover slide (matches the master template): LEFT = logo (**logo-colorful on light / logo-white on dark**, ~44px tall); RIGHT = 'Intelligence with Everyone' wordmark (**wordmark-tagline [colored] on light / wordmark-tagline-white on dark**, ~20px tall). Margins ~40px, bottom ~22px. NO page number, NO section name — logo left + slogan right, nothing else."
  growth-arrow:
    spec: "Gold (#FFD388) thin zig-zag-up arrow — the brand's optimism motif. Already baked into cover/section bg art; reuse sparingly as an inline SVG accent."
  accent-bar:
    spec: "Short coral rule, ~80x8px radius 4, above cover/section titles where the bg lacks a strong anchor."
  media-frame:
    spec: "Rounded (radius 22) container for REAL screenshots/videos; soft shadow 0 22px 55px rgba(0,0,0,.14). Default object-fit:cover; add .contain (panel bg) for wide whiteboards/infographics so nothing is cropped. Optional top-left play-badge ('现场演示' / '动效实拍')."
  link-btn:
    spec: "Pill CTA to a real URL. Solid coral+white (primary), .ghost (coral tint), or .on-dark (white on coral). Trailing ↗. Use for 领取 / 体验同款 / 预约."
  link-chip:
    spec: "Inline underlined coral link (Outfit) for reference URLs (github repos, 回放, 作品集). .mut = slate for non-linked refs."
  prompt-box:
    spec: "Coral-tint (8%) rounded box holding one agent instruction line, prefixed by a small coral arrow icon (inline SVG) + a '一句话指令' label. The signature copy-this-prompt element."

archetypes:
  cover:       "标题页 — bg-cover-coral; top-anchored big display title (~120-164px, start ~top:170) + white subtitle + short gold accent line; presenter line (name + role, NO '汇报人' label, no date) upper-middle (~top:600); logo-and-tagline-white (full lockup, mark+wordmark+tagline) bottom-left (~88px); NO footer bar, NO eyebrow."
  toc:         "目录 — light canvas; '目录' page-title; numbered list with Outfit coral-deep index numbers + MiSans items."
  section:     "章节页 — bg-section-red; huge Outfit number + MiSans title; vertical mini-TOC, current item highlighted; white footer bar."
  transition:  "过渡页 — bg-coral-cta; eyebrow PART NN; one big white forward line; gold arrow; logo-and-tagline-white; light footer optional."
  body:        "正文页 — bg-light-rings-red; eyebrow + page-title header; content starts CLOSE under the title (content-region top ≈ 262–322px, ~55–60px below the title — never floated to mid-page); card-panel of 3 white cards OR 2-col text+metric; footer bar."
  quote:       "金句页 — bg-light-mark; oversized coral quote glyph; big MiSans statement (left ~60%) with coral keyword highlights; cite line."
  closing:     "封底 — bg-cover-coral (same art as the cover); BIG logo-and-tagline-white top-left (~240px, start ~top:96); a small white tagline line below it (~40px, ~top:452); the REAL QR(s) the user chose in Phase 0 — any channel(s), don't assume 官网 (官网 / 微信 / 公众号 / 小红书 / 飞书群 / 活动码…) — bottom-left (~top:788, left:40; ~186px white rounded tile + ~24px white label = that channel's name) — never a 'QR' placeholder; NO contact block, NO footer bar."
  image-text:  "图文页 — lv-split: left eyebrow+title+lead+bullets, right a coral-gradient visual OR a media-frame product screenshot; footer bar."
  metrics:     "数据页 — 3 metric cells on a panel; Outfit numerals in coral with ink %."
  charts:      "图表页 — horizontal bar chart (one coral series, rest slate-blue) + conic-gradient donut + brand-color legend."
  process:     "流程页 — timeline of 4 step-circles (diminishing opacity 1→.55) on a hairline connector."
  case-gallery:"案例页 — media3 (three screenshots/whiteboards) or media2 (two videos), each framed with a MiSans title + slate caption. For showing REAL examples."
  level-detail:"层级页 — lv-split: left 定位 + tags(优势) + prompt-box + link-btn(体验同款); right an autoplay-muted demo video with controls."
---

## Fixed-Stage Policy

mm-ppt renders as a **fixed 1920×1080 stage scaled uniformly to the viewport** (letterbox/pillarbox; never reflow per device). Include the full `viewport-base.css`. All values above are authored at the 1920×1080 stage. Treat any percentage as a proportion of that stage, not a live responsive rule.

## Overview

mm-ppt is a **single-commitment brand system**: one saturated coral-red (`{colors.coral}` `#FF604A`) is the whole identity. It is the cover field, the section field, every eyebrow, every stat numeral, every highlighted keyword, every icon dot and CTA. A warm gold (`{colors.gold}` `#FFD388`) is the only secondary accent — it appears almost exclusively as the brand's **growth-arrow** motif and the occasional highlight. Everything else is a tight ink→slate text ladder on warm-white surfaces.

The system has **two registers**:
- **Coral register** (cover, section, transition, closing): full coral/deep-red fields, white type, geometric brand art (M/X letterform, AI head-circuit, radar rings, speech-bubble, search bar, gold arrow). Energetic, confident, "this is an AI company."
- **White register** (body, quote, TOC): warm-white canvas with brand decoration pushed to the corners, ink headlines, slate body, white-on-`{colors.panel}` rounded cards. Calm, legible, information-dense.

The discipline is: **let the background art carry the brand; keep the content surfaces quiet.** Never put coral fields behind body text; never put hard borders on cards; never introduce a third accent hue (the blue variant is a *whole-deck* alternate, not a second accent inside the coral deck).

**Key characteristics**
- Coral `#FF604A` is the only brand accent; gold `#FFD388` is the only secondary, used as the growth-arrow.
- Type is MiSans (CJK + display) + Outfit (every numeral and Latin word). Never substitute or cross roles.
- Content cards are white on a `#F3F4F7` panel, radius 20-28, **no borders, no drop shadows** — depth is tint + radius only.
- Every numeral is Outfit and usually coral; the `%` stays ink so the figure reads first.
- Every slide except the cover carries a **footer logo bar** (logo left + "Intelligence with Everyone" slogan right, **no page number**).
- Headlines are ink on white / white on coral — never coral. Coral is reserved for eyebrows, numerals, and inline keyword highlights.
- Real brand PNGs in `./assets` supply the backgrounds and logo; the system is asset-driven, not gradient-faked.

## Colors

Use coral for **emphasis moments only**: eyebrow labels, the leading numeral of a stat, 1-2 highlighted keywords inside a statement, icon dots, the active item in a mini-TOC, CTAs. Body copy is `{colors.slate}` `#6D7B89`; headlines are `{colors.ink}` `#000`. `{colors.coral-deep}` `#F33318` is the slightly hotter red used for **index numbers** (01–07 on the TOC) and for the **section-divider field**. `{colors.gold}` is the growth-arrow and rare highlight; do not use it as a text color on white (too low-contrast). The chart ladder (`coral`, `coral-light`, `gold`, `red-dark`) exists for multi-series data only. The blue tokens drive an **optional alternate theme** (swap coral→blue everywhere); never mix blue and coral in one deck.

## Typography

**MiSans** carries all CJK and all display headlines (weights: Regular 400 → Medium 500 → Semibold 600 → Demibold 700). **Outfit** carries every Arabic numeral, percentage, and pure-Latin word (e.g. `AI`, `Agent`, `M2`, `100%`). This split is the system's most recognizable typographic signature: in `用更少的时间 处理更多的数据 → 100%`, the Chinese is MiSans and the `100%` is a big Outfit numeral in coral.

- Cover/section titles: MiSans Semibold/Demibold, `display` 128px / `section-number` 160px.
- Page titles (正文页): MiSans Demibold `page-title` 80px.
- 金句 statements: MiSans Demibold `quote` 107px with coral keyword runs.
- Lead/subhead: MiSans Medium `h2` 53px.
- Eyebrow + card subhead: MiSans Demibold `eyebrow` 37px (coral for eyebrow, ink for card subhead).
- Body: MiSans Regular 24–28px; caption/placeholder 18–21px in slate.
- Stats: Outfit Medium 144px (hero) / 80px (secondary), coral numeral + ink `%`.

CJK adjustments (mandatory): letter-spacing 0 on CJK; line-height 1.25 display / 1.6–1.75 body; full-width CJK punctuation；no uppercase on CJK; one ASCII space between CJK and Latin/number. Numerals stay Latin Arabic in Outfit even inside Chinese sentences.

## Backgrounds & Assets

Backgrounds are **real brand PNGs**, not CSS fakes. Pick by register:

| Surface | Asset | Notes |
|---|---|---|
| 标题页 cover | `bg-cover-coral.png` | Busiest art (M/X + AI head + arrow). Keep title in the open left 55%. |
| 章节页 section | `bg-section-red.png` | Clean deep-red, gold arrow bottom-right. Number + title on the left. |
| 过渡页 / 封底 | `bg-coral-cta.png` | Speech-bubble top-right, search bar bottom. One line of copy. |
| 正文页 body | `bg-light-rings-red.png` | Coral radar rings in corners; clean for a card row. |
| 金句页 quote | `bg-light-mark.png` | =slide 7. M/X mark top-right; keep statement in the left ~60%. |
| 正文 alt (warm) | `bg-light-content.png` | =slide 10/13. Gold radar rings; warm content variant. |
| dense / data | `bg-light-arc.png` | =slide 21/22. Single minimal arc; maximum quiet. |
| ring variants | `bg-light-rings-red / -yellow / -blue.png` | coral (default 正文) / warm gold / blue theme. |

Place full-bleed at `0,0,1920×1080`, `object-fit: cover`. Logos: `logo-and-tagline-white.png` (full lockup) for cover/closing big-logo moments; compact wordmark in footers — **logo-colorful on light, logo-white on dark** (logo-black available). Never all-black by default — match logo/tagline color to the background. Keep the logo's clear-space ≥ its cap height.

## Layout

A consistent **80px left/right margin** is the spine. White-register pages follow: eyebrow (coral) → page-title (ink, 80px) at top-left (margin-top 64px); content region **directly below, sitting close to the title** — the title bottom lands ~211px, so start the content region at ~262–322px (only a ~55–60px gap) and let it fill downward; **don't strand content in the vertical middle** with a big empty band under the title; **footer logo bar** at the bottom. The footer bar = logo left + "Intelligence with Everyone" wordmark(slogan) right (**logo-colorful on light / logo-white on dark**), **no page number**, present on every non-cover slide. Coral-register pages center or left-align a single dominant element and skip the panel/card system.

Content density: this is a **reading-capable** brand deck. A body page comfortably holds a 3-card row or a 2-column text+metric split. If content exceeds that, split to a new slide — never shrink body below `caption` (21px) or crowd the panel.

## The Five Page Archetypes (recipes)

**(a) 标题页 Title** — `bg-cover-coral`. **Top-anchored title block** (start ~top:170px): big white `display` title (~120–164px, 1–2 lines) → white `subtitle` (~44px, weight 500) → a short **gold accent line** (340×6px, `--gold`, radius 3). A **presenter line** sits upper-middle (~top:600px), white ~34px: **name + role separated by spaces — no “汇报人” label, no date** (e.g. `姓名    团队 / 角色`; fill from Phase 0 — never ship a hard-coded person). `logo-and-tagline-white` bottom-left (~88px, `bottom:84`). No footer bar, no eyebrow. Keep the title clear of the right-side brand art (stay left of ~x:1300).

**(b) 正文页 Body** — `bg-light-rings-red`. Header: coral `eyebrow` + ink `page-title` (e.g. 构建围绕 AI 实验的创新文化), small `tag-pill` top-right. Body **starts close under the title** (content-region top ≈ 262–322px, ~55–60px below the title — not floated to mid-page): a `card-panel` holding 3 white `card`s (icon-dot + ink subhead + slate body), OR a 2-column split (left lead + bullets, right a `metric` or product image). `footer-bar` (logo-colorful on this light bg) bottom.

**(c) 金句页 Quote** — `bg-light-mark`. Oversized coral quote glyph (“) at ~220px, 12% opacity, top-left of the text. Big MiSans `quote` statement left-aligned in the left ~60% (clear of the top-right M/X mark), with 1–2 coral keyword runs (e.g. AI, 商业价值). **Line breaks are hand-set per quote** — wrap each line in `.nb` and place `<br>` at meaning boundaries so keywords never split; size to fit (short 金句 ~104–120px; longer 2–3 line quotes drop to ~64–80px so each line clears the mark). A slate `caption` cite line below. `footer-bar` optional.

**(d) 过渡页 Transition** — `bg-coral-cta`. White `eyebrow` PART 02 (Outfit number + MiSans), one big white `display`/`quote` forward line (e.g. 接下来，我们聊聊技术架构), an inline gold growth-arrow. `logo-and-tagline-white` small. This is the lighter "bridge" beat — one idea, lots of coral.

**(e) 章节页 Section** — `bg-section-red`. Huge Outfit `section-number` (03) beside/above a MiSans `display` chapter title; a vertical **mini-TOC** of chapters with the current one in white/gold and the rest at 55% white. `footer-bar` (white logo). This is the heavier numbered chapter opener (distinct from the transition's single-line bridge).

Plus **目录 TOC** (light; Outfit coral-deep index numbers + MiSans items) and **封底 closing** (matches the master template: `bg-cover-coral`, a **big logo-and-tagline-white top-left ~240px** (~top:96), a small white tagline line (~top:452), and the **real QR(s) the user picked in Phase 0 at bottom-left** (~top:788, `left:40`) — **any channel, don't default to 官网** (官网 / 微信 / 公众号 / 小红书 / 飞书群 / 活动码…), white rounded tile + white label set to **that channel's name**, **tile & caption sharing one center (pad width = tile width)**; **never a "QR" placeholder**; no contact block, no footer bar).

### Extended page library (content variants)

Beyond the five core archetypes, the system composes the same tokens + components into the common content pages every deck needs:

- **图文页 Image + Text** — 2-column split: left `eyebrow` + `page-title` + lead + bulleted points; right a coral-gradient visual panel (radius 28) holding a product image or a big Outfit glyph.
- **数据页 Metrics** — a 3-up row of `metric` cells on `panel` cards: Outfit numeral (130px) in coral + ink `%`, MiSans label, slate sub-line.
- **图表页 Charts** — horizontal bar chart (`bar-track` #EEF0F4 + `bar-fill`: one coral-highlighted series, the rest `slate-blue`) and a conic-gradient donut (coral / gold / slate-blue) with a centered Outfit value and a brand-color legend. Single-accent rule: one series is coral, others neutral.
- **流程页 Process / Timeline** — 4 `step-circle`s (coral, diminishing opacity 1→.85→.7→.55) on a hairline connector, each with a MiSans step title + slate description.
- **层级/图文页 Level-detail** — `lv-split` (grid 1fr / 1.15fr): left `eyebrow` + `page-title` + lead + `tags`(优势) + `prompt-box` + `link-btn`; right a `media-frame` demo video. The workhorse for "explain a capability + show it".
- **案例页 Case gallery** — `media3` (three framed screenshots/whiteboards) or `media2` (two framed videos), each with a MiSans title + slate caption. For showing REAL examples/results.

All are built from the documented components — no new primitives. See `gallery.html` for the design-system reference (13 pages: cover + elements board + every archetype).

## Media, Video & Links

Real screenshots, videos, **audio**, and clickable links are first-class — a brand deck that shows real product/results beats one full of placeholders. **When the source carries any media, proactively embed it** (download → compress → place); don't fall back to a text-only deck when there are real clips, recordings, or images to show.

**Images.** Put every real screenshot in a `{components.media-frame}`. Use `object-fit:cover` for UI captures that fill the frame; use `.contain` (on a `{colors.panel}` bg) for **wide whiteboards / infographics** so nothing is cropped. Add a MiSans title + slate caption beneath. Grid them with `media3` (3-up) or `media2` (2-up), whose rows are height-locked (`grid-template-rows:1fr` + item `min-height:0`) so frames shrink to fit — never overflow.

**Video.** Embed with `<video autoplay muted loop playsinline controls>`. Two hard rules:
- **Browsers block autoplay WITH sound.** Muted autoplay gives a silent looping preview; `controls` let the viewer un-mute to hear narration. Never expect sound on load.
- **Compress before embedding.** Source screen-recordings are huge (30–45MB each). Run `ffmpeg -i in.mp4 -vf "scale='min(1280,iw)':-2" -c:v libx264 -crf 30 -preset veryfast -c:a aac -b:a 96k -movflags +faststart out.mp4` → ~0.2–1MB each. Keep `-c:a aac` to **preserve narration**; only use `-an` when the clip is genuinely silent. (107MB → 6.5MB in the example.)

**Audio.** Put narration, interviews, or 语音 samples in an `<audio controls style="width:100%">` inside a card — a 声波/喇叭 line-SVG (`stroke="currentColor"`, no emoji) + MiSans title + slate caption. **No autoplay** (browsers block audio-with-sound on load, same as video) — the viewer clicks to play. Compress raw audio first: `ffmpeg -i in.wav -c:a aac -b:a 128k -movflags +faststart out.m4a` (or mp3 128k). Audio lives in the deck's local `media/`.

**Links.** Turn every real URL into a clickable element: `{components.link-btn}` for CTAs (领取 / 体验同款 / 预约), `{components.link-chip}` for reference URLs (github, 回放, 作品集). Prompts the doc wants people to copy go in a `{components.prompt-box}`.

**Where media lives.** Task-specific media stays with its own deck (a local `media/` folder) and references the skill's shared `assets/`. Don't pollute the shared `assets/` with per-deck screenshots.

## Components

`{components.eyebrow}` · `{components.tag-pill}` · `{components.card}` · `{components.card-panel}` · `{components.metric}` · `{components.footer-bar}` · `{components.growth-arrow}` · `{components.accent-bar}` · `{components.media-frame}` · `{components.link-btn}` · `{components.link-chip}` · `{components.prompt-box}`. Depth is always **tint + radius**, never shadow or hard border.

## Do / Don't

**Do**
- Let coral live in the background art and in accents; keep body on white-on-panel cards.
- Use Outfit for every number and Latin word; MiSans for every CJK run; one ASCII space between them.
- Keep headlines ink-on-white / white-on-coral; reserve coral for eyebrows, numerals, keyword highlights.
- Put a footer logo bar on every slide except the cover.
- Use the real asset PNGs for backgrounds; match logo color to field.

**Don't**
- Don't set a coral field behind body text, or a coral headline.
- Don't add borders or drop shadows to cards — tint + radius only.
- Don't introduce a third hue; don't mix the blue variant with coral in one deck.
- Don't let MiSans render Latin numerals or Outfit render CJK.
- Don't uppercase or letter-space CJK; don't omit the CJK↔Latin space.
- Don't let CJK break mid-word (自｜动) or strand a Latin token at a line-end — use `word-break:keep-all` on blurbs/cards, and `<br>` + `.nb` (nowrap) on titles/quotes so keywords never split.
- Don't use emoji anywhere (🎬🤖💡… included). Use inline SVG line icons instead — `stroke="currentColor"`, white inside coral `icon`/`glyph` boxes, coral elsewhere. Emoji render inconsistently across OSes and break the brand look.
- Don't shrink on-slide text below ~24px (≈9pt). The source template drops to 5.25pt for dense data labels, but slide text **floors at 24px** for legibility (captions ≥24px, body ≥27px, labels ≥24px). "最小号的字体不要太小。"

## CJK Notes

The brand uses **three real faces**, self-hosted in `assets/fonts` as subset woff2: **MiSans** (CJK — display + body, weights 400/500/600/700), **Outfit** (标题字体 — every numeral + Latin heading), **DM Sans** (正文字体 — Latin body / captions). Each stack falls back `→ PingFang SC → Noto Sans SC → system`. Weight map: Normal/Regular→400, Medium→500, Semibold→600, Demibold→700. MiSans is subset to the full **GB2312 common-hanzi set** (~6.7k chars) + CJK/Latin punctuation + ASCII — ~1MB/weight (~4.3MB total) — so any normal Chinese text renders in MiSans on any machine (rare chars outside GB2312 fall back to PingFang SC). Outfit / DM Sans are subset by Unicode range, so they cover all Latin already.

**Line-breaking (换行) — mandatory.** Chinese wraps between *any* two Han characters by default, so words split mid-way (自｜动) and a Latin token (`Agent`, `Skill`, `100+`) can strand at a line-end and drag the next CJK char down. Control it:
- **Body blurbs, bullets, captions, cards** → `word-break:keep-all` (already on `.card p`/`.card h3`; add `text-wrap:pretty` too). CJK then breaks only at punctuation (、，。；：) and spaces, so 词 stay whole. Keep every punctuation-free run shorter than its container (≈ ≤18 CJK @25px in a 3-up card, ~461px) — a longer unbroken run can overflow, so shorten the copy instead.
- **Titles, quotes, 金句 (display type)** → author the breaks yourself with `<br>`, and wrap each line — or any Latin+CJK phrase that must stay glued — in `.nb` (`white-space:nowrap`) so keywords like `「生成」` or `调研、思路与制作` never split. Size the type so each intended line fits; on 金句 pages keep line 1 clear of the top-right M/X art (stay left of ~x:1150 in the upper band, or push the long line lower).
- **Never** let a Latin/number token sit at a line-end pulling the following CJK down; glue the token to its CJK with `.nb`.

## Known Gaps

- MiSans full weights are large; the official CDN subsets by glyph so first paint is fast, but on a flaky network the deck falls back to PingFang SC (acceptable, slightly rounder).
- The background PNGs bake in their art positions; if a title collides with the art, switch to a quieter asset (`bg-light-arc`) rather than repositioning text into the art.
- The blue secondary palette only has a light-ring asset; a full blue deck needs blue cover/section art produced separately.
- Body type is intentionally small in the source template (8pt); mm-ppt raises baseline body to 24–28px for speaker legibility — bump to `caption` 21px only for genuinely dense reference slides.
