# sosmed-carousel-prompt-generator

> Cinematic AI image prompt generator for social media carousels — every frame must trigger visceral "WOW".

A Claude Code plugin that generates production-ready AI image prompts for carousel content across Instagram, TikTok, and LinkedIn. Built around a cinematography-first philosophy: if Deakins wouldn't light it and Fincher wouldn't approve the frame, it doesn't ship.

## The Problem

| What happens | Result |
|---|---|
| Generic AI prompts produce flat, lifeless carousel images | Users scroll past |
| No consistent visual identity across slides | Brand looks amateur |
| Rebranding third-party carousels means starting from scratch | Hours wasted per carousel |
| Text baked into AI images looks terrible | Unusable output |
| No quality standard — every prompt is a gamble | Inconsistent feed |

## The Solution

### 1. WOW Quality Gate

Every prompt is scored against 8 cinematic criteria before output:

| # | Factor | What It Catches |
|---|--------|----------------|
| 1 | Lighting Drama | Flat, even lighting with no mood |
| 2 | Depth Layers | Missing foreground/background separation |
| 3 | Atmosphere | No haze, particles, or volumetric rays |
| 4 | Color Contrast | No warm-cool tension or accent highlights |
| 5 | Emotional Peak | Neutral, lifeless expressions |
| 6 | Camera Intention | Random angles with no purpose |
| 7 | Texture Realism | Smooth, plastic-looking surfaces |
| 8 | Cinematic Reference | No film stock or DP style anchor |

**Minimums enforced:** Hook 5+, CTA 4+, Thumbnail 4+, Body 3+, B-Roll 3+. Below minimum = automatic revision.

### 2. Creator Identity System

Your physical description, brand handle, accent color, and brand icon are injected VERBATIM into every prompt — ensuring consistent AI-generated visuals across your entire content library.

### 3. Image-Video Split Rule

```
IMAGE PROMPT = ALL VISUALS (subject, lighting, lens, color, atmosphere)
VIDEO PROMPT = MOTION ONLY (camera movement, micro-motion, audio)
```

No duplication between image and video prompts. Clean separation that AI generators actually understand.

---

## Installation

### Claude Code (via Plugin Marketplace)

```
/install-plugin alisadikinma/sosmed-carousel-prompt-generator
```

### Manual Installation

```bash
# Clone to Claude Code plugins directory
git clone https://github.com/alisadikinma/sosmed-carousel-prompt-generator.git \
  ~/.claude/plugins/sosmed-carousel-prompt-generator
```

### Verify Installation

After installing, the skill auto-triggers when you mention carousels, thumbnails, rebranding, or AI image prompts. You can also invoke it explicitly:

```
/carousel-prompt-generator
```

---

## What's Inside

### Skill

| Skill | Triggers On |
|---|---|
| `carousel-prompt-generator` | carousel, thumbnail, rebrand, image generation, visual content, AI image, buat prompt, bikinin gambar |

### Agent

| Agent | Purpose |
|---|---|
| `carousel-prompt-generator` | Subagent for batch carousel prompt work — reads reference docs, generates all prompts, writes output to file |

### Reference Docs (7 files, read on-demand)

| File | When Used |
|---|---|
| `creator-bible.md` | ALWAYS — creator identity template, brand rules |
| `carousel-rebranding.md` | Converting third-party carousels to your brand |
| `platform-specs.md` | Platform routing: Instagram, TikTok, LinkedIn |
| `cinematography-lut.md` | Lighting setups, lens choices, film stock lookup |
| `prompt-formulas.md` | Proven prompt templates and patterns |
| `localization-id.md` | Indonesian language content localization |
| `carousel-best-practices.md` | Carousel design and engagement best practices |

---

## The Workflow

