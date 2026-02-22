# Creator Bible — Template

## 1. Character Bible (USER MUST CUSTOMIZE)

Replace this template with the creator's actual physical description. This description is used VERBATIM in every creator-facing prompt for AI consistency.

```
[Age]-year-old [ethnicity/nationality] [gender] with [hair description] and [face shape].
[Skin tone] with natural texture and visible pores.
[Eye description] [glasses if applicable].
[Facial hair], with a [expression style] expression.
```

**Example:**
```
A 30-year-old Southeast Asian woman with long black hair and oval face shape.
Medium warm skin undertone with natural texture and visible pores.
Dark brown almond-shaped eyes with minimal makeup.
Confident, warm expression.
```

Face reference file: `[creator-face-ref.png]`
Prompt instruction: `"using facial identity from reference image: [creator-face-ref.png]"`

## 2. Branding Assets

| Asset | File | Usage |
|-------|------|-------|
| Brand icon/logo | `[brand-icon.png]` | Carousel divider, header branding |
| Face reference | `[creator-face-ref.png]` | AI face generation reference |

## 3. Branding Rules (HARD — NON-NEGOTIABLE)

### ALWAYS include:
- Brand icon centered on vertical divider (content slides)
- @handle below icon, 30% opacity (Hook = 100% opacity)
- Corner labels where applicable: series name, episode number
- "SWIPE FOR MORE >" on slides 1-3 only (data-backed: 20-30% engagement boost)

### NEVER include:
- Third-party badges, brand logos, other handles
- Other creator watermarks
- Generic stock branding elements

### CTA Slide Additions:
- Social handles (IG, TikTok, LinkedIn, etc.)
- Website URL
- Tagline below main text

## 4. Style DNA — Visual Identity

