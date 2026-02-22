---
name: carousel-prompt-generator
description: Cinematic AI image prompt generator for social media carousel content. Use whenever the user needs carousel image prompts, thumbnail prompts, carousel rebranding, or any visual content production for social media. Triggers on carousel, thumbnail, rebrand, image generation, Nano Banana Pro, visual content, AI image, buat prompt, bikinin gambar, or any request to create cinematic AI-generated visuals.
---

# Carousel Prompt Generator

Cinematic AI image prompt generator for social media carousel content.
Every frame must trigger visceral "WOW" — the reaction that stops scrolling.

## How to Use This Skill

### As Subagent (Recommended for batch work)
Copy `agents/carousel-prompt-generator.md` to your project's `.claude/agents/` directory:

```bash
# One-time setup after installing skill
mkdir -p .claude/agents
cp <skill-path>/agents/carousel-prompt-generator.md .claude/agents/
cp <skill-path>/references/ ./references/ -r
```

Then invoke via Task tool:
```
Task(agent="carousel-prompt-generator", prompt="Generate carousel prompts for topic X...")
```

### As Inline Skill (For single prompts)
Claude reads this SKILL.md directly and follows the workflow below.

---

## Reference Files (Read On-Demand)

| Task | Read First |
|------|-----------|
| ANY prompt | `references/creator-bible.md` (ALWAYS) |
| Carousel rebranding | + `references/carousel-rebranding.md` |
| Platform choice / aspect ratio | + `references/platform-specs.md` |
| Lighting/lens lookup | + `references/cinematography-lut.md` |
| Prompt templates | + `references/prompt-formulas.md` |
| Indonesian content | + `references/localization-id.md` |
| Carousel best practices | + `references/carousel-best-practices.md` |
| Caption/copywriting | + `references/caption-copywriting.md` |

---

## Creator Identity (USER-PROVIDED)

The user must supply their creator identity for personalized prompts. If not provided, ask for:

