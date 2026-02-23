# Prompt Formulas — Nano Banana Pro

## Golden Rule
```
Treat every prompt like a Creative Director brief — natural language, NOT keyword spam.
⚠ Use: "Maintain exact appearance from reference image" for character consistency
⚠ Text rendered IN-IMAGE — all headlines, accents, branding, and labels are part of the prompt
⚠ Default language for in-image text = Bahasa Indonesia (English only if user explicitly requests)
```

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
| Category tag | Centered above headline | Accent color, small caps (e.g., "TEKNOLOGI") |
| Headline | Bottom gradient zone | White #FFFFFF bold condensed ALL CAPS |
| Accent words | Within headline | Accent color (default: Golden Yellow #F5A623) |
| Brand icon | Top-right corner | Brand icon filename, every slide |
| @handle watermark | **Center of image** | White, **30% opacity on ALL slides** |
| SWIPE FOR MORE > | Bottom center | White small text, all slides EXCEPT CTA |
| Slide counter | Optional | "3/10" format, small, top-left |

### Default Language
- In-image text (headlines, accent words, category tags) = **Bahasa Indonesia** by default
- English only if user explicitly requests
- Prompt instructions (scene description) = ALWAYS English (AI model instruction)

### Text Rendering Syntax in Prompt
```
Bottom [N]% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Text must be MASSIVE — billboard-scale, dominating the gradient zone, extra bold/black weight.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
["GESER UNTUK LANJUT >" in small white text at bottom center. | omit for CTA slide]
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

| Hook Category | Creator Expression | Scene Direction | Lighting |
|---------------|-------------------|-----------------|----------|
| Visual Shock | Wide-eyed shock, mouth open, frozen mid-reaction | Visual contradiction or unexpected scale — something "wrong" in the scene | High contrast 4:1, dramatic rim light |
| Negative Bias | Concerned frown, warning hand gesture, serious eye contact | Warning visual (red accent glow), "stop" composition | Moody, underlit face, 3:1 ratio |
| Curiosity Gap | Knowing smirk, raised eyebrows, "I know something you don't" | Partially hidden/blurred element that teases the reveal | Rembrandt 4:1, warm key, mystery shadows |
| Relatability | Relatable frustration OR joy, "that's so me" expression | Everyday scenario elevated to cinematic — familiar but beautiful | Soft loop lighting, 2:1, warm natural |
| Speed & Value | Confident authority, direct unblinking eye contact, chin slightly up | Clean composition, minimal distraction, focus on creator authority | Butterfly 2:1, clean, professional |

### Power Word Rendering in Prompt

When writing the hook prompt, the power word gets special treatment:

```
Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[FULL HEADLINE]" with the word "[POWER WORD]" rendered at 120% size in [accent color hex],
visually dominant within the headline. Remaining text in white #FFFFFF.
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
```

---

## Templates

### Template — Hook Slide (Slide 1)

**Pre-generation:** Score headline 3/5 on Hook Scoring Gate (see Hook Headline Formula above). If < 3/5, rewrite before proceeding.

```
A photorealistic cinematic [shot type — CU/MCU, match Hook Category table] of [CREATOR DESCRIPTION VERBATIM].
[Expression MUST match Hook Category → Creator Expression mapping — e.g., wide-eyed shock for Visual Shock].
[Wardrobe]. [Action/pose that amplifies the emotion].

[Scene with PATTERN INTERRUPT — something visually unexpected or contradictory that stops the scroll.
Match Hook Category → Scene Direction mapping. The scene must feel "wrong" or surprising at first glance.]
[Foreground element] + [subject] + [background with bokeh/depth — 3 distinct layers].

Shot on [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern from Hook Category → Lighting mapping] at [ratio] ratio, [Kelvin]K [key direction].
[Film stock], [color grade]. [Atmosphere/particles — haze, volumetric, bokeh].
[Texture detail: natural skin texture with visible pores, fabric weave].
[Cinematic DP reference].

Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HOOK HEADLINE — scored 3/5+]" with the word "[POWER WORD]" rendered at 120% size
in [accent color hex], visually dominant within the headline. Remaining text in white #FFFFFF.
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

### Template — Creator Shot (CTA)

See "Template — CTA Slide" section below for the 4 CTA visual types.

### Template — Creator Shot (General — Non-Hook, Non-CTA)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM].
[Expression keywords from cinematography-lut.md]. [Wardrobe]. [Action/pose].

[Setting/environment with specific details].
[Foreground element] + [subject] + [background with bokeh/depth].

