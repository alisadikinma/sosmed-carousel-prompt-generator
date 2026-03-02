# Video Prompt Specs — Grok 3 Imagine Video (Basic Mode)

## 1. Platform Overview

| Setting | Value |
|---------|-------|
| Model | Grok 3 (Aurora engine) |
| Mode | Basic prompt (single text field) + Image Reference |
| Capability | Image-to-video animation with auto-generated SFX/audio |
| Resolution | 720p (HD) recommended |
| Duration | 6s (default) or 10s |
| Orientation | Landscape 16:9, Portrait 9:16, Square 1:1, **Vertical 2:3** (carousel default), Horizontal 3:2 |

## 2. Orientation Mapping (Carousel → Grok 3)

| Carousel Format | Carousel Ratio | Grok 3 Orientation |
|-----------------|---------------|-------------------|
| IG Feed | 4:5 | **Vertical (2:3)** — closest match |
| TikTok/Reels | 9:16 | Portrait (9:16) — exact match |
| LinkedIn | 4:5 or 1:1 | Vertical (2:3) or Square (1:1) |

## 3. Image-to-Video Prompting Rules

The carousel image IS the video frame — Grok 3 animates it with motion + SFX.

**Core rules:**
- Image already contains the scene — do NOT re-describe static elements
- Prompt describes ONLY what **MOVES** and what **SOUNDS**
- Keep it short and direct (2-4 sentences, ~50-100 words)
- First 20-30 words weighted most heavily by the model
- Negative prompts do NOT work in Grok 3
- Formula: `[motion description] + [camera movement] + [text preservation] + [SFX/audio direction]`

### HARD RULE: Text Preservation + Interactive Elements

All text elements baked into the carousel image MUST remain visible and readable throughout the entire video:
- **Headline** (bottom gradient zone) — stays sharp from first to last frame
- **Creator brand icon + @handle watermark** — stays visible
- **Page number** (top-left) — stays visible
- **English subtitle** — stays visible

**EXCEPTION — Animated text elements:**
- **"SWIPE (GESER) >"** — animate with a subtle repeating slide-right / bounce-right motion to encourage swiping. This is an interactive cue, NOT static
- **CTA slide text** — animate with attention-grabbing motion (pulse, glow, scale up) to drive engagement

**To achieve text preservation:**
- Animate ONLY the visual scene area (top portion of image)
- Keep camera movements SLOW and SUBTLE — no fast zooms, no extreme pans
- Avoid push-in that crops out the bottom text zone
- Avoid rotation or shake that blurs text
- Prefer: slow drift, subtle parallax, locked camera with subject motion
- If camera pushes in, frame it so text zone is never cut off
- Explicitly state in prompt: "all text, headline, branding, and watermark remain sharp and readable throughout. The SWIPE text gently pulses or slides right repeatedly as an interactive cue"

## 4. SFX & Audio Vocabulary

### War / Military
- gunfire, rapid gunfire bursts, distant explosions
- bullet impacts on metal, ricochet sounds
- missile launch roar, rocket exhaust whoosh
- laser beam hum, energy weapon charging whine
- radar ping, sonar sweep, electronic warning beeps
- military radio chatter, command center ambient hum
- helicopter blades, jet flyby

### Atmospheric / Environmental
- wind howling, desert wind gusting
- dust and debris settling
- distant thunder rumble
- ocean waves, rain
- city ambient noise, traffic hum

### Technology / Data
- holographic display hum, data processing beeps
- keyboard typing, console alert tones
- digital interface whoosh, futuristic UI sounds
- power-up surge, energy shield activation hum
- satellite communication static crackle

### Emotional / Cinematic
- dramatic orchestral swell (hook/climax)
- tension building low drone (foreshadow)
- heartbeat pulse (urgency)
- warm ambient music (CTA)
- silence then sudden impact (mini-hook)
- cinematic bass drop

### Human
- breathing (heavy, calm, nervous)
- footsteps on different surfaces
- armor/leather creaking
- crowd murmur, gasp

## 5. Camera Movement Vocabulary

