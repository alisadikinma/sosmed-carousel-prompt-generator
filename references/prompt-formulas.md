# Prompt Formulas — Nano Banana Pro

## Golden Rule
```
Treat every prompt like a Creative Director brief — natural language, NOT keyword spam.
⚠ Use: "Maintain exact appearance from reference image" for character consistency
⚠ Text rendered IN-IMAGE — all headlines, accents, branding, and labels are part of the prompt
⚠ Default language: Per global-config.md Language section (bilingual by default). Single language on user request
```

---

## Prompt Body Rendering Rules (Nano Banana Pro)

Nano Banana Pro renders ALL text in the prompt as visible image content. To prevent unwanted text artifacts in generated images, follow these rules strictly when writing the actual prompt body:

| Rule | Wrong (renders as text) | Correct |
|------|------------------------|---------|
| Only in-image text in ALL CAPS | `Text must be ULTRA MASSIVE` | `the text uses the largest possible font size` |
| No instruction caps | `MANDATORY: render the icon` | `render the icon` |
| No `//` separators | `120 TB/DETIK // KECEPATAN: CAHAYA` | `120 TB/DETIK` (core data only) |
| No raw percentages | `30% opacity` | `thirty percent opacity, subtle background mark only` |
| No raw filenames in body | `[brand-icon.png] rendered in corner` | `render the creator's brand icon from reference image [brand-icon.png] as a small circular badge` |
| No "Shot on" prefix | `Shot on 85mm f/1.8` | `Lens: 85mm f/1.8` |
| No category tags | `"TEKNOLOGI" badge above headline` | (remove entirely) |
| No metadata labels in HUD | `THROUGHPUT: 120 TB/DETIK` | `120 TB/DETIK` |
| Sizing via description | `MASSIVE billboard-scale` | `the largest possible font size that fills the width, extra bold weight` |
| Positioning lowercase | `CENTERED in the middle` | `centered in the middle` |
| Negations lowercase | `NOT cold blue` | `not cold blue` |

**What MAY be ALL CAPS in prompt body (actual in-image text):**
- Headline text: `"INSANE — THIS IS WHAT HAPPENS IN 1 SECOND ON EARTH"`
- HUD display data: `"120 TB/SEC"`
- CTA text: `"[config: swipe_cta_text]"`
- Power words within headlines: `"INSANE"`
- Watermark handle: `"[config: handle]"`

---

## Nano Banana Pro — Structure (8-Element Priority Order)
```
1. Subject (who/what) — always first
2. Action/pose
3. Setting/location
4. Camera/composition (shot type, angle)
5. Lighting/atmosphere (MUST include lighting pattern, ratio, Kelvin)
6. Style/medium (MUST include film stock, color grade)
7. Texture/cinematic detail (MUST include texture realism + DP reference)
8. In-image text rendering (headline, accent words, branding, labels)
```

All 8 elements are MANDATORY in every prompt. No exceptions.

---

## Text Rendering — In-Image (NOT Post-Production)

All user-facing text is rendered directly in the AI-generated image. The prompt MUST describe:

### Text Elements to Include
| Element | Where | Rule |
|---------|-------|------|
| Main headline | Bottom gradient zone | White bold condensed ALL CAPS (per global-config.md `headline_color`) |
| Subtitle | Below main headline | Translation in [config: subtitle_language]. [config: subtitle_color] at 70-80% size of main headline. NEVER same white as main headline — must create visual hierarchy |
| Accent keywords (2-4) | Within headline | 2-4 emotionally impactful keywords in [config: accent_color]. Hook: power word at 120% size + 1-3 more. Never highlight just 1 word |
| Brand icon | **Center of image, above watermark** | From reference file, thirty percent opacity, every slide. In prompt body: "thirty percent opacity" — NEVER "30%" |
| @handle watermark | **Center of image, below brand icon** | White, thirty percent opacity on ALL slides. In prompt body: "thirty percent opacity" — NEVER "30%" |
| [config: swipe_cta_text] | Bottom center | White small text, all slides EXCEPT CTA |
| Page number | **Top-left corner** | "N/TOTAL" format (e.g., "1/10"), small white text, ALL slides. Helps viewers track progress and simplifies posting order |

### Default Language

See `global-config.md` Language section for current defaults. Override: user specifies single language → use that language, no subtitle. Prompt instructions (scene description) = ALWAYS English (AI model instruction).

### Text Rendering Syntax in Prompt
```
Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HEADLINE IN [config: main_headline_language]]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line reading "[SUBTITLE TRANSLATION]" in [config: subtitle_color] at slightly smaller size,
creating clear visual hierarchy — the subtitle must NOT be white like the main headline.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
["[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap. | omit for CTA slide]
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.
```

### Subject Brand Context in Prompt
When a slide discusses a specific company/product/service, the prompt MUST include:
```
[Subject brand logo/UI/interface] clearly visible in the scene, establishing context
for the informational claim. Example: Google search interface visible on phone screen,
WhatsApp chat UI with green accent, etc.
```
**Without subject brand context, factual claims about that brand are meaningless to viewers.**

---

## Suggested Filename Convention (Per Slide)

