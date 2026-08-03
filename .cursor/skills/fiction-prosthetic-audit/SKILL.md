---
name: fiction-prosthetic-audit
description: >-
  Readonly Step 2 prosthetic audit. Use after Step 1 structural/grounding output,
  or when the user asks to audit six alternatives, check quote/tagline/apply gates,
  or run a prosthetic-gates pass before manuscript apply. Use for developmental edits
  with action items, dialogue prosthetics, and grounding-heavy beats. Do not use to
  rewrite manuscript or invent dialogue without speaker+situation. Do not add rubric Signs.
---

# Fiction prosthetic audit (Step 2)

## Rule

**Readonly.** Output `PASS` or `FAIL` + cited gates. **No manuscript rewrite** on FAIL. Return to Step 1 or the author.

**Load order (this repo):**

1. [`docs/02-prosthetic-model.md`](../docs/02-prosthetic-model.md) — two-step, pick/cluster, malformed beat
2. [`docs/04-audit-and-governance.md`](../docs/04-audit-and-governance.md) — apply gate, Signs, priority fixes
3. If `NOVELIST_FRANCHISE_ROOT` is set: franchise `prompts/system/prosthetic-gates.md` and `prompts/rubric.md` for live manuscript work

Do **not** add Signs to rubric during audit.

## When this applies

- After Step 1 beat order / PGM crosswalk / situation options
- User asks to “audit the six alternatives,” “prosthetic gate check,” or “Step 2”
- Developmental review produced numbered alternatives that could become prose
- Dialogue options offered — verify `speaker:` + `situation:` were set in Step 1
- **Methodology / example maintenance** that cites franchise grounding — verify against registered artifacts (`methodology_check`, `grounding_check`) before copying or claiming spatial facts

## Mandatory checks

| Gate | Fail if |
|------|---------|
| **Quote** | Numbered alternative is full dialogue without `speaker:` + `situation:` |
| **Tagline** | State-vs-state aphorism / poster thesis / “X hands / Y punishes” as craft |
| **NON-PROSE** | Chat compression not labeled `NON-PROSE — not for manuscript or PGM` |
| **PGM lock** | Apply would contradict loaded PGM / era / calendar / author lock |
| **Domain collapse** | Exploration/simulation treated as canon without registration |
| **Apply** | Output includes manuscript or doc edits without author pick or named line fix |
| **Sign sample** | Offered prose fragments trip Signs 4, 7, 11, 16 |
| **Grounding** | Spatial/example claims without MCP locate or filed artifact path |

Also reject **forbidden shapes:** worker proverb lines without author sample; negation triangulation as scene summary; acquisition smoothers without situation-level options.

## Output shape

```text
PROSTHETIC AUDIT — Step 2
Result: PASS | FAIL
Gates failed: [names]
Breaches:
- [gate]: [what]
Next: return to Step 1 | ask author | (if PASS) await author pick before apply
```

## Waive

Author may skip Step 2 with explicit pick (`use option 3`) or named line fix. Document waive in chat; still do not expand apply to other items.

## Do not

- Substitute chapter prose
- Offer six new dialogue lines to “fix” a FAIL
- Treat this Skill as rewrite license
- Copy grounding assets from filesystem search when MCP can resolve registered paths
