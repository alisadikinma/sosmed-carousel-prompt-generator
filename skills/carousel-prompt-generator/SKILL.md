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
| Platform choice | + `references/platform-specs.md` |
| Lighting/lens lookup | + `references/cinematography-lut.md` |
| Prompt templates | + `references/prompt-formulas.md` |
| Indonesian content | + `references/localization-id.md` |
| Carousel best practices | + `references/carousel-best-practices.md` |

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
8. Aspect ratio = 9:16 vertical for all social content
9. Image size = 4K via Nano Banana Pro
10. All prompts must pass WOW minimum score

---

## Fixed Technical Specs

| Parameter | Value |
|-----------|-------|
| Aspect Ratio | 9:16 vertical |
| Image Resolution | 4K (Nano Banana Pro) |
| Video Resolution | 1080p |
| Frame Rate | 24fps |
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

## Workflow: Fresh Content Production

1. ANALYZE script/brief — identify segments, emotions, shot types
2. ROUTE each segment to platform (read `references/platform-specs.md`)
3. GENERATE prompt pairs: image (all visuals) + video (motion only)
4. SCORE each prompt via WOW gate
5. OUTPUT continuity bible

## Workflow: Thumbnail Generation

1. READ `references/creator-bible.md` for expression + lighting setup
2. GENERATE prompt with: creator face 50-60%, exaggerated emotion, topic visual, text-safe zone
3. SCORE WOW minimum 4/8

---

## Platform Routing

```
Image: Nano Banana Pro (primary) | DALL-E 3 (fallback)
Video: VEO 3.1 (default, best lip-sync) | Sora 2 (physics, duration >8s)
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
- SWIPE FOR MORE: yes/no
### WOW: [N]/8
```

### Video Segment
```
## Segment [N]: [Description]
Duration: [N]s | Platform: VEO 3.1

### Image Prompt (Nano Banana Pro)
[ALL visuals]
### Video Prompt (VEO 3.1)
[MOTION ONLY — no visual duplication]
### WOW: [N]/8
```