| Movement | When to Use | Prompt Fragment |
|----------|------------|-----------------|
| slow push-in | Emotional close-up, hook reveal | "camera slowly pushes in toward face" |
| slow pull-out | Reveal scale, establishing | "camera slowly pulls back revealing the full scene" |
| slow pan left/right | Environmental scanning | "camera slowly pans right across the landscape" |
| slight drift | Subtle life, CTA warmth | "camera gently drifts to the right" |
| static / locked | Focus on subject action only | "camera stays locked, subject moves" |
| tilt up/down | Vertical reveal, awe | "camera slowly tilts upward" |
| handheld sway | Urgency, documentary feel | "subtle handheld camera movement" |
| locked + shake | Impact, explosion reaction | "camera stays locked with subtle shake from impacts" |

**Rule: ONE camera movement per prompt.** Never combine multiple competing moves.

## 6. Per-Slide-Type Animation & SFX Guide

### HOOK (Slide 1)
| Setting | Value |
|---------|-------|
| Duration | 6s (punchy) or 10s (complex action) |
| Motion | HIGH energy — main action plays out (bullets, explosions, dramatic gesture) |
| Camera | slow push-in or static with subject action |
| SFX | loud, dramatic, impactful — match the visual shock |
| Text | headline sharp, SWIPE slides right repeatedly |

### FORESHADOW (Slide 2)
| Setting | Value |
|---------|-------|
| Duration | 6s |
| Motion | SUBTLE — slow atmospheric shift, smoke drifting, slight body movement |
| Camera | slight drift or static |
| SFX | tension drone, subtle ambient, quiet before the storm |
| Text | headline sharp, SWIPE slides right repeatedly |

### BODY — Tech / Military
| Setting | Value |
|---------|-------|
| Duration | 6s |
| Motion | operational — systems activating, data flowing, mechanical movement, light pulsing |
| Camera | slow pan or static |
| SFX | technology sounds — hum, beeps, mechanical, energy |
| Text | headline sharp, SWIPE slides right repeatedly |

### BODY — Data / Stats
| Setting | Value |
|---------|-------|
| Duration | 6s |
| Motion | holographic data animation, screen glow pulsing, ambient room activity |
| Camera | slight drift or static |
| SFX | command center ambient, console sounds, subtle electronic |
| Text | headline sharp, SWIPE slides right repeatedly |

### BODY — Epic / Climax
| Setting | Value |
|---------|-------|
| Duration | 10s (dramatic payoff) |
| Motion | maximum drama — shields pulsing, missiles impacting, energy rippling |
| Camera | slow pull-out to reveal scale |
| SFX | orchestral swell, impact sounds, cinematic crescendo |
| Text | headline sharp, SWIPE slides right repeatedly |

### CTA (Last Slide) — INTERACTIVE ENGAGEMENT
| Setting | Value |
|---------|-------|
| Duration | 10s (more time to absorb + act) |
| Motion | INVITING + INTERACTIVE — creator expression shifts warmly, hand gesture beckons viewer, bokeh particles drift, social media icons glow/pulse one by one, CTA headline text pulses or scales up subtly |
| Camera | very slow push-in toward creator face (intimate, conversational) |
| SFX | warm uplifting ambient music, subtle notification chime when social icons appear, inviting conversational tone |
| Text | CTA question text pulses to draw attention, social icons glow one by one, NO SWIPE on CTA |
| Goal | make viewer feel personally addressed, compelled to comment/share/follow |

## 7. Prompt Templates (Basic Mode)

### Non-CTA Slides

```
[Primary motion in the visual scene area — what moves/animates]. [Camera movement — one single subtle move]. All text, headline, branding, and watermark remain sharp and readable throughout, the SWIPE text gently slides right repeatedly as an interactive cue. [SFX/audio — specific sounds matching the scene and emotional beat].
```

### CTA Slide

```
[Creator motion — expression shift, hand gesture, inviting body language]. [Camera movement — slow push-in for intimacy]. All headline and branding text remains sharp and readable throughout, the CTA question text subtly pulses to draw attention, social media icons glow one by one. [SFX/audio — warm, inviting, notification chimes].
```

### Example Prompts

