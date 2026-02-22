# Sosmed Carousel Prompt Generator — Claude Project Instructions

## Project Overview

Claude Code plugin that generates cinematic AI image/video prompts for social media carousels. 1 skill + 1 agent + 7 reference documents as RAG knowledge base.

## Architecture

```
Plugin (Claude Code)
├── SKILL.md          → Inline skill (user invokes directly)
├── Agent             → Subagent for batch/parallel processing
└── References (7)    → RAG knowledge base (loaded on demand)
```

### File Roles

| File | Role | When Loaded |
|------|------|-------------|
| `skills/carousel-prompt-generator/SKILL.md` | Entry point — workflows, hard rules, WOW gate | Always (on skill invoke) |
| `agents/carousel-prompt-generator.md` | Batch subagent with step-by-step workflows | When parallel processing needed |
| `references/creator-bible.md` | Creator identity template | Before any prompt generation |
| `references/prompt-formulas.md` | Structured prompt templates per model | During prompt generation |
| `references/platform-specs.md` | AI model specs + decision matrix | When choosing model/config |
| `references/cinematography-lut.md` | Emotion → lighting → lens lookup tables | During prompt generation |
| `references/carousel-rebranding.md` | 5-step rebranding pipeline | Rebranding workflow only |
| `references/carousel-best-practices.md` | Platform strategies + design rules | Platform optimization |
| `references/localization-id.md` | Indonesian language adaptation | Indonesian content only |

## Key Concepts

### WOW Quality Gate
8-point scoring system (0-8 scale) applied to every generated prompt:
- Lighting Drama, Depth Layers, Atmosphere, Color Contrast
- Emotional Peak, Camera Intention, Texture Realism, Cinematic Ref
- Minimums: Hook >= 5, CTA >= 4, Thumbnail >= 4, Body/B-Roll >= 3
- Below minimum = revise before output

### Creator Identity (VERBATIM Rule)
- User provides: physical description, face reference image, brand handle, brand icon, accent color
- Physical description is used **word-for-word** in every prompt
- This ensures AI model consistency across all generated content
- Template in `references/creator-bible.md`

### Creator Face Allocation
| Slide Type | Face? | Why |
|------------|-------|-----|
| Hook | Yes | Exaggerated emotion grabs attention |
| Content body | No | Topic visuals only, no distraction |
| Split-panel | Yes | Creator provides context |
| CTA | Yes | Warm confident connection |
| Thumbnail | Yes | Curiosity gap drives clicks |

### Prompt Engineering Golden Rule
```
IMAGE PROMPT = ALL VISUALS (subject, lighting, lens, color, atmosphere)
VIDEO PROMPT = MOTION ONLY (camera movement, micro-motion, audio)
NEVER duplicate visual details in video prompt
```

## Technical Defaults

| Setting | Value | Why |
|---------|-------|-----|
| Aspect ratio | 9:16 vertical | Social media standard |
| Film stock | Kodak Portra 400 | Warm skin tones |
| Color temp | 3200-3500K | Golden hour warmth |
| Accent color | #F5A623 (golden yellow) | High contrast on dark |
| Image res | 4K | Nano Banana Pro native |
| Prompt length | 40-120 words | Nano Banana sweet spot |

## AI Model Routing

### Image Models
| Use Case | Primary | Fallback |
|----------|---------|----------|
| Creator face shots | Nano Banana Pro | DALL-E 3 |
| B-Roll (no face) | Nano Banana Pro | DALL-E 3 |

### Video Models
| Use Case | Primary | Fallback |
|----------|---------|----------|
| Dialogue (<=8s) | VEO 3.1 | Sora 2 |
| No dialogue | VEO 3.1 | Sora 2 |
| Complex physics / >8s | Sora 2 | VEO 3.1 |

### Critical Config Notes
- Nano Banana Pro: `image_size="4K"` (UPPERCASE K — lowercase silently degrades to 1K)
- Nano Banana Pro: `temperature` must be `1.0`
- VEO 3.1: dialogue format is `[Character] says: "text"` (colon syntax)
- VEO 3.1: face must be >= 20% of frame for lip-sync

