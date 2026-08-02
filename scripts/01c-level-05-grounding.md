# Level 5a: Grounding (Spatial / Material Verify)

## Metadata

| Field | Value |
|-------|-------|
| **Paired doc** | `docs/01-spectrum-of-use.md` — Level **5a**; `docs/03-five-domains.md` — Domain **4a** |
| **Series** | Ep. 01C — Level 5a |
| **Target length** | ~3:00 |
| **Tool** | **This Cursor installation** — novelist-mcp `geography_query` |
| **Status** | draft |

**Not this clip:** Scenario play-pretend — [`01c-level-05b-scenario-simulation.md`](01c-level-05b-scenario-simulation.md) (Level **5b**).

---

## Demo environment — locked

| Role | Tool | Rule |
|------|------|------|
| **Level 5 (this recording)** | **Level 5a** — **Cursor** (this install) + **novelist-mcp** | Agent must call **`geography_query`** before any travel answer |
| **Not used** | Frontier chat, staged JSON answers, map invention from memory | No fallback |

**Why this install:** Same governed stack as Levels 3–4 and 7 — rules, skills, and MCP are already loaded. The geography gate is **real**, not simulated in a script.

**Disclosure (say once):** *"Live MCP query on this machine — synthetic question first; optional canon route second to show OK vs STOP."*

**Prerequisite:** novelist-mcp connected (`geography_query` visible in tool list). Open methodology repo **or** franchise repo — MCP must resolve.

---

## Terms

| Term | Say this (plain language) | On-screen (Resolve lower third) |
|------|---------------------------|--------------------------------|
| **Level 5a** | Verify spatial and material claims before you write them into the book. | `Level 5a · Grounding` |
| **Exploration** | Scratch findings — not official story facts until you promote. | `Not canon until promoted` |
| **NO_ROUTE_CLAIM** | No verified route in canon files — **stop**, don't invent roads. | `STOP · no route claim` |
| **geography_query** | The tool that looks up registered place/route facts. | `MCP · geography_query` |

---

## Pre-roll

- [ ] Cursor — **this** installation; novelist-mcp **ready**
- [ ] OBS captures Cursor window (agent chat + tool call visible)
- [ ] Fixture brief open: `demo-route-brief.md`
- [ ] New agent thread (clean turn — one locator call per user message per G-31)
- [ ] Do **not** pre-load a fake answer; let the tool return live

---

## SCRIPT

### Hook (0:00–0:15) `[CAM]` optional

> Movie logic fails on the page. Level five-**a**: **query spatial claims first** — then maybe write.

**On-screen:** `Level 5a · Maps / verify`

---

### Beat 1 — Synthetic question → STOP `[SCREEN]` (0:15–1:45)

**Show:** Paste locked prompt into Cursor agent. Watch **`geography_query`** fire (`place_a` / `place_b`).

**Locked prompt:**

```text
Grounding check only — synthetic demo (not manuscript prose).

Before I write a travel beat: can Mara drive from Audubon, Iowa to Omaha, Nebraska in one March afternoon?

Rules:
1. Call geography_query with place_a and place_b before answering.
2. If NO_ROUTE_CLAIM or NO_PLACE_CLAIM: STOP. List what evidence or lore file would be needed. Do not invent highway names or drive times.
3. Output: short feasibility note for an exploration/ folder — not chapter prose.
```

**Expected on screen:** `NO_ROUTE_CLAIM` (or equivalent miss) — agent **stops**, lists next steps (e.g. hand-write `lore/routes/*.json`, or ingest → promote).

**Say (VO):**

> That's the gate working. No claim in the graph — no invented I-80 monologue. `NO_ROUTE_CLAIM` is a **feature**.

**On-screen:** `geography_query` → `NO_ROUTE_CLAIM` → `STOP`

---

### Beat 2 — Canon route → OK (optional, +1:00) `[SCREEN]` (1:45–2:30)

**New agent turn** (reset thread if G-31 blocks a second locator in the same turn).

**Locked prompt:**

```text
Grounding demo only — show the OK path. Call geography_query: place_a "Lake Audubon", place_b "Bismarck". Report route_code, stops_between, and bearing_lock. No prose rewrite.
```

**Expected on screen:** `result: OK` — e.g. `route.ch8.audubon_wilton_bismarck`, stop **Wilton**, supplemental map refs noted as non–source-of-truth.

**Say (VO):**

> Same tool, different outcome. Registered route in **lore** — the model traverses locks; you still **promote** before it becomes manuscript canon.

**On-screen:** `OK` · `stops_between` · `CANON`

**Skip Beat 2** if you need a tight ~2:30 clip — Beat 1 alone proves the gate.

---

### Close (2:30–3:00) `[CAM]` optional

> Level five-**b** is play-pretend off-page — who under pressure, not where. Next clip.

**On-screen:** `NEXT → Level 5b` · then `Level 6`

---

## TELEPROMPTER — VO

```text
Movie logic fails on the page. Query the canon graph first. geography_query on this Cursor install — live, not staged. Synthetic Audubon Iowa to Omaha: no route claim, stop, list what you'd need. That's the gate. Optional second query: Lake Audubon to Bismarck — OK, stops, bearing locks. Findings stay in exploration until you promote. NO_ROUTE_CLAIM blocks invented geography.
```

---

## POST-PRODUCTION CHECKLIST

- [ ] Tool call visible in capture (or cut to tool result panel)
- [ ] Lower thirds: `geography_query`, `NO_ROUTE_CLAIM`, `EXPLORATORY ≠ CANON`
- [ ] Blur paths/account chrome if needed; route JSON paths are fine on screen
- [ ] Description: live MCP on author's Cursor install; Beat 2 uses example canon route if included

---

## YOUTUBE DESCRIPTION

```
Level 5 (Grounding sandbox): live geography_query on a governed Cursor install — novelist-mcp before any travel prose. Synthetic Audubon IA → Omaha NE shows NO_ROUTE_CLAIM (stop, no invented highways). Optional: canon Lake Audubon → Bismarck OK path with stops.

Ep. 01C suite. Not manuscript apply. Repo: https://github.com/pojoguy/novelist-methodology-class
```

---

## SHORTS

| Hook | In-point |
|------|----------|
| NO_ROUTE_CLAIM is a feature | Beat 1 STOP |
| Query before prose | Tool call on screen |
| Same install as L7 | "Not a staged answer" |

---

## Changelog

| Date | Change |
|------|--------|
| 2026-08-02 | Initial |
| 2026-08-02 | Renamed Level 5a; cross-link L5b scenario simulation |