### Color Palette
| Role | Color | Hex |
|------|-------|-----|
| Primary text | White | #FFFFFF |
| Accent keyword | [User's accent] | [User's hex, default #F5A623] |
| Background mood | Warm amber/golden | — |
| Secondary accent | Soft gold | #D4AF37 |

### Typography (Post-Production)
- Headlines: Condensed bold sans-serif (Oswald / Bebas Neue family)
- ALL CAPS for main headlines
- Mixed case for subtitles/taglines
- Text hierarchy: Large bold title > medium subtitle > small tagline

### Film Stock & Color Temperature
| Context | Film Stock | Kelvin | Grade |
|---------|-----------|--------|-------|
| Default / warm | Kodak Portra 400 | 3200-3500K | Warm golden amber |
| Dramatic | Kodak Vision3 500T | 3200K | Rich warm shadows |
| Vivid/saturated | Kodak Ektar 100 | 5600K | Punchy warm colors |
| Night/moody | CineStill 800T | 3200K | Warm halation |

**Default to warm palettes unless the creator's brand explicitly uses cool tones.**

### Background & Setting Preferences
- Customize to creator's locale and brand identity
- Warm lifestyle environments: brick walls, Edison bulbs, warm bokeh
- Professional: Modern office with warm lighting
- Avoid: Generic sterile settings, cold corporate

## 5. Creator Face Allocation

| Slide Type | Creator Face? | Expression | Shot Type |
|------------|---------------|------------|-----------|
| HOOK | YES | Exaggerated (shock, curiosity, excitement) | CU/MCU |
| Content body | NO | — | B-roll topic visuals |
| Split-panel (with creator) | YES | Context-appropriate | MS/MWS |
| CTA | YES | Warm, confident, inviting | MCU |
| Thumbnail | YES | Exaggerated curiosity gap | CU tight |

## 6. Wardrobe Defaults

| Context | Wardrobe |
|---------|----------|
| Professional/Tech | Blazer, open-collar shirt |
| Casual/Lifestyle | Henley, hoodie, or denim jacket |
| Street/Outdoor | Denim jacket over solid tee |

*Customize to creator's actual wardrobe preferences.*

## 7. Text Gradient Zone Allocation (Single Source of Truth)

| Slide Type | Gradient Zone | Prompt Instruction |
|------------|--------------|-------------------|
| Hook | Bottom 40% | "Bottom 40% reserved for text overlay (dark gradient zone)" |
| Content B-Roll | Bottom 35% | "Bottom 35% reserved for text overlay (dark gradient zone)" |
| Split-Panel | Bottom 30% | "Bottom 30% dark gradient for text" |
| CTA | Bottom 40% | "Bottom 40% reserved for text overlay + social handles" |
| Thumbnail | Bottom 25% | "Bottom 25% dark gradient for title text" |

All gradient zones use a smooth dark-to-transparent gradient (not a hard cut).

## 8. Lighting for Creator's Features

Customize lighting based on creator's physical features (hair, face shape, glasses, skin tone, etc.)

### Recommended Default Setups
| Content | Lighting | Ratio | Kelvin | Lens |
|---------|----------|-------|--------|------|
| Hook | Rembrandt | 4:1 | 3200K | 85mm f/1.8 |
| CTA | Butterfly | 2:1 | 3500K | 85mm f/2 |
| Split-panel | Loop + rim | 3:1 | 3500K | 50mm f/2.8 |
| Thumbnail | Rembrandt/Split | 4:1-6:1 | Mixed | 85mm f/1.8 |

## 9. Wardrobe x Lighting Notes

How wardrobe interacts with lighting — adjust fill, flags, and edge lights accordingly.

| Wardrobe | Lighting Note |
|----------|--------------|
| Dark blazer/jacket | Absorbs well, good skin contrast — works with all setups |
| White/light shirt | Can blow out — reduce fill or flag shirt area |
| Dark henley/polo | Needs edge light for separation on dark backgrounds |
| Dark suit | Very absorbent — requires rim/edge light for definition |

> **Note:** Customize these setups based on the creator's physical features (see Section 1.3 and 1.4 in RAG source — Creator Cinematography and Holiday Production Guide — for detailed examples of how hair type, face shape, glasses, and skin tone affect lighting choices).

## 10. Background by Mood

Match background treatment to the emotional tone of each slide or content piece.

| Mood | Background | Depth | Color Relationship |
|------|-----------|-------|-------------------|
| Professional authority | Dark, minimal | Deep bokeh f/1.8-2.8 | Contrast with skin |
| Approachable teaching | Office context | Moderate blur f/4 | Complementary |
| Tech credibility | Monitor/screen elements | Soft glow bokeh | Cool BG, warm face |
| Casual connection | Home/lifestyle hint | Moderate blur | Warm, inviting |

## 11. Holiday Content Production

Holiday content bridges personal brand identity with seasonal themes. The goal is to feel festive without losing professional credibility — warm and celebratory, but still unmistakably *you*.

### 11.1 The 70/30 Rule

Holiday atmosphere should occupy **70-80%** of the composition, with professional/tech identity taking up **20-30%**. This ensures the seasonal mood dominates while your brand stays recognizable.

**Prompt element order:**
1. Holiday scene (dominant visual — sets the mood)
2. Subject with professional cues (wardrobe, posture, setting)
3. Subtle tech elements (pick 1-2 max — do not overcrowd)
4. Atmosphere + technical specs (film stock, lighting, lens)

### 11.2 Holiday Film Stock Pairing

Each holiday has a natural color palette. Match film stock to amplify the holiday's inherent mood.

| Holiday | Best Film Stock | Reason |
|---------|----------------|--------|
| Christmas / Valentine's | Kodak Portra 400 | Warm skin, nostalgic warmth |
| Chinese New Year / Imlek | Kodak Ektar 100 | Vivid saturated reds/golds |
| Eid al-Fitr / Lebaran | Fujifilm Pro 400H | Cool greens, soft pastels |
| Diwali / New Year's Eve | Kodak Vision3 500T | Tungsten drama, rich blacks |
| Thanksgiving | Kodak Portra 400 | Warm earth tones |

### 11.3 Natural Tech Props (Pick 1-2 for Professional Identity Blend)

These props allow you to weave professional/tech identity into holiday scenes without breaking the festive mood.

| Prop | Description |
|------|-------------|
| Laptop | Casually open near holiday setting, showing AI workflow diagrams |
| Holographic display | Blue-cyan glow contrasting warm holiday tones |
| Smartwatch | Subtly displaying AI metrics |
| Transparent tablet | Reflecting holiday lights, showing neural network viz |
| Code patterns | Integrated into frost, snowflakes, or decorative elements |

**Key insight:** Warm analog holiday lighting vs cool blue tech glow = natural cinematic color temperature tension. This contrast makes the image visually compelling without feeling forced.

### 11.4 Photorealism + Holiday Magic Balance

Holiday content walks a line between realistic and magical. The rule: keep the **subject hyperrealistic** and let the **environment carry the magic**.

- **Subject = hyperrealistic:** natural skin texture, visible pores, real fabric weave, subtle imperfections
- **Magical elements = ambient/environmental:** "subtle golden particles floating lazily," "soft ethereal glow from decorations"
- **Booster keywords:** RAW photo, 8K UHD, natural skin texture with visible pores, film grain, high dynamic range

> Never apply magical effects directly to the subject's face or body. Keep magic in the air, the light, and the decorations.

### 11.5 Posting Strategy

Timing matters. Holiday content performs best when it builds anticipation, not when it arrives late.

| Timing | Action |
|--------|--------|
| 3-4 weeks before | Generate images (iterate, refine, select hero shots) |
| 2 weeks before | Post teaser/BTS content (process shots, prompt breakdowns) |
| Holiday day | Publish hero image |
| After holiday | "How I made this" tutorial (educational content with high shelf life) |

**Platform note:** LinkedIn holiday engagement increases ~18% in December; tech-focused accounts see up to 5x more impressions during holiday periods. Plan your best content accordingly.
