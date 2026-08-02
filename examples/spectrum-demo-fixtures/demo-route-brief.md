# Grounding brief (synthetic) — Level **5a** demo

**Not scenario simulation** — see `demo-scenario-brief.md` (Level **5b**).

**Record on:** This **Cursor** installation with **novelist-mcp** (`geography_query`).

## Beat 1 — synthetic (expect STOP)

**Question:** Can Mara drive from **Audubon, Iowa** to **Omaha, Nebraska** in one afternoon in March?

**MCP call:** `geography_query` — `place_a: "Audubon, Iowa"`, `place_b: "Omaha, Nebraska"`

**Expected:** `NO_ROUTE_CLAIM` — no invented highways; list evidence needed for a future `lore/routes/*.json` or ingest → promote path.

**Output location:** exploration note only — **not** manuscript.

## Beat 2 — optional (expect OK)

**Question:** Demonstrate a registered canon route (example from live franchise graph).

**MCP call:** `geography_query` — `place_a: "Lake Audubon"`, `place_b: "Bismarck"`

**Expected:** `OK` — e.g. `route.ch8.audubon_wilton_bismarck`, stop **Wilton**.

**Note:** Illustrates contrast with Beat 1; not part of the synthetic Mara shop storyline.

## Promotion rule

Findings stay in **exploration** until author promotes to PGM / route CANON.