Every slide output includes a suggested filename for the generated image. SEO-optimized filenames improve discoverability in Google Images, Pinterest, portfolio sites, and content management workflows.

### Naming Pattern
```
{number}-{topic-keywords}-{brand-handle}-{slide-type}.png
```

### Rules
| Rule | Detail |
|------|--------|
| Separator | Hyphens only (`-`). Google treats hyphens as word separators |
| Case | All lowercase. Prevents duplicate URL issues |
| Word count | 5-8 words total (including number, brand, type) |
| Topic keywords | 2-3 descriptive words per slide — slide-specific, not carousel-level |
| Brand handle | [config: handle_no_at] — handle without `@` |
| Numeric prefix | Sequential: `1-`, `2-`, `3-`... for easy posting order |
| Slide type suffix | `hook`, `foreshadow`, `body`, `cta`, `thumb` |
| Extension | `.png` default (Nano Banana Pro output) |
| No keyword stuffing | Natural, descriptive — not SEO spam |
| No special characters | No `@`, `#`, spaces, underscores |

### Slide Type Suffixes
| Slide Type | Suffix |
|------------|--------|
| Hook (Slide 1) | `hook` |
| Foreshadow (Slide 2) | `foreshadow` |
| Body / Content | `body` |
| CTA (Last slide) | `cta` |
| Thumbnail | `thumb` |

### Example (Topic: "5 AI Tools yang Bikin Kerjaan 10x Lebih Cepat")
| Slide | Suggested Filename |
|-------|--------------------|
| 1 (Hook) | `1-ai-tools-kerja-cepat-alisadikinma-hook.png` |
| 2 (Foreshadow) | `2-ai-tools-skip-rugi-alisadikinma-foreshadow.png` |
| 3 (Body) | `3-chatgpt-prompt-tips-alisadikinma-body.png` |
| 4 (Body) | `4-midjourney-visual-design-alisadikinma-body.png` |
| 5 (Body) | `5-notion-ai-productivity-alisadikinma-body.png` |
| 6 (Body) | `6-claude-code-automation-alisadikinma-body.png` |
| 7 (Body) | `7-canva-ai-content-alisadikinma-body.png` |
| 8 (CTA) | `8-ai-tools-productivity-alisadikinma-cta.png` |

### Why Slide-Level Keywords
Each body slide covers a different subtopic. Slide-specific keywords make each image independently discoverable in Google Image Search, Pinterest, and portfolio pages — rather than all slides sharing the same generic carousel-level keywords.

> **Note:** Instagram and TikTok rename files on upload. Filenames still matter for: website embeds, Pinterest repins, Google Image Search indexing, portfolio/blog posts, and content management/archiving.

---

## Hook Headline Formula (Slide 1 — MANDATORY)

The hook headline is the single most important text in the entire carousel. It determines whether the viewer swipes or scrolls past. A generic headline = dead carousel.

### Headline Structure (Mandatory for Hook Slides)

```
[POWER WORD in caps] + [curiosity gap / number / negative frame] + [unrevealed payoff]
```

**Rules:**
1. **Score FIRST, prompt SECOND** — headline MUST score minimum 3/5 on Hook Scoring Checklist (see hook-science.md) BEFORE entering the image prompt
2. **Billboard rule** — maximum 8-12 words total. Must be readable in under 1 second at phone-scroll speed
3. **Open loop mandatory** — headline MUST create a question/itch that can ONLY be answered by swiping to the next slide. If the hook reveals the answer, it fails
4. **Power word amplification** — the power word is rendered in accent color AND at 120% size relative to the rest of the headline (visually dominant within the text)
5. **No generic headlines** — "Fakta Menarik Tentang AI" = REJECTED. Must trigger emotional response

### Hook Scoring Gate (Pre-Generation)

Before generating the hook image prompt, verify the headline scores 3/5:

| # | Feature | Check |
|---|---------|-------|
| 1 | Contains a question (?)  | |
| 2 | Contains a number/digit | |
| 3 | Contains POWER WORD in caps (GILA, PARAH, RAHASIA, FATAL, BAHAYA, GRATIS, WAJIB, TERLARANG) | |
| 4 | Uses negative frame (JANGAN, STOP, SALAH, GAGAL, KESALAHAN) | |
| 5 | Payoff NOT revealed in headline (open loop) | |

**If score < 3/5: REWRITE headline before generating prompt.**

### Hook Headline Bank (Ready-to-Adapt, 3 Per Category)

#### Visual Shock
1. `"GILA — Ini yang Terjadi dalam [N] Detik"` → power word + number + unrevealed payoff
2. `"Lo NGGAK SIAP Lihat Ini"` → negative frame + unrevealed payoff + power word
3. `"[N] Hal yang TERLARANG Tapi Semua Orang Lakuin"` → number + power word + curiosity gap

#### Negative Bias
1. `"STOP Lakuin Ini — Lo Keliatan AMATIR"` → power word + negative frame + unrevealed payoff
2. `"KESALAHAN FATAL yang [N]% Orang Gak Sadar"` → power word + number + negative frame
3. `"Kenapa [Topik] Lo GAGAL? Ini Alasannya"` → question + power word + negative frame