**Hook — ancient warrior vs bullets:**
> Bullets slam into the bronze shield creating sparks and metal fragments flying outward, the warrior flinches and screams behind the shield, smoke and dust swirl around the impact zone. Camera stays locked with subtle shake from impacts. All text, headline, branding, and watermark remain sharp and readable throughout, the SWIPE text gently slides right repeatedly. Loud rapid gunfire bursts, bullet ricochets on metal shield, shell casings clinking on stone ground, dramatic cinematic bass impact.

**Body — satellite in space:**
> The satellite's solar panels slowly rotate catching sunlight, the cyan scanning beam sweeps across Earth's curved surface below, a missile exhaust trail rises from the atmosphere. Camera stays locked on the satellite. All text, headline, branding, and watermark remain sharp and readable throughout, the SWIPE text gently slides right repeatedly. Subtle space ambient hum, faint electronic scanning beeps, distant rocket exhaust whoosh.

**Body — energy shield climax:**
> Missiles impact the glowing hexagonal energy shield dome creating rippling golden shockwaves across the surface, explosion debris scatters outward, the shield pulses brighter with each hit while the city lights below remain peaceful. Camera slowly pulls back revealing the full scale of the shield dome. All text, headline, branding, and watermark remain sharp and readable throughout, the SWIPE text gently slides right repeatedly. Dramatic orchestral crescendo, deep shield energy hum, missile impact explosions, cinematic bass swell.

**CTA — interactive engagement:**
> The creator's expression shifts into a warm curious smile, eyebrow raises slightly, one hand gestures toward camera invitingly as if asking a question, soft golden bokeh particles drift in the warm background, the social media icons glow and pulse gently one by one. Camera slowly pushes in toward the creator's face creating intimate eye contact. All headline and branding text remains sharp and readable throughout, the CTA question text subtly pulses to draw attention. Warm uplifting ambient music, subtle notification chime, inviting conversational tone.

## 8. Quality Checklist

| # | Check | Required |
|---|-------|----------|
| 1 | Motion matches slide emotional beat (HIGH/DIP/BUILD/CLIMAX/WARM) | ALL |
| 2 | Only ONE camera movement (not multiple competing moves) | ALL |
| 3 | No re-description of static image elements | ALL |
| 4 | SFX/audio direction is specific (not just "add sound") | ALL |
| 5 | Duration appropriate: 6s default, 10s for hook/climax/CTA | ALL |
| 6 | Headline + subtitle + brand + page number remain sharp and readable | ALL |
| 7 | SWIPE (GESER) has sliding/pulsing animation cue | Non-CTA |
| 8 | CTA text has interactive pulse/glow animation cue | CTA only |
| 9 | CTA social icons animate (glow one by one) | CTA only |
| 10 | Text preservation instruction explicitly stated in prompt | ALL |

## 9. Common Mistakes

| Mistake | Fix |
|---------|-----|
| Re-describing the entire scene | Only describe what MOVES and SOUNDS — image already has the scene |
| Multiple camera moves | Pick ONE — slow push-in OR pan, not both |
| No SFX direction | Always include specific audio cues |
| Generic audio ("add music") | Be specific: "dramatic orchestral swell" or "rapid gunfire bursts" |
| Too long for simple scene | 6s is enough for most slides — only hook/climax/CTA need 10s |
| Complex hand/finger motion | Keep hand actions simple — Grok struggles with detailed fingers |
| Extreme camera that blurs text | Keep moves slow and subtle — headline must stay readable |
| Text zone cropped out | Avoid push-in that frames out bottom half gradient zone |
| SWIPE not animated | Always include "SWIPE text gently slides right repeatedly" in prompt |
| CTA too passive | CTA must have interactive elements: text pulse, icon glow, beckoning gesture |

## 10. Grok 3 UI Settings Quick Reference

| Setting | Default for Carousel Animation |
|---------|-------------------------------|
| Model | Grok 3 |
| Image Reference | Select the carousel PNG for each slide |
| Generation Mode | Custom |
| Prompt | Basic (single text field) |
| Orientation | Vertical (2:3) for IG 4:5 carousel |
| Resolution | High 720p (HD) |
| Duration | 6s default — 10s for hook/climax/CTA |
