# Prompt Formulas — All Platforms

## Golden Rule
```
IMAGE prompt = ALL VISUALS (subject, lighting, lens, color, atmosphere)
VIDEO prompt = MOTION ONLY (camera movement, micro-motion, audio)
⚠ NEVER duplicate visual details in video prompt
⚠ Use: "Maintain exact appearance from reference image"
```

---

## Nano Banana Pro (PRIMARY)

### Structure (6-Element Priority Order)
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
9:16 vertical aspect. No text, no watermarks, no logos.
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
9:16 vertical aspect. No third-party branding, no watermarks.
```

### Key Rules
- Natural language, NOT keyword spam
- 40-120 words optimal (up to 200 for complex)
- Negative constraints at END: "no text overlays, no artifacts"
- Always specify reference image filename for creator shots
- API: `response_modalities=['TEXT', 'IMAGE']`, `image_size="4K"` (uppercase K)

---

## VEO 3.1 (PRIMARY VIDEO)

### 5-Part Formula
```
[Cinematography] + [Subject] + [Action] + [Context] + [Style & Ambiance]
```

### Template — I2V Motion Prompt
```
~[N] seconds, 1080p, 9:16.

Camera: [VEO-verified movement term], [speed].

Subject motion: [micro-movements — blinks, breathing, subtle gestures].
Expression shift: [if any emotional change].

Ambient motion: [particles, environmental elements].

Audio: [specific ambient], [music or no music].
[Character] says: "[max 15 words]" (if dialogue)
No subtitles, no audience sounds, no text overlays.

Transition: [end instruction].
Maintain exact lighting, environment, and appearance from reference image.
```

### Audio Rules
- Dialogue: ≤15 words per 8s clip
- Lip-sync format: `[Character] says: "[text]"` (COLON syntax)
- Face must be ≥20% of frame for lip-sync
- Always specify audio — unspecified = random sounds
- Required: "no subtitles, no audience sounds"

### VEO-Verified Camera Terms
Push: `smooth dolly push-in` / `gentle dolly push-in`
Pull: `dolly-out` / `gentle dolly pull-back`
Lateral: `tracking shot following subject` / `truck left/right`
Rotation: `slow pan left/right` / `orbit shot circling subject`
Vertical: `crane shot rising` / `tilt up/down`
Style: `handheld camera` / `Steadicam floating movement`
Static: `static shot` / `locked-off shot`

---

## Sora 2 (SECONDARY VIDEO)

### Template — I2V Prompt
```
[Scene action — what happens from starting point]

Cinematography:
Camera: [framing + single movement]
Lens: [focal length + DOF]
Lighting: [key source, fill, color temperature]
Mood: [emotional tone]

Actions:
- [Beat 1: 0-2s]
- [Beat 2: 2-4s]

Dialogue (if needed): "[brief natural lines]"
```

### Key Rules
- ONE camera move + ONE subject action per shot
- Beat-based timing: `(0-2s)`, `(2-4s)`
- 50-200 words optimal
- Two 4s clips > one 8s clip for quality
- Explicit physics descriptions

---

## DALL-E 3 (FALLBACK ONLY)

### When to Use
- Nano Banana Pro unavailable
- API pipeline automation needed
- Text rendering critical (signs, posters)

### Template
```
[Camera spec: "Shot on 85mm f/1.4"]. [Subject description from creator bible
VERBATIM]. [Action/pose]. [Environment]. [Lighting: "Rembrandt lighting,
3200K warm"]. [Film stock: "Kodak Portra 400"]. [Atmosphere].
Photorealistic, natural skin texture.
```

### Rules
- Model: `dall-e-3`, Quality: `hd`, Style: `vivid`
- Size: `1024x1792` (9:16)
- No negative prompts — positive framing only
- No reference image support — use character bible verbatim
- Automatic prompt rewriting (prefix with "My prompt has full detail:")