## 3 Workflows

### 1. Fresh Content Production
1. User provides topic + creator identity
2. Generate HOOK → VALUE slides → CTA structure
3. Score each slide through WOW gate
4. Output structured prompts (image + optional video)

### 2. Carousel Rebranding
1. Analyze source carousel (extract content map per slide)
2. Style conversion matrix (map source elements → user's brand)
3. Generate slide-by-slide prompts with creator face on Hook/CTA
4. Text overlay guide per slide
5. Visual continuity checklist (13 items)

### 3. Thumbnail Generation
1. Creator face with curiosity-gap expression
2. WOW minimum 4/8
3. High-contrast lighting (Rembrandt 4:1 or Split 8:1)
4. Bottom 30% reserved for text overlay

## Hard Rules (Non-Negotiable)

1. Creator description used VERBATIM — never paraphrase
2. No third-party branding (logos, badges, watermarks)
3. User's brand icon + handle on every slide
4. Kodak Portra 400 default — warm palette, never cold
5. WOW score must meet minimum before output
6. Hook = creator face + exaggerated emotion (always)
7. Content body = topic visuals only (no creator face)
8. Bottom 30-40% reserved for text overlay (dark gradient)
9. "SWIPE FOR MORE" on all slides except CTA
10. Image prompt = ALL visuals | Video prompt = MOTION only

## Conventions for Contributors

### Adding a New Reference File
1. Create `.md` file in `references/`
2. Add entry to the Reference Files table in `SKILL.md`
3. Add entry to the Reference Files table in `agents/carousel-prompt-generator.md`
4. Update this CLAUDE.md file

### Adding a New Localization
1. Create `references/localization-{code}.md` (e.g., `localization-hi.md` for Hindi)
2. Follow the structure in `localization-id.md`:
   - Language style + pronouns
   - Headline writing rules
   - Cultural adaptation (settings, brands, data)
   - Visual context rules
   - Holiday localization
   - Tone & voice template
   - CTA phrases

### Updating AI Model Specs
1. Edit `references/platform-specs.md`
2. Update decision matrix tables
3. Update `references/prompt-formulas.md` templates if API format changed
4. Update model routing tables in `SKILL.md` and `agents/carousel-prompt-generator.md`

### File Naming
- Reference files: lowercase, kebab-case (e.g., `carousel-best-practices.md`)
- No spaces in filenames
- Prefix localizations with `localization-`

## Platform-Specific Notes

### Instagram
- Aspect ratio: 4:5 (1080x1350) in feed, 9:16 for Stories/Reels
- Algorithm rewards: saves > shares > comments > likes
- Ideal slides: 7-10
- "SWIPE" indicator increases swipe-through 20-30%

### TikTok
- Aspect ratio: 9:16 only (1080x1920)
- Algorithm rewards: swipe completion rate, shares
- Ideal slides: 5-8
- Bold text, high contrast, fast value delivery

### LinkedIn
- Aspect ratio: 4:5 or 1:1 (1080x1350 or 1080x1080)
- Algorithm rewards: dwell time, comments, reposts
- Ideal slides: 8-12
- PDF format supported, professional polish
- Data-heavy content performs well

## Debugging

| Issue | Check |
|-------|-------|
| Prompt too long | Nano Banana sweet spot is 40-120 words |
| Image resolution low | Ensure `4K` uppercase in config, not `4k` |
| Creator face inconsistent | Verify face reference filename matches across prompts |
| Wrong aspect ratio | Check platform-specs.md for platform → ratio mapping |
| Cold/blue tone | Default is Kodak Portra 400 (warm) — check color temp is 3200-3500K |
| Video duplicates image visuals | Golden rule: video prompt = MOTION ONLY |
| VEO lip-sync fails | Face must be >= 20% of frame, dialogue <= 15 words per 8s |
| Branding leak | Check all slides for third-party logos/handles (hard rule #2) |

---

**Version:** 1.0.0
**Last Updated:** February 2026