#### Curiosity Gap
1. `"Gue Nemu RAHASIA di Balik [Topik]"` → power word + unrevealed payoff
2. `"Ini Mungkin ILEGAL untuk Diketahui"` → power word + curiosity gap + unrevealed payoff
3. `"[N] Hari Coba [Hal Sulit] — Hasilnya GILA"` → number + unrevealed payoff + power word

#### Relatability
1. `"Kalau Lo [Job/Situasi], Lo Dalam BAHAYA"` → negative frame + power word + identity
2. `"POV: Akhirnya Ngerti [Topik] Tanpa [Pain]"` → curiosity gap + unrevealed payoff
3. `"Buat yang Baca Ini Jam 2 Pagi..."` → identity + curiosity gap + open loop

#### Speed & Value
1. `"Kasih Gue 30 Detik — Gue Hemat [N] Jam Kerja Lo"` → number + unrevealed payoff
2. `"CURI Strategi Gue Buat [Result]"` → power word + unrevealed payoff
3. `"[N] Langkah WAJIB (Tanpa Basa-Basi)"` → number + power word + speed promise

### Hook Category → Visual Direction Mapping

The hook headline category MUST match the visual composition and creator expression:

| Hook Category | Creator Expression | Scene Direction | Lighting | Camera Default |
|---------------|-------------------|-----------------|----------|---------------|
| Visual Shock | Eyes blown wide, full iris visible, dropped jaw in small O, head tilted back, hand raised in shock gesture — "frozen visceral 'wait WHAT' reaction" | Disrupted environment, warm-cool clash, motion elements, single dramatic element | Hard Rembrandt 4:1, 3200K tungsten key, strong cool 5600K rim, deep dramatic shadows | CU 85mm f/1.8 eye-level |
| Negative Bias | Intense stare through narrowed lids, brows furrowed deeply, tight lips pulled down, chin lowered looking up through brows, palm-out stop gesture — "protective warning urgency" | Dark minimal, shadow-dominant, exposed brick/dark void, faint red-amber accent glow | Short-side Rembrandt 3:1, 3800K neutral-warm, cool fill from below, thin warm rim | MCU 85mm f/1.8 eye-level |
| Curiosity Gap | One eyebrow raised creating asymmetric intrigue, closed-lip smirk one corner lifted, head tilted ten degrees, hand near mouth as if whispering — "smug insider confidence" | Warm atmospheric with depth, golden practicals, partially hidden/blurred tease element | Rembrandt 4:1, 3200K warm golden key, warm ambient fill, subtle warm halo rim | MCU 85mm f/1.8 slight angle |
| Relatability | Soft warm eye contact with raised brows of recognition, natural smile hint of teeth, slight forward nod, hands wrapped around coffee mug — "the 'oh you TOO?' face" | Authentic lifestyle (cafe, desk, bedroom), warm naturals, recognizable everyday objects | Soft loop 2:1, 3500K warm natural daylight, large soft fill, barely visible rim | MCU 50mm f/2.0 slight offset |
| Speed & Value | Direct unwavering gaze, steady confident brows, closed-lip half-smile, chin up three degrees with authoritative nod, hand showing number gesture — "calm unshakeable competence" | Clean professional (studio, organized desk), neutral warmth, competence signals (screens, tools) | Butterfly 2:1, 4000K neutral-warm, even controlled fill, subtle professional rim | MCU 85mm f/1.8 centered |

> Full expression libraries (eyes, mouth, head, hands, body per category), 3 camera variants (A/B/C), environment palettes, and synergy matrix → see `references/hook-visual-library.md`

### Multi-Keyword Highlighting in Prompt (All Slides)

Every headline must highlight **2-4 emotionally impactful keywords** in accent color — not just 1 power word. Single-word highlighting looks weak and fails to create visual rhythm across the headline.

**Keyword Selection Rules:**
1. **Power words** — GILA, PARAH, RAHASIA, FATAL, BAHAYA, GRATIS, WAJIB, TERLARANG, INSANE, SKIP, NEVER
2. **Emotional triggers** — words that provoke fear, curiosity, or urgency (COLLECTED, KNOWS, NEVER, STOP, RUGI)
3. **Numbers/stats** — concrete data points that add credibility ("10x", "30 DETIK", "99%")
4. **Identity words** — words the viewer self-identifies with (YOU, YOUR, LO, GUE)
5. **Minimum 2 keywords highlighted per headline** — 1 keyword = weak visual impact. 3-4 keywords = optimal rhythm

**Example headline analysis:**
- `"SKIP THIS AND YOU'LL NEVER KNOW WHAT THEY'VE COLLECTED"` → highlight: **SKIP**, **NEVER**, **COLLECTED** (3 keywords)
- `"INSANE — WHAT YOUR PHONE KNOWS ABOUT YOU RIGHT NOW"` → highlight: **INSANE**, **YOUR PHONE**, **KNOWS**, **RIGHT NOW** (4 keywords)
- `"GILA — 5 HAL TERLARANG yang Semua Orang Lakuin"` → highlight: **GILA**, **5**, **TERLARANG** (3 keywords)

