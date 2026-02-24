---
name: validate-references
description: Cross-file consistency checker for carousel prompt generator references. Run after editing any reference file, before commits, or after merging new RAG content. Triggers on validate, consistency check, reference check, cek referensi, cek konsistensi.
---

# Validate References

Run 6 automated consistency checks across all operational files. Reports PASS/FAIL per check with exact file:line for every violation.

## Scope

**Operational files** (checked):
- `skills/carousel-prompt-generator/SKILL.md`
- `agents/carousel-prompt-generator.md`
- `references/*.md` (all 9 files)
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
**Expected:** All 4 tables list exactly 9 reference files:
1. `creator-bible.md`
2. `hook-science.md`
3. `carousel-rebranding.md`
4. `platform-specs.md`
5. `cinematography-lut.md`
6. `prompt-formulas.md`
7. `localization-id.md`
8. `carousel-best-practices.md`
9. `caption-copywriting.md`
**How to verify:** For each of the 4 files, grep for each reference filename. All 9 must appear.

### Check 4: Hashtag Counts
**Pattern:** Any mention of `hashtag` with a number
**Expected:** Instagram = max 5, TikTok = max 5 (or exactly 5), LinkedIn = 3-5. Never "5-10", never "no hashtags".
**How to verify:** Grep for `hashtag` in all operational files. Check each numeric value matches the platform rule.

### Check 5: Gradient Zones
**Source of truth:** `references/creator-bible.md` Section 7
**Expected values:**
| Slide Type | Gradient |
|------------|----------|
| Hook | Bottom 40% |
| Content B-Roll | Bottom 35% |
| Split-Panel | Bottom 30% |
| CTA | Bottom 40% |
| Thumbnail | Bottom 25% |
**How to verify:** Grep for `%` near `gradient`, `overlay`, or `text zone` in all operational files. Each hardcoded percentage must match the table above for its slide type context. Placeholder `[N]%` is acceptable in templates.

### Check 6: Aspect Ratio Default
**Pattern:** `aspect ratio` near `default` or as a standalone spec
**Expected:** Always platform-specific. Default for unspecified platform = 4:5 (not 9:16).
**How to verify:** Grep for `aspect` in all operational files. No file should declare a single global aspect ratio. The fallback default must be 4:5.

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

**Score: [N]/6 PASS**

## Issues Found

### Check [N]: [Name]
- `[file]:[line]` — [what's wrong] → [what it should say]

## All Clear
[If no issues: "All 6 checks passed. References are consistent."]
```

---

## When to Run

- After editing any `references/*.md` file
- After merging new RAG content from external sources
- Before `git commit` (as a pre-flight consistency check)
- After adding a new reference file or localization
