# sosmed-carousel-prompt-generator

> Cinematic AI image prompt generator for social media carousels — every frame must trigger visceral "WOW".

A Claude Code plugin that generates production-ready AI image prompts for carousel content across Instagram, TikTok, LinkedIn, and Threads. Built around a cinematography-first philosophy with psychology-based hook science: if Deakins wouldn't light it and Fincher wouldn't approve the frame, it doesn't ship.

## The Problem

| What happens | Result |
|---|---|
| Generic AI prompts produce flat, lifeless carousel images | Users scroll past |
| No consistent visual identity across slides | Brand looks amateur |
| Rebranding third-party carousels means starting from scratch | Hours wasted per carousel |
| No quality standard — every prompt is a gamble | Inconsistent feed |
| Different platform specs ignored | Wrong aspect ratios, suboptimal engagement |
| Caption writing is a separate manual step | Workflow friction, inconsistent tone |
| Factual claims in carousels go unverified | Credibility damage |
| Agent generates everything without asking | Mismatched creative decisions |

## The Solution

### 1. WOW Quality Gate (8/8 Mandatory, Min 6/8)

Every prompt is scored against 8 cinematic criteria — ALL must be present:

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

**Minimum 6/8 for ALL slide types.** Below minimum = automatic revision.

### 2. Text-in-Image Rendering

All text (headlines, accent words, branding, SWIPE CTA) is described directly in the Nano Banana Pro prompt for in-image rendering. No more separate "post-production" step — you get complete slides.

### 3. Creator Identity System

Your physical description, brand handle, accent color, and brand icon are injected VERBATIM into every prompt — ensuring consistent AI-generated visuals across your entire content library.

### 4. Auto Captions for All Platforms

Every carousel automatically generates captions for IG + TikTok + LinkedIn + Threads:

```
Single Brief → Carousel Prompts (text in-image)
                    ↓
             IG Caption (≤2200 chars, 5 hashtags)
             TikTok Caption (≤4000 chars, 5 hashtags)
             LinkedIn Caption (≤3000 chars, 3-5 hashtags)
             Threads Caption (≤500 chars, no hashtags)
```

Default language: **Bahasa Indonesia**. English only when explicitly requested.

### 5. Fact Verification

All factual claims (statistics, data, quotes) are automatically web-searched and verified before prompt generation. Sources included in output.

### 6. Interactive Slide Design

The agent detects ambiguous creative decisions and asks before generating:
- Profession-specific costumes → "Lab coat or your default blazer?"
- Setting ambiguity → "Modern glass server room or industrial gritty?"

**Note:** B-Roll with human figures automatically uses your creator face as the most prominent figure — no question needed.

### 7. Psychology-Based Hook Science

5 hook categories with 100-hook bank (20 per category, Bahasa + English), backed by research data (Backlinko 912M posts, TokPortal Q2-2025, Virvid 2026, Sephora May-2025):
- **Visual Shock** — pattern interrupt in <0.5s (+131% attention retention, +400% dopamine)
- **Negative Bias** — loss aversion trigger (+63% CTR, 2:1 outperform generic)
- **Curiosity Gap** — open loop psychology (+41% retention, 70%+ completion)
- **Relatability** — identity alignment (+91.7% engagement, +31% authentic)
- **Speed & Value** — ROI on attention (2.5x saves/shares, +217% lead gen)

Plus: Gen-Z transcreation rules, interactive carousel hooks (quiz/flowchart), cover slide design specs, and algorithm engagement hierarchy.

### 8. CTA Science (Algorithm-Optimized)

4 CTA types ranked by engagement impact, designed around the 2026 algorithm engagement hierarchy (DM shares 3-5x > Saves 3x > Comments > Likes):

| CTA Type | Strength | Example |
|---|---|---|
| **Engagement Reward** | Highest conversion (12-18%) | "Comment 'MAU' dan gue kirim guide-nya ke DM lo" |
| **Question Trigger** | Highest comment volume | "Lo termasuk yang mana? Comment angkanya!" |
| **Polarize Debate** | Highest shares + depth | "Menurut lo [A] atau [B]?" |
| **Identity Tag** | Highest DM shares | "Tag temen yang BUTUH ini" |