**Hook slide:** Power word at 120% size + additional 1-3 keywords in accent color at normal size.
**All other slides:** 2-4 keywords in accent color (no size difference needed).

```
Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[FULL HEADLINE]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The word "[POWER WORD]" in slightly larger size, visually dominant within the headline. Remaining text in white.
The text uses the largest possible font size that fills the width, extra bold weight, dominating the gradient zone.
```

---

## Templates

### Template — Hook Slide (Slide 1)

**MANDATORY — Hook Category Selection (DO NOT SKIP):**
1. Identify topic from the **Topic → Hook Category Mapping** in `references/hook-science.md`
2. Use the **PRIMARY** hook category for this topic
3. If the PRIMARY was used in a previous carousel this session, use **SECONDARY**
4. **NEVER** use a category listed in "Avoid" for this topic — e.g., Education → Avoid: Visual Shock
5. Read the **visual profile** for the selected category from `references/hook-visual-library.md`
6. State the selected category explicitly: `Hook Category: [X]`

**Pre-generation:** Score headline 3/5 on Hook Scoring Gate (see Hook Headline Formula above). If < 3/5, rewrite before proceeding.

**Visual Action selection:** Choose a visual action from the Visual Action Hook Bank in `references/hook-science.md`. Use the Topic → Visual Action Mapping table for default selection. Insert the action fragment at `[Action/pose]` and `[Scene with pattern interrupt]` slots below. The absurd mundane action IS the pattern interrupt.

**Anti-repetition:** If this topic has been used before this session, select a different camera variant (A/B/C) from `references/hook-visual-library.md` Section 4. Check the synergy matrix (Section 6) for expression modifications when combining category + visual action.

```
A photorealistic cinematic [shot type — from hook-visual-library.md Camera Angle Bank, variant A/B/C] of [CREATOR DESCRIPTION VERBATIM].
[Expression from hook-visual-library.md Expression Library — use FULL prompt phrases for eyes, mouth, head, hands, body, emotion. NOT generic "shocked face"].
[Wardrobe]. [Action/pose from Visual Action Hook Bank — e.g., mid-bite into bread, pouring coffee, holding absurd object].

[Scene with pattern interrupt — use the contrast/context from the Visual Action prompt fragment.
The mundane action contrasts with the serious headline, creating cognitive dissonance.
Match Hook Category -> Scene Direction mapping. The scene must feel wrong or surprising at first glance.]
[Foreground element] + [subject] + [background with bokeh/depth — 3 distinct layers].

Lens: [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern from Hook Category -> Lighting mapping] at [ratio] ratio, [Kelvin]K [key direction].
[Film stock], [color grade]. [Atmosphere/particles — haze, volumetric, bokeh].
[Texture detail: natural skin texture with visible pores, fabric weave].
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HOOK HEADLINE — scored 3/5+]" with the words "[POWER WORD]", "[KEYWORD 2]", and "[KEYWORD 3]"
in [config: accent_color]. The word "[POWER WORD]" in slightly larger size, visually dominant. Remaining text in white.
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
Maintain exact facial identity from reference image: [face-ref.png].
```

### Template — Creator Shot (CTA)

See "Template — CTA Slide" section below for the 4 CTA visual types.

### Template — Creator Shot (General — Non-Hook, Non-CTA)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM].
[Expression keywords from cinematography-lut.md]. [Wardrobe]. [Action/pose].

[Setting/environment with specific details].
[Foreground element] + [subject] + [background with bokeh/depth].

Lens: [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K [key direction].
[Film stock], [color grade]. [Atmosphere/particles].
[Texture detail: natural skin texture with visible pores, fabric weave].
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HEADLINE IN BAHASA]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
Maintain exact facial identity from reference image: [face-ref.png].
```

### Template — Foreshadow Slide (Slide 2 — MANDATORY)

**Purpose:** Bridge the hook to the body. Instagram re-serves carousel from slide 2 if user didn't engage on slide 1 — this is your SECOND CHANCE to capture attention. Slide 2 must create FOMO: "If you skip this, you'll miss [consequence]."

**Foreshadow Type Selection:**

| Type | When to Use | Headline Formula | Visual Direction |
|------|-------------|-----------------|------------------|
| **Steps Tease** | Listicle, tutorial, how-to | "Ada [N] cara, dan yang ke-[N] bikin gue berhenti [activity]" | Numbered list visual with LAST ITEM blurred/hidden. Items 1-3 visible, item N = blur overlay with "?" |
| **Fear Urgency** | Education, finance, business, health | "Kalau lo skip ini, lo terus [negative consequence]" | Creator with concerned/urgent expression, subtle red warning accent, tension composition |
| **Quiz/Choice** | Comparison, opinion, debate topics | "Mana yang lebih [adjective] — [A] atau [B]? Jawabannya MENGEJUTKAN" | Split composition showing A vs B, both slightly blurred, "?" in center |
| **Visual Tease** | Story, reveal, transformation, case study | "[Preview of reveal] — tapi tunggu sampai slide [N]..." | Partial/blurred preview of the climax slide, gaussian blur 40-60% with "coming soon" energy |

```
A photorealistic cinematic MCU of [CREATOR DESCRIPTION VERBATIM].
[Expression: concerned urgency or teasing "I know something" smirk — matching foreshadow type].
[Wardrobe]. [Pose: leaning slightly forward, creating intimacy and urgency].

