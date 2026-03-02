# Sosmed Carousel Prompt Generator — Claude Project Instructions

## Project Overview

Claude Code plugin that generates cinematic AI image prompts for social media carousels. 1 skill + 1 agent + 12 reference documents as RAG knowledge base.

## Architecture

| Path | Purpose |
|------|---------|
| `.claude-plugin/plugin.json` | Plugin metadata (name, version, author) |
| `.claude-plugin/marketplace.json` | Marketplace listing |
| `hooks/hooks.json` | SessionStart hook definition |
| `hooks/session-start.sh` | Session start script — announces available skills |
| `skills/carousel-prompt-generator/SKILL.md` | Main skill definition — carousel prompt generation |
| `skills/validate-references/SKILL.md` | Cross-file consistency checker (7 checks) |
| `skills/new-localization/SKILL.md` | Scaffold new localization files + wire reference tables |
| `agents/carousel-prompt-generator.md` | Subagent for batch carousel prompt work |
| `references/` | 12 reference docs read on-demand by skill/agent |
| `README.md` | Repo README |
| `LICENSE` | MIT license |

### Reference Files

| File | When Used |
|------|-----------|
| `global-config.md` | ALWAYS (read FIRST) — single source of truth for all configurable values (language, colors, handle, film stock, platform specs) |
| `creator-bible.md` | ALWAYS — creator identity, brand rules, gradient zones, holiday production, brand-in-image specs |
| `hook-science.md` | Hook slides — 5 hook categories (100-hook bank), Visual Action Hook Bank (12 absurd action types for static carousel hooks), CTA science (4 types + algorithm hierarchy), Gen-Z transcreation, engagement benchmarks, cover slide specs, interactive hooks |
| `hook-formula-bank.md` | 52 fill-in-the-blank hook formula templates in 8 psychology categories (Seefluencer) — works for ALL content types, cross-mapped to visual hook categories |
| `hook-visual-library.md` | Hook visual specs — expression libraries (5+8 categories), lighting presets, camera angle banks (3 variants per category), environment palettes, Visual Action × Expression synergy matrix, anti-repetition variation system |
| `carousel-rebranding.md` | Rebranding third-party carousels |
| `platform-specs.md` | Platform routing, aspect ratios, Nano Banana Pro specs |
| `cinematography-lut.md` | Lighting/lens/film stock/atmosphere/DP signature lookup |
| `prompt-formulas.md` | Prompt templates (text-in-image), hook headline formula, foreshadow, CTA visual types, emotional arc, quality checklists |
| `localization-id.md` | Indonesian localization extras, holidays, AI bias countermeasures |
| `carousel-best-practices.md` | Carousel design and engagement best practices |
| `caption-copywriting.md` | Caption formulas, character limits, hashtag strategy per platform |

## Key Concepts

