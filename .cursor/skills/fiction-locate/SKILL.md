---
name: fiction-locate
description: >-
  Locates manuscript passages via novelist-plugin MCP L2 (passages.resolve /
  passages.search / facts.query / entities.query / geography.query), not @Codebase.
  Use when the user asks where/when something happens in the book, route/stop-between
  places, CH## L## catalog status, where a name or identity changes, who is present,
  find a beat or passage, canon-sensitive locate, or continuity lookup. Also use for
  verify.run when they ask if prose conflicts with canon. Do not use for drafting new
  prose or vocabulary alternatives.
---

# Fiction locate (novelist-plugin L2)

## Rule

**One locator per question.** For canon-sensitive locate, call MCP **`passages_resolve`**, **`passages_search`**, **`facts_query`**, **`entities_query`**, or **`geography_query`**. Do **not** use `@Codebase` (L1) in the same turn.

MCP cannot block `@Codebase` — this Skill is the enforcement point (G-31).

## When this applies

- “Where does…?” / “When does…?” / “Find the beat where…”
- **Route / corridor:** “Where did he stop between X and Y?” → **`geography_query`** (`place_a` / `place_b`) — not `passages_search`. Missing Earth corridor → report `NO_ROUTE_CLAIM`; author may draft via **`geography_ingest`** (DERIVED) then **`geography_promote`**.
- Name / identity changes (e.g. scout → Aria) → prefer **`entities_query`** first (`name` + optional `chapter`), then prose locate if needed
- Who is co-present; place/time of a scene
- “Does this contradict canon?” → prefer **`verify.run`** after locate
- **Example / grounding maintenance** — resolve registered artifact paths (`danish-cemetery`, chapter headers) via MCP before copying into `examples/`

## Procedure

1. If a prior MCP locator already ran this turn, call **`session_reset_turn`** only when starting a **new** user question; otherwise return `LOCATOR_ALREADY_USED` and stop.
2. **Itinerary / between places:** call **`geography_query`** with `place_a` and `place_b` (or `place` for a single toponym on a route claim). Answer from `stops_between` + `passage_ids`. Map images are supplemental — do not invent geometry from JPGs.
3. **Identity / alias:** call **`entities_query`** with `name` (and `chapter` when epoch matters). Cite `entity.code` + `identity_epoch`.
4. **Live locus on screen (`CH## L##` / chapter+line):** call **`passages_resolve`** with `source_file` + `line`. Report `passage_id`, `discourse.effective`, and `catalog` (override / PGM / arc). Line is a live pointer; UUID is the join key.
5. **Fuzzy prose locate (no line):** call **`passages_search`** with a concrete `query` string (distinctive words, not the whole sentence).
6. Prefer hits that have `passage_id` / `code` (reanchored chapters). If `passage_id` is null, note the chapter is not reanchored yet; still cite `source_file` + line / `segment_index`.
7. Answer from returned excerpts/claims. Cite **`code`** and **`passage_id`** when present.
8. For continuity / PGM locks, use **`facts_query`** — still one L2 locator per turn.
9. For conflict checks, call **`verify_run`** with explicit claims or `co_presence_pairs` — not a second locate.

## Do not

- Run `@Codebase` for these questions
- Invent passage text not in tool results
- Answer “stop between A and B” from `passages_search` when a route claim exists or `NO_ROUTE_CLAIM` should be reported
- Treat `discourse.layer` from search as calibrated MEMORY/SCENE without Tier 0 override or gold label (G-28)
- Auto-edit manuscript from verify flags
- Walk the franchise filesystem for grounding paths when MCP can resolve them

## MCP server

Requires **novelist-mcp** configured (`NOVELIST_FRANCHISE_ROOT` = franchise repo). If tools are missing, say so and ask the author to restart MCP in Cursor Settings. Fall back to `Read` on `chapters/` only — still not `@Codebase` for canon answers.
