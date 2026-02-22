# sosmed-carousel-prompt-generator

Claude Code plugin: Cinematic AI image prompt generator for social media carousels.

## Project Structure

| Path | Purpose |
|------|---------|
| `.claude-plugin/plugin.json` | Plugin metadata (name, version, author) |
| `.claude-plugin/marketplace.json` | Marketplace listing |
| `skills/carousel-prompt-generator/SKILL.md` | Main skill definition — carousel prompt generation |
| `agents/carousel-prompt-generator.md` | Subagent for batch carousel prompt work |
| `references/` | 7 reference docs read on-demand by skill/agent |
| `README.md` | Repo README |
| `LICENSE` | MIT license |

## Reference Files

| File | When Used |
|------|-----------|
| `creator-bible.md` | ALWAYS — creator identity, brand rules |
| `carousel-rebranding.md` | Rebranding third-party carousels |
| `platform-specs.md` | Platform routing (IG, TikTok, LinkedIn) |
| `cinematography-lut.md` | Lighting/lens/film stock lookup |
| `prompt-formulas.md` | Prompt templates and patterns |
| `localization-id.md` | Indonesian content localization |
| `carousel-best-practices.md` | Carousel design best practices |

## Key Concepts

- **WOW Quality Gate**: 8-point scoring (lighting, depth, atmosphere, color, emotion, camera, texture, cinematic ref). Minimums: Hook 5+, CTA/Thumb 4+, Body/B-Roll 3+
- **Image→Video Split**: Image prompt = ALL visuals, Video prompt = MOTION ONLY
- **Hard Rules**: No third-party branding, creator face only on Hook/CTA/Loop-end/Thumbnail, text is post-production only
- **Default specs**: 9:16 vertical, 4K, Kodak Portra 400, warm golden amber grade

## Development Conventions

- This is a prompt-only plugin (no code, no tests, no build)
- All content is Markdown — skill definitions, agent definitions, reference docs
- Version tracked in `.claude-plugin/plugin.json`
- Plugin format follows Claude Code plugin spec (marketplace installable)
