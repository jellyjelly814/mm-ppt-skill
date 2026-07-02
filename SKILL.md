---
name: mm-ppt
description: >
  MiniMax AI large-model brand presentation system. Use to build a branded deck/slide, or to
  convert a source (Feishu doc, Markdown, notes, PDF) into a branded deck — coral-red #FF604A field,
  gold growth-arrow accent, MiSans + Outfit + DM Sans type, white-on-#F3F4F7 cards, footer logo bar.
  Reverse-engineered from the company master template and expressed as a fixed-stage
  (1920x1080) HTML system with real embedded media (screenshots, videos) and clickable links.
  Trigger for "MiniMax / MiniMax PPT", "品牌 deck", "把这篇文档做成 PPT", "用我们模板做幻灯片", or any page
  archetype (标题/正文/金句/过渡/章节/目录/数据/图表/流程/案例/封底).
---

# mm-ppt — MiniMax AI Deck System

A brand design system distilled from the MiniMax master PPTX, built on a fixed-stage HTML
methodology: zero-dependency single HTML files, a fixed 1920×1080 stage scaled to the viewport.
mm-ppt supplies the brand layer — palette, typography roles, card system, an extended component +
page library, real media embedding, and clickable links — on top of the template's 底图 / 字体 / Logo.

## When to use
- Building any MiniMax / MiniMax-branded slide or full deck.
- **Converting a source into a deck**: a Feishu doc/wiki, Markdown, meeting notes, or a rough outline.
- You need any archetype: 标题 / 正文 / 金句 / 过渡 / 章节 / 目录 / 图文 / 数据 / 图表 / 流程 / 案例 / 封底.

