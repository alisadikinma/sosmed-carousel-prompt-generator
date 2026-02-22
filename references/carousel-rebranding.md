# Carousel Rebranding Pipeline

## Overview
Transform third-party carousel designs into the user's branded content while preserving the educational value and visual impact.

## Step 1: Source Analysis

For each uploaded carousel, extract:
1. **Slide count** and sequence (Hook → Content → CTA)
2. **Per-slide content**: topic, key data/stats, visual concept
3. **Source style DNA**: color palette, typography, layout, branding elements
4. **Third-party elements to REMOVE**: badges, logos, handles, watermarks

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
| Third-party badge | → DELETE completely |
| No creator face | → ADD face on Hook + CTA |
| Generic branding | → User's brand icon + handle |
| Cold color grading | → Kodak Portra 400 warm look |
| Blue HUD overlays | → Warm golden/amber HUD overlays |

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
[WARM-TONED HUD/data overlay elements showing KEY STAT].

Shot on [LENS]mm f/[APERTURE], [ANGLE]. [DEPTH OF FIELD].
[LIGHTING PATTERN], [RATIO], [KELVIN — always warm side].
Kodak Portra 400, warm golden amber grade. [ATMOSPHERE].

Bottom 35% reserved for text overlay (dark gradient zone).
[PLATFORM ASPECT] aspect. No third-party branding, no watermarks.
No creator face in this slide.
```

### Split-Panel Slide Template
```
A photorealistic split-panel composition divided vertically into two halves.

LEFT HALF ("[LABEL A]"): [Current/old way scene] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, Kodak Portra 400.

RIGHT HALF ("[LABEL B]"): Same person in same location but [CONTRAST VERSION].
Warm-toned holographic interfaces. Enhanced but still warm color temperature.

Both halves: same environment context.
50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
[PLATFORM ASPECT] aspect. Bottom 30% dark gradient for text.
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
- **Main headline**: "[TEXT]" — White #FFFFFF, condensed bold, ALL CAPS
- **Accent keyword(s)**: "[WORD]" — [User's accent color]
- **Position**: Bottom 35%, centered
- **Branding**:
  - [User's brand icon] [position: centered top / on divider]
  - [User's handle] below icon [opacity: 30% / 100% for hook]
- **Corner labels**: [series name / episode ID] (if applicable)
- **SWIPE FOR MORE >**: Bottom center (slides 1-3 only)
```

## Step 5: Visual Continuity Checklist

Before delivering carousel set, verify:

- [ ] ALL slides use consistent warm palette
- [ ] Accent color is consistent throughout
- [ ] NO third-party branding on ANY slide
- [ ] Hook slide has creator face with exaggerated expression
- [ ] CTA slide has creator face with warm confident expression
- [ ] Content slides have NO creator face (unless split-panel)
- [ ] All slides have dark gradient text zone (bottom 30-40%)
- [ ] Brand icon placement specified for every slide
- [ ] Handle specified for every slide
- [ ] SWIPE FOR MORE on slides 1-3 only
- [ ] Film stock consistently warm (Portra 400 / Vision3 500T)
- [ ] Aspect ratio matches target platform (IG Feed 4:5, TikTok 9:16, LinkedIn 4:5)
