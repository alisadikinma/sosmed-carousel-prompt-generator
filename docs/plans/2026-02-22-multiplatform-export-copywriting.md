> **For Claude:** REQUIRED SKILL: Use gaspol-execute to implement this plan.
> **CRITICAL:** This is a prompt-only plugin (all Markdown). No code, no tests, no build.
> Every phase = editing Markdown files. Verification = reading the file and confirming
> consistency with other reference docs. NEVER leave conflicting guidance across files.

## Goal

Upgrade the sosmed-carousel-prompt-generator plugin with three workstreams:
1. **Fix inconsistencies + strip video/DALL-E 3** — make this a pure Nano Banana Pro carousel IMAGE generator
2. **Merge RAG source content** — enrich references with missing content from `D:\Projects\image_video_generator_files\files\`
3. **Add multi-platform export + copywriting** — platform-specific prompts + captions for IG, TikTok, LinkedIn

## Architecture Context

From CLAUDE.md:
- Plugin: 1 skill (`skills/carousel-prompt-generator/SKILL.md`), 1 agent (`agents/carousel-prompt-generator.md`), 7→8 reference docs
- Prompt-only plugin — all Markdown, no code/tests/build
- Key concepts: WOW Quality Gate (8-point), Hard Rules, Creator Identity
- **SCOPE CHANGE:** Removing DALL-E 3, VEO 3.1, Sora 2 — plugin is IMAGE-ONLY via Nano Banana Pro
- **RAG SOURCE FILES** at `D:\Projects\image_video_generator_files\files\`:
  - `nano-banana-pro-reference.md` — failure modes, text rendering rules, character consistency, split-panel limits
  - `AI_Video_Production_Technical_Reference.md` — extended emotion table, DP signatures, film stocks, grading styles, volumetric lighting, surface effects, quality checklists
  - `Creator_Cinematography_and_Holiday_Production_Guide.md` — bald head lighting, glasses glare, Diwali/Valentine/Thanksgiving holidays, AI bias countermeasures, modular holiday template, 70/30 rule

## Tech Stack

Markdown only. No dependencies. Edits are surgical text changes across `.md` files.

## Data Integration Map

| Feature | Source | Target File | Exists? | Action |
|---------|--------|-------------|---------|--------|
| Remove DALL-E 3 | SKILL.md, agent.md, prompt-formulas.md, platform-specs.md | All 4 files | Yes (to remove) | Strip all DALL-E 3 references |
| Remove VEO/Sora/video | SKILL.md, agent.md, prompt-formulas.md, platform-specs.md, cinematography-lut.md | All 5 files | Yes (to remove) | Strip all video workflows, templates, specs |
| Nano Banana Pro enrichment | `nano-banana-pro-reference.md` | platform-specs.md | Partial | Merge: failure modes, text rendering rules, character consistency, split-panel |
| Extended cinematography | `AI_Video_Production_Technical_Reference.md` | cinematography-lut.md | Partial | Merge: DP signatures, extra film stocks, color grading styles, volumetric setups, surface effects |
| Extended emotions | `AI_Video_Production_Technical_Reference.md` Sec 1 | cinematography-lut.md | Partial | Merge: 2 missing emotions (Determination, Fear) + expression keyword phrases |
| Creator lighting specifics | `Creator_Cinematography_and_Holiday_Production_Guide.md` Sec 1-2 | creator-bible.md | Partial | Merge: bald head considerations, glasses glare, wardrobe×lighting, background by mood |
| Extra holidays | `Creator_Cinematography_and_Holiday_Production_Guide.md` Sec 3 | localization-id.md | Partial | Merge: Diwali, Valentine, Thanksgiving + AI bias countermeasures |
| Holiday template system | `Creator_Cinematography_and_Holiday_Production_Guide.md` Sec 5 | creator-bible.md | No | Merge: modular template, 70/30 rule, holiday film stock pairing |
| Quality checklists | `AI_Video_Production_Technical_Reference.md` Sec 12 | prompt-formulas.md | No | Merge: image prompt checklist, thumbnail checklist |
| Aspect ratio conflict | Hard-coded 9:16 everywhere | SKILL.md, agent.md, carousel-rebranding.md | Yes (wrong) | Make platform-specific |
| SWIPE FOR MORE conflict | creator-bible.md vs best-practices.md | creator-bible.md, carousel-rebranding.md | Yes (conflicting) | Align to slides 1-3 |
| Gradient zones | Scattered values | creator-bible.md | Inconsistent | Single source of truth table |
| Thinking mode | platform-specs.md | platform-specs.md | Unexplained | Explain or clarify |
| Localization orphaned | localization-id.md | SKILL.md, agent.md, localization-id.md | No trigger | Add integration points |
| Caption/copywriting | Brainstorm research | caption-copywriting.md (NEW) | No | Create new reference doc |
| Multi-platform workflow | Brainstorm design | SKILL.md, agent.md | No | Add new workflow + output format |
| Thumbnail formula | Missing from prompt-formulas.md | prompt-formulas.md | No | Add template (from RAG source Sec 11) |

---

# WORKSTREAM 1: Strip Video/DALL-E 3 + Fix Inconsistencies

---

## Phase A: Remove DALL-E 3 Entirely

**Estimated time:** 5 minutes

**Files:**
- Modify: `skills/carousel-prompt-generator/SKILL.md`
- Modify: `agents/carousel-prompt-generator.md`
- Modify: `references/prompt-formulas.md`
- Modify: `references/platform-specs.md`

**Steps:**

1. `SKILL.md` line 119: Remove `| DALL-E 3 (fallback)` from Platform Routing — becomes `Image: Nano Banana Pro (only)`

2. `agents/carousel-prompt-generator.md` line 105: Same removal in PLATFORM ROUTING

3. `references/prompt-formulas.md` lines 136-156: DELETE entire "DALL-E 3 (FALLBACK ONLY)" section (Section heading + When to Use + Template + Rules)

4. `references/platform-specs.md` lines 86-96: DELETE entire "4. DALL-E 3 (FALLBACK IMAGE)" section

5. `references/platform-specs.md` line 105: Remove `Nano unavailable? → DALL-E 3 fallback` from Decision Matrix

**Verification:**
- [ ] Zero mentions of "DALL-E 3" or "DALL-E" in any file across the entire plugin
- [ ] Platform Routing in SKILL.md shows only Nano Banana Pro
- [ ] Platform Routing in agent.md shows only Nano Banana Pro
- [ ] prompt-formulas.md has no DALL-E section
- [ ] platform-specs.md has no DALL-E section

---

## Phase B: Remove ALL Video (VEO 3.1 + Sora 2)

**Estimated time:** 8 minutes

**Files:**
- Modify: `skills/carousel-prompt-generator/SKILL.md`
- Modify: `agents/carousel-prompt-generator.md`
- Modify: `references/prompt-formulas.md`
- Modify: `references/platform-specs.md`
- Modify: `references/cinematography-lut.md`

**Steps:**

1. `SKILL.md`:
   - Line 82-83: Remove `Video Resolution | 1080p` and `Frame Rate | 24fps` from Fixed Technical Specs
   - Line 100-106: Remove "Workflow: Fresh Content Production" entirely (this is the video workflow with prompt pairs)
   - Line 120: Remove `Video: VEO 3.1 ... | Sora 2 ...` from Platform Routing
   - Lines 160-170: DELETE "Video Segment" output format section

2. `agents/carousel-prompt-generator.md`:
   - Line 14-15: Remove items 2 (`Video prompts (VEO 3.1 / Sora 2)`) from YOUR CAPABILITIES
   - Lines 67-76: Remove `Video Resolution | 1080p` and `Frame Rate | 24fps` from FIXED SPECS
   - Lines 102-112: Remove video entries from PLATFORM ROUTING
   - Lines 169-193: DELETE entire "WORKFLOW: FRESH VIDEO PRODUCTION" section
   - Lines 197-216: DELETE "Golden Rules" video sections (VEO 3.1 + Image→Video Split Rule)
   - Lines 206-210: Keep Image Prompts golden rules, remove Video Prompts golden rules

3. `references/prompt-formulas.md`:
   - Lines 1-9: Update Golden Rule — REMOVE Image→Video split rule (no longer applicable, image-only plugin)
   - Lines 63-106: DELETE entire "VEO 3.1 (PRIMARY VIDEO)" section
   - Lines 108-133: DELETE entire "Sora 2 (SECONDARY VIDEO)" section

4. `references/platform-specs.md`:
   - Lines 34-65: DELETE entire "2. VEO 3.1 (PRIMARY VIDEO)" section
   - Lines 66-85: DELETE entire "3. Sora 2 (SECONDARY VIDEO)" section
   - Lines 109-118: DELETE Video Platform decision matrix

5. `references/cinematography-lut.md`:
   - Lines 90-99: DELETE "Section 8: Transition Reference (VEO)" — no longer relevant

**Verification:**
- [ ] Zero mentions of "VEO", "Sora", "video prompt", "motion only", "lip-sync" in any plugin file
- [ ] No "Image→Video Split" rule anywhere (image-only plugin)
- [ ] No video workflows remain in SKILL.md or agent.md
- [ ] No video output format in SKILL.md or agent.md
- [ ] No video platform specs in platform-specs.md
- [ ] No VEO transition table in cinematography-lut.md
- [ ] prompt-formulas.md is Nano Banana Pro only
- [ ] platform-specs.md is Nano Banana Pro only

---

## Phase C: Fix Aspect Ratio — Make Platform-Specific

**Estimated time:** 5 minutes

**Files:**
- Modify: `skills/carousel-prompt-generator/SKILL.md`
- Modify: `agents/carousel-prompt-generator.md`
- Modify: `references/carousel-rebranding.md`

**Steps:**

1. `SKILL.md` Hard Rule #8: Change `Aspect ratio = 9:16 vertical for all social content` to:
   `Aspect ratio = platform-specific. IG Feed/LinkedIn: 4:5, TikTok/Reels: 9:16 (see Platform Routing)`

2. `SKILL.md` Fixed Technical Specs: Change `Aspect Ratio | 9:16 vertical` to `Aspect Ratio | Platform-specific (see Platform Routing)`

3. `SKILL.md` Platform Routing (after removing video): Replace with:
   ```
   Image Generation: Nano Banana Pro (exclusive)

   Carousel Aspect Ratios:
     Instagram Feed → 4:5 (1080x1350)
     Instagram Reels → 9:16 (1080x1920)
     TikTok → 9:16 (1080x1920)
     LinkedIn → 4:5 (1080x1350) or 1:1 (1080x1080)
     Default (unspecified) → 4:5 (1080x1350)
   ```

4. `agents/carousel-prompt-generator.md`: Apply identical changes to Hard Rule #8, FIXED SPECS, and PLATFORM ROUTING

5. `references/carousel-rebranding.md`: Change all hard-coded `9:16 vertical aspect` (lines 53, 68, 84, 101) to `[PLATFORM ASPECT] aspect` and add note: "Set per target platform — see platform-specs.md"

6. `references/carousel-rebranding.md` checklist (line 135): Change `9:16 aspect ratio for all slides` to `Aspect ratio matches target platform for all slides`

**Verification:**
- [ ] No remaining hard-coded "9:16 for all" in SKILL.md, agent.md, or carousel-rebranding.md
- [ ] Platform Routing table is the single source of truth for aspect ratios
- [ ] Default aspect is 4:5 (most common: IG feed + LinkedIn)

---

## Phase D: Fix SWIPE FOR MORE Conflict

**Estimated time:** 2 minutes

**Files:**
- Modify: `references/creator-bible.md`
- Modify: `references/carousel-rebranding.md`

**Steps:**

1. `creator-bible.md` line 38: Change `"SWIPE FOR MORE >" on every slide except CTA` to `"SWIPE FOR MORE >" on slides 1-3 only (20-30% more engagement vs all slides)`

2. `carousel-rebranding.md` line 117: Change `Bottom center (all slides except CTA)` to `Bottom center (slides 1-3 only)`

3. `carousel-rebranding.md` checklist line ~133: Change `SWIPE FOR MORE on all slides except CTA` to `SWIPE FOR MORE on slides 1-3 only`

**Verification:**
- [ ] All files say "slides 1-3 only" — consistent with carousel-best-practices.md line 64

---

## Phase E: Fix Text Gradient Zones — Single Source of Truth

**Estimated time:** 3 minutes

**Files:**
- Modify: `references/creator-bible.md`

**Steps:**

1. Add after Section 5 (Face Allocation, line 91):

   ```markdown
   ## 5b. Text Gradient Zone Allocation

   | Slide Type | Gradient Zone | Rationale |
   |------------|---------------|-----------|
   | Hook | Bottom 40% | Large headline + branding + SWIPE |
   | Content B-Roll | Bottom 35% | Medium headline + accent word |
   | Split-Panel | Bottom 30% | Smaller text, image content takes priority |
   | CTA | Bottom 40% | Social handles + tagline + branding |
   | Thumbnail | Bottom 25% | Minimal text, face dominates |

   This table is the single source of truth. All prompt templates reference these values.
   ```

**Verification:**
- [ ] creator-bible.md has authoritative gradient table
- [ ] Values match carousel-rebranding.md templates (Hook 40%, B-Roll 35%, Split 30%, CTA 40%)
- [ ] prompt-formulas.md B-Roll template says 35% — consistent

---

## Phase F: Fix "Thinking Mode" Reference

**Estimated time:** 1 minute

**Files:**
- Modify: `references/platform-specs.md`

**Steps:**

1. Change `Complex composition? → Nano Banana Pro (thinking mode)` to:
   `Complex composition? → Nano Banana Pro (extend prompt to 120-200 words with detailed spatial descriptions)`

**Verification:**
- [ ] No unexplained "thinking mode" — replacement is actionable

---

## Phase G: Fix Localization Orphaned

**Estimated time:** 3 minutes

**Files:**
- Modify: `skills/carousel-prompt-generator/SKILL.md`
- Modify: `agents/carousel-prompt-generator.md`
- Modify: `references/localization-id.md`

**Steps:**

1. `SKILL.md`: Add after Hard Rules section:
   ```markdown
   ## Localization Trigger

   If user requests Indonesian content, speaks Bahasa, or targets Indonesian audience:
   1. Read `references/localization-id.md` BEFORE generating prompts
   2. Apply setting conversions (Times Square → Bundaran HI, etc.)
   3. Apply language style (casual Gen Z Bahasa + English mix)
   4. Apply holiday adaptations if seasonal content
   5. Apply Bahasa caption rules from `references/caption-copywriting.md`
   ```

2. `agents/carousel-prompt-generator.md`: Add same trigger after HARD RULES section

3. `references/localization-id.md`: Add Section 6 at end:
   ```markdown
   ## 6. Integration Points

   Triggered when: user speaks Bahasa, targets Indonesia, or requests holiday content (Imlek/Lebaran/Natal).

   Cross-references:
   - Captions → `references/caption-copywriting.md` (Bahasa section)
   - Settings → apply to ALL prompt templates
   - Visuals → tropical, no snow, local landmarks
   ```

**Verification:**
- [ ] SKILL.md and agent.md have localization trigger rules
- [ ] localization-id.md has integration points with cross-references

---

# WORKSTREAM 2: Merge RAG Source Content

---

## Phase H: Enrich platform-specs.md with Nano Banana Pro Details

**Estimated time:** 5 minutes

**Files:**
- Modify: `references/platform-specs.md`
- Source: `D:\Projects\image_video_generator_files\files\nano-banana-pro-reference.md`

**Steps:**

After stripping DALL-E 3 and video sections (Phases A-B), platform-specs.md will be much shorter. Add the following missing content from the RAG source:

1. Add to Nano Banana Pro section — **Model IDs**:
   ```
   | Model IDs | Pro: `gemini-3-pro-image-preview`, Fast: `gemini-2.5-flash-image` |
   | Generation Speed | ~10-30s (4K: up to 170s peak hours) |
   ```

2. Add new section: **Text Rendering Rules** (from RAG source Sec 4):
   ```markdown
   ### Text Rendering (5 Rules)
   1. Wrap exact text in quotes: `"AI Innovation Conference 2025"`
   2. Describe fonts, don't name them: "clean bold sans-serif" NOT "Helvetica"
   3. Multi-line → explicit hierarchy: Line 1 (large bold), Line 2 (medium), Line 3 (small)
   4. Use 4K resolution for text-heavy images (critical for legibility)
   5. Colored text: "The text 'BERLIN' in alternating blue, red, white, black letters"
   Warning: ~20-25% failure rate for complex text — always verify output manually.
   ```

3. Add new section: **Character Consistency** (from RAG source Sec 3):
   ```markdown
   ### Character Consistency Tips
   - Practical sweet spot: 3-5 reference images (14 supported, but 6+ = diminishing returns)
   - Repeat defining traits verbatim in every prompt
   - Change only ONE variable per generation (background OR outfit OR lighting)
   - Re-anchor every 3-4 generations by re-uploading reference
   - Use targeted edits: "change background to forest" — NOT full regeneration
   - Multi-character: identify explicitly per reference image
   ```

4. Add new section: **Split-Panel Limits** (from RAG source Sec 5):
   ```markdown
   ### Split-Panel Compositions
   - 4 panels = reliable
   - 8+ panels = unreliable → generate individually + composite
   - Carousels: generate each slide separately with consistent character references
   - Aspect guidance: side-by-side → 16:9 or 3:2, stacked → 9:16, social → 4:5 or 9:16
   ```

5. Add new section: **Failure Modes** (from RAG source Sec 6):
   ```markdown
   ### Failure Modes & Fixes

   | Problem | Cause | Fix |
   |---------|-------|-----|
   | Text-only response (no image) | Missing `responseModalities` | Add `['TEXT', 'IMAGE']` to config |
   | Wrong aspect ratio | Gemini App bug | Use API `aspect_ratio` param |
   | Silent quality downgrade | Daily quota exhausted | Switch session / check quota |
   | 4K ignored in editing | API bug during image-to-image | Export → re-import at high res |
   | Content filter false positive | Trigger words | Rephrase, retry |
   | 4K timeout / 503 error | Peak hours | Exponential backoff: 60s initial wait |
   ```

6. Add to existing Key Rules or Workflow section: **Iteration best practice**:
   `Iterate, don't regenerate — if 80% correct, use targeted edit prompt instead of full regeneration.`