- **Image-Only Plugin**: Nano Banana Pro is the exclusive image generation platform
- **Text-in-Image**: All text (headlines, accent words, branding, SWIPE CTA) rendered directly in the AI-generated image via prompt — NOT post-production. Font must be **largest possible billboard-scale, extra bold/black weight**
- **WOW Quality Gate**: 8-point scoring (lighting, depth, atmosphere, color, emotion, camera, texture, cinematic ref). **All 8 mandatory, minimum 6/8 for ALL slide types**
- **Platform-Specific Aspect Ratios**: IG Feed 4:5, TikTok/Reels 9:16, LinkedIn 4:5/1:1, Default 4:5
- **Subject Brand Context**: When discussing a specific company (Google, WhatsApp, etc.), their brand elements MUST be visible in the image for context. Without it, factual claims are meaningless
- **No Competitor Branding**: No other creator badges, watermarks, handles, or source category tags (e.g., "TECHNOLOGY" badge from source = competitor branding)
- **Creator Face Rules**: Hook/CTA/Foreshadow/Thumbnail = ALWAYS. B-Roll with human figures = ALWAYS (creator as most prominent figure). B-Roll without humans = NO face. **Exception — Public Figure Topics** (criminal, head of state, artist/celebrity, prominent CEO): body slides show the public figure's face as primary — creator as optional companion. Hook + CTA + Foreshadow + Thumbnail = creator face still mandatory
- **Brand Icon + Watermark**: Both at **thirty percent opacity**. Brand icon center of image above watermark, @handle center below brand icon. Split-panel comparison (A vs B): both on **vertical divider line**. In prompt body: ALWAYS spell "thirty percent opacity" — NEVER "30%"
- **SWIPE FOR MORE**: "SWIPE (GESER) >" rendered in-image on all slides except CTA, positioned directly beneath headline (20-30% engagement boost)
- **Gradient Zones**: Bottom half for all slide types, bottom third for thumbnails (source of truth in creator-bible.md Section 7)
- **Prompt Body Rendering Rules**: In the actual Nano Banana Pro prompt body, ALL instruction words must be lowercase, no raw percentages, no "Shot on" prefix (use "Lens:"), no `//` separators, no category tags. Only in-image text (headlines, HUD data, CTA, watermark handle) may be ALL CAPS. Full rules in `references/prompt-formulas.md`
- **Default Language**: Per `global-config.md` Language section (bilingual by default). Single language on user request
- **Auto Captions**: Captions for all 4 platforms (IG + TikTok + LinkedIn + Threads) generated by DEFAULT with every carousel
- **Fact Verification**: All factual claims auto-verified via web search before prompt generation
- **Interactive Design**: Agent pauses + asks user at ambiguous slides (costumes, settings). Human figures = automatic creator face
- **Multi-Keyword Highlighting**: Every headline highlights **2-4 emotionally impactful keywords** in accent color — NEVER just 1 word. Includes power words, emotional triggers, numbers, identity words
- **Subtitle**: Per global-config.md — subtitle language translation, rendered below main headline in **subtitle color from config** (not white). Creates visual hierarchy and bilingual accessibility
- **Hook Headline Formula**: Mandatory structure `[POWER WORD] + [curiosity gap/number] + [unrevealed payoff]`. Must score 3/5 on Hook Scoring Gate BEFORE generating prompt. Power word at 120% size in accent color
- **Hook Science**: 5 psychology-based hook categories with 100-hook bank (20 per category, Bahasa + English). Hook category determines expression + scene + lighting. Includes Gen-Z transcreation rules, interactive carousel hooks (quiz/flowchart), and cover slide design specs. **Hook Formula Bank**: 52 fill-in-the-blank hook formula templates in 8 psychology categories (Seefluencer framework) for ALL content types — see `references/hook-formula-bank.md`. **Hook Visual Library**: Deep visual specs per hook category — expression libraries (eyes, mouth, head, hands, body), lighting presets, camera angle banks (3 variants A/B/C), environment palettes, Visual Action × Expression synergy matrix, anti-repetition variation system — see `references/hook-visual-library.md`. **MANDATORY: Hook category MUST match Topic → Hook Category Mapping. NEVER default to Visual Shock**
- **Visual Action Hook Bank**: 12 absurd mundane action types for static carousel hook slides (makan nyeleneh, minum dramatic, objek absurd, destruction, satisfying process, scale absurd, wrong context, frozen mid-action, extreme close-up, props overflow, contradiction pose, mundane zen). Each hook slide MUST use a visual action from the bank — the absurd action IS the pattern interrupt. Topic → Visual Action mapping in `hook-science.md`
- **Foreshadow (Slide 2)**: MANDATORY bridge between hook and body. 4 types: Steps Tease, Fear Urgency, Quiz/Choice, Visual Tease. Creates FOMO to keep swiping. Instagram re-serves from slide 2 = second chance
- **CTA Visual Types**: 4 engagement-driven types ranked by impact: Engagement Reward (12-18% conversion), Question (highest comment volume), Polarize (highest shares + depth), Identity Tag (highest DM shares). Each has specific visual composition and lighting
- **Algorithm Engagement Hierarchy**: DM Shares (3-5x weight) > Saves (3x) > Comments (depth matters) > Dwell time > Completion rate > Likes. Optimize CTA for top signals
- **Comment-to-DM**: "Comment [WORD] and I'll DM you [resource]" = highest-converting CTA format in 2026 (12-18% with automation)
- **Emotional Arc**: Roller coaster pattern with intensity tags — HIGH (hook) → DIP (foreshadow) → BUILD (body) → MINI-HOOK (slide 5-7 surprise) → CLIMAX (reveal) → WARM (CTA). Each slide tagged with beat + intensity
- **5-Hashtag Era**: IG max 5 (Dec 2025), TikTok max 5 (Aug 2025), LinkedIn 3-5
- **Default specs**: Per `global-config.md` Visual Defaults section (resolution, film stock, color grade, prompt length)
- **Content Language**: Per `global-config.md` Language section (bilingual by default). Single language on user request
- **Source URL Collection**: Agent asks for source post URL at start of every generation. Extracts caption + metadata via og:tags to enrich context. Optional — user can skip. NEVER copy caption verbatim — rewrite in creator voice. Source account = competitor branding (DELETE)
- **Page Numbers**: Every carousel slide includes `"[N]/[TOTAL]"` as a small white page number in the top-left corner. Makes posting order easy to track. All slides get page numbers (thumbnails typically excluded since they're standalone)
- **Suggested Filenames**: Every slide includes an SEO-optimized filename: `{N}-{topic-keywords}-{brand-handle}-{slide-type}.png`. Hyphens only, lowercase, slide-level keywords, 5-8 words. Full convention in `references/prompt-formulas.md`

## Capabilities

1. **Carousel image prompts** — Nano Banana Pro, per-slide with text-in-image + WOW scoring (min 6/8)
2. **Thumbnail prompts** — creator face 50-60%, exaggerated emotion, topic visual, text in-image
3. **Carousel rebranding** — convert third-party designs to user's brand (remove competitor branding, keep subject brand)
4. **Multi-platform export** — IG + TikTok + LinkedIn + Threads with platform-specific output
5. **Caption copywriting** — auto-generated for all 4 platforms with every carousel (English default)
6. **Fact verification** — auto-verify all claims before prompt generation
7. **Hook optimization** — mandatory headline formula + 3/5 scoring gate + category→visual matching
8. **Foreshadow system** — mandatory slide 2 bridging hook to body with FOMO
9. **CTA engagement system** — 4 visual types matching engagement goals
10. **Emotional arc plotting** — roller coaster intensity mapping across full carousel
11. **SEO filename suggestions** — per-slide optimized filenames for content management and discoverability
12. **Source URL metadata extraction** — extract caption, account, engagement from Instagram/TikTok/LinkedIn post URLs to enrich prompt context and caption writing

### Creator Identity (VERBATIM Rule)
- User provides: physical description, face reference image, brand handle, brand icon, accent color
- Physical description is used **word-for-word** in every prompt
- This ensures AI model consistency across all generated content
- Template in `references/creator-bible.md`

### Carousel Engagement Funnel (Slide Structure)
| Slide | Type | Purpose | Mandatory? |
|-------|------|---------|-----------|
| 1 | HOOK | Stop the scroll — mindblowing headline + pattern interrupt visual | YES |
| 2 | FORESHADOW | Bridge to body — create FOMO, "don't skip or you'll miss..." | YES |
| 3-N | BODY | Value delivery — progressive build with emotional arc | YES |
| 5-7 | MINI-HOOK | Mid-carousel surprise — re-engage committed swipers | YES (within body) |
| Last | CTA | Convert attention to action — specific visual type for engagement goal | YES |

### Creator Face Allocation
| Slide Type | Face? | Why |
|------------|-------|-----|
| Hook | Yes (always) | Exaggerated emotion matching hook category |
| Foreshadow | Yes (always) | Concerned urgency or teasing smirk |
| Content body (no humans) | No | Topic visuals only, no distraction |
| Content body (with humans) | **Yes (always)** | Creator as most prominent figure — no need to ask |
| Content body (**public figure topic**) | **Public figure primary**, creator optional companion | Topic is about a specific public figure (criminal, head of state, artist, CEO) — their face is the main subject |
| Split-panel | Yes | Creator in both or relevant panel |
| CTA | Yes (always) | Expression matches CTA type (see 4 CTA visual types) |
| Thumbnail | Yes (always) | Curiosity gap drives clicks |

### Brand Elements In-Image
| Element | Where | Every Slide? |
|---------|-------|-------------|
| Brand icon | **Center of image, above watermark** (thirty percent opacity) | YES |
| @handle watermark | **Center of image, below brand icon** (thirty percent opacity). On **vertical divider** for comparison split-panel | YES |
| Headline | Bottom gradient zone — **largest possible billboard-scale font** | YES |
| Subtitle | Below main headline — **[config: subtitle_color]** (never white) | YES |
| Accent keywords (2-4) | Within headline — **[config: accent_color]** | YES |
| Page number | **Top-left corner** — per global-config.md `page_number_format` | YES |
| Subject brand | In scene (logo/UI of discussed company) | When discussing specific brand |
| SWIPE CTA | Bottom center — per global-config.md `swipe_cta_text` | All except CTA |
| Social icons + handle | Per global-config.md CTA Social Media Block | CTA only |

## Technical Defaults

> All configurable values are in `references/global-config.md`. This table shows setting NAMES — see global-config.md for current VALUES.

| Setting | Source |
|---------|--------|
| Aspect ratio | Per global-config.md Platform Specs (platform-specific) |
| Film stock | Per global-config.md `film_stock` |
| Color temp | Per global-config.md `color_temp` |
| Accent color | Per global-config.md `accent_color` |
| Image res | Per global-config.md `image_resolution` |
| Prompt length | Per global-config.md `prompt_length` |
| WOW minimum | Per global-config.md `wow_minimum` |
| Default language | Per global-config.md Language section |
| Captions | All 4 platforms by default |
| Font weight | Per global-config.md `font_weight` |
| Brand icon position | Per global-config.md `brand_icon_position` |
| Watermark position | Per global-config.md `watermark_position` |
| Brand icon + watermark opacity | Per global-config.md `opacity` (spell out in prompt body — NEVER "30%") |
| Gradient zone | Per global-config.md `gradient_zone` |
| Page number | Per global-config.md `page_number_format` |
| Filename pattern | Per global-config.md `filename_pattern` |

## Conventions for Contributors

### Changing a Global Setting
To change any configurable value (language, color, handle, film stock, etc.):
1. Edit `references/global-config.md` — single source of truth
2. No need to edit other files — they all reference global-config.md

### Adding a New Reference File
1. Create `.md` file in `references/`
2. Add entry to the Reference Files table in `SKILL.md`
3. Add entry to the Reference Files table in `agents/carousel-prompt-generator.md`
4. Update this CLAUDE.md file
5. Run `/validate-references` to verify cross-file consistency

### Adding a New Localization
1. Create `references/localization-{code}.md` (e.g., `localization-hi.md` for Hindi)
2. Follow the structure in `localization-id.md`

### File Naming
- Reference files: lowercase, kebab-case (e.g., `carousel-best-practices.md`)
- No spaces in filenames
- Prefix localizations with `localization-`

## Debugging

| Issue | Check |
|-------|-------|
| Prompt too long | Nano Banana sweet spot is 80-200 words (up to 250 complex) |
| Image resolution low | Ensure `4K` uppercase in config, not `4k` |
| Creator face inconsistent | Verify face reference filename matches across prompts |
| Wrong aspect ratio | Check platform-specs.md for platform → ratio mapping |
| Cold/blue tone | Default film stock is warm (per global-config.md) — check color temp matches config |
| Source branding leak | Check all slides for competitor category tags, badges, watermarks from source |
| Missing subject brand | If slide discusses Google/WhatsApp/etc., their logo/UI MUST be visible |
| Text too small | Must use "largest possible font size that fills the width, extra bold weight" — check prompt wording uses descriptive sizing, not ALL CAPS like MASSIVE |
| Text not in image | Verify prompt includes text rendering block (in-image, not post-production) |
| Watermark wrong position | Center of image, below brand icon (thirty percent opacity). Vertical divider for comparison split-panel |
| Only 1 keyword highlighted | Must highlight 2-4 keywords in accent color per headline. Check Multi-Keyword Highlighting rules in prompt-formulas.md |
| Subtitle same color as headline | Subtitle must be [config: subtitle_color], never white. Check template for subtitle line |
| Brand icon not transparent | Brand icon must also be thirty percent opacity (same as watermark). Check template has "at thirty percent opacity" on brand icon line |
| Unwanted text in image | ALL CAPS instruction words (MASSIVE, CENTERED, MANDATORY, etc.) render as literal text. Check Prompt Body Rendering Rules in prompt-formulas.md |
| "Shot on" watermark in image | AI renders "Shot on Kodak Portra 400" as camera watermark. Use "Lens:" prefix instead |
| "30%" rendered in image | Raw percentages render as text. Use descriptive words: "thirty percent opacity, subtle background mark only" |
| Category tag in image | Tags like TEKNOLOGI/SCIENCE render as text. Remove all category tags from prompt body |
| // rendered in image | Separator characters render literally. Use only core data points in HUD text, no // or metadata labels |
| Filename in image | Raw filenames render as text. Use descriptive reference: "render from reference image [file.png] as a small circular badge" |
| Brand icon wrong | AI generates new icon instead of using file. Use descriptive file reference instruction, not creative description |
| Wrong language | Default per global-config.md Language section (bilingual). Check if user requested single language |
| Missing captions | Captions for all 4 platforms are default — check if user filtered |
| WOW too low | Min 6/8, all 8 elements mandatory — check each element is in prompt |
| Weak hook headline | Must score 3/5 on Hook Scoring Gate (question, number, power word, negative frame, unrevealed payoff). If < 3/5, REWRITE before generating |
| Hook visual doesn't match | Hook category determines expression + scene + lighting — check visual profile in hook-visual-library.md. MANDATORY: category MUST match Topic → Hook Category Mapping in hook-science.md |
| Hook always Visual Shock | Agent must follow Topic → Hook Category Mapping. Education/Business/Health = Avoid Visual Shock. Check enforcement step in prompt-formulas.md |
| Hook images repetitive | Use anti-repetition system: rotate camera variants A/B/C per category. Check hook-visual-library.md Anti-Repetition section |
| Creator face on public figure slide | When topic is about a public figure (criminal, head of state, artist, CEO), body slides should show the public figure's face as primary — creator is optional companion. Check Public Figure Face Priority in creator-bible.md |
| Missing foreshadow | Slide 2 MUST be foreshadow type (Steps Tease / Fear Urgency / Quiz / Visual Tease) |
| Foreshadow doesn't create FOMO | Headline must create urgency to swipe — "kalau lo skip..." / "tunggu sampai..." |
| Flat CTA | Must use specific CTA visual type (Polarize/Question/Identity Tag/Reward) — not generic creator shot. Check CTA Selection Guide in hook-science.md |
| CTA not driving engagement | Check algorithm hierarchy: DM shares (3-5x) > Saves (3x) > Comments. Engagement Reward (comment-to-DM) = highest conversion (12-18%) |
| Hook sounds formal/stiff | Must follow Gen-Z transcreation rules — gue/lo pronouns, particles (sih/tuh/banget), code-mixing. Check hook-science.md Gen-Z section |
| No emotional arc | Each slide must have emotional beat tag (HIGH/DIP/BUILD/MINI-HOOK/CLIMAX/WARM) + intensity |
| Missing mini-hook | Slide 5-7 must have sudden visual change (angle shift, split panel, color temp disruption) |
| Missing creator face in crowd | B-Roll with humans = creator ALWAYS as most prominent figure |
| Unverified facts | All factual claims must be web-searched before prompt generation |
| Cross-file drift | Run `/validate-references` — checks SWIPE, hashtags, gradients, aspect ratios |
| URL metadata empty | Instagram/TikTok may block or truncate — inform user and proceed without metadata. Extraction is best-effort |
| Source caption copied verbatim | NEVER copy — always rewrite in creator voice (Gen-Z Bahasa, gue/lo). Source caption is inspiration only |
| Source account branding leaked | Source account handle/watermark = competitor branding. Must NOT appear in any prompt |

---

**Version:** 2.12.0
**Last Updated:** March 2026