[For Steps Tease: background shows floating numbered cards/list items, items 1-3 crisp,
last item heavily blurred with glowing "?" overlay]
[For Fear Urgency: warning-toned environment, subtle red/amber accent lighting,
visual tension — creator gesturing stop or pointing urgently at camera]
[For Quiz/Choice: split background showing option A and option B,
both partially visible, creator in center between them]
[For Visual Tease: background shows a blurred/partially revealed version of the
climax slide content, heavy gaussian blur, creating anticipation]

[Foreground element] + [creator subject] + [foreshadow background — 3 depth layers].

Lens: 85mm f/2, eye-level to slight low angle (authority), shallow depth of field.
Loop lighting at 3:1 ratio, 3200K warm key. Slightly muted palette compared to hook
(tension build, not peak energy — save that for later slides).
[Film stock], [warm but restrained grade]. [Subtle atmosphere: light haze, minimal particles].
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[FORESHADOW HEADLINE — creates FOMO/urgency to keep swiping]"
with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
Maintain exact facial identity from reference image: [face-ref.png].
```

**Foreshadow Headline Bank:**
- Steps Tease: `"Ada 7 Cara, yang ke-7 GILA"` / `"[N] Langkah — Tapi yang Terakhir Bikin Kaget"`
- Fear Urgency: `"Kalau Lo Skip, Lo Terus Buang [Amount] Tanpa Sadar"` / `"BAHAYA — Dan Lo Mungkin Lagi Lakuin Ini"`
- Quiz/Choice: `"Mana yang Benar — [A] atau [B]?"` / `"Lo Pasti Salah Pilih"`
- Visual Tease: `"Tunggu Sampai Lo Lihat Slide [N]..."` / `"Ini Baru Awalnya"`

### Template — B-Roll / Topic Visual (No Creator Face)
```
A photorealistic cinematic [shot type] of [subject/scene].
[Detailed scene description]. [Context-specific elements].
[If slide discusses a specific brand/product: include recognizable brand elements
(logo, UI, interface, color scheme) of the subject being discussed for viewer context.]
[Foreground element] + [main subject] + [background depth layer].

Lens: [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere: haze/particles/volumetric].
[Texture detail: surface materials, environmental textures].
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HEADLINE IN BAHASA]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding (subject brand is required for context).
```

### Template — B-Roll with Human Figure (Creator Face ALWAYS)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM] as a prominent figure in [scene].
[Context-appropriate expression]. [Profession-specific wardrobe or creator default wardrobe].
[Scene description with creator clearly identifiable among other figures.
For crowd scenes: creator in center-foreground, slightly closer to camera, clearly the most recognizable face.
For single/few person scenes: creator is the primary subject.]
[Foreground element] + [subject] + [background depth layer].

Lens: [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere].
[Texture detail]. [Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HEADLINE IN BAHASA]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight,
positioned starting from the vertical center of the image extending downward, not crammed at the very bottom.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding (subject brand is required for context).
Maintain exact facial identity from reference image: [face-ref.png].
```

**NOTE:** B-Roll with ANY visible human figures = creator face ALWAYS included (no need to ask). Creator must be the most prominent/identifiable figure. Only pure object/landscape B-Roll has no creator face.

### Template — Thumbnail
```
A photorealistic cinematic thumbnail composition:

Primary subject: [CREATOR DESCRIPTION VERBATIM], [exaggerated hook expression].
Expression: [specific exaggerated emotion] — wide eyes, raised brows,
[mouth position], energy that screams "KAMU HARUS LIHAT INI".
Position: face occupies majority of frame, positioned [left/right/center].

Secondary element: [topic visual] — [description of topic element visible
in background or beside creator, e.g., AI interface, data visualization].
[Foreground detail] + [creator subject] + [topic visual background layer].

Lens: 85mm f/1.8, eye-level, slight dutch tilt for dynamic energy.
Rembrandt or Split lighting, 4:1-6:1 ratio, mixed warm face / cool topic element.
Strong rim light separating creator from background.
Kodak Vision3 500T, high saturation, boosted contrast, vibrant teal-orange.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom third of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[JUDUL THUMBNAIL DALAM BAHASA]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
Maintain exact facial identity from reference image: [face-ref.png].
```

> **Note:** Thumbnails typically don't need page numbers since they are standalone images, not part of the carousel sequence. Omit `"[N]/[TOTAL]"` for thumbnails.