**Verification:**
- [ ] platform-specs.md has model IDs, generation speed
- [ ] Text rendering 5 rules present
- [ ] Character consistency tips present
- [ ] Split-panel limits present
- [ ] Failure modes table present
- [ ] All content from nano-banana-pro-reference.md merged

---

## Phase I: Enrich cinematography-lut.md with Extended Content

**Estimated time:** 8 minutes

**Files:**
- Modify: `references/cinematography-lut.md`
- Source: `D:\Projects\image_video_generator_files\files\AI_Video_Production_Technical_Reference.md`

**Steps:**

1. **Section 1 (Emotion table)**: Add 2 missing emotions from RAG Sec 1.1:
   - `Determination | Set jaw, focused eyes, slight brow furrow | Forward lean, squared stance | Strong key, minimal fill`
   - `Fear/Concern | Wide eyes, tense lips, raised inner brows | Pulled-back, defensive posture | Underlit, cold 6500K+`

2. **Add new Section 1b: Expression Keyword Phrases** (from RAG Sec 1.2):
   ```markdown
   ## 1b. Expression Keyword Phrases for Prompts

   **Positive:** "bright animated eyes, genuine warm smile, lifted eyebrows, energetic presence"
   **Neutral:** "steady unwavering gaze, composed expression, subtle knowing smile"
   **Tension:** "intense fixed gaze, clenched jaw, rigid shoulders, tight lips"
   **Awe:** "softened wide eyes, slightly parted lips, upward gaze, open relaxed posture"
   ```

