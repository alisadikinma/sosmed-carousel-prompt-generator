---
name: new-localization
description: Scaffold a new localization file for the carousel prompt generator. Creates localization-{code}.md from the Indonesian template and updates all reference tables. Triggers on new localization, add language, tambah bahasa, localization scaffold.
---

# New Localization

Scaffold a new localization file and wire it into all reference tables.

## Required Input

Ask the user for:
1. **Language code** (ISO 639-1) — e.g., `hi` for Hindi, `ja` for Japanese, `es` for Spanish
2. **Language name** — e.g., Hindi, Japanese, Spanish
3. **Target audience** — age group, tone (formal/casual), cultural context

## Workflow

### Step 1: Create Localization File

Create `references/localization-{code}.md` with this structure (adapted from `localization-id.md`):

```markdown
# {Language Name} Localization Rules

## Integration Points

This file is loaded when the Localization Trigger activates:

| Trigger | Action |
|---------|--------|
| User speaks {Language Name} | Load this file before generating prompts |
| User targets {country/region} audience | Load this file before generating prompts |
| User mentions {country} holidays | Load this file + apply holiday section |
| User mentions {country} locations | Apply Setting Conversion table |
| Caption generation for {country} audience | Apply {Language} caption conventions from `references/caption-copywriting.md` |

**How this file integrates with other references:**
- `references/creator-bible.md` — Creator description stays in English; this file localizes surrounding content
- `references/carousel-rebranding.md` — Apply Setting Conversion when rebranding global carousels
- `references/caption-copywriting.md` — Use {Language} caption formulas and CTA phrases from this file
- `references/platform-specs.md` — Platform specs remain the same; localization affects content, not technical specs

---

## 1. Language Style

[Define: pronouns, formality level, slang rules, sentence style, provocation patterns]

## 2. Cultural Adaptation

### Headline Writing Rules
[Define: character limits, emphasis patterns, power words]

### Setting Conversion
[Map: Western locations → local equivalents]

### Data Localization
[Map: Western brands/references → local equivalents]

## 3. Visual Context Rules

[Define: skin tones, clothing, architecture, food, religious symbols to include/avoid]

## 4. Holiday Localization

[For each major holiday: name, date range, color palette with hex codes, lighting mood, prompt keywords, atmosphere]

## 5. Tone & Voice

[Define: CTA phrases, emotional triggers, humor style, formality switches]

## 6. AI Bias Countermeasures

[Define: common AI stereotypes to avoid, accurate representation rules]

## 7. Cultural Authenticity Checklist

[Define: per-slide checklist items for cultural accuracy]
```

### Step 2: Update Reference Tables (4 files)

Add entry to each reference table:

**`skills/carousel-prompt-generator/SKILL.md`** — Reference Files table:
```
| {Language Name} content | + `references/localization-{code}.md` |
```

**`agents/carousel-prompt-generator.md`** — REFERENCE FILES table:
```
| {Language Name} content | + `references/localization-{code}.md` |
```

**`CLAUDE.md`** — Reference Files table:
```
| `localization-{code}.md` | {Language Name} localization, holidays, AI bias countermeasures |
```

**`README.md`** — Reference Docs table:
```
| `localization-{code}.md` | {Language Name} localization, holidays, cultural adaptation |
```

### Step 3: Update Localization Trigger

In both `SKILL.md` and `agents/carousel-prompt-generator.md`, add the new language to the Localization Trigger section:

```
If the user speaks {Language Name} or targets {country} audience:
1. Read `references/localization-{code}.md` BEFORE generating any prompts
```

### Step 4: Update CLAUDE.md

Increment reference count from N to N+1 in:
- Architecture table: `references/` row
- Project Overview line

### Step 5: Verify

Run `/validate-references` to confirm:
- New file appears in all 4 reference tables
- Reference count is correct
- No cross-file drift introduced

## Output

After scaffolding, tell the user:
1. File created at `references/localization-{code}.md`
2. All 4 reference tables updated
3. Localization trigger wired
4. Sections that need user content: Language Style, Cultural Adaptation, Holiday Localization, AI Bias Countermeasures