Shot on [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K [key direction].
[Film stock], [color grade]. [Atmosphere/particles].
[Texture detail: natural skin texture with visible pores, fabric weave].
[Cinematic DP reference].

Bottom [N]% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
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
[Expression: concerned urgency OR teasing "I know something" smirk — matching foreshadow type].
[Wardrobe]. [Pose: leaning slightly forward, creating intimacy and urgency].

[FOR Steps Tease: background shows floating numbered cards/list items, items 1-3 crisp,
last item heavily blurred with glowing "?" overlay]
[FOR Fear Urgency: warning-toned environment, subtle red/amber accent lighting,
visual tension — creator gesturing "stop" or pointing urgently at camera]
[FOR Quiz/Choice: split background showing option A and option B,
both partially visible, creator in center between them]
[FOR Visual Tease: background shows a blurred/partially revealed version of the
climax slide content, gaussian blur 40-60%, creating anticipation]

[Foreground element] + [creator subject] + [foreshadow background — 3 depth layers].

Shot on 85mm f/2, eye-level to slight low angle (authority), shallow depth of field.
Loop lighting at 3:1 ratio, 3200K warm key. Slightly muted palette compared to hook
(tension build, NOT peak energy — save that for later slides).
[Film stock], [warm but restrained grade]. [Subtle atmosphere: light haze, minimal particles].
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom 35% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[FORESHADOW HEADLINE — creates FOMO/urgency to keep swiping]"
with the word "[KEY WORD]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
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
[IF slide discusses a specific brand/product: include recognizable brand elements
(logo, UI, interface, color scheme) of the SUBJECT being discussed for viewer context.]
[Foreground element] + [main subject] + [background depth layer].

Shot on [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere: haze/particles/volumetric].
[Texture detail: surface materials, environmental textures].
[Cinematic DP reference].

Bottom 35% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding (subject brand IS required for context).
```

### Template — B-Roll with Human Figure (Creator Face ALWAYS)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM] as a prominent figure in [scene].
[Context-appropriate expression]. [Profession-specific wardrobe OR creator default wardrobe].
[Scene description with creator clearly identifiable among other figures.
For crowd scenes: creator in center-foreground, slightly closer to camera, clearly the most recognizable face.
For single/few person scenes: creator IS the primary subject.]
[Foreground element] + [subject] + [background depth layer].

Shot on [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere].
[Texture detail]. [Cinematic DP reference].

Bottom 35% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding (subject brand IS required for context).
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

**NOTE:** B-Roll with ANY visible human figures = creator face ALWAYS included (no need to ask). Creator must be the most prominent/identifiable figure. Only pure object/landscape B-Roll has no creator face.

### Template — Thumbnail
```
A photorealistic cinematic thumbnail composition:

PRIMARY: [CREATOR DESCRIPTION VERBATIM], [EXAGGERATED HOOK EXPRESSION].
Expression: [specific exaggerated emotion] — wide eyes, raised brows,
[mouth position], energy that screams "KAMU HARUS LIHAT INI".
Position: Face occupies 50-60% of frame, positioned [left/right/center].

SECONDARY: [TOPIC VISUAL] — [description of topic element visible
in background or beside creator, e.g., AI interface, data visualization].
[Foreground detail] + [creator subject] + [topic visual background layer].

Shot on 85mm f/1.8, eye-level, slight dutch tilt (5-10°) for dynamic energy.
Rembrandt or Split lighting, 4:1-6:1 ratio, mixed warm face / cool topic element.
Strong rim light separating creator from background.
Kodak Vision3 500T, HIGH SATURATION, boosted contrast, vibrant teal-orange.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom 25% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[JUDUL THUMBNAIL DALAM BAHASA]" with key words in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

### Template — Split-Panel
```
A photorealistic split-panel composition divided vertically into two halves.

LEFT HALF ("[LABEL A IN BAHASA]"): [Scene A] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, Kodak Portra 400.
[Texture: natural skin, fabric detail]. [DP reference].

RIGHT HALF ("[LABEL B IN BAHASA]"): Same person in same location but [CONTRAST VERSION].
[Contrasting visual elements]. Enhanced but still warm color temperature.
[Foreground + subject + background depth layers in each half].

Both halves: same environment context.
50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
[Atmosphere: haze, particles, or environmental effect].

Bottom 30% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with accent words in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight, dominating the gradient zone.
[brand-icon.png] + "@[handle]" watermark in white at 30% opacity, placed ON the vertical
center divider line between the two panels (not top-right — on the divider for split-panel).
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No competitor branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
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
"I want to hear YOUR take" energy. Arms open, gesturing to both sides.
[Wardrobe: default creator wardrobe].

Background split into TWO ZONES: left side shows [OPTION A visual],
right side shows [OPTION B visual]. Both options clearly visible and distinct.
Creator positioned CENTER between both options, acting as the "referee."
[Foreground element] + [creator center] + [split background with options].

Shot on 50mm f/2.8, eye-level, centered composition.
Butterfly lighting at 2:1 ratio, 3500K warm key, soft fill.
Kodak Portra 400, warm golden amber grade. Soft haze, warm bokeh.
Natural skin texture with visible pores, fabric weave.
[Cinematic DP reference].

Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "MENURUT LO [A] ATAU [B]?" with "[A]" and "[B]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
[Social handles listed: @ig | @tiktok | @linkedin]

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "GESER UNTUK LANJUT" on CTA.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 2: Question ("Lo yang mana?")

**Goal:** Low-friction engagement. Simple choice = easy to comment.
**Best stat:** "Which one?" CTAs get +25% more comments than open-ended questions.

```
A photorealistic cinematic CU of [CREATOR DESCRIPTION VERBATIM].
Expression: warm curiosity, direct eye contact, slight head tilt —
"I'm genuinely asking YOU" energy. One hand near chin (thinking pose)
or pointing directly at camera (breaking fourth wall).
[Wardrobe: default creator wardrobe].

Background: clean, warm, minimal distraction — soft bokeh environment
that keeps ALL attention on creator's face and the question.
[Foreground element: subtle] + [creator face dominant] + [warm bokeh background].

Shot on 85mm f/1.8, eye-level, tight framing — face fills 60% of frame.
Butterfly lighting at 2:1 ratio, 3500K warm intimate key.
Kodak Portra 400, warm golden grade. Gentle atmosphere, minimal particles.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "[SIMPLE CHOICE QUESTION IN BAHASA]?" with key word in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
[Social handles listed: @ig | @tiktok | @linkedin]

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "GESER UNTUK LANJUT" on CTA.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 3: Identity Tag ("Tag temen yang BUTUH ini")

**Goal:** Trigger share/tag behavior. Highest reach amplification via DM/tag shares.
**Best stat:** IG DM shares = 3-5x heavier algorithm weight than likes.

```
A photorealistic cinematic MWS of [CREATOR DESCRIPTION VERBATIM]
with a SECOND PERSON (friend/colleague energy — similar age, casual interaction).
Expression: both laughing/smiling warmly, creator nudging/pointing at the other person
as if saying "THIS is for you." Natural, candid friendship moment.
[Wardrobe: casual, approachable for both figures].

Setting: warm lifestyle environment — coffee shop, co-working space, or casual hangout.
Natural warm light streaming in. Feeling of genuine connection between two people.
[Foreground element: table/coffee] + [two subjects] + [warm interior bokeh background].

Shot on 50mm f/2, eye-level, slightly wider to fit both subjects.
Loop lighting at 2:1 ratio, 3500K natural warm key.
Kodak Portra 400, warm golden grade. Soft atmospheric haze.
Natural skin texture with visible pores on both subjects, fabric detail.
[Cinematic DP reference].

Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "TAG TEMEN YANG BUTUH INI" with "BUTUH" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
[Social handles listed: @ig | @tiktok | @linkedin]

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "GESER UNTUK LANJUT" on CTA.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

#### CTA Type 4: Engagement Reward ("Comment KEYWORD buat dapetin...")

**Goal:** Comment keyword → DM automation funnel → lead generation.
**Best stat:** Comment-to-DM funnels can generate 1,000+ leads/month.

```
A photorealistic cinematic MCU of [CREATOR DESCRIPTION VERBATIM].
Expression: generous, excited to give — bright smile, eyes lit up,
one hand extended toward camera holding/presenting [REWARD VISUAL:
a glowing guide/book/template/phone showing the resource].
The "gift" is the visual focal point alongside the creator's face.
[Wardrobe: default creator wardrobe].

Setting: warm, professional but inviting environment.
[Reward object] in foreground, slightly glowing with accent color light.
[Creator subject] + [reward in hand] + [warm professional bokeh background].

Shot on 85mm f/2, eye-level, medium-close framing.
Butterfly lighting at 2:1 ratio, 3500K warm key.
Accent color rim light on the reward object (making it "glow" and stand out).
Kodak Portra 400, warm golden grade. Subtle golden particles floating.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom 40% dark gradient zone with extremely large, bold, impactful condensed ALL CAPS text
reading "COMMENT '[KEYWORD]' BUAT DAPETIN [REWARD]" with "[KEYWORD]" in [accent color hex].
Text must be MASSIVE — billboard-scale, extra bold/black weight.
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
[Social handles listed: @ig | @tiktok | @linkedin]

[PLATFORM ASPECT] aspect ratio. No competitor branding. No "GESER UNTUK LANJUT" on CTA.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
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
| **MINI-HOOK** | 5-7 | 5/6 | SUDDEN CHANGE — split panel, extreme angle, color temperature shift, or unexpected composition. "Tapi tunggu..." energy | Extreme angle OR split panel OR dramatic zoom | Sudden shift — if previous slides were warm, add cool accent | Color temperature disruption — introduce unexpected contrast |
| **CLIMAX** | 8+ (Reveal) | 6/6 | Widest establishing shot OR most intimate close-up (contrast with body), peak saturation, biggest text, most shareable insight | Widest OR tightest (contrast with body slides) | Peak drama, 4:1, rim light dominant | Peak saturation, accent color dominant, full visual impact |
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
- [ ] Headline text specified in Bahasa Indonesia (or user-requested language)
- [ ] Accent words identified and color specified
- [ ] Category tag present
- [ ] Brand icon filename + position specified
- [ ] @handle watermark + opacity specified
- [ ] SWIPE FOR MORE present (or omitted for CTA)
- [ ] Gradient zone percentage matches slide type

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
- **Default text language = Bahasa Indonesia**
- API: `response_modalities=['TEXT', 'IMAGE']`, `image_size="4K"` (uppercase K)
- Aspect ratio set per target platform — see `references/platform-specs.md`