3. **Section 2 (Lighting)**: Add missing patterns from RAG Sec 3.1:
   - `Broad | Lit side toward camera | Wider appearance | "Broad lighting, open"`
   - `Short | Shadow side toward camera | Slimming, moody | "Short lighting, sculptural"`

4. **Section 2 (Ratios)**: Add `16:1 | Extreme | Horror, extreme drama`

5. **Section 3 (Color Temp)**: Add missing values from RAG Sec 3.3:
   - `Candlelight | 1900K | Deep warm orange | "candlelit 1900K warm glow"`
   - `Tungsten bulb | 2700K | Warm amber | "tungsten 2700K amber"`
   - `Shade | 7500K | Cool blue | "open shade 7500K cool"`
   - `Blue hour | 9000-12000K | Twilight blue | "blue hour 9000K mystery"`

6. **Add new section: Cinematographer Signatures** (from RAG Sec 3.4):
   ```markdown
   ## Cinematographer Signatures

   | DP | Style | Best For | Prompt |
   |----|-------|----------|--------|
   | Roger Deakins | Motivated practical sources, atmospheric haze | Natural drama, sci-fi | "Roger Deakins motivated naturalistic lighting" |
   | Greig Fraser | Desaturated, wet surfaces, LED volume | Gritty noir, epic | "Greig Fraser muted tones, wet reflections" |
   | Hoyte van Hoytema | Shallow DOF T2.0, underexposure, grain | Epic intimate | "Van Hoytema shallow focus, organic grain" |
   | Bradford Young | Subtractive "black first", heavy practicals | Meditative, emotional | "Bradford Young soft practical sources" |
   | Emmanuel Lubezki | Natural/magic hour light, long takes, wide | Poetic, immersive | "Lubezki natural light magic hour" |
   ```

