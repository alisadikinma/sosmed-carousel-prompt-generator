# Carousel Rebranding Pipeline

## Overview
Transform third-party carousel designs into the user's branded content while preserving the educational value and visual impact.

## Step 1: Source Analysis

For each uploaded carousel, extract:
1. **Slide count** and sequence (Hook → Content → CTA)
2. **Per-slide content**: topic, key data/stats, visual concept
3. **Source style DNA**: color palette, typography, layout, branding elements
4. **Source elements to REMOVE**: competitor badges, logos, handles, watermarks, **source category tags** (e.g., "TECHNOLOGY" badge — this is the source creator's branding, NOT a content category to keep)
5. **Subject brands to KEEP**: logos/UI of the brand being DISCUSSED (Google, WhatsApp, etc.) — these provide essential context

Output a content map:
```
| Slide | Type | Topic | Key Data | Visual Concept | Remove |
```

## Step 2: Style Conversion Matrix

Convert source style → user's brand style using this mapping:

| Source Element | Conversion |
|----------------|---------------|
| Source accent color | → User's accent color |
| Cold tech background | → Warm amber/golden environment |
| Generic global setting | → Creator's locale context |
| Source creator badge/watermark | → DELETE completely (competitor branding) |
| **Subject brand** (Google, WhatsApp, etc.) | → **KEEP** — subject brand IS the context, must remain visible |
| No creator face | → ADD face on Hook + CTA |
| Source branding | → User's brand icon + handle (center watermark 30% opacity) |
| Cold color grading | → Kodak Portra 400 warm look |
| Blue HUD overlays | → Warm golden/amber HUD overlays |
| Small/weak text overlay | → **MASSIVE billboard-scale text** in gradient zone |

### Color Temperature Shift Rules
- Cold accent colors (blues, cyans) → shift to user's accent color
- Dark backgrounds stay dark but shift from blue-black → warm-black (hint of amber)
- Data overlays/HUDs: keep futuristic feel but use warm glow instead of cold
- Holographic elements: warm-toned holographic instead of cold-toned

## Step 3: Slide-by-Slide Prompt Generation

### Hook Slide Template
```
A photorealistic cinematic close-up of [CREATOR DESCRIPTION VERBATIM].
[EXAGGERATED HOOK EXPRESSION — e.g., wide shocked eyes, mouth open].
[WARDROBE]. [WARM ENVIRONMENT — e.g., modern cafe, lifestyle setting].

Shot on 85mm f/1.8, shallow depth of field with warm bokeh background.
Rembrandt lighting at 4:1 ratio, 3200K warm key from left.
Kodak Portra 400, warm golden grade. Subtle atmospheric haze.

Bottom 40% reserved for text overlay (dark gradient zone).
[PLATFORM ASPECT] aspect. No text, no watermarks, no logos.
Using facial identity from reference image: [face-ref.png].
```

### Content B-Roll Slide Template
```
A photorealistic cinematic [SHOT TYPE] of [TOPIC VISUAL CONCEPT].
[SPECIFIC SCENE DESCRIPTION with culturally relevant context].
[IF slide discusses a specific brand/product: include recognizable brand elements
(logo, UI, interface, color scheme) of the SUBJECT for viewer context.
Example: Google search bar visible, WhatsApp green chat UI, etc.]
[WARM-TONED HUD/data overlay elements showing KEY STAT].

Shot on [LENS]mm f/[APERTURE], [ANGLE]. [DEPTH OF FIELD].
[LIGHTING PATTERN], [RATIO], [KELVIN — always warm side].
Kodak Portra 400, warm golden amber grade. [ATMOSPHERE].

Bottom 35% dark gradient zone with extremely large, bold, impactful condensed
ALL CAPS text — MASSIVE billboard-scale, extra bold/black weight.
[brand-icon.png] in top-right corner.
"@[handle]" watermark in white at 30% opacity, CENTERED in the middle of the image.
"GESER UNTUK LANJUT >" in small white text at bottom center.
[PLATFORM ASPECT] aspect. No competitor branding (subject brand required for context).
No creator face in this slide.
```

### Split-Panel / Comparison Slide Template
```
A photorealistic split-panel composition divided vertically into two halves.

LEFT HALF ("[LABEL A IN BAHASA]"): [Current/old way scene] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, Kodak Portra 400.

RIGHT HALF ("[LABEL B IN BAHASA]"): Same person in same location but [CONTRAST VERSION].
Warm-toned holographic interfaces. Enhanced but still warm color temperature.

Both halves: same environment context.
50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
Bottom 30% dark gradient zone with extremely large, bold, impactful condensed
ALL CAPS text — MASSIVE billboard-scale, extra bold/black weight.
[brand-icon.png] + "@[handle]" watermark in white at 30% opacity,
placed ON the vertical center divider line between the two panels.
"GESER UNTUK LANJUT >" in small white text at bottom center.
[PLATFORM ASPECT] aspect. No competitor branding.
Using facial identity from reference image: [face-ref.png].
```

### CTA Slide Template
```
A photorealistic cinematic medium close-up of [CREATOR DESCRIPTION VERBATIM].
Wearing [WARDROBE].
Expression: warm confident smile, direct eye contact, approachable and inviting.
Arms crossed or relaxed professional pose.

Background: warm bokeh with soft golden ambient light, modern interior.
Shot on 85mm f/2, shallow DOF. Butterfly lighting 2:1, 3500K golden.
Kodak Portra 400, warm amber grade.

Bottom 40% reserved for text overlay + social handles.
[PLATFORM ASPECT] aspect. No text, no watermarks.
Using facial identity from reference image: [face-ref.png].
```

## Step 4: Text Overlay Guide (Per Slide)

For each slide, output a text specification sheet:

```
### Text Overlay — Slide [N]
- **Main headline**: "[TEXT]" — White #FFFFFF, EXTRA BOLD/BLACK weight condensed, ALL CAPS
  - Font must be MASSIVE — billboard-scale, dominating gradient zone
- **Accent keyword(s)**: "[WORD]" — [User's accent color], same massive size
- **Position**: Bottom 35-40%, centered
- **Branding**:
  - [User's brand icon] top-right corner
  - [User's @handle] CENTER of image, 30% opacity (ALL slides)
- **Subject brand** (if applicable): [Brand logo/UI] visible in scene for context
- **Corner labels**: [series name / episode ID] (if applicable)
- **SWIPE FOR MORE >**: Bottom center (all slides except CTA)
```

## Step 5: Visual Continuity Checklist

Before delivering carousel set, verify:

- [ ] ALL slides use consistent warm palette
- [ ] Accent color is consistent throughout
- [ ] NO competitor branding on ANY slide (source creator badges/watermarks removed)
- [ ] Subject brand visible where required (Google logo for Google stats, WhatsApp UI for WhatsApp data, etc.)
- [ ] Hook slide has creator face with exaggerated expression
- [ ] CTA slide has creator face with warm confident expression
- [ ] B-Roll with human faces = creator face ALWAYS included
- [ ] B-Roll without humans = NO creator face
- [ ] All slides have dark gradient text zone (bottom 30-40%) with MASSIVE billboard-scale text
- [ ] Brand icon in top-right of every slide
- [ ] @handle watermark CENTERED in image at 30% opacity on every slide
- [ ] SWIPE FOR MORE on all slides except CTA
- [ ] Film stock consistently warm (Portra 400 / Vision3 500T)
- [ ] Aspect ratio matches target platform (IG Feed 4:5, TikTok 9:16, LinkedIn 4:5)