### Template — Split-Panel
```
A photorealistic split-panel composition divided vertically into two halves.

Left half ("[LABEL A IN BAHASA]"): [Scene A] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, [config: film_stock].
[Texture: natural skin, fabric detail]. [DP reference].

Right half ("[LABEL B IN BAHASA]"): Same person in same location but [contrasting version].
[Contrasting visual elements]. Enhanced but still warm color temperature.
[Foreground + subject + background depth layers in each half].

Both halves: same environment context.
Lens: 50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
[Atmosphere: haze, particles, or environmental effect].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[HEADLINE IN BAHASA]" with the words "[KEYWORD 1]", "[KEYWORD 2]", and "[KEYWORD 3]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight, dominating the gradient zone.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
[If comparison (A vs B): brand icon + watermark on divider:]
Render the creator's brand icon from reference image [brand-icon.png] on the vertical center divider line
between the two panels as a small circular badge at thirty percent opacity — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white on the vertical center divider line,
thirty percent opacity, subtle background mark only.
[If non-comparison: brand icon + watermark centered:]
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
"[config: swipe_cta_text]" in small white text positioned directly beneath the headline text with minimal gap.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
Maintain exact facial identity from reference image: [face-ref.png].
```

### Template — CTA Slide (Last Slide — 4 Visual Types)

The CTA slide must CONVERT attention into action. A generic "follow me" composition = wasted opportunity. Select the CTA visual type that best matches the carousel's engagement goal.

**CTA Type Selection Guide:**

| Topic Type | Best CTA | Why |
|------------|----------|-----|
| Debate / opinion / comparison | **Polarize** | Creates comment war → highest comment volume |
| Listicle / ranking / choice | **Question** | Low-friction engagement → "pick one" is easy |
| Relatable / community / friends | **Identity Tag** | Triggers share/tag → highest reach amplification |
| Tutorial / how-to / resource | **Engagement Reward** | Comment keyword → DM funnel → lead generation |

**CTA Lighting (All Types):** Butterfly lighting, 2:1 ratio, 3500K — warmer and more intimate than body slides. This signals "conversation" not "lecture."

#### CTA Type 1: Polarize ("Menurut lo A atau B?")

**Goal:** Drive comments through debate. Two sides = everyone has an opinion.
**Best stat:** Debate-driven CTAs generate highest comment volume per impression.

```
A photorealistic cinematic MS of [CREATOR DESCRIPTION VERBATIM].
Expression: confident, playful challenge — one eyebrow raised, slight smirk,
"I want to hear your take" energy. Arms open, gesturing to both sides.
[Wardrobe: default creator wardrobe].

Background split into two zones: left side shows [option A visual],
right side shows [option B visual]. Both options clearly visible and distinct.
Creator positioned center between both options, acting as the referee.
[Foreground element] + [creator center] + [split background with options].

Lens: 50mm f/2.8, eye-level, centered composition.
Butterfly lighting at 2:1 ratio, 3500K warm key, soft fill.
[config: film_stock], [config: color_grade]. Soft haze, warm bokeh.
Natural skin texture with visible pores, fabric weave.
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "MENURUT LO [A] ATAU [B]?" with "[A]" and "[B]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
Three small social media icons (Instagram logo, TikTok logo, LinkedIn logo) arranged in a single horizontal row with "[config: handle]" in white text beside the icons row.
Below the icons row, "[config: portfolio_url]" in white text at slightly smaller size.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "SWIPE (GESER)" on CTA.
Maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 2: Question ("Lo yang mana?")

**Goal:** Low-friction engagement. Simple choice = easy to comment.
**Best stat:** "Which one?" CTAs get +25% more comments than open-ended questions.

```
A photorealistic cinematic CU of [CREATOR DESCRIPTION VERBATIM].
Expression: warm curiosity, direct eye contact, slight head tilt —
"I'm genuinely asking you" energy. One hand near chin (thinking pose)
or pointing directly at camera (breaking fourth wall).
[Wardrobe: default creator wardrobe].

Background: clean, warm, minimal distraction — soft bokeh environment
that keeps all attention on creator's face and the question.
[Foreground element: subtle] + [creator face dominant] + [warm bokeh background].

Lens: 85mm f/1.8, eye-level, tight framing — face fills majority of frame.
Butterfly lighting at 2:1 ratio, 3500K warm intimate key.
[config: film_stock], [config: color_grade]. Gentle atmosphere, minimal particles.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "[SIMPLE CHOICE QUESTION IN BAHASA]?" with the words "[KEYWORD 1]" and "[KEYWORD 2]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
Three small social media icons (Instagram logo, TikTok logo, LinkedIn logo) arranged in a single horizontal row with "[config: handle]" in white text beside the icons row.
Below the icons row, "[config: portfolio_url]" in white text at slightly smaller size.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "SWIPE (GESER)" on CTA.
Maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 3: Identity Tag ("Tag temen yang BUTUH ini")

**Goal:** Trigger share/tag behavior. Highest reach amplification via DM/tag shares.
**Best stat:** IG DM shares = 3-5x heavier algorithm weight than likes.

