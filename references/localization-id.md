# Indonesian Localization Rules

## Integration Points

This file is loaded when the Localization Trigger activates (see `SKILL.md` / `agents/carousel-prompt-generator.md`):

| Trigger | Action |
|---------|--------|
| User speaks Bahasa Indonesia | Load this file before generating prompts |
| User targets Indonesian audience | Load this file before generating prompts |
| User mentions Indonesian holidays (Imlek, Lebaran, Natal) | Load this file + apply holiday section |
| User mentions Indonesian locations | Apply Setting Conversion table |
| Caption generation for Indonesian audience | Apply Bahasa caption conventions from `references/caption-copywriting.md` |

**How this file integrates with other references:**
- `references/creator-bible.md` — Creator description stays in English; this file localizes the surrounding content text
- `references/carousel-rebranding.md` — Apply Setting Conversion when rebranding global carousels for Indonesian audience
- `references/caption-copywriting.md` — Use Bahasa caption formulas and CTA phrases from this file
- `references/platform-specs.md` — Platform specs remain the same; localization affects content, not technical specs

---

## 1. Language Style

### Default: Casual Gen Z Bahasa
- Use "kamu" not "Anda" (unless formal context)
- Slang OK: "gue/gw", "lo", "nggak", "banget", "literally", "slay"
- Mix Bahasa + English naturally: "Ini literally mind-blowing banget"
- Short punchy sentences for carousel text
- Questions that provoke: "Tau nggak?", "Serius nih...", "Kamu masih lakuin ini?"

### Headline Writing
- ALL CAPS for main headline
- Mix Bahasa + English keywords
- Accent color on power words
- Max 8-10 words per headline block

### Examples
| English Source | Indonesian Adaptation |
|---------------|---------------------|
| "What Actually Happens in 1 Second" | "YANG TERJADI DALAM 1 DETIK DI BUMI" |
| "120 Terabytes of Internet Data" | "120 TERABYTE DATA INTERNET" |
| "Follow for more" | "FOLLOW BUAT KONTEN LAINNYA" |
| "This will change everything" | "INI BAKAL UBAH SEGALANYA" |
| "You won't believe this" | "KAMU NGGAK BAKAL PERCAYA INI" |

## 2. Cultural Adaptation

### Setting Conversion
| Global/Generic | Indonesian Context |
|---------------|-------------------|
| Times Square, NYC | Bundaran HI Jakarta / local landmark |
| Amazon warehouse | Tokopedia/Shopee warehouse |
| London streets | Local streets, pasar, gang-gang |
| Generic office | Co-working space Indonesian style |
| Western cafe | Warung kopi / kafe lokal |
| US highway | Jalan raya / toll road |

### Brand Substitution (when culturally relevant)
| Global Brand | Indonesian Alternative |
|-------------|---------------------|
| Amazon orders | Tokopedia / Shopee orders |
| WhatsApp (keep) | WhatsApp (dominant in Indonesia) |
| Google (keep) | Google (universal) |
| YouTube (keep) | YouTube (universal) |
| Uber | Gojek / Grab |
| Venmo / PayPal | GoPay / OVO / Dana |

### Data Localization
- Keep global stats for "wow factor" (120TB data, 99K Google searches)
- Add Indonesian context where available: "Di Indonesia, 100+ juta pengguna..."
- Currency: show both USD and IDR when relevant

## 3. Visual Context Rules

### Indonesian Street Scenes
- Motor bikes (Honda Beat, Vario) — ubiquitous in Indonesia
- Warung/toko kelontong with corrugated roofs
- Street food carts, bakso, mie ayam
- Tropical vegetation, palm trees, humid atmosphere
- Mixed architecture: shophouses, modern malls, traditional markets

### Avoid
- Snow or winter elements (tropical country)
- Middle Eastern architecture for Islamic content (use Indonesian mosques)
- Generic "Asian" stereotypes
- Rural poverty stereotypes — show modern urban Indonesia

### Indonesian People
- Diverse ethnicities: Malay, Javanese, Chinese-Indonesian, Batak, etc.
- Modern clothing: hijab + jeans, batik + sneakers, casual professional
- Tech-savvy: everyone has smartphones, active on social media
- Friendly, community-oriented, gotong royong spirit

## 4. Holiday Localization

### Chinese New Year → Imlek

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Red | #C8102E | Joy, luck, prosperity |
| Gold | #CC9900 | Wealth, fortune |
| Crimson | #960316 | Deep celebration, tradition |

- **Avoid:** White/black as dominant colors (mourning association)
- **2026 Zodiac:** Fire Horse

**Cultural Elements:**
- Barongsai on poles, not just dragon dance
- Dodol keranjang (nian gao), bak kwa
- Kebaya encim (Peranakan dress)
- Vihara/klenteng, not pagodas
- Cap Go Meh parades in Singkawang
- Tok panjang communal dinner
- Sam Poo Kong Temple Semarang

**Lighting:** Dramatic red-gold, paper lantern warmth

**Prompt Keywords:** "vibrant red and gold tones, paper lantern glow, rich reds, golden highlights"

