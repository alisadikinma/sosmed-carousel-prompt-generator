---
name: validate-references
description: Cross-file consistency checker for carousel prompt generator references (7 checks including global-config consistency). Run after editing any reference file, before commits, or after merging new RAG content. Triggers on validate, consistency check, reference check, cek referensi, cek konsistensi.
---

# Validate References

Run 7 automated consistency checks across all operational files. Reports PASS/FAIL per check with exact file:line for every violation.

## Scope

**Operational files** (checked):
- `skills/carousel-prompt-generator/SKILL.md`
- `agents/carousel-prompt-generator.md`
- `references/*.md` (all 10 files)
- `CLAUDE.md`
- `README.md`

**Excluded** (not checked):
- `docs/plans/*.md` — historical planning artifacts
- `.claude-plugin/*.json` — plugin metadata

---

## Checks

### Check 1: 9:16 Scope
**Pattern:** `9:16` appearing outside platform routing context
**Expected:** Only in TikTok/Reels-specific sections. Never as a global default.
**How to verify:** Grep for `9:16` in all operational files. Each hit must be on a line that also contains `TikTok`, `Reels`, or is inside a platform routing table.

### Check 2: SWIPE Rule
**Pattern:** Any mention of `SWIPE`
**Expected:** Every occurrence says "all slides except CTA". Never "slides 1-3", never "all slides except last", never "every slide".
**How to verify:** Grep for `SWIPE` in all operational files. Each hit must contain `except CTA`.

### Check 3: Reference Table Completeness
**Pattern:** Reference/file tables in SKILL.md, agent.md, README.md, CLAUDE.md
**Expected:** All 4 tables list exactly 12 reference files:
1. `global-config.md`
2. `creator-bible.md`
3. `hook-science.md`
4. `hook-formula-bank.md`
5. `hook-visual-library.md`
6. `carousel-rebranding.md`
7. `platform-specs.md`
8. `cinematography-lut.md`
9. `prompt-formulas.md`
10. `localization-id.md`
11. `carousel-best-practices.md`
12. `caption-copywriting.md`
**How to verify:** For each of the 4 files, grep for each reference filename. All 12 must appear.

### Check 4: Hashtag Counts
**Pattern:** Any mention of `hashtag` with a number
**Expected:** Instagram = max 5, TikTok = max 5 (or exactly 5), LinkedIn = 3-5, Threads = none (0). Never "5-10", never "no hashtags" for IG/TikTok/LinkedIn.
**How to verify:** Grep for `hashtag` in all operational files. Check each numeric value matches the platform rule.

### Check 5: Gradient Zones
**Source of truth:** `references/creator-bible.md` Section 7
**Expected values:**
| Slide Type | Gradient |
|------------|----------|
| Hook | Bottom half |
| Content B-Roll | Bottom half |
| Split-Panel | Bottom half |
| CTA | Bottom half |
| Thumbnail | Bottom third |
**How to verify:** Grep for `bottom half` and `bottom third` in all operational files. Each slide type context must match the table above. Thumbnail = "bottom third", all others = "bottom half". No hardcoded percentages (e.g., "bottom 40%") should appear in gradient zone contexts.

### Check 6: Aspect Ratio Default
**Pattern:** `aspect ratio` near `default` or as a standalone spec
**Expected:** Always platform-specific. Default for unspecified platform = 4:5 (not 9:16).
**How to verify:** Grep for `aspect` in all operational files. No file should declare a single global aspect ratio. The fallback default must be 4:5.

### Check 7: Global Config Consistency
**Pattern:** Hardcoded configurable values outside `global-config.md`
**Expected:** No operational file (except `global-config.md`) should hardcode values that are configurable via global-config.md. Known patterns to check:
- `#F5A623` — should not appear standalone (only in config refs or examples)
- `@alisadikinma` — should not appear standalone (only in config refs, examples, or global-config.md)
- `alisadikinma.com` — same
- `Kodak Portra 400` as a default spec — should reference global-config.md (OK in debugging problem descriptions or cinematography LUT)
**How to verify:** Grep for each pattern in all operational files EXCEPT `references/global-config.md`. Hits in template examples, headline banks, debugging problem descriptions, or cinematography LUT entries are OK. Hits in default specs, config tables, or template values are FAIL.

---

## Output Format

```markdown
# Reference Validation Report

**Date:** [current date]
**Files checked:** [count]

## Results

| # | Check | Status | Issues |
|---|-------|--------|--------|
| 1 | 9:16 scope | PASS/FAIL | [count] |
| 2 | SWIPE rule | PASS/FAIL | [count] |
| 3 | Reference tables | PASS/FAIL | [count] |
| 4 | Hashtag counts | PASS/FAIL | [count] |
| 5 | Gradient zones | PASS/FAIL | [count] |
| 6 | Aspect ratio default | PASS/FAIL | [count] |
| 7 | Global config consistency | PASS/FAIL | [count] |

**Score: [N]/7 PASS**

## Issues Found

### Check [N]: [Name]
- `[file]:[line]` — [what's wrong] → [what it should say]

## All Clear
[If no issues: "All 7 checks passed. References are consistent."]
```

---

## When to Run

- After editing any `references/*.md` file
- After merging new RAG content from external sources
- Before `git commit` (as a pre-flight consistency check)
- After adding a new reference file or localization