7. **Section 5 (Film Stocks)**: Add missing stocks from RAG Sec 5.1:
   - `Kodak Portra 800 | Versatile, slightly more grain | Daylight, warmth | "Portra 800 natural warmth"`
   - `Kodak Vision3 250D | Crisp, accurate | Daylight scenes | "Kodak 250D daylight crisp"`
   - `Kodak Tri-X 400 | High contrast B&W | Dramatic B&W | "Tri-X black and white contrasty"`
   - `Fujifilm Velvia 50 | Extreme saturation | Hyper-vivid | "Velvia hyper-saturated"`

8. **Add new section: Color Grading Styles** (from RAG Sec 5.2):
   ```markdown
   ## Color Grading Styles

   | Style | Mood | Prompt Phrase |
   |-------|------|---------------|
   | Teal & Orange | Blockbuster energy | "teal and orange Hollywood grade" |
   | Bleach Bypass | Gritty, desaturated | "bleach bypass silver retention" |
   | Golden Hour | Romantic, nostalgic | "golden hour warmth amber" |
   | Blue Hour | Mysterious, ethereal | "blue hour cool twilight" |
   | Muted/Desaturated | Somber, realistic | "muted desaturated palette" |
   | Cross-Process | Retro, stylized | "cross-processed retro" |
   ```

