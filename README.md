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
| Different platform specs ignored | Wrong aspect ratios, suboptimal engagement |
| Caption writing is a separate manual step | Workflow friction, inconsistent tone |

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

### 3. Multi-Platform Export

Generate carousel prompts AND captions for all platforms from a single brief:

```
Single Brief → IG (4:5) + TikTok (9:16) + LinkedIn (4:5)
                ↓           ↓              ↓
             Prompts     Prompts        Prompts
             Caption     Caption        Caption
             5 hashtags  5 hashtags     3-5 hashtags
```

---

## Installation

### From GitHub (Recommended)

```bash
# Step 1: Add marketplace source
claude plugins marketplace add https://github.com/alisadikinma/sosmed-carousel-prompt-generator

# Step 2: Install plugin (choose scope)
claude plugins install sosmed-carousel-prompt-generator --scope user    # All projects
claude plugins install sosmed-carousel-prompt-generator --scope project # This project only
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

### Skills

| Skill | Triggers On |
|---|---|
| `carousel-prompt-generator` | carousel, thumbnail, rebrand, image generation, visual content, AI image, buat prompt, bikinin gambar |
| `validate-references` | Cross-file consistency checker (SWIPE rules, hashtags, gradients, aspect ratios) |
| `new-localization` | Scaffold new localization files + wire reference tables |

### Agent

| Agent | Purpose |
|---|---|
| `carousel-prompt-generator` | Subagent for batch carousel prompt work — reads reference docs, generates all prompts, writes output to file |

### Reference Docs (8 files, read on-demand)

| File | When Used |
|---|---|
| `creator-bible.md` | ALWAYS — creator identity, brand rules, gradient zones, holiday production |
| `carousel-rebranding.md` | Converting third-party carousels to your brand |
| `platform-specs.md` | Nano Banana Pro specs, platform aspect ratios |
| `cinematography-lut.md` | Lighting, lens, film stock, atmosphere, DP signatures |
| `prompt-formulas.md` | Prompt templates, thumbnail template, quality checklists |
| `localization-id.md` | Indonesian localization, holidays with color palettes, AI bias countermeasures |
| `carousel-best-practices.md` | Carousel design, engagement benchmarks, TikTok Photo Mode, algorithm signals, cross-platform strategy |
| `caption-copywriting.md` | Caption formulas, emotional triggers, CTA psychology, hashtag strategy, triple-layer TikTok SEO |

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
  Analyze brief/topic           Analyze source slides
  Set platform aspect ratio     Strip third-party branding
  Generate prompts              Convert to user's brand
    |                                    |
    v                                    v
[5] Score each prompt via WOW gate
    |
    ├── Below minimum? ──> REVISE
    |
    v
[6] Generate captions per platform (if multi-platform export)
    |
    v
[7] Output with text overlay guides
    |
    v
[8] Continuity checklist verification
```

---

## Capabilities

### Carousel Image Prompts
Generate cinematic Nano Banana Pro prompts for each carousel slide — Hook, Content, CTA — with proper creator face placement and brand consistency.

### Carousel Rebranding
Upload any third-party carousel and get it fully converted to your brand: colors, lighting, style, branding elements. No third-party logos survive.

### Thumbnail Generation
Creator face at 50-60% frame, exaggerated emotion, topic visual, text-safe zone. Optimized for click-through.

### Multi-Platform Export
Generate platform-specific carousel prompts AND captions from a single brief. Automatically adapts aspect ratio (IG 4:5, TikTok 9:16, LinkedIn 4:5), slide count, content tone, and caption style per platform.

### Caption Copywriting
Platform-aware captions with enforced character limits (IG 2200, TikTok 4000, LinkedIn 3000), truncation-safe hooks, and the 2-2-1 hashtag formula (2 broad + 2 niche + 1 branded). Includes emotional trigger patterns per platform, CTA psychology (engagement ladder, micro-commitments, algorithm weight signals), TikTok triple-layer keyword SEO, and LinkedIn engagement bait avoidance.