---

### Eid al-Fitr → Lebaran

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Islamic Green | #009A0A | Faith, paradise |
| White | #FFFFFF | Purity, forgiveness |
| Gold | #CFB53B | Celebration, blessings |

**Greeting Text:** "Selamat Hari Raya Idul Fitri" / "Mohon Maaf Lahir Batin"

**Cultural Elements:**
- Indonesian mosque = multi-tiered roofs (NOT Middle Eastern domes)
- Ketupat + opor ayam + rendang
- Mudik (mass homecoming)
- Baju koko, batik, peci
- Sungkeman (Javanese forgiveness ritual)
- Takbiran night with bedug drums

**Lighting:** Soft ethereal white-green, moonlit serenity

**Prompt Keywords:** "soft ethereal lighting, diffused white light, moonlit glow, muted pastel greens"

---

### Christmas → Natal

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Red | #BB2528 | Celebration, warmth |
| Evergreen | #165B33 | Life, renewal |
| Gold | #F8B229 | Star of Bethlehem, joy |
| White | — | Peace, purity |
| Silver | — | Elegance, starlight |

**Cultural Elements:**
- Tropical Christmas: palm trees, frangipani
- NO snow — use glitter, tropical greenery
- Handcrafted ornaments: wood, rattan, coconut shell
- Nasi kuning tumpeng, lapis legit
- Bamboo stars/torches tradition
- Wayang kulit Nativity (Yogyakarta)
- Klapertart

**Lighting:** Warm golden glow, fairy light bokeh

**Prompt Keywords:** "warm golden lighting, fairy light bokeh, fireplace glow, candlelight ambiance"

---

### Diwali

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Deep Red | #891E1B | Tradition, auspiciousness |
| Marigold | #F79E1F | Sacred offering, celebration |
| Gold | #FFDF00 | Prosperity, divine light |
| Purple | #542182 | Royalty, spirituality |
| Saffron | — | Sacred, purity |

**Key Symbols:** Diyas (oil lamps), rangoli, marigold garlands, fireworks

**Lighting:** Warm amber diya glow, festival sparkle

**Prompt Keywords:** "warm golden diya glow, oil lamp lighting, fairy lights, amber illumination"

---

### Valentine's Day

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Wine | #5E081E | Deep passion, romance |
| Rose Pink | #E24767 | Love, affection |
| Blush | #E4CDD3 | Tenderness, softness |
| Soft Gold | #D4AF37 | Elegance, luxury |

**Lighting:** Soft romantic, rose-tinted, candlelight

**Prompt Keywords:** "soft romantic lighting, rose-tinted warmth, intimate candlelight, dreamy soft focus"

---

### Thanksgiving

**Color Palette:**
| Color | Hex | Symbolism |
|-------|-----|-----------|
| Dark Red | #C1311C | Autumn harvest, warmth |
| Pumpkin | #FF8039 | Harvest, abundance |
| Seal Brown | #623004 | Earth, grounding |
| Moss Green | #858453 | Nature, gratitude |

**Lighting:** Autumn golden hour, harvest candlelight

**Prompt Keywords:** "warm earth tones, amber and russet, golden afternoon light, autumn sunlight"

---

## 5. Tone & Voice

### Content Creator Voice (Generic Template)
- Expert but accessible — explain simply
- Confident not arrogant — share knowledge, invite discussion
- Local pride — celebrate local culture and achievements
- Future-oriented — always looking at what's next
- Genuine curiosity — express authentic wonder

### CTA Phrases
| English | Indonesian |
|---------|-----------|
| "Follow for more" | "Follow buat konten lainnya" |
| "Save this post" | "Save post ini, penting!" |
| "Share with a friend" | "Share ke temen yang perlu tau" |
| "Comment below" | "Comment pendapat kamu" |
| "Link in bio" | "Link di bio ya" |

## 6. AI Bias Countermeasures

When generating AI images for Indonesian content, actively counter these common bias patterns:

| Bias Pattern | Countermeasure |
|-------------|----------------|
| Indonesian women → stereotypical headscarves | Include diverse appearance descriptors |
| Middle Eastern men → always bearded/traditional | Specify contemporary styling |
| Generic "Chinatown" for Imlek | Use Indonesian-specific landmarks and traditions |
| Middle Eastern mosque for Indonesian Lebaran | Specify multi-tiered roof architecture |
| Racial homogenization | Add specific ethnic/cultural context in prompt |

**Rule:** Always include geographic + cultural context. "Indonesian Lebaran celebration in Javanese setting" NOT "Eid celebration."

## 7. Cultural Authenticity Checklist

Before publishing any localized content, verify the following:

- [ ] Geographic context in prompt ("Indonesian Lebaran in Javanese setting" not generic "Eid")
- [ ] Verify Arabic calligraphy / Chinese characters are correct
- [ ] Show contemporary + traditional elements together
- [ ] Diverse appearance within cultural group
- [ ] Indonesian mosque = multi-tiered roofs, NOT Middle Eastern domes
- [ ] Have imagery reviewed by community member before publishing
