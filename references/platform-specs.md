# Platform Specifications & Decision Matrix

## 1. Nano Banana Pro (PRIMARY IMAGE)

| Parameter | Value |
|-----------|-------|
| Model | `gemini-3-pro-image-preview` |
| Max Resolution | 4K (16MP) — API only |
| Aspect Ratios | 1:1, 2:3, 3:2, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9 |
| Reference Images | Up to 14 (5 faces + 6 objects) |
| Prompt Sweet Spot | 40-120 words |
| Text Rendering | Best-in-class (~75-80% accuracy) |
| Negative Prompts | NOT supported — use semantic exclusion at end |
| Temperature | Must be 1.0 |

### API Config (CRITICAL)
```python
config=types.GenerateContentConfig(
    response_modalities=['TEXT', 'IMAGE'],   # MANDATORY
    image_config=types.ImageConfig(
        aspect_ratio="9:16",
        image_size="4K"    # UPPERCASE K — "4k" silently fails → 1K
    ),
)
```

### Resolution Pricing
| Tier | Price |
|------|-------|
| 1K (default) | $0.07 |
| 2K | $0.13 (same as 1K — always use 2K minimum) |
| 4K | $0.24 |

## 2. VEO 3.1 (PRIMARY VIDEO)

| Parameter | Value |
|-----------|-------|
| Resolution | 720p (default), 1080p |
| Aspect Ratios | 16:9, 9:16 (no 1:1) |
| Frame Rate | 24fps fixed |
| Duration | 4, 6, 8 seconds |
| Max Tokens | 1,024 (optimal 100-150 words) |
| Extensions | +7s per hop, max 20 (~148s total) |
| Reference Images | Up to 3 |

### Audio Constraints
| Parameter | Limit |
|-----------|-------|
| Dialogue per 8s | 12-15 words MAX |
| Syllables per 8s | 20-25 MAX |
| Format | `[Character] says: "[dialogue]"` (COLON syntax) |
| Exclusions | "no subtitles, no audience sounds" |

### Pricing
| Quality | With Audio | Without |
|---------|-----------|---------|
| Standard | $0.40/s | $0.20/s |
| Fast | $0.15/s | $0.10/s |

### Lip Sync Requirements
- Face ≥20% of frame (MCU or CU)
- 3-6 second dialogue optimal
- Keywords: "clearly enunciates", "visible mouth openings"
- "no background music" for clean sync

## 3. Sora 2 (SECONDARY VIDEO)

| Parameter | Value |
|-----------|-------|
| Resolution | 1280×720 (std), 1792×1024 (pro) |
| Duration | 4s, 8s, 12s (API); up to 20s (Pro app) |
| Native Audio | Yes |
| Pricing | ~$0.10/s (std), ~$0.30-0.50/s (pro) |

### Key Strengths vs VEO
- Better multi-shot consistency
- Better physics simulation
- Longer single clips (up to 20s)
- Cameo feature for identity lock

### Key Weaknesses vs VEO
- Max 1080p (VEO has 4K)
- Lip-sync not as good as VEO
- Blocks face uploads (enterprise only)

## 4. DALL-E 3 (FALLBACK IMAGE)

| Parameter | Value |
|-----------|-------|
| Model | `dall-e-3` |
| Sizes | 1024×1024, 1792×1024, 1024×1792 |
| Quality | `standard` / `hd` (always use hd) |
| Style | `vivid` / `natural` (use vivid for cinematic) |
| Prompt Max | 4,000 characters |
| Reference Images | ❌ NOT supported |
| Negative Prompts | ❌ NOT effective |

## 5. Decision Matrix

### Image Platform
```
Creator face needed? → Nano Banana Pro
Complex composition? → Nano Banana Pro (thinking mode)
Text rendering critical? → Nano Banana Pro
Nano unavailable? → DALL-E 3 fallback
Quick iteration test? → Nano Banana Pro
```

### Video Platform
```
Dialogue ≤8s? → VEO 3.1
Need 4K? → VEO 3.1
Best lip-sync? → VEO 3.1
Complex physics? → Sora 2
Duration >8s single clip? → Sora 2
Multi-shot continuity? → Sora 2
Default? → VEO 3.1
```

### Social Platform → Aspect Ratio
| Platform | Aspect | Resolution |
|----------|--------|-----------|
| Instagram Reels / TikTok | 9:16 | 1080×1920 |
| Instagram Feed | 4:5 | 1080×1350 |
| YouTube | 16:9 | 1920×1080 |
| LinkedIn | 16:9 or 4:5 | 1920×1080 |
| Carousel (all) | 4:5 or 9:16 | 1080×1350 or 1080×1920 |
