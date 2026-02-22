# Sosmed Carousel Prompt Generator

A Claude Code plugin that generates cinematic AI image prompts for social media carousel content. Built for Instagram, TikTok, and LinkedIn creators who want professional, on-brand carousels with consistent visual identity.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-Plugin-blue.svg)](https://github.com/alisadikinma/sosmed-carousel-prompt-generator)

---

## What It Does

This plugin turns your carousel ideas into production-ready AI image prompts with:

- **WOW Quality Gate** — 8-point scoring system ensures every frame meets cinematic standards before output
- **Creator Identity (VERBATIM)** — Your physical description is used exactly in every prompt for AI consistency
- **Platform-Specific Optimization** — Tailored for Instagram (saves), TikTok (swipe completion), LinkedIn (dwell time)
- **Cinematic Storytelling** — Kodak Portra 400 warmth, Rembrandt lighting, intentional camera work
- **3 Workflows** — Fresh content production, carousel rebranding, thumbnail generation

## Installation

```bash
claude plugin add alisadikinma/sosmed-carousel-prompt-generator
```

## Quick Start

After installation, invoke the skill in Claude Code:

```
/carousel-prompt-generator
```

You'll be asked for 5 identity inputs:

| Input | Example |
|-------|---------|
| Physical description | "Southeast Asian woman, mid-20s, warm skin tone, shoulder-length black hair..." |
| Face reference image | `creator-face.png` |
| Brand handle | `@yourbrand` |
| Brand icon filename | `brand-icon.png` |
| Accent color | `#F5A623` (golden yellow default) |

Then choose a workflow:

1. **Fresh Content** — Topic → 7-12 slide carousel with Hook/Value/CTA structure
2. **Carousel Rebranding** — Convert third-party carousel → your brand identity
3. **Thumbnail Generation** — High-impact emotional thumbnail (WOW 4+/8 minimum)

## WOW Quality Gate

Every generated prompt is scored on 8 dimensions (0-8 scale):

| Dimension | What It Measures |
|-----------|-----------------|
| Lighting Drama | Contrast ratio, key light intention |
| Depth Layers | Foreground/midground/background separation |
| Atmosphere | Haze, bokeh, practical light sources |
| Color Contrast | Warm/cool tension, palette harmony |
| Emotional Peak | Expression intensity, body language |
| Camera Intention | Lens choice, angle, composition purpose |
| Texture Realism | Surface detail, fabric, skin quality |
| Cinematic Ref | "Would Deakins light this?" standard |

**Minimum scores by slide type:**

| Slide Type | Minimum Score |
|------------|--------------|
| Hook | 5/8 |
| CTA | 4/8 |
| Thumbnail | 4/8 |
| Body / B-Roll | 3/8 |

Prompts below minimum are automatically revised before output.

## Platform Support

| Platform | Aspect Ratio | Ideal Slides | Algorithm Signal |
|----------|-------------|-------------|-----------------|
| Instagram | 4:5 (1080x1350) | 7-10 | Saves > Likes |
| TikTok | 9:16 (1080x1920) | 5-8 | Swipe completion |
| LinkedIn | 4:5 or 1:1 | 8-12 | Dwell time |

## AI Model Routing

| Task | Primary Model | Fallback |
|------|--------------|----------|
| Creator shots (with face) | Nano Banana Pro (4K) | DALL-E 3 |
| B-Roll (no face) | Nano Banana Pro | DALL-E 3 |
| Video (with dialogue) | VEO 3.1 | Sora 2 |
| Video (no dialogue) | VEO 3.1 | Sora 2 |

## Creator Face Allocation

| Slide Type | Creator Face? | Expression | Shot |
|------------|:------------:|------------|------|
| Hook | Yes | Exaggerated emotion | CU / MCU |
| Content body | No | — | Topic visuals |
| Split-panel | Yes | Context-appropriate | MCU |
| CTA | Yes | Warm, confident | MCU / MS |
| Thumbnail | Yes | Curiosity gap | CU |

## Project Structure

```
sosmed-carousel-prompt-generator/
├── .claude-plugin/
│   ├── plugin.json              # Plugin metadata (name, version, author)
│   └── marketplace.json         # Marketplace configuration
├── skills/
│   └── carousel-prompt-generator/
│       └── SKILL.md             # Main skill — workflows, rules, WOW gate
├── agents/
│   └── carousel-prompt-generator.md  # Subagent for batch processing
├── references/                  # RAG knowledge base (7 files)
│   ├── carousel-best-practices.md    # Platform strategies + design rules
│   ├── carousel-rebranding.md        # 5-step rebranding pipeline
│   ├── cinematography-lut.md         # Emotion → lighting → lens lookups
│   ├── creator-bible.md              # Creator identity template
│   ├── localization-id.md            # Indonesian language adaptation
│   ├── platform-specs.md             # AI model specs + decision matrix
│   └── prompt-formulas.md            # Structured prompt templates
├── LICENSE                      # MIT
├── README.md                    # This file
└── CLAUDE.md                    # Project instructions for contributors
```

### Reference Files Guide

| When You Need To... | Read This File |
|---------------------|---------------|
| Set up creator identity | `creator-bible.md` |
| Generate image prompts | `prompt-formulas.md` |
| Choose AI model + config | `platform-specs.md` |
| Look up lighting/lens for emotion | `cinematography-lut.md` |
| Rebrand a third-party carousel | `carousel-rebranding.md` |
| Optimize for a specific platform | `carousel-best-practices.md` |
| Create Indonesian content | `localization-id.md` |

## Technical Defaults

| Setting | Default |
|---------|---------|
| Aspect ratio | 9:16 vertical |
| Film stock | Kodak Portra 400 (warm) |
| Color temperature | 3200-3500K |
| Accent color | Golden Yellow `#F5A623` |
| Image resolution | 4K (Nano Banana Pro) |
| Prompt length | 40-120 words |

## Hard Rules

1. Creator physical description used **VERBATIM** in every prompt
2. No third-party branding (logos, badges, handles) — ever
3. User's brand icon + handle on every slide
4. Kodak Portra 400 default — warm, never cold
5. WOW score must meet minimum before output
6. Hook slide always features creator face with exaggerated emotion
7. Content body slides: topic visuals only, no creator face
8. Bottom 30-40% reserved for text overlay (dark gradient zone)
9. "SWIPE FOR MORE" indicator on all slides except CTA
10. Image prompt = ALL visuals | Video prompt = MOTION only (never duplicate)

## Localization

Currently supported:
- **Indonesian (ID)** — Gen Z casual tone (gue/lo, mix Bahasa + English), cultural setting swaps, holiday-specific visuals

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/your-feature`)
3. Follow the conventions in `CLAUDE.md`
4. Submit a pull request

## License

MIT License — see [LICENSE](LICENSE) for details.

## Author

**Ali Sadikin** — [@alisadikinma](https://github.com/alisadikinma)
