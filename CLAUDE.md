# Sosmed Carousel Prompt Generator — Claude Project Instructions

## Project Overview

Claude Code plugin that generates cinematic AI image prompts for social media carousels. 1 skill + 1 agent + 8 reference documents as RAG knowledge base.

## Architecture

| Path | Purpose |
|------|---------|
| `.claude-plugin/plugin.json` | Plugin metadata (name, version, author) |
| `.claude-plugin/marketplace.json` | Marketplace listing |
| `hooks/hooks.json` | SessionStart hook definition |
| `hooks/session-start.sh` | Session start script — announces available skills |
| `skills/carousel-prompt-generator/SKILL.md` | Main skill definition — carousel prompt generation |
| `skills/validate-references/SKILL.md` | Cross-file consistency checker (6 checks) |
| `skills/new-localization/SKILL.md` | Scaffold new localization files + wire reference tables |
| `agents/carousel-prompt-generator.md` | Subagent for batch carousel prompt work |
| `references/` | 8 reference docs read on-demand by skill/agent |
| `README.md` | Repo README |
| `LICENSE` | MIT license |

### Reference Files

| File | When Used |
|------|-----------|
| `creator-bible.md` | ALWAYS — creator identity, brand rules, gradient zones, holiday production |
| `carousel-rebranding.md` | Rebranding third-party carousels |
| `platform-specs.md` | Platform routing, aspect ratios, Nano Banana Pro specs |
| `cinematography-lut.md` | Lighting/lens/film stock/atmosphere/DP signature lookup |
| `prompt-formulas.md` | Prompt templates, thumbnail template, quality checklists |
| `localization-id.md` | Indonesian localization, holidays, AI bias countermeasures |
| `carousel-best-practices.md` | Carousel design and engagement best practices |
| `caption-copywriting.md` | Caption formulas, character limits, hashtag strategy per platform |

## Key Concepts

- **Image-Only Plugin**: Nano Banana Pro is the exclusive image generation platform
- **WOW Quality Gate**: 8-point scoring (lighting, depth, atmosphere, color, emotion, camera, texture, cinematic ref). Minimums: Hook 5+, CTA/Thumb 4+, Body/B-Roll 3+
- **Platform-Specific Aspect Ratios**: IG Feed 4:5, TikTok/Reels 9:16, LinkedIn 4:5/1:1, Default 4:5
- **Hard Rules**: No third-party branding, creator face only on Hook/CTA/Loop-end/Thumbnail, text is post-production only
- **SWIPE FOR MORE**: All slides except CTA (20-30% engagement boost)
- **Gradient Zones**: Hook 40%, B-Roll 35%, Split-Panel 30%, CTA 40%, Thumbnail 25% (source of truth in creator-bible.md Section 7)
- **Localization Trigger**: When user speaks Bahasa or targets Indonesia, load localization-id.md first
- **Multi-Platform Export**: Generate carousel prompts + captions for IG + TikTok + LinkedIn from single brief
- **5-Hashtag Era**: IG max 5 (Dec 2025), TikTok max 5 (Aug 2025), LinkedIn 3-5
- **Default specs**: 4K, Kodak Portra 400, warm golden amber grade
- **Content Language**: Single language per carousel — English OR Bahasa, never bilingual mix

## Capabilities

1. **Carousel image prompts** — Nano Banana Pro, per-slide with WOW scoring
2. **Thumbnail prompts** — creator face 50-60%, exaggerated emotion, topic visual
3. **Carousel rebranding** — convert third-party designs to user's brand
4. **Multi-platform export** — IG + TikTok + LinkedIn with platform-specific aspect ratios
5. **Caption copywriting** — platform-specific captions with character limits + hashtag strategy

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
| Split-panel | No | Topic visuals, side-by-side comparison |
| CTA | Yes | Warm confident connection |
| Thumbnail | Yes | Curiosity gap drives clicks |

## Technical Defaults

| Setting | Value |
|---------|-------|
| Aspect ratio | Platform-specific (IG 4:5, TikTok 9:16, LinkedIn 4:5) |
| Film stock | Kodak Portra 400 (warm) |
| Color temp | 3200-3500K |
| Accent color | #F5A623 (golden yellow) |
| Image res | 4K (Nano Banana Pro) |
| Prompt length | 40-120 words |

## Conventions for Contributors

### Adding a New Reference File
1. Create `.md` file in `references/`
2. Add entry to the Reference Files table in `SKILL.md`
3. Add entry to the Reference Files table in `agents/carousel-prompt-generator.md`
4. Update this CLAUDE.md file
5. Run `/validate-references` to verify cross-file consistency

### Adding a New Localization
1. Create `references/localization-{code}.md` (e.g., `localization-hi.md` for Hindi)
2. Follow the structure in `localization-id.md`

### File Naming
- Reference files: lowercase, kebab-case (e.g., `carousel-best-practices.md`)
- No spaces in filenames
- Prefix localizations with `localization-`

## Debugging

| Issue | Check |
|-------|-------|
| Prompt too long | Nano Banana sweet spot is 40-120 words |
| Image resolution low | Ensure `4K` uppercase in config, not `4k` |
| Creator face inconsistent | Verify face reference filename matches across prompts |
| Wrong aspect ratio | Check platform-specs.md for platform → ratio mapping |
| Cold/blue tone | Default is Kodak Portra 400 (warm) — check color temp is 3200-3500K |
| Branding leak | Check all slides for third-party logos/handles |
| Cross-file drift | Run `/validate-references` — checks SWIPE, hashtags, gradients, aspect ratios |

---

**Version:** 1.2.0
**Last Updated:** February 2026