1. **Physical description** (age, gender, ethnicity, distinguishing features)
2. **Face reference image** filename (for AI face generation)
3. **Brand handle** (e.g., @username)
4. **Brand icon/logo** filename (for carousel branding)
5. **Accent color** (default: Golden Yellow #F5A623)

Use the creator description VERBATIM in every creator-facing prompt.

---

## Hard Rules (NON-NEGOTIABLE)

1. NEVER third-party branding (no badges, logos, other handles)
2. ALWAYS include user's brand icon + handle on every slide
3. Creator face ONLY on: Hook, CTA, Loop-end, Thumbnail
4. B-roll / content slides = NO creator face
5. Text = post-production only — clean images with dark gradient text zones
6. Accent color = user's brand color (default: Golden Yellow #F5A623)
7. Default film stock = Kodak Portra 400 (warm golden, NOT cold)
8. Aspect ratio = platform-specific. IG Feed/LinkedIn: 4:5, TikTok/Reels: 9:16 (see Platform Routing)
9. Image size = 4K via Nano Banana Pro
10. All prompts must pass WOW minimum score

---

## Localization Trigger

If the user requests Indonesian content, speaks Bahasa, or targets Indonesian audience:
1. Read `references/localization-id.md` BEFORE generating any prompts
2. Apply setting conversions (Times Square → Bundaran HI, etc.)
3. Apply language style (casual Gen Z Bahasa + English mix)
4. Apply holiday adaptations if seasonal content
5. Apply Bahasa caption rules from `references/caption-copywriting.md`

---

## Fixed Technical Specs

| Parameter | Value |
|-----------|-------|
| Image Platform | Nano Banana Pro (exclusive) |
| Image Resolution | 4K |
| Aspect Ratio | Platform-specific (see Platform Routing) |
| Default Film Stock | Kodak Portra 400 |
| Default Grade | Warm golden amber |
| Accent Color | User-defined (default: #F5A623) |
| Primary Text | White #FFFFFF |

---

## Workflow: Carousel Rebranding

1. ANALYZE source slides — extract topic, data, visual concept per slide
2. IDENTIFY third-party elements to REMOVE
3. CONVERT style to user's brand palette (warm, cinematic)
4. GENERATE Nano Banana Pro prompt per slide (read `references/carousel-rebranding.md`)
5. OUTPUT text overlay guide per slide (post-production)
6. VERIFY continuity checklist

## Workflow: Fresh Carousel Production

1. ANALYZE brief/topic — identify key messages, slide structure, emotions
2. DETERMINE target platform and set aspect ratio (read `references/platform-specs.md`)
3. GENERATE Nano Banana Pro prompt per slide
4. SCORE each prompt via WOW gate
5. OUTPUT continuity checklist

## Workflow: Thumbnail Generation

1. READ `references/creator-bible.md` for expression + lighting setup
2. GENERATE prompt with: creator face 50-60%, exaggerated emotion, topic visual, text-safe zone
3. SCORE WOW minimum 4/8

## Workflow: Multi-Platform Export

Generate platform-specific carousel prompts AND captions from a single brief.

1. ANALYZE input brief/topic
2. READ `references/platform-specs.md` + `references/carousel-best-practices.md` + `references/caption-copywriting.md`
3. For EACH target platform, set:
   - Aspect ratio: IG Feed 4:5, TikTok 9:16, LinkedIn 4:5
   - Slide count: IG 7-10, TikTok 5-7, LinkedIn 5-8
   - Content tone: IG visual-first, TikTok trend-driven, LinkedIn insight-led
4. GENERATE full prompt set per platform (all slides)
5. GENERATE caption per platform (hook + body + CTA + hashtags)
6. SCORE each prompt via WOW gate
7. VERIFY character limits: IG ≤2200, TikTok ≤4000, LinkedIn ≤3000
8. OUTPUT all variants grouped by platform

---

## Platform Routing

```
Image Generation: Nano Banana Pro (exclusive)

Carousel Aspect Ratios:
  Instagram Feed → 4:5 (1080x1350)
  Instagram Reels → 9:16 (1080x1920)
  TikTok → 9:16 (1080x1920)
  LinkedIn → 4:5 (1080x1350) or 1:1 (1080x1080)
  Default (unspecified) → 4:5 (1080x1350)
```

---

## WOW Quality Gate

Score 1 point each (max 8):
1. LIGHTING DRAMA — Rembrandt/chiaroscuro, not flat
2. DEPTH LAYERS — Foreground + subject + bokeh
3. ATMOSPHERE — Haze, particles, volumetric
4. COLOR CONTRAST — Warm-cool tension, accent color highlights
5. EMOTIONAL PEAK — Expression at max intensity
6. CAMERA INTENTION — Every angle has purpose
7. TEXTURE REALISM — Pores, fabric, surface detail
8. CINEMATIC REF — Film stock or DP reference

Minimums: Hook 5+, CTA 4+, Thumbnail 4+, Body 3+, B-Roll 3+.
Below minimum = REVISE before output.

---

## Output Format

### Carousel Slide
```
## Slide [N]: [Topic]
Type: Hook / Content / CTA | Creator Face: YES/NO | Platform: Nano Banana Pro

### Nano Banana Pro Prompt
[full natural-language prompt, 40-120 words]

### Text Overlay (Post-Production)
- Headline: "[TEXT]" — White bold condensed ALL CAPS
- Accent: "[WORD]" — [User's accent color]
- Branding: [user's brand icon] [position] + [user's handle]
- SWIPE FOR MORE: slides 1-3 only
### WOW: [N]/8
```

### Multi-Platform Export
```
# Multi-Platform Export: [Topic]

## Instagram Carousel (4:5 — 1080x1350, [N] slides)

[Slide 1-N prompts in standard Carousel Slide format]

### Instagram Caption ([N]/2,200 chars)
**Hook (≤125 chars):**
[Hook text]

**Body:**
[Body text]

**CTA:**
[CTA text]

**Hashtags (5):**
#tag1 #tag2 #tag3 #tag4 #tag5

---

## TikTok Carousel (9:16 — 1080x1920, [N] slides)

[Slide 1-N prompts in standard Carousel Slide format]

### TikTok Caption ([N]/4,000 chars)
**Hook (≤100 chars):**
[Hook text — casual Gen Z tone]

**Body:**
[SEO-optimized body text]

**CTA:**
[CTA text]

**Hashtags (5):**
#tag1 #tag2 #tag3 #tag4 #tag5

---

## LinkedIn Carousel (4:5 — 1080x1350, [N] slides)

[Slide 1-N prompts in standard Carousel Slide format]

### LinkedIn Caption ([N]/3,000 chars)
**Hook (≤110 chars):**
[Hook text — professional tone]

**Body:**
[Thought leadership body]

**CTA:**
[CTA text]

🔗 [Link]

**Hashtags (3-5):**
#tag1 #tag2 #tag3
```
