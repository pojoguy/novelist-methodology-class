---
name: fiction-travel-edit
description: >-
  Edit-time geography gate for travel / corridor / highway rewrites. Use when
  the user edits or asks to rewrite driving, stops between towns, road choice,
  or any Earth itinerary beat. Requires geography_query before prose changes;
  stops on NO_ROUTE_CLAIM. Do not use for non-travel locate (use fiction-locate)
  or vocabulary alternatives.
---

# Fiction travel edit (geography lock)

DESIGN §16.4.1 — retrieve CANON route/place claims **before** rewriting travel beats.

## Hard gate

1. **Before** changing travel prose, call MCP **`geography_query`** with the beat’s endpoints (`place_a` / `place_b`), or `place` for a single toponym.
2. If result is **`NO_ROUTE_CLAIM`** / **`NO_PLACE_CLAIM`**: **STOP**. Do not invent roads, towns, or bearings from map JPGs or memory.
3. Only then draft or apply prose that stays inside the returned `sequence`, `via`, `bearing_lock`, and `rejected[]`.

This Skill is not a second locator for “where is X?” — use **fiction-locate** for that. Here the locator call is a **precondition for edit**.

## When this applies

- Rewrite / expand / fix a drive, stop, fork, overnight, or approach
- “He took Hwy…” / “stopped near…” / “between A and B…”
- Any Earth corridor defined in `lore/routes/`
- Author says “edit the travel beat” / “fix the road” / “corridor drift”

## Procedure

1. Identify endpoints and any named midpoints from the author’s request or the open chapter span (Read the beat if needed — that is not an L2 locator).
2. Call **`geography_query`** (`place_a`, `place_b`). One locator per turn (G-31); `session_reset_turn` only when starting a **new** user question.
3. Branch:
   - **`OK`** — cite `route_code`, stops between, `rejected[]`, and any `passage_ids` / `passage_codes`. Proceed with edit only within those locks.
   - **`NO_ROUTE_CLAIM`** — report the miss. Offer next steps; do **not** write travel geometry:
     1. Author hand-writes `lore/routes/*.json` CANON, or
     2. **`geography_ingest`** (`dry_run: true` first) → review → write DERIVED → **`geography_promote`** after author confirm.
4. Map images under `artifacts/grounding/maps/` are **supplemental** — never SoT, never substitute for a missing claim.
5. After manuscript change: **`passages_reanchor`** on that chapter (and `passages_ingest` runs with it). Do not auto-promote DERIVED.

## Do not

- Invent towns or highways not in the route claim or its `rejected[]` list
- Answer itinerary from `passages_search` alone when a route claim exists or `NO_ROUTE_CLAIM` should fire
- Treat DERIVED routes as editable canon (`include_derived` only when the author explicitly wants draft geometry)
- Substitute prose without author pick when your editorial rules require author selection

## MCP server

Requires **novelist-mcp** (`NOVELIST_FRANCHISE_ROOT` = franchise repo). If tools are missing, refuse travel geometry edits and ask the author to restore MCP or supply a route claim path under `lore/routes/`.
