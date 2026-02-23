# Prompt Formulas — Nano Banana Pro

## Golden Rule
```
Treat every prompt like a Creative Director brief — natural language, NOT keyword spam.
⚠ Use: "Maintain exact appearance from reference image" for character consistency
⚠ Text rendered IN-IMAGE — all headlines, accents, branding, and labels are part of the prompt
⚠ Default language for in-image text = Bahasa Indonesia (English only if user explicitly requests)
```

---

## Nano Banana Pro — Structure (8-Element Priority Order)
```
1. Subject (who/what) — always first
2. Action/pose
3. Setting/location
4. Camera/composition (shot type, angle)
5. Lighting/atmosphere (MUST include lighting pattern, ratio, Kelvin)
6. Style/medium (MUST include film stock, color grade)
7. Texture/cinematic detail (MUST include texture realism + DP reference)
8. In-image text rendering (headline, accent words, branding, labels)
```

All 8 elements are MANDATORY in every prompt. No exceptions.

---

## Text Rendering — In-Image (NOT Post-Production)

All user-facing text is rendered directly in the AI-generated image. The prompt MUST describe:

### Text Elements to Include
| Element | Where | Rule |
|---------|-------|------|
| Category tag | Centered above headline | Accent color, small caps (e.g., "TEKNOLOGI") |
| Headline | Bottom gradient zone | White #FFFFFF bold condensed ALL CAPS |
| Accent words | Within headline | Accent color (default: Golden Yellow #F5A623) |
| Brand icon | Top-right corner | Brand icon filename, every slide |
| @handle watermark | Below brand icon | White, 100% opacity on Hook/CTA, 30% on content |
| SWIPE FOR MORE > | Bottom center | White small text, all slides EXCEPT CTA |
| Slide counter | Optional | "3/10" format, small, top-left |

### Default Language
- In-image text (headlines, accent words, category tags) = **Bahasa Indonesia** by default
- English only if user explicitly requests
- Prompt instructions (scene description) = ALWAYS English (AI model instruction)

### Text Rendering Syntax in Prompt
```
Bottom [N]% dark gradient zone with bold white condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white [opacity]% below brand icon.
["GESER UNTUK LANJUT >" in small white text at bottom center. | omit for CTA slide]
```

---

## Templates

### Template — Creator Shot (Hook / CTA)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM].
[Expression keywords from cinematography-lut.md]. [Wardrobe]. [Action/pose].

[Setting/environment with specific details].
[Foreground element] + [subject] + [background with bokeh/depth].

Shot on [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K [key direction].
[Film stock], [color grade]. [Atmosphere/particles].
[Texture detail: natural skin texture with visible pores, fabric weave].
[Cinematic DP reference: "Deakins motivated lighting" / "Fraser atmospheric texture" etc.].

Bottom [N]% dark gradient zone with bold white condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white [100% for Hook/CTA]% below brand icon.
["GESER UNTUK LANJUT >" in small white text at bottom center. | omit for CTA]

[PLATFORM ASPECT] aspect ratio. No third-party branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

### Template — B-Roll / Topic Visual (No Creator Face)
```
A photorealistic cinematic [shot type] of [subject/scene].
[Detailed scene description]. [Context-specific elements].
[Foreground element] + [main subject] + [background depth layer].

Shot on [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere: haze/particles/volumetric].
[Texture detail: surface materials, environmental textures].
[Cinematic DP reference].

Bottom 35% dark gradient zone with bold white condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white 30% opacity below brand icon.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No third-party branding, no watermarks.
```

### Template — B-Roll with Human Figure (Creator Face Optional)
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM / anonymous figure].
[Context-appropriate expression]. [Profession-specific wardrobe OR creator default wardrobe].
[Scene description with human figure in context].
[Foreground element] + [subject] + [background depth layer].

Shot on [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern] at [ratio] ratio, [Kelvin]K.
[Film stock], [color grade]. [Atmosphere].
[Texture detail]. [Cinematic DP reference].

Bottom 35% dark gradient zone with bold white condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with the words "[KATA AKSEN]" in [accent color hex].
Small "[KATEGORI]" label in [accent color] small caps centered above headline.
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white 30% opacity below brand icon.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio. No third-party branding.
[IF creator face: MANDATORY: maintain exact facial identity from reference image: [face-ref.png].]
```

**NOTE:** When a B-Roll scene involves visible human figures, the agent MUST ask the user whether to use the creator's face or keep as anonymous figure. See Interactive Slide Design rules.

### Template — Thumbnail
```
A photorealistic cinematic thumbnail composition:

PRIMARY: [CREATOR DESCRIPTION VERBATIM], [EXAGGERATED HOOK EXPRESSION].
Expression: [specific exaggerated emotion] — wide eyes, raised brows,
[mouth position], energy that screams "KAMU HARUS LIHAT INI".
Position: Face occupies 50-60% of frame, positioned [left/right/center].

SECONDARY: [TOPIC VISUAL] — [description of topic element visible
in background or beside creator, e.g., AI interface, data visualization].
[Foreground detail] + [creator subject] + [topic visual background layer].

Shot on 85mm f/1.8, eye-level, slight dutch tilt (5-10°) for dynamic energy.
Rembrandt or Split lighting, 4:1-6:1 ratio, mixed warm face / cool topic element.
Strong rim light separating creator from background.
Kodak Vision3 500T, HIGH SATURATION, boosted contrast, vibrant teal-orange.
Natural skin texture with visible pores, fabric weave detail.
[Cinematic DP reference].

Bottom 25% dark gradient zone with bold white condensed ALL CAPS text
reading "[JUDUL THUMBNAIL DALAM BAHASA]" with key words in [accent color hex].
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white 100% below brand icon.

[PLATFORM ASPECT] aspect ratio. No third-party branding.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

### Template — Split-Panel
```
A photorealistic split-panel composition divided vertically into two halves.

LEFT HALF ("[LABEL A IN BAHASA]"): [Scene A] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, Kodak Portra 400.
[Texture: natural skin, fabric detail]. [DP reference].

RIGHT HALF ("[LABEL B IN BAHASA]"): Same person in same location but [CONTRAST VERSION].
[Contrasting visual elements]. Enhanced but still warm color temperature.
[Foreground + subject + background depth layers in each half].

Both halves: same environment context.
50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
[Atmosphere: haze, particles, or environmental effect].

Bottom 30% dark gradient zone with bold white condensed ALL CAPS text
reading "[HEADLINE IN BAHASA]" with accent words in [accent color hex].
[brand-icon.png] rendered in top-right corner.
"@[handle]" watermark in white below brand icon.
"GESER UNTUK LANJUT >" in small white text at bottom center.

[PLATFORM ASPECT] aspect ratio.
MANDATORY: maintain exact facial identity from reference image: [face-ref.png].
```

---

## Quality Checklists

### Image Prompt Checklist (All 8 WOW Elements)
Before finalizing each image prompt, verify ALL 8 are present:
- [ ] **Lighting Drama** — Lighting pattern named (Rembrandt, Loop, etc.) + ratio (2:1, 4:1) + Kelvin
- [ ] **Depth Layers** — Foreground element + subject + background (3 distinct layers)
- [ ] **Atmosphere** — Haze, particles, volumetric, fog, bokeh, or environmental effect
- [ ] **Color Contrast** — Warm-cool tension, accent color highlights, or complementary palette
- [ ] **Emotional Peak** — Expression keywords (if creator) or scene emotion (if B-Roll)
- [ ] **Camera Intention** — Shot type + lens + aperture + angle with purpose
- [ ] **Texture Realism** — Pores, fabric weave, surface materials, or environmental textures
- [ ] **Cinematic Ref** — Film stock named + color grade + optional DP reference

### Text Rendering Checklist
- [ ] Headline text specified in Bahasa Indonesia (or user-requested language)
- [ ] Accent words identified and color specified
- [ ] Category tag present
- [ ] Brand icon filename + position specified
- [ ] @handle watermark + opacity specified
- [ ] SWIPE FOR MORE present (or omitted for CTA)
- [ ] Gradient zone percentage matches slide type

### Thumbnail Checklist
- [ ] Creator face from reference image, 50-60% of frame
- [ ] Topic visual included (background/side element)
- [ ] Text overlay rendered in image (title in gradient zone)
- [ ] Expression EXAGGERATED (readable at 100x100px)
- [ ] High contrast, saturated colors
- [ ] Curiosity gap created — "What does he know?"
- [ ] Aspect ratio matches target platform
- [ ] All 8 WOW elements present

---

## Key Rules
- Natural language, NOT keyword spam
- **80-200 words optimal** (up to 250 for complex compositions with text)
- Negative constraints at END: "no third-party branding"
- Always specify reference image filename for creator shots
- **All 8 WOW elements MANDATORY** — minimum score 6/8
- **Text rendered IN-IMAGE** — no separate post-production section
- **Default text language = Bahasa Indonesia**
- API: `response_modalities=['TEXT', 'IMAGE']`, `image_size="4K"` (uppercase K)
- Aspect ratio set per target platform — see `references/platform-specs.md`