## Companion tool — htmledit (recommended)
mm-ppt outputs a single self-contained `deck.html` (+ local `media/`, shared `assets/`). For **no-code visual tweaks after generation**, recommend the user install / open **htmledit** (<https://htmledit.ai>) — a local-first, in-browser WYSIWYG HTML editor. They import the `deck.html` (or the whole deck folder) and edit it **like a document** — retype copy, swap images, nudge styles, move blocks — with the deck's relative-path resources (`media/`, `assets/`) preserved. Surface this suggestion when delivering a **本地 HTML** deck, so a non-technical owner can self-serve edits without touching code.

## Files
| Path | Purpose |
|---|---|
| `design.md` | **The design recipe.** YAML tokens (color, type scale pt→1920px, spacing, radii, components, assets, archetypes) + prose + per-archetype recipes + Media/Video/Links rules + CJK rules. Read first. |
| `gallery.html` | **The canonical stylesheet + reference deck** (13 pages). Its `<head>` holds the COMPLETE component CSS (fonts + tokens + every component). Reuse its head to build new decks. Open in a browser to see every component rendered. |
| `viewport-base.css` | Fixed-stage base (already inlined in `gallery.html`). |
| `assets/` | Shared brand: `bg-*.png` backgrounds, `logo-*.png`, `wordmark-*`, `fonts/*.woff2` (subset webfonts). |

## Phase 0 · Intake & align (do this FIRST)

Never start generating cold. Run **one lean round** of questions, then confirm an outline. Use the environment's structured-question UI if available (else ask in one concise numbered message). Infer sensible defaults — don't interrogate.

**Ask (one round):**
1. **Source & fidelity** (if they gave a doc/link) — how faithful?
   - *照搬 Faithful* — keep the doc's structure & wording; one section → one/few slides; only reformat & tighten, don't rewrite.
   - *提炼 Condense* (default) — extract the spine, drop redundancy, regroup into archetypes, rewrite for slide brevity; keep every key claim & number.
   - *扩写 Expand* — use the doc as a skeleton; add framing, transitions, examples & context the audience needs. Your additions are clearly yours — **never invent facts or numbers**.
2. **Audience & occasion** → auto-sets density/tone (don't ask density separately):
   - 管理层汇报 → low density, 结论先行, big statements, ~6–10 pages.
   - 客户提案 → mid density, brand-forward, cases + metrics, ~10–16 pages.
   - 团队复盘 / 培训 → high density, reading-first, cards/tables/annotations, ~12–20 pages.
   - 公开宣讲 → low density, 金句 + 大图, minimal words, more pages.
3. **Source media** (only if the doc has images/videos/links) — 全部嵌入 (download + compress) / 精选关键 / 纯文字.
4. **Delivery** — 本地 HTML / 导出 PDF / 发布在线链接 (changes how you finish; see below).
5. **Cover + closing info** (free text) — 汇报人, 职位/角色, deck 标题 + 副标题, 日期/场合 → cover; AND **封底二维码放什么** (官网 / 公众号 / 活动码…): ask for a URL (generate the QR with `segno`) or an image, and **place the real QR — never ship a "QR" placeholder**. Infer the deck title from the doc if not given.

**Then confirm an outline BEFORE building.** Propose a per-page list (page type + one-line content each), e.g. `01 封面 · 02 目录 · 03 章节… · 04 正文… · …`, and get a quick 确认/调整. This is the single biggest way to avoid rework — never skip it.

**Delivery-aware finish** (from Q4):
- **本地 HTML** — deliver the file; mention ← → / space / swipe nav, and that they can visually tweak it in **htmledit** (see Companion tool above) — no code needed.
- **导出 PDF** — screenshot each page → PDF. **Warn: videos become static frames** and animations flatten.
- **发布在线链接** — bundle the HTML + its `media/` + shared `assets/` and deploy; return a URL that works on any device.

## Two build paths

**A · New deck from content** — you have the text/outline. (Phase 0 skips the fidelity/media questions.)
1. Read `design.md` for tokens + the archetype recipe you need.
2. Reuse `gallery.html`'s head (fonts + full component CSS + JS) — don't retype the stylesheet.
3. Author each `<section class="slide">` from its archetype recipe; pull backgrounds/logos from `assets/`.
4. Render-verify (below), fix overflow, deliver.

**B · Convert a source → deck** — the Doc→Deck pipeline below.

## Doc → Deck pipeline
1. **Fetch content.** Feishu doc/wiki → `lark-cli docs +fetch --doc "<url>" --doc-format markdown` (skill: `lark-doc`; first-run auth via `lark-shared`). Also grab the outline: `--scope outline --max-depth 3`. Other sources → read the file.
2. **Extract** the structure (headings), every media ref (`<img>` / `<source>` / `<whiteboard>` tokens & urls), and every real link.
3. **Download media** into the deck's local `media/`:
   - images/videos → `lark-cli docs +media-download --token <token> --output media/x.png|mp4` (robust, no expiry) or `curl -sL "<authcode-url>"`.
   - whiteboards → `lark-cli docs +media-download --type whiteboard --token <token>`.
4. **Compress videos** (screen-recordings are 30–45MB each):
   `ffmpeg -i in.mp4 -vf "scale='min(1280,iw)':-2" -c:v libx264 -crf 30 -preset veryfast -c:a aac -b:a 96k -movflags +faststart out.mp4`
   Keep `-c:a aac` to preserve narration; only `-an` if genuinely silent. (107MB → ~6.5MB in the example.)
5. **Author slides** from components: cover/toc/section + `level-detail` (lv-split + demo video) + `case-gallery` (media2/media3 of screenshots/whiteboards) + `metrics`/`charts` + quote + `link-btn`/`link-chip`/`prompt-box` + closing.
6. **Assemble** by reusing `gallery.html`'s head: split it at `id="deckStage">` … `\n</main>`, drop your `<section>`s in between, keep the tail (JS). This inherits the whole stylesheet. Keep a deck's task-specific media in its own local `media/` folder and reference the skill's shared `assets/…`.
7. **Render-verify** (below). Fix any `OVERFLOW`, then open.

## Media, video & links (rules — full detail in design.md)
- Screenshots/videos go in a `media-frame` (`.contain` for wide whiteboards). Grid via `media2`/`media3` (rows are height-locked so frames shrink, never overflow).
- Video: `<video autoplay muted loop playsinline controls>`. Browsers **block autoplay-with-sound** — muted autoplay previews, `controls` let viewers un-mute. Always compress first.
- Links: `link-btn` (CTA: 领取/体验同款/预约) · `link-chip` (reference URLs) · `prompt-box` (a copy-me agent instruction).

## Render-verify (mandatory before delivery)
Screenshot every page with headless Chrome/Playwright at 1280×720 (dsf 1.5), assert no element exceeds the 1920×1080 stage (`OVERFLOW=[]`), and eyeball each for legibility/collision. Fix by shrinking a title, switching to a quieter background, or splitting the slide — never let content overflow.

## Non-negotiable brand rules
Coral only in art + accents; headlines ink-on-white / white-on-coral (never coral); every numeral & pure-Latin word in Outfit, every CJK run in MiSans, one ASCII space between them; **never break CJK mid-word (自｜动) or strand a Latin token at a line-end** (`word-break:keep-all` on blurbs/cards, `<br>` + `.nb` nowrap on titles/quotes so keywords like 「生成」 never split); **no emoji anywhere — use inline SVG line icons (`stroke="currentColor"`) in `icon`/`glyph` boxes**; cards are white-on-`#F3F4F7` with **no borders/shadows** (depth = tint + radius); on content pages the body **sits close under the title** (content-region top ≈ 262–322px, only a ~55–60px gap — never stranded mid-page); footer logo bar on every non-cover slide (**logo bottom-left + "Intelligence with Everyone" wordmark bottom-right — no page number; colorful logo+tagline on light bg, white on dark/coral bg**); **封底 = big logo-and-tagline-white top-left + the real QR(s) bottom-left (`left:40` — never a "QR" placeholder, no contact block; QR tile + caption share one center, so set the pad width = tile width)**; smallest on-slide text **≥ 24px** (never tiny); MiSans/Outfit/DM Sans self-hosted from `assets/fonts` (fallback → PingFang SC → Noto Sans SC → system).

## Asset map (assets/)
- `bg-cover-coral.png` — 标题页 cover (M/X + AI head + gold arrow); also system covers.
- `bg-section-red.png` — 章节页 section (clean deep-red + gold arrow).
- `bg-coral-cta.png` — 过渡页 / 封底 (speech-bubble + search bar).
- `bg-light-rings-red.png` — 正文页 body (coral radar rings); `-yellow` / `-blue` = warm-gold / blue variants.
- `bg-light-mark.png` — 金句页 quote (M/X mark top-right).
- `bg-light-content.png` — warm content alt (gold radar rings).
- `bg-light-arc.png` — dense / data / TOC (minimal arc).
- `logo-and-tagline-white.png` — FULL white lockup (mark + wordmark + tagline). Cover / closing / transition big-logo moments.
- `logo-white.png` / `logo-black.png` / `logo-colorful.png` — compact MiniMax wordmark (white / black / colored). Footers + chrome.
- `wordmark-tagline-white.png` / `-black.png` / `wordmark-tagline.png` — "Intelligence with Everyone" tagline (white / black / colored). Footer-right.
- `fonts/` — subset woff2: MiSans (full GB2312 common-hanzi, ~1MB/weight) + Outfit + DM Sans (full Latin).