9. **Section 6 (Atmosphere)**: Add from RAG Sec 6:
   - Missing types: `Fog | Thick, mysterious | "thick fog mysterious"`, `Ground fog | Floor mist | "ground fog low mist"`, `Smoke | Noir, dramatic | "wispy smoke noir atmosphere"`, `Rain | Wet, moody | "rain backlit streaking"`
   - Add Volumetric Lighting Setups: god rays, window blinds, backlit particles, smoke shafts
   - Add Surface Effects: wet streets, puddle reflections, frost, steam

**Verification:**
- [ ] 11 emotions in table (was 9)
- [ ] Expression keyword phrases section added
- [ ] 7 lighting patterns (added Broad + Short)
- [ ] 4 contrast ratios (added 16:1)
- [ ] 8 color temperatures (added candlelight, tungsten bulb, shade, blue hour)
- [ ] DP signatures table with 5 cinematographers
- [ ] 8 film stocks (added Portra 800, Vision3 250D, Tri-X, Velvia)
- [ ] Color grading styles table
- [ ] Extended atmosphere: fog, ground fog, smoke, rain + volumetric setups + surface effects

---

## Phase J: Enrich creator-bible.md with Creator-Specific Lighting + Holidays

**Estimated time:** 8 minutes

**Files:**
- Modify: `references/creator-bible.md`
- Source: `D:\Projects\image_video_generator_files\files\Creator_Cinematography_and_Holiday_Production_Guide.md`