```
User Request
    |
    v
[1] Read creator-bible.md (ALWAYS)
    |
    v
[2] Read task-specific references
    |
    v
[3] Analyze input ──────────────────────┐
    |                                    |
    v                                    v
[4a] FRESH CONTENT            [4b] REBRANDING
  Analyze script/brief          Analyze source slides
  Route to platforms            Strip third-party branding
  Generate prompt pairs         Convert to user's brand
    |                                    |
    v                                    v
[5] Score each prompt via WOW gate
    |
    ├── Below minimum? ──> REVISE
    |
    v
[6] Output with text overlay guides
    |
    v
[7] Continuity checklist verification
```

---

## Capabilities

### Carousel Image Prompts
Generate cinematic Nano Banana Pro prompts for each carousel slide — Hook, Content, CTA — with proper creator face placement and brand consistency.

### Carousel Rebranding
Upload any third-party carousel and get it fully converted to your brand: colors, lighting, style, branding elements. No third-party logos survive.

### Thumbnail Generation
Creator face at 50-60% frame, exaggerated emotion, topic visual, text-safe zone. Optimized for click-through.

### Video Prompt Pairs
Separate image + video prompts using the split rule. Routes automatically: VEO 3.1 for dialogue/4K, Sora 2 for complex physics or >8s duration.

---

## Hard Rules

These are non-negotiable across all generated prompts:

| Rule | Enforcement |
|---|---|
| No third-party branding | Zero external badges, logos, or handles |
| Brand icon + handle on every slide | User's brand always present |
| Creator face placement | ONLY on Hook, CTA, Loop-end, Thumbnail |
| Text is post-production | Clean images with dark gradient text zones |
| Default film stock | Kodak Portra 400 (warm golden, not cold) |
| Aspect ratio | 9:16 vertical for all social content |
| Image resolution | 4K via Nano Banana Pro |
| Accent color | User-defined (default: Golden Yellow #F5A623) |

---

## Output Format

Each slide outputs a structured block:

```
## Slide [N]: [Topic]
Type: Hook / Content / CTA | Creator Face: YES/NO | Platform: Nano Banana Pro

### Nano Banana Pro Prompt
[Full natural-language prompt, 40-120 words]

### Text Overlay (Post-Production)
- Headline: "[TEXT]" — White bold condensed ALL CAPS
- Accent: "[WORD]" — [User's accent color]
- Branding: [brand icon] [position] + [handle]
- SWIPE FOR MORE: yes/no

### WOW: [N]/8
```

---

## Project Structure

```
sosmed-carousel-prompt-generator/
├── .claude-plugin/
│   ├── plugin.json              # Plugin metadata
│   └── marketplace.json         # Marketplace listing
├── skills/
│   └── carousel-prompt-generator/
│       └── SKILL.md             # Skill definition
├── agents/
│   └── carousel-prompt-generator.md  # Subagent definition
├── references/
│   ├── creator-bible.md         # Creator identity template
│   ├── carousel-rebranding.md   # Rebranding conversion rules
│   ├── platform-specs.md        # Platform routing specs
│   ├── cinematography-lut.md    # Lighting/lens/film stock LUT
│   ├── prompt-formulas.md       # Prompt templates
│   ├── localization-id.md       # Indonesian localization
│   └── carousel-best-practices.md  # Design best practices
├── CLAUDE.md                    # Project documentation
├── README.md
└── LICENSE                      # MIT
```

---

## Philosophy

### Cinematography First

Every prompt is anchored in real cinematography — named lighting setups, specific lens choices, actual film stocks. No "make it look cinematic" hand-waving.

### Text is Post-Production

AI-generated text in images looks terrible. This plugin generates clean images with dark gradient zones designed for text overlay in your actual design tool.

### Creator Consistency

Your face, your brand, your colors — injected verbatim into every prompt. The AI sees the same description every time, producing consistent results across hundreds of slides.

### Platform-Aware

Instagram carousels, TikTok slideshows, LinkedIn posts — each has different specs and engagement patterns. Reference docs encode platform-specific best practices so prompts are optimized for where they'll actually be posted.

---

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'feat: add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

Contributions to reference docs (new platforms, updated specs, additional cinematography techniques) are especially welcome.

---

## License

MIT - see [LICENSE](LICENSE) for details.

---

Built by [Ali Sadikin](https://github.com/alisadikinma)
