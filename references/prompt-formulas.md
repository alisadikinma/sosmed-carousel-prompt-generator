# Prompt Formulas — Nano Banana Pro

## Golden Rule
```
Treat every prompt like a Creative Director brief — natural language, NOT keyword spam.
⚠ Use: "Maintain exact appearance from reference image" for character consistency
```

---

## Nano Banana Pro — Structure (6-Element Priority Order)
```
1. Subject (who/what) — always first
2. Action/pose
3. Setting/location
4. Camera/composition (shot type, angle)
5. Lighting/atmosphere
6. Style/medium
```

### Template — Creator Shot
```
A photorealistic cinematic [shot type] of [CREATOR DESCRIPTION VERBATIM].
[Expression]. [Wardrobe]. [Action/pose].

[Setting/environment with specific details].

Shot on [lens]mm f/[aperture], [angle], [depth of field].
[Lighting pattern], [ratio], [Kelvin]K, [key direction].
[Film stock], [color grade]. [Atmosphere/particles].

Bottom [N]% reserved for text overlay (dark gradient zone).
[PLATFORM ASPECT] aspect. No text, no watermarks, no logos.
Using facial identity from reference image: [face-ref.png].
```

### Template — B-Roll / Topic Visual
```
A photorealistic cinematic [shot type] of [subject/scene].
[Detailed scene description]. [Context-specific elements].
[Optional: warm-toned HUD/data overlay showing key statistic].

Shot on [lens]mm f/[aperture], [angle]. [Depth of field].
[Lighting pattern], [ratio], [Kelvin]K.
[Film stock], [color grade]. [Atmosphere].

Bottom 35% dark gradient zone for text overlay.
[PLATFORM ASPECT] aspect. No third-party branding, no watermarks.
```

### Template — Thumbnail
```
A photorealistic cinematic thumbnail composition:

PRIMARY: [CREATOR DESCRIPTION VERBATIM], [EXAGGERATED HOOK EXPRESSION].
Expression: [specific exaggerated emotion] — wide eyes, raised brows,
[mouth position], energy that screams "YOU NEED TO SEE THIS".
Position: Face occupies 50-60% of frame, positioned [left/right/center].

SECONDARY: [TOPIC VISUAL] — [description of topic element visible
in background or beside creator, e.g., AI interface, data visualization].

Shot on 85mm f/1.8, eye-level, slight dutch tilt (5-10°) for dynamic energy.
Rembrandt or Split lighting, 4:1-6:1 ratio, mixed warm face / cool topic element.
Strong rim light separating creator from background.
Kodak Vision3 500T, HIGH SATURATION, boosted contrast, vibrant teal-orange.

Bottom 25% dark gradient for title text.
[PLATFORM ASPECT] aspect. No text, no watermarks.
Using facial identity from reference image: [face-ref.png].
```

### Template — Split-Panel
```
A photorealistic split-panel composition divided vertically into two halves.

LEFT HALF ("[LABEL A]"): [Scene A] featuring [CREATOR].
[Context-appropriate setting]. Natural warm daylight, Kodak Portra 400.

RIGHT HALF ("[LABEL B]"): Same person in same location but [CONTRAST VERSION].
[Contrasting visual elements]. Enhanced but still warm color temperature.

Both halves: same environment context.
50mm f/2.8, eye-level. Warm golden hour lighting bridging both panels.
[PLATFORM ASPECT] aspect. Bottom 30% dark gradient for text.
Using facial identity from reference image: [face-ref.png].
```

---

## Quality Checklists

### Image Prompt Checklist
Before finalizing each image prompt:
- [ ] Shot type specified (CU, MCU, MS, etc.)
- [ ] Lens specified (mm + aperture)
- [ ] Lighting pattern named (Rembrandt, Loop, etc.)
- [ ] Lighting ratio specified (2:1, 4:1, etc.)
- [ ] Color temperature in Kelvin
- [ ] Film stock named
- [ ] Atmosphere specified (even if "clean")
- [ ] Aspect ratio matches target platform
- [ ] Face reference included (if creator shot)
- [ ] Wardrobe specified
- [ ] Text gradient zone noted (see `references/creator-bible.md` Section 7)

### Thumbnail Checklist
- [ ] Creator face from reference image, 50-60% of frame
- [ ] Topic visual included (background/side element)
- [ ] Text overlay zone reserved for title
- [ ] Expression EXAGGERATED (readable at 100×100px)
- [ ] High contrast, saturated colors
- [ ] Curiosity gap created — "What does he know?"
- [ ] Aspect ratio matches target platform

---

## Key Rules
- Natural language, NOT keyword spam
- 40-120 words optimal (up to 200 for complex compositions)
- Negative constraints at END: "no text overlays, no artifacts"
- Always specify reference image filename for creator shots
- API: `response_modalities=['TEXT', 'IMAGE']`, `image_size="4K"` (uppercase K)
- Aspect ratio set per target platform — see `references/platform-specs.md`