```
A photorealistic cinematic MWS of [CREATOR DESCRIPTION VERBATIM]
with a second person (friend/colleague energy — similar age, casual interaction).
Expression: both laughing/smiling warmly, creator nudging/pointing at the other person
as if saying "this is for you." Natural, candid friendship moment.
[Wardrobe: casual, approachable for both figures].

Setting: warm lifestyle environment — coffee shop, co-working space, or casual hangout.
Natural warm light streaming in. Feeling of genuine connection between two people.
[Foreground element: table/coffee] + [two subjects] + [warm interior bokeh background].

Lens: 50mm f/2, eye-level, slightly wider to fit both subjects.
Loop lighting at 2:1 ratio, 3500K natural warm key.
[config: film_stock], [config: color_grade]. Soft atmospheric haze.
Natural skin texture with visible pores on both subjects, fabric detail.
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "TAG TEMEN YANG BUTUH INI" with "BUTUH" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
Three small social media icons (Instagram logo, TikTok logo, LinkedIn logo) arranged in a single horizontal row with "[config: handle]" in white text beside the icons row.
Below the icons row, "[config: portfolio_url]" in white text at slightly smaller size.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "SWIPE (GESER)" on CTA.
Maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 4: Engagement Reward ("Comment KEYWORD buat dapetin...")

**Goal:** Comment keyword → DM automation funnel → lead generation.
**Best stat:** Comment-to-DM funnels can generate 1,000+ leads/month.

```
A photorealistic cinematic MCU of [CREATOR DESCRIPTION VERBATIM].
Expression: generous, excited to give — bright smile, eyes lit up,
one hand extended toward camera holding/presenting [reward visual:
a glowing guide/book/template/phone showing the resource].
The gift object is the visual focal point alongside the creator's face.
[Wardrobe: default creator wardrobe].

Setting: warm, professional but inviting environment.
[Reward object] in foreground, slightly glowing with accent color light.
[Creator subject] + [reward in hand] + [warm professional bokeh background].

Lens: 85mm f/2, eye-level, medium-close framing.
Butterfly lighting at 2:1 ratio, 3500K warm key.
Accent color rim light on the reward object (making it glow and stand out).
[config: film_stock], [config: color_grade]. Subtle golden particles floating.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom half of the image has a smooth dark gradient zone. Extremely large, bold, impactful condensed uppercase text
reading "COMMENT '[KEYWORD]' BUAT DAPETIN [REWARD]" with "[KEYWORD]" in [config: accent_color].
The text uses the largest possible font size that fills the width, extra bold weight.
Below the main headline, a [config: subtitle_language] subtitle line in [config: subtitle_color] at slightly smaller size — subtitle must not be white.
Render the creator's brand icon from reference image [brand-icon.png] centered in the middle of the image
as a small circular badge at thirty percent opacity, positioned directly above the @handle watermark — use the exact icon from the file, do not generate a new one.
"[config: handle]" as a watermark in white, centered in the middle of the image directly below the brand icon,
thirty percent opacity, subtle background mark only.
Three small social media icons (Instagram logo, TikTok logo, LinkedIn logo) arranged in a single horizontal row with "[config: handle]" in white text beside the icons row.
Below the icons row, "[config: portfolio_url]" in white text at slightly smaller size.
"[N]/[TOTAL]" as a small white page number in the top-left corner of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "SWIPE (GESER)" on CTA.
Maintain exact facial identity from reference image: [face-ref.png].
```

**CTA Headline Bank:**
- Polarize: `"Menurut Lo [A] atau [B]?"` / `"Setuju atau Nggak? Tulis di Komentar"`
- Question: `"Lo yang Mana? Tulis 1, 2, atau 3!"` / `"Pilih yang Paling Lo Relate"`
- Identity Tag: `"Tag Temen yang BUTUH Ini"` / `"Share ke Temen Lo yang [situation]"`
- Engagement Reward: `"Comment 'TEMPLATE' Buat Dapetin GRATIS"` / `"Comment 'GUIDE' dan Gue DM"`

---

## Emotional Arc Visual Map (MANDATORY Pre-Generation Step)

Before generating individual slide prompts, PLOT the emotional arc for the entire carousel. Each slide gets an emotional beat and intensity tag. This ensures the carousel feels like a JOURNEY, not a flat sequence.

### The Roller Coaster Pattern

```
6/6 ██████  HOOK ─────┐
5/6 █████              │                              ┌── CLIMAX
4/6 ████               │              ┌── MINI-HOOK ──┘
3/6 ███                └── FORESHADOW─┤
2/6 ██                                └── BUILD ──────┘
1/6 █                                                      WARM (CTA)
    ─────────────────────────────────────────────────────────────────
    Slide 1   Slide 2    Slide 3-4    Slide 5-7    Slide 8+   Last
