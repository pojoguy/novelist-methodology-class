---
name: fiction-craft-compare
description: >-
  Compare franchise subject prose to quarantined unrelated reference excerpts for
  craft diagnosis (chapter hooks, info dumps, prior-knowledge assumptions, thin
  characterization). Uses MCP comparanda_* tools. Never rewrites manuscript or
  promotes references into canon.
---

# Fiction craft compare (comparanda)

Requires **novelist-mcp** with `NOVELIST_FRANCHISE_ROOT` set to a franchise repo.

## When to use

- Opening does not “hook the customer”
- Suspected info dump, unstated prior knowledge, thin characterization, setup-without-hook
- Author wants **technique contrast** against successful *unrelated* openings — not genre pastiche from franchise lore

## Isolation (hard rules)

1. References live only under `artifacts/exploration/comparanda/` (exploration → not indexed, not canon).
2. Subject (`chapters/`) is **read-only**.
3. Reports write only under `comparanda/reports/`.
4. **Never** paste reference wording into the manuscript.
5. **Never** call `canon_promote` on comparanda paths (tool refuses).
6. Prosthetic gate: diagnose; six alternatives only if author asks; apply only on explicit pick.

## Workflow

1. Ensure pack exists: `comparanda/packs/<pack_id>/pack.json` + excerpt files with attribution.
2. Call MCP `comparanda_list` — confirm pack + lenses (`chapter_hook`, `scene_drive`).
3. Call MCP `comparanda_compare` with `lens_id`, `pack_id`, and `source_file` + line span or `passage_ids`.
4. Use returned `subject`, `references`, and `lens.failure_modes` to write the diagnosis.
5. For methodology docs: cite technique contrast only — do not paste copyrighted reference text into `docs/` or `examples/`.

## Lens: chapter_hook failure modes

| id | Ask |
|----|-----|
| `info_dump` | World/backstory before reason to care? |
| `prior_knowledge` | Names/stakes assumed, not earned? |
| `thin_characterization` | Want/competence/voice from behavior? |
| `stakes_fog` | Present pressure forcing next page? |
| `summary_over_scene` | Told about vs enacted? |
| `setup_over_hook` | Logistics crowding the first question? |

## Do not

- Load comparanda into continuity audits or co-presence
- Treat reference voice as franchise voice target
- Expand placeholders into full copyrighted books in-repo