**Steps:**

1. **Section 7 (Lighting)**: Replace generic notes with creator-specific considerations from RAG Sec 1.1:
   ```markdown
   ## 7. Lighting for Creator's Features

   Customize based on creator's physical features:

   | Attribute | Cinematography Impact |
   |-----------|----------------------|
   | Bald head | Avoid harsh overhead → soft angled key, flag from above if needed |
   | Round face | Short lighting more slimming; Rembrandt for authority |
   | Glasses | Key at 30-45° to avoid glare; slight head tilt eliminates reflections |
   | Warm skin tone | Responds well to 3200K tungsten; avoid overly cool lighting |
   | Dark eyes | Need adequate light for catchlights — ensure visible for life/connection |
   ```

2. Add new section: **Wardrobe × Lighting** (from RAG Sec 1.3):
   ```markdown
   ## 7b. Wardrobe × Lighting

   | Wardrobe | Lighting Note |
   |----------|--------------|
   | Navy blazer | Absorbs well, good skin contrast — works with all setups |
   | White shirt | Can blow out — reduce fill or flag shirt area |
   | Dark henley/polo | Needs edge light for separation on dark backgrounds |
   ```

3. Add new section: **Background by Mood** (from RAG Sec 1.4):
   ```markdown
   ## 7c. Background by Mood

   | Mood | Background | Depth | Color Relationship |
   |------|-----------|-------|--------------------|
   | Professional authority | Dark, minimal | Deep bokeh f/1.8-2.8 | Contrast with skin |
   | Approachable teaching | Office context | Moderate blur f/4 | Complementary |
   | Tech credibility | Monitor/screen elements | Soft glow bokeh | Cool BG, warm face |
   | Casual connection | Home/lifestyle hint | Moderate blur | Warm, inviting |
   ```

4. Add new section: **Holiday Template System** (from RAG Sec 4-5):
   ```markdown
   ## 8. Holiday Content Production

   ### 70/30 Rule
   Holiday atmosphere 70-80% of composition, professional/tech identity 20-30%.

   ### Holiday Film Stock Pairing
   | Holiday | Best Film Stock | Reason |
   |---------|----------------|--------|
   | Christmas / Valentine's | Kodak Portra 400 | Warm skin, nostalgic |
   | Chinese New Year / Imlek | Kodak Ektar 100 | Vivid saturated reds/golds |
   | Eid / Lebaran | Fujifilm Pro 400H | Cool greens, soft pastels |
   | Diwali | Kodak Vision3 500T | Tungsten drama, rich blacks |
   | Thanksgiving | Kodak Portra 400 | Warm earth tones |

   Cross-reference: See `references/localization-id.md` for Indonesian holiday specifics.
   ```

**Verification:**
- [ ] Creator-specific lighting table replaces generic notes
- [ ] Wardrobe × lighting section present
- [ ] Background by mood table present
- [ ] Holiday template system with 70/30 rule and film stock pairing
- [ ] Cross-reference to localization-id.md for holiday specifics

---

## Phase K: Enrich localization-id.md with Extra Holidays + AI Bias

**Estimated time:** 5 minutes

**Files:**
- Modify: `references/localization-id.md`
- Source: `D:\Projects\image_video_generator_files\files\Creator_Cinematography_and_Holiday_Production_Guide.md`

**Steps:**

1. **Section 4 (Holidays)**: Enrich existing Imlek, Lebaran, Natal with RAG color palettes and symbols:
   - Imlek: Add `Primary colors: Red #C8102E, Gold #CC9900` + `Barongsai on poles, dodol keranjang, kebaya encim, Cap Go Meh Singkawang, Sam Poo Kong Temple`
   - Lebaran: Add `Primary colors: Islamic green #009A0A, White, Gold #CFB53B` + `Greeting: "Selamat Hari Raya Idul Fitri" / "Mohon Maaf Lahir Batin"` + `Takbiran night with bedug drums`
   - Natal: Add `Primary colors: Red #BB2528, Evergreen #165B33, Gold #F8B229` + `Wayang kulit Nativity (Yogyakarta), klapertart`

2. Add 2 NEW holidays from RAG Sec 3.1:
   ```markdown
   ### Diwali
   | Element | Specification |
   |---------|--------------|
   | Primary colors | Deep red #891E1B, Marigold #F79E1F, Gold #FFDF00, Saffron |
   | Key symbols | Diyas (oil lamps), rangoli, marigold garlands, fireworks |
   | Lighting | Warm amber diya glow, festival sparkle |
   | Prompt keywords | "warm golden diya glow, oil lamp lighting, amber illumination" |

   ### Valentine's Day
   | Element | Specification |
   |---------|--------------|
   | Colors | Wine #5E081E, Rose pink #E24767, Blush #E4CDD3, Soft gold #D4AF37 |
   | Lighting | Soft romantic, rose-tinted, candlelight |
   | Prompt keywords | "soft romantic lighting, rose-tinted warmth, intimate candlelight" |
   ```

