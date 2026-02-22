# Platform Specifications — Nano Banana Pro + Social Carousel

## 1. Nano Banana Pro (IMAGE GENERATION)

| Parameter | Value |
|-----------|-------|
| Model (Pro) | `gemini-3-pro-image-preview` |
| Model (Fast) | `gemini-2.5-flash-image` |
| Max Resolution | 4K (16MP) — API only |
| Aspect Ratios | 1:1, 2:3, 3:2, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9 |
| Reference Images | Up to 14 (5 faces + 6 objects) |
| Prompt Sweet Spot | 40-120 words (simple: 15-50, complex: up to 200) |
| Text Rendering | Best-in-class (~75-80% accuracy) |
| Negative Prompts | NOT supported — use semantic exclusion at end |
| Temperature | Must be 1.0 |
| Generation Speed | ~10-30s (4K: up to 170s peak hours) |

### API Config (CRITICAL)
```python
config=types.GenerateContentConfig(
    response_modalities=['TEXT', 'IMAGE'],   # MANDATORY — omit = text-only output
    image_config=types.ImageConfig(
        aspect_ratio="4:5",                  # Set per target platform
        image_size="4K"                      # ⚠ UPPERCASE K — "4k" silently fails → 1K
    ),
)
```

### Resolution Pricing
| Tier | Price |
|------|-------|
| 1K (default) | $0.07 |
| 2K | $0.13 (same as 1K — always use 2K minimum) |
| 4K | $0.24 |

---

## 2. Decision Matrix

```
Creator face needed? → Nano Banana Pro
Complex composition? → Nano Banana Pro (extend prompt to 120-200 words with detailed spatial descriptions)
Text rendering critical? → Nano Banana Pro
Quick iteration test? → Nano Banana Pro (Fast model)
```

Nano Banana Pro is the **exclusive** image generation platform for this plugin.

---

## 3. Social Platform → Carousel Specs

| Platform | Carousel Aspect | Resolution | Ideal Slides | Format |
|----------|----------------|-----------|-------------|--------|
| Instagram Feed | 4:5 | 1080×1350 | 7-10 | JPG/PNG |
| Instagram Reels | 9:16 | 1080×1920 | 7-10 | JPG/PNG |
| TikTok | 9:16 | 1080×1920 | 5-7 (max 35) | JPG/PNG |
| LinkedIn | 4:5 or 1:1 | 1080×1350 or 1080×1080 | 5-8 (max 300 PDF) | PDF recommended |
| YouTube | 16:9 | 1920×1080 | — | — |

**Default (unspecified platform):** 4:5 (1080×1350) — covers IG feed + LinkedIn.

---

## 4. Text Rendering Rules (5 Rules)

1. **Wrap exact text in quotes:** `Create a poster with the text "AI Innovation Conference 2025"`
2. **Describe fonts, don't name them:** "clean bold sans-serif" NOT "Helvetica"
3. **Multi-line → explicit hierarchy:**
   ```
   Line 1 (large, bold): "SUMMER SALE"
   Line 2 (medium): "Up to 50% Off"
   Line 3 (small): "Valid through August 31"
   ```
4. **Use 4K resolution** for text-heavy images (critical for legibility)
5. **Colored text:** "The text 'BERLIN' in alternating blue, red, white, black letters"

⚠ ~20-25% failure rate for complex text — always verify output manually.

---

## 5. Character Consistency Tips

- Practical sweet spot: **3-5 reference images** (14 supported, but 6+ = diminishing returns)
- Repeat defining traits **verbatim** in every prompt (eye color, hairstyle, scars)
- Change only **ONE variable** per generation (background OR outfit OR lighting)
- Use **targeted edits**: "change background to forest" — NOT full regeneration
- Stay in same conversation thread (model preserves visual context)
- **Re-anchor every 3-4 generations** by re-uploading reference
- Multi-character: identify explicitly per reference image

---

## 6. Split-Panel Compositions

- **4 panels = reliable.** 8+ panels = unreliable → generate individually + composite
- Carousels: generate each slide separately with consistent character references
- Use bullet-point spatial language for panel descriptions
- Aspect guidance: side-by-side → 16:9 or 3:2, stacked → 9:16, social → 4:5 or 9:16

---

## 7. Failure Modes & Fixes

| Problem | Cause | Fix |
|---------|-------|-----|
| Text-only response (no image) | Missing `responseModalities` | Add `['TEXT', 'IMAGE']` to config |
| Wrong aspect ratio | Gemini App bug | Use API `aspect_ratio` param |
| Silent quality downgrade | Daily quota exhausted (falls back to Nano) | Switch session / check quota |
| 4K ignored in editing | API bug during image-to-image | Export → re-import at high res |
| Content filter false positive | Trigger words | Rephrase, retry (filter is inconsistent) |
| 4K timeout / 503 error | Peak hours | Exponential backoff: 60s initial wait |

---

## 8. Workflow Best Practices

1. **Iterate, don't regenerate** — if 80% correct, use targeted edit prompt
2. **Gemini App fallback** for aspect ratio: upload blank canvas at target dimensions
3. **Carousel production:** individual frames > single multi-panel prompt
4. **For hands:** specify "natural hand positions, correct finger count" or frame to exclude hands
5. **Temperature control:** prompt specificity = more controlled output (no slider in UI)