### Indonesian Localization
Automatic localization trigger when user speaks Bahasa or targets Indonesian audience. Includes setting conversions, holiday adaptations with color palettes, and AI bias countermeasures.

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
| Aspect ratio | Platform-specific: IG Feed 4:5, TikTok 9:16, LinkedIn 4:5 |
| Image resolution | 4K via Nano Banana Pro |
| Accent color | User-defined (default: Golden Yellow #F5A623) |
| SWIPE FOR MORE | All slides except CTA |
| Hashtags | Max 5 (IG/TikTok), 3-5 (LinkedIn) |

---

## Output Format

### Carousel Slide

```
## Slide [N]: [Topic]
Type: Hook / Content / CTA | Creator Face: YES/NO | Platform: Nano Banana Pro

### Nano Banana Pro Prompt
[Full natural-language prompt, 40-120 words]

### Text Overlay (Post-Production)
- Headline: "[TEXT]" — White bold condensed ALL CAPS
- Accent: "[WORD]" — [User's accent color]
- Branding: [brand icon] [position] + [handle]
- SWIPE FOR MORE: all slides except CTA

### WOW: [N]/8
```

### Multi-Platform Export

```
# Multi-Platform Export: [Topic]

## Instagram Carousel (4:5 — 1080×1350, [N] slides)
[Slide prompts + Caption with 5 hashtags]

## TikTok Carousel (9:16 — 1080×1920, [N] slides)
[Slide prompts + Caption with 5 hashtags]

## LinkedIn Carousel (4:5 — 1080×1350, [N] slides)
[Slide prompts + Caption with 3-5 hashtags]
```

---

## Project Structure

```
sosmed-carousel-prompt-generator/
├── .claude-plugin/
│   ├── plugin.json              # Plugin metadata
│   └── marketplace.json         # Marketplace listing
├── skills/
│   ├── carousel-prompt-generator/
│   │   └── SKILL.md             # Main skill — carousel prompt generation
│   ├── validate-references/
│   │   └── SKILL.md             # Cross-file consistency checker
│   └── new-localization/
│       └── SKILL.md             # Scaffold new localizations
├── agents/
│   └── carousel-prompt-generator.md  # Subagent definition
├── references/
│   ├── creator-bible.md         # Creator identity + holidays
│   ├── carousel-rebranding.md   # Rebranding conversion rules
│   ├── platform-specs.md        # Nano Banana Pro + platform specs
│   ├── cinematography-lut.md    # Lighting/lens/film stock LUT
│   ├── prompt-formulas.md       # Prompt templates + checklists
│   ├── localization-id.md       # Indonesian localization
│   ├── carousel-best-practices.md  # Design best practices
│   └── caption-copywriting.md   # Caption formulas + hashtags
├── CLAUDE.md                    # Project documentation
├── README.md
└── LICENSE                      # MIT
```

---

## Philosophy

### Cinematography First

Every prompt is anchored in real cinematography — named lighting setups, specific lens choices, actual film stocks, cinematographer signatures. No "make it look cinematic" hand-waving.

### Text is Post-Production

AI-generated text in images looks terrible. This plugin generates clean images with dark gradient zones designed for text overlay in your actual design tool.

### Creator Consistency

Your face, your brand, your colors — injected verbatim into every prompt. The AI sees the same description every time, producing consistent results across hundreds of slides.

### Platform-Aware

Instagram carousels, TikTok Photo Mode carousels, LinkedIn document posts — each has different specs, aspect ratios, algorithm signals, and engagement patterns. Reference docs encode platform-specific best practices including IG's second-chance algorithm, TikTok's reverse-swipe signal, and LinkedIn's Depth Score so prompts and captions are optimized for where they'll actually be posted.

### Caption-Ready

Captions aren't an afterthought. The multi-platform export workflow generates both prompts AND captions with platform-specific character limits, truncation-safe hooks, and the right hashtag count.

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