3. Add new Section 5b: **AI Bias Countermeasures** (from RAG Sec 6):
   ```markdown
   ## 5b. AI Bias Countermeasures

   | Bias Pattern | Countermeasure |
   |-------------|----------------|
   | Indonesian women → stereotypical headscarves | Include diverse appearance descriptors |
   | Generic "Chinatown" for Imlek | Use Indonesian-specific landmarks (Sam Poo Kong, etc.) |
   | Middle Eastern mosque for Lebaran | Specify multi-tiered roof architecture |
   | Racial homogenization | Add specific ethnic/cultural context in prompt |

   Rule: Always include geographic + cultural context. "Indonesian Lebaran in Javanese setting" NOT "Eid celebration."
   ```

**Verification:**
- [ ] Imlek, Lebaran, Natal enriched with color hex codes and extra details
- [ ] Diwali and Valentine's Day holidays added
- [ ] AI bias countermeasures table present
- [ ] All holidays have color palettes, symbols, lighting keywords, and prompt keywords

---

## Phase L: Add Thumbnail + Quality Checklists to prompt-formulas.md

**Estimated time:** 5 minutes

**Files:**
- Modify: `references/prompt-formulas.md`
- Source: `D:\Projects\image_video_generator_files\files\AI_Video_Production_Technical_Reference.md` Sec 11 + 12

**Steps:**