```

### Beat → Visual Treatment Mapping

| Beat | Slides | Intensity | Visual Treatment | Camera | Lighting | Color |
|------|--------|-----------|-----------------|--------|----------|-------|
| **HIGH** | 1 (Hook) | 6/6 | Extreme CU, pattern interrupt scene, creator's most exaggerated expression | CU/MCU, 85mm f/1.8, slight dutch tilt | High contrast 4:1, dramatic key | Peak saturation, strong accent color on power word |
| **DIP** | 2 (Foreshadow) | 3/6 | Pull back to MCU/MS, tension build composition, partially hidden/blurred elements | MCU/MS, 85mm f/2, eye-level | 3:1, slightly muted key | Restrained palette — warm but held back, building anticipation |
| **BUILD** | 3-5 (Body) | 2→4/6 | Progressive escalation: each slide slightly more saturated, tighter framing as value increases | Varies, progressively tighter | Progressively brighter, 3:1→2:1 | Gradual saturation increase slide-over-slide |
| **MINI-HOOK** | 5-7 | 5/6 | Sudden change — split panel, extreme angle, color temperature shift, or unexpected composition. "Tapi tunggu..." energy | Extreme angle or split panel or dramatic zoom | Sudden shift — if previous slides were warm, add cool accent | Color temperature disruption — introduce unexpected contrast |
| **CLIMAX** | 8+ (Reveal) | 6/6 | Widest establishing shot or most intimate close-up (contrast with body), peak saturation, biggest text, most shareable insight | Widest or tightest (contrast with body slides) | Peak drama, 4:1, rim light dominant | Peak saturation, accent color dominant, full visual impact |
| **WARM** | Last (CTA) | 1/6 | Softest, warmest, most intimate — direct eye contact, inviting expression, connection energy | MCU, 85mm f/2, direct eye-level | Butterfly 2:1, warmest Kelvin (3500K), soft fill | Warmest tone, golden, gentle — "come closer" feeling |

### Emotional Intensity Scale

```
6/6 = Maximum impact (hook, climax) — highest contrast, saturation, drama
5/6 = High impact (mini-hook) — sudden change, surprise element
4/6 = Rising energy (late body slides) — building toward reveal
3/6 = Tension build (foreshadow, early body) — restrained but anticipatory
2/6 = Foundation (early body slides) — establishing value, steady build
1/6 = Intimate warmth (CTA) — softest, connection-focused
```

### Output Tag Format

Every slide in the output MUST include the emotional beat tag:

```
## Slide N: [TYPE] — [Topic] | Emotion: [BEAT] ([intensity]/6)
```

Examples:
- `## Slide 1: HOOK — 7 Tools AI | Emotion: HIGH (6/6)`
- `## Slide 2: FORESHADOW — Tease | Emotion: DIP (3/6)`
- `## Slide 5: CONTENT — Surprise Reveal | Emotion: MINI-HOOK (5/6)`
- `## Slide 8: CTA — Follow | Emotion: WARM (1/6)`

### Mini-Hook Placement Rule

**Place a mini-hook at slides 5-7** to prevent mid-carousel drop-off. Exit rates stabilize at 12-15% per slide after slide 4. A mid-carousel surprise re-engages committed swipers.

Mini-hook triggers:
- Sudden split-panel composition (if body was single-frame)
- Extreme camera angle change (dutch tilt, bird's eye, worm's eye)
- Color temperature shift (warm → cool accent → back to warm)
- "Tapi..." or "Plot twist:" headline prefix
- Visual contradiction or unexpected scale comparison

---

## Quality Checklists

### Image Prompt Checklist (All 8 WOW Elements)
Before finalizing each image prompt, verify ALL 8 are present:
- [ ] **Lighting Drama** — Lighting pattern named (Rembrandt, Loop, etc.) + ratio (2:1, 4:1) + Kelvin
- [ ] **Depth Layers** — Foreground element + subject + background (3 distinct layers)
- [ ] **Atmosphere** — Haze, particles, volumetric, fog, bokeh, or environmental effect
- [ ] **Color Contrast** — Warm-cool tension, accent color highlights, or complementary palette
- [ ] **Emotional Peak** — Expression keywords (if creator) or scene emotion (if B-Roll)
- [ ] **Camera Intention** — Shot type + lens + aperture + angle with purpose
- [ ] **Texture Realism** — Pores, fabric weave, surface materials, or environmental textures
- [ ] **Cinematic Ref** — Film stock named + color grade + optional DP reference

### Text Rendering Checklist
- [ ] Main headline in [config: main_headline_language], subtitle in [config: subtitle_language] + [config: subtitle_color] (or single language if user-requested)
- [ ] Accent words identified and color specified
- [ ] Brand icon filename + position specified
- [ ] @handle watermark + opacity specified
- [ ] SWIPE FOR MORE present (or omitted for CTA)
- [ ] Gradient zone matches slide type (bottom half, bottom third for thumbnail)

### Thumbnail Checklist
- [ ] Creator face from reference image, 50-60% of frame
- [ ] Topic visual included (background/side element)
- [ ] Text overlay rendered in image (title in gradient zone)
- [ ] Expression EXAGGERATED (readable at 100x100px)
- [ ] High contrast, saturated colors
- [ ] Curiosity gap created — "What does he know?"
- [ ] Aspect ratio matches target platform
- [ ] All 8 WOW elements present

---

## Key Rules
- Natural language, NOT keyword spam
- **80-200 words optimal** (up to 250 for complex compositions with text)
- Negative constraints at END: "no third-party branding"
- Always specify reference image filename for creator shots
- **All 8 WOW elements MANDATORY** — minimum score 6/8
- **Text rendered IN-IMAGE** — no separate post-production section
- **Default: Per global-config.md Language section (bilingual by default)**
- API: `response_modalities=['TEXT', 'IMAGE']`, `image_size="4K"` (uppercase K)
- Aspect ratio set per target platform — see `references/platform-specs.md`