### 9. Subject Brand Context

When discussing a specific company (Google, WhatsApp, Tesla), their brand elements (logo, UI, color scheme) are included in the image. Without subject brand context, factual claims are meaningless to viewers.

### 10. Source URL Metadata Extraction (NEW in v2.6.0)

Paste an Instagram/TikTok/LinkedIn post URL and the agent auto-extracts caption, account name, engagement stats, and post date. This metadata enriches prompt context and powers caption writing — no manual copy-paste needed.

```
/carousel-prompt-generator

Agent: "Punya URL source carousel-nya?"
User:  https://instagram.com/p/DVJgCUcDAVI/

Agent extracts:
  → @getintoai (account)
  → "Another major week in AI!..." (caption)
  → 173 likes, 1 comments (engagement)
  → Feb 24, 2026 (date)

Uses caption as:
  → Topic context for image prompts
  → Skeleton for our own captions (rewritten in creator voice)
  → Factual claims → fed into verification step
  → Hashtag research reference
```

### 11. Carousel Engagement Funnel (NEW in v2.2.0)

Full-funnel engagement system from first impression to conversion:

```
HOOK (Slide 1)     → Mindblowing headline + pattern interrupt visual
    ↓                 Score 3/5 on Hook Scoring Gate before generating
FORESHADOW (Slide 2) → Bridge to body with FOMO ("kalau lo skip...")
    ↓                 4 types: Steps Tease, Fear Urgency, Quiz, Visual Tease
BODY (Slides 3-N)  → Progressive value with emotional arc
    ↓                 Mini-hook at slide 5-7 re-engages committed swipers
CTA (Last Slide)    → 4 visual types matching engagement goal
                      Polarize | Question | Identity Tag | Engagement Reward
```

### 11. Emotional Arc System (NEW in v2.2.0)

Every carousel follows a "roller coaster" emotional pattern with visual treatment mapped per beat:

| Beat | Visual Treatment |
|------|-----------------|
| HIGH (Hook) | Extreme CU, 4:1 lighting, peak saturation, pattern interrupt |
| DIP (Foreshadow) | Pull back, muted palette, tension build |
| BUILD (Body) | Progressive saturation + tighter framing |
| MINI-HOOK (Mid) | Sudden change — angle shift, color disruption |
| CLIMAX (Reveal) | Peak drama, biggest text, most shareable insight |
| WARM (CTA) | Softest lighting, warmest tone, intimate connection |

---

## Installation

### From Marketplace (Recommended)

```bash
# Step 1: Add marketplace source
claude plugins marketplace add https://github.com/alisadikinma/sosmed-carousel-prompt-generator

# Step 2: Install plugin
claude plugins install sosmed-carousel-prompt-generator

# Optional: Choose scope
claude plugins install sosmed-carousel-prompt-generator --scope user    # All projects
claude plugins install sosmed-carousel-prompt-generator --scope project # This project only
```

### Manual Installation

```bash
# Clone to Claude Code marketplaces directory
git clone https://github.com/alisadikinma/sosmed-carousel-prompt-generator.git \
  ~/.claude/plugins/marketplaces/sosmed-carousel-prompt-generator
```

### Verify Installation

After installing, the plugin announces itself on every session start:

```
sosmed-carousel-prompt-generator loaded. Skills available:
  carousel-prompt-generator — cinematic AI image prompts for social media carousels
  validate-references — cross-file consistency checker (6 checks)
  new-localization — scaffold new localization files
```

The skill auto-triggers when you mention carousels, thumbnails, rebranding, or AI image prompts. You can also invoke it explicitly:

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
| `carousel-prompt-generator` | Subagent for batch carousel prompt work — reads references, verifies facts, asks about ambiguities, generates prompts + captions, writes output |

### Reference Docs (9 files, read on-demand)