1. Add **Thumbnail template** after B-Roll template (using RAG Sec 11.3 structure, simplified):
   ```markdown
   ### Template — Thumbnail
   ```
   A photorealistic cinematic tight close-up thumbnail composition:
   [CREATOR DESCRIPTION VERBATIM]. [EXAGGERATED EXPRESSION — curiosity gap].
   Face occupies 50-60% of frame, positioned [left/right/center].
   [TOPIC VISUAL] visible beside/behind creator.

   Shot on 85mm f/1.8, tight framing, slight dutch tilt (5-10°).
   Rembrandt or Split lighting 4:1-6:1 ratio, mixed warm/cool Kelvin.
   Strong rim light separating creator from background.
   Kodak Portra 400, HIGH SATURATION, boosted contrast.

   Bottom 25% dark gradient zone for text overlay.
   Text-safe zone: [position] for title.
   [PLATFORM ASPECT] aspect. No text, no watermarks.
   Using facial identity from reference image: [face-ref.png].
   ```

2. Add **Expression × Topic combinations** (from RAG Sec 11.4):
   ```markdown
   ### Thumbnail Expression × Topic Combinations
   | Topic | Expression | Topic Visual |
   |-------|-----------|-------------|
   | AI replacing jobs | Shock + concern | AI/robot silhouette, code |
   | Tech breakthrough | Awe + excitement | Glowing tech, data viz |
   | Warning/danger | Serious + urgent | Warning symbols, red accents |
   | Secret/revelation | Knowing smirk + intrigue | Hidden/revealed element |
   | Challenge/debate | Confident + confrontational | VS graphic, split visual |
   | Money/opportunity | Excited + eager | Dollar signs, charts up |
   ```

3. Add **Image Prompt Quality Checklist** (from RAG Sec 12.1, adapted for image-only):
   ```markdown
   ## Image Prompt Checklist

   Before finalizing each prompt:
   - [ ] Shot type specified (CU, MCU, MS, etc.)
   - [ ] Lens specified (mm + aperture)
   - [ ] Lighting pattern named + ratio
   - [ ] Color temperature in Kelvin
   - [ ] Film stock named
   - [ ] Atmosphere specified (even if "clean")
   - [ ] Aspect ratio per target platform
   - [ ] Face reference included (if creator)
   - [ ] Wardrobe specified (if creator)
   - [ ] Text overlay space noted (gradient zone %)
   - [ ] No text baked into image prompt
   - [ ] Negative constraints at end
   ```

**Verification:**
- [ ] Thumbnail template with expression × topic table
- [ ] Image prompt quality checklist at end of file
- [ ] Template references correct gradient zone (25%) per creator-bible.md
- [ ] No video references in any added content

---

# WORKSTREAM 3: Multi-Platform Export + Copywriting

---

## Phase M: Create `references/caption-copywriting.md`

**Estimated time:** 10 minutes

**Files:**
- Create: `references/caption-copywriting.md`

**Steps:**

Create with FULL content from brainstorm (already detailed in conversation). Include all 7 sections:
1. Platform Character Limits table (IG 2200, TikTok 4000, LinkedIn 3000)
2. Caption Hook Rules (truncation points)
3. Hashtag Strategy (5-hashtag era: 2 broad + 2 niche + 1 branded)
4. Caption Formulas per platform (IG, TikTok, LinkedIn)
5. Character Budget Templates
6. Hook Examples by Platform (5 per platform)
7. Bahasa Indonesia Caption Conventions

**Verification:**
- [ ] File created at `references/caption-copywriting.md`
- [ ] All 7 sections present with complete content
- [ ] Hashtag rules reflect Dec 2025 (IG) + Aug 2025 (TikTok) policy

---

## Phase N: Add Multi-Platform Export Workflow + Output Format

**Estimated time:** 5 minutes

**Files:**
- Modify: `skills/carousel-prompt-generator/SKILL.md`
- Modify: `agents/carousel-prompt-generator.md`

**Steps:**

1. Both files: Add `caption-copywriting.md` to reference files table

2. `SKILL.md`: Add "Workflow: Multi-Platform Export" (8-step workflow from brainstorm)

3. `SKILL.md`: Add Multi-Platform Export output format (IG + TikTok + LinkedIn sections with caption blocks)

4. `agents/carousel-prompt-generator.md`: Add capabilities #5 (multi-platform export) and #6 (caption copywriting)

5. `agents/carousel-prompt-generator.md`: Add "WORKFLOW: MULTI-PLATFORM EXPORT" (4-step version)

**Verification:**
- [ ] Both files reference caption-copywriting.md
- [ ] Multi-platform workflow present in both files
- [ ] Output format includes caption block per platform with character count

---

## Phase O: Update carousel-best-practices.md Hashtag Counts

**Estimated time:** 2 minutes

**Files:**
- Modify: `references/carousel-best-practices.md`

**Steps:**

1. IG caption strategy (line 80): `5-10 relevant hashtags` → `5 hashtags max (see caption-copywriting.md)`
2. TikTok caption strategy (line 127): `3-5 hashtags` → `exactly 5 hashtags (2 broad + 2 niche + 1 branded)`
3. LinkedIn caption strategy (line 174): `No hashtags needed` → `3-5 hashtags at END of post`
4. Engagement checklist (line 288): `Hashtags researched` → `Hashtags: max 5 for IG/TikTok, 3-5 for LinkedIn`

**Verification:**
- [ ] All hashtag counts consistent with caption-copywriting.md

---

## Phase P: Update CLAUDE.md + README.md

**Estimated time:** 5 minutes

**Files:**
- Modify: `CLAUDE.md`
- Modify: `README.md`

**Steps:**

1. `CLAUDE.md`:
   - Reference table: add `caption-copywriting.md`, update count to 8
   - Key Concepts: remove Image→Video Split, add Multi-Platform Export + 5-Hashtag Era
   - Update "Default specs" to note platform-specific aspect ratios
   - Note: "Image-only plugin (Nano Banana Pro). No video, no DALL-E 3."

2. `README.md`:
   - Update description: image-only plugin (remove video references)
   - Add caption-copywriting.md to reference docs table
   - Add "Caption Copywriting" to Capabilities
   - Add "Multi-Platform Export" to Capabilities
   - Update workflow diagram (remove video, add caption generation)
   - Update project structure tree
   - Update Hard Rules table (platform-specific aspect ratio)
   - Remove Image→Video Split from The Solution section
   - Update Platform Routing section (Nano Banana Pro only)
   - Update all "7 reference docs" → "8 reference docs"

**Verification:**
- [ ] CLAUDE.md reflects image-only plugin with 8 reference docs
- [ ] README.md has no DALL-E 3, VEO, Sora, or video references
- [ ] README.md documents caption copywriting + multi-platform export

---

## Phase Q: Final Cross-File Consistency Check

**Estimated time:** 5 minutes

**Files:**
- Read: ALL files in plugin

**Steps:**

1. Grep entire plugin for:
   - `DALL-E` → must be ZERO hits
   - `VEO` → must be ZERO hits
   - `Sora` → must be ZERO hits
   - `video prompt` / `VIDEO PROMPT` → must be ZERO hits
   - `motion only` / `MOTION ONLY` → must be ZERO hits
   - `lip-sync` → must be ZERO hits
   - `9:16 vertical for all` → must be ZERO hits
   - `30 hashtag` → must be ZERO hits

2. Verify cross-file consistency:
   - SWIPE: all files say "slides 1-3 only"
   - Gradient zones: all templates match creator-bible.md table
   - Aspect ratios: all templates say `[PLATFORM ASPECT]` or reference Platform Routing
   - caption-copywriting.md referenced in: SKILL.md, agent.md, carousel-best-practices.md, localization-id.md
   - localization-id.md has integration points
   - Thumbnail template exists in prompt-formulas.md with expression × topic table

3. Count reference docs: must be 8 everywhere

**Verification:**
- [ ] ZERO forbidden terms across all files
- [ ] Zero cross-file contradictions
- [ ] 8 reference docs consistently stated
- [ ] CLAUDE.md matches actual file state
- [ ] README.md accurately describes the plugin