| File | When Used |
|---|---|
| `creator-bible.md` | ALWAYS — creator identity, brand rules, gradient zones, holiday production, brand-in-image specs |
| `hook-science.md` | Hook slides — 5 hook categories (100-hook bank), CTA science (4 types + algorithm hierarchy), Gen-Z transcreation, engagement benchmarks, interactive hooks |
| `carousel-rebranding.md` | Converting third-party carousels to your brand |
| `platform-specs.md` | Nano Banana Pro specs, platform aspect ratios |
| `cinematography-lut.md` | Lighting, lens, film stock, atmosphere, DP signatures |
| `prompt-formulas.md` | Prompt templates, hook headline formula, foreshadow, CTA visual types, emotional arc, checklists |
| `localization-id.md` | Indonesian localization extras, holidays, AI bias countermeasures |
| `carousel-best-practices.md` | Carousel design, engagement benchmarks, algorithm signals |
| `caption-copywriting.md` | Caption formulas, emotional triggers, CTA psychology, hashtag strategy |

---

## The Workflow

```
User Request
    |
    v
[0] Ask for source URL (optional) ── extract caption + metadata
    |
    v
[1] Read creator-bible.md (ALWAYS)
    |
    v
[2] Read task-specific references
    |
    v
[3] Analyze input (enriched with source metadata if available)
    |                                    |
    v                                    v
[4a] FRESH CONTENT            [4b] REBRANDING
  Analyze brief/topic           Analyze source slides
  Set platform aspect ratio     Strip third-party branding
    |                                    |
    v                                    v
[5] VERIFY FACTS — web-search all claims
    |
    v
[6] PLOT EMOTIONAL ARC — assign beat + intensity per slide
    |
    v
[7] INTERACTIVE DESIGN — ask about ambiguous slides
    |
    v
[8] SCORE HOOK HEADLINE — 3/5 on Hook Scoring Gate
    |
    v
[9] Generate prompts (Engagement Funnel Order):
    ├── Slide 1: HOOK (category-matched visual + scored headline)
    ├── Slide 2: FORESHADOW (mandatory bridge with FOMO)
    ├── Slides 3-N: BODY (emotional arc + mini-hook at 5-7)
    └── Last: CTA (4 visual types matching engagement goal)
    |
    ├── Below 6/8? ──> REVISE
    |
    v
[10] Generate captions for all 4 platforms (Bahasa default)
    |
    v
[11] Output with verified sources + continuity checklist
```

---

## Capabilities

### Carousel Image Prompts
Generate cinematic Nano Banana Pro prompts for each carousel slide — Hook, Content, CTA — with text rendered in-image, proper creator face placement, brand consistency, and all 8 WOW elements.

### Carousel Rebranding
Upload any third-party carousel and get it fully converted to your brand: colors, lighting, style, branding elements. No third-party logos survive.

### Thumbnail Generation
Creator face at 50-60% frame, exaggerated emotion, topic visual, text rendered in-image. Optimized for click-through.

### Caption Copywriting (Auto, All Platforms)
Captions generated by default for IG + TikTok + LinkedIn + Threads with every carousel. Platform-specific character limits, truncation-safe hooks, 2-2-1 hashtag formula, emotional triggers, CTA psychology, and TikTok triple-layer keyword SEO. Default language: Bahasa Indonesia.

### Fact Verification
All factual claims (statistics, numbers, quotes) auto-verified via web search. Sources included per slide. Inaccurate claims flagged with corrections.

### Interactive Slide Design
Agent detects ambiguous slides and asks before generating — human figures (creator face or anonymous?), profession costumes, setting interpretations. Straightforward slides generated without asking.

### Indonesian Localization
Bahasa Indonesia is the default content language. Includes setting conversions, holiday adaptations with color palettes, and AI bias countermeasures.

---

## Hard Rules

These are non-negotiable across all generated prompts:

| Rule | Enforcement |
|---|---|
| No competitor branding | Zero competitor badges, logos, handles, or source category tags. Subject brand (Google, WhatsApp) KEPT for context |
| Brand icon + handle on every slide | Both at thirty percent opacity. Icon CENTER (above watermark). @handle CENTER (below icon). Vertical divider for comparison split-panel |
| Multi-keyword highlighting | 2-4 emotionally impactful keywords in accent color per headline — never just 1 word |
| Bahasa subtitle color | Bahasa subtitle line in accent color (never white like main headline) |
| Creator face placement | Hook, CTA, Thumbnail always. B-Roll with humans: ALWAYS (creator as most prominent figure) |
| Text rendered in-image | Headlines (MASSIVE billboard-scale, extra bold), accents, branding, SWIPE CTA — all in prompt |
| Default film stock | Kodak Portra 400 (warm golden, not cold) |
| Aspect ratio | Platform-specific: IG Feed 4:5, TikTok 9:16, LinkedIn 4:5 |
| Image resolution | 4K via Nano Banana Pro |
| WOW minimum | 6/8, all 8 elements mandatory |
| Default language | Bahasa Indonesia (English only if user requests) |
| Auto captions | All 4 platforms by default |
| Fact verification | All claims web-verified before output |
| SWIPE FOR MORE | "GESER UNTUK LANJUT >" on all slides except CTA |
| Page numbers | "[N]/[TOTAL]" in top-left corner on all slides |
| Hashtags | Max 5 (IG/TikTok), 3-5 (LinkedIn) |
| Suggested filenames | SEO-optimized per slide: `{N}-{topic}-{brand}-{type}.png` |

---

## Output Format

### Carousel Slide

```
## Slide [N]: [TYPE] — [Topic] | Emotion: [BEAT] ([intensity]/6)
Type: Hook / Foreshadow / Content / CTA | Creator Face: YES/NO | Platform: Nano Banana Pro

### Suggested Filename
`[N]-[topic-keywords]-[brand-handle]-[slide-type].png`

### Nano Banana Pro Prompt
[Full merged prompt: scene + cinematography + 8 WOW elements + text rendering + branding, 80-200 words]

### Verified Fact
"[Claim]" — ✓ Verified | Source: [URL]

### WOW: [N]/8
✓ Lighting Drama | ✓ Depth Layers | ✓ Atmosphere | ✓ Color Contrast
✓ Emotional Peak | ✓ Camera Intention | ✓ Texture Realism | ✓ Cinematic Ref
```

### Captions (Auto-Generated)

```
## Captions — All Platforms

### Instagram Caption ([N]/2,200 chars)
[Continuous caption — Bahasa Indonesia, 5 hashtags at end]

### TikTok Caption ([N]/4,000 chars)
[Continuous caption — casual Gen Z Bahasa, 5 hashtags at end]

### LinkedIn Caption ([N]/3,000 chars)
[Continuous caption — professional Bahasa, link inline, 3-5 hashtags at end]

### Threads Caption ([N]/500 chars)
[Continuous caption — conversational Bahasa, no hashtags]
```

**Note:** No section labels (Hook/Body/CTA/Hashtags) — each caption is one continuous text.

---

## Project Structure

```
sosmed-carousel-prompt-generator/
├── .claude-plugin/
│   ├── plugin.json              # Plugin metadata
│   └── marketplace.json         # Marketplace listing
├── hooks/
│   ├── hooks.json               # Hook definitions (SessionStart)
│   └── session-start.sh         # Session start announcement
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
│   ├── creator-bible.md         # Creator identity + brand-in-image + holidays
│   ├── hook-science.md          # Hook psychology, 5 categories, power words, scoring
│   ├── carousel-rebranding.md   # Rebranding conversion rules
│   ├── platform-specs.md        # Nano Banana Pro + platform specs
│   ├── cinematography-lut.md    # Lighting/lens/film stock LUT
│   ├── prompt-formulas.md       # Prompt templates + hook formula + foreshadow + CTA types + emotional arc
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

### Complete Slides

Text is rendered in the AI-generated image — headlines, accent words, branding, SWIPE CTA. You get a complete carousel slide, not a bare image that needs extensive post-production.

### Creator Consistency

Your face, your brand, your colors — injected verbatim into every prompt. The AI sees the same description every time, producing consistent results across hundreds of slides.

### Platform-Aware

Instagram carousels, TikTok Photo Mode carousels, LinkedIn document posts — each has different specs, aspect ratios, algorithm signals, and engagement patterns. Reference docs encode platform-specific best practices so prompts and captions are optimized for where they'll actually be posted.

### Caption-Ready

Captions aren't an afterthought — they're generated by default for all 4 platforms with every carousel. Platform-specific character limits, truncation-safe hooks, and the right hashtag count.

### Verified Facts

Every factual claim is web-searched and verified before it goes into a prompt. Sources are cited. Inaccurate data is flagged and corrected.

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
