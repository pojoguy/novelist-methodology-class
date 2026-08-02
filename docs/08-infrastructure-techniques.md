# Infrastructure Techniques — RAG, Continuity, Comparanda

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Infrastructure** | The **files, indexes, and checks** under your workflow — not the chat window itself. |
| **RAG** | **Retrieval-augmented generation** — search your manuscript to find passages; **locates** text, does not prove it is consistent. |
| **L0 / L1 / L2 / L3** | **Levels of lookup:** excluded scratch (L0), fuzzy search (L1), search **with story metadata** (L2), **fact-check** (L3). Use **one level per question**. |
| **FTS** | **Full-text search** — keyword-style index of your prose, like a powerful Find across the book. |
| **Passage / passage_id** | A **segment of your chapter** with a stable ID so edits do not break references. |
| **Reanchor** | After you change a chapter, **rebuild** those segments and IDs from the new text. |
| **Ingest** | **Refresh the search index** so lookups match the latest draft. |
| **Canon status** | Label on a passage: official (**CANON**), draft, scratch (**EXPLORATORY**), or rejected. |
| **Discourse layer** | Tag for **how** text works in the story: present scene, memory, dream, etc. — stops false "they can't be in two places" errors. |
| **Verify / verify_run** | Automated **continuity report**: rule name, result, compared quotes — not a rewrite. |
| **`event_id`** | **Reference number** on one continuity check for your records or editor letters. |
| **Entities query** | Lookup **who someone is** and **name changes** across chapters. |
| **Facts query** | Lookup **locked story facts** (PGMs) with source tags. |
| **Geography query** | Lookup **routes and stops** between real places — blocks invented highways if no route exists. |
| **`NO_ROUTE_CLAIM`** | System says **no verified route on file** — stop and register facts before writing travel prose. |
| **Comparanda** | **Quarantined short excerpts** from other works to compare **opening technique** — never your canon, never pasted in. |
| **Lens** | A **checklist of craft questions** (e.g. info dump? thin characterization?) for a comparanda run. |
| **Pack** | A **folder of attributed excerpts** used only for craft comparison. |
| **PGM** | Structured **official fact file** for characters, world, or chapter state. |
| **MCP** | Plug-in protocol so your editor can **call project tools** (search, verify) safely. |
| **Provenance** | Tag on a fact: **documented**, inferred, invented for story, or **unknown** — blocks blind trust. |
| **Apply gate** | Verify and search **diagnose only**; you still authorize every manuscript change. |

---

Episodes 0–7 and the prosthetic model cover **governance** — six alternatives, apply gates, domains, failure modes. This document covers the **infrastructure** serious long-form projects add underneath: indexed retrieval, continuity verification, quarantined craft comparison, and structured graph queries.

**Design lock (carry everywhere):**

```text
RAG locates.  Graphs verify, frame, and attribute.  The system diagnoses.  You apply.
```

Chat memory is not canon. Indexed state + audit events are.

---

## Why infrastructure matters

| Without infrastructure | With infrastructure |
|------------------------|---------------------|
| Agent greps the repo or hallucinates "where did I say that?" | **Passage index** returns cited loci with IDs |
| Continuity argued from vibes in context window | **Verify reports** with rule names, literals, `event_id` |
| Reference novels poison voice or canon | **Comparanda** quarantine — craft diagnosis only |
| Travel edits invent highways | **Geography gate** — `NO_ROUTE_CLAIM` stops prose |
| Exploration chat becomes truth | **Promotion workflow** — EXPLORATORY → CANON explicit |

Prosthetic gates govern *output shape*. Infrastructure governs *what the agent is allowed to know and cite*.

---

## Locator tiers — do not collapse

Most authoring environments expose **one** retrieval mode (embed search / `@Codebase`). Mature methodology uses **tiered locators** — each tier has a job; mixing tiers in one turn causes false joins.

```text
L0 — Index policy          exploration/ excluded from embed index
L1 — Fuzzy RAG             fast "where mentioned?" — NO canon/discourse join
L2 — Structured passage    canon + discourse + PGM join on passage IDs
L3 — Verify                truth check — not retrieval
AUDIT — Event log          literal rules + passages compared; event_id
```

| Tier | Tool class | Use when | Do not use for |
|------|------------|----------|----------------|
| **L1** | Vector / FTS fuzzy search | Quick grep-like locate; brainstorming | Canon-sensitive "who was present?" |
| **L2** | Passage resolve / search + metadata | `CH## L##` on screen; identity epochs; filtered canon | Proving no spatial conflict |
| **L2** | Entities / facts / geography query | Name changes, locks, route between towns | Craft hook diagnosis |
| **L3** | Verify run | Co-presence, polarity, calendar, skill precedence | Finding a quote |
| **Audit** | Continuity report | Developmental edit attachments; `event_id` on recommendations | Substituting prose |

**Rule:** **One locator per question.** Do not run fuzzy RAG and structured passage search in the same turn and merge results — you will double-count and mis-attribute discourse layer.

---

## RAG indexing and passage reanchoring

### What gets indexed

Long-form work needs a **passage index** — stable IDs joined to:

- Source file + line span (live pointer for author)
- `passage_id` (UUID join key — survives line edits after reanchor)
- Canon status: `CANON` | `DRAFT` | `EXPLORATORY` | `REJECTED_VARIANT`
- Discourse layer: `SCENE` | `MEMORY` | `DREAM` | `FORESHADOW` | `UNRELIABLE`
- PGM / arc catalog tags when reanchored

**RAG (L1)** embeds or FTS-indexes **prose text** for fuzzy retrieval.

**L2 search** joins that text to **metadata** — so "Thunder Butte" in a flashback does not co-present with a scene in Kansas.

### Reanchor workflow

When chapter prose changes:

1. **Reanchor** — segment prose into passages; assign or confirm IDs
2. **Ingest** — mirror into FTS / SQLite (or equivalent) for search
3. **Verify preflight** — refuse or auto-reanchor if file mtime newer than index

**Never hand-author passage UUIDs** in production workflows — generate from reanchor on real prose.

### Index exclusion (L0)

Paths under `exploration/`, `comparanda/`, scratch sandboxes:

- **Excluded** from Cursor/codebase embed index (`.cursorindexingignore` or equivalent)
- **Never** ingested into passage FTS
- **Never** promoted to canon without explicit author workflow

This is how comparanda and grounding sandboxes stay out of retrieval bias for continuity questions.

### Minimum viable (no custom MCP)

| Capability | Manual approach |
|------------|-----------------|
| Fuzzy locate | Editor search / `@Codebase` — accept no metadata join |
| Stable loci | Author-maintained `CH## L##` + chapter files |
| Canon state | PGMs + markdown timeline |
| Reanchor | Re-run line citations after edits; accept drift risk |

**Full stack** adds automated reanchor, ingest, and L2 MCP tools — reference implementation: **novelist-plugin** (franchise MCP server; companion to this methodology).

---

## Structured queries (L2 graph access)

Beyond fuzzy RAG, continuity modeling needs **typed queries**:

| Query type | Answers | Example question |
|------------|---------|------------------|
| **Passages resolve** | Catalog at `CH## L##` — discourse, PGM, arc | "What is the catalog status of this line?" |
| **Passages search** | Fuzzy prose + filters | "Find the naming speech" |
| **Entities query** | Identity epochs, aliases, who is whom when | "When does Dylan become Masti?" |
| **Facts query** | PGM locks, provenance-tagged claims | "What is locked about peel color?" |
| **Geography query** | Stops between places, corridor claims | "Where did he stop between A and B?" |

### Geography gate (travel edits)

For Earth-itinerary / corridor rewrites:

1. Query geography **before** prose changes
2. If `NO_ROUTE_CLAIM` — **stop**; author ingests route (DERIVED) then promotes — do not invent from map priors
3. After manuscript change — reanchor affected chapter

Skill pattern: structural/grounding agent loads geography first; prosthetic audit second.

### Provenance on facts

| Value | Meaning |
|-------|---------|
| **DOCUMENTED** | Grounding artifact or verified source |
| **DERIVED** | Inferred from documented facts |
| **INVENTED** | Author lock — not real-world fact |
| **UNKNOWN** | Blocks auto-apply — ask first |

Query with provenance filters when simulation (Domain 4) must not leak into audit (Domain 2).

---

## Continuity reporting (verify + audit events)

**Retrieval** answers "where is it mentioned?" **Verification** answers "does this contradict canon?"

### Verify run

Inputs: source files, explicit claims, co-presence pairs, optional auto-reanchor.

Outputs per rule evaluated:

| Field | Purpose |
|-------|---------|
| `event_id` | Audit trail join key |
| `rule` | e.g. `SPATIAL_COPRESENCE`, `POLARITY_CONFLICT`, `SKILL_PRECEDENCE` |
| `result` | `NO_CONFLICT` \| `CONFLICT` \| `WARNING` \| `SKIPPED` |
| **Literals** | Compared passage texts and claim polarity — not chat summary |

**Example — no conflict:**

```text
event_id: ae-2026-07-10-003
rule: SPATIAL_COPRESENCE
result: NO_CONFLICT
note: passage_b layer=MEMORY excluded from co-presence with SCENE passage_a
```

**Example — conflict:**

```text
event_id: ae-2026-07-10-004
rule: POLARITY_CONFLICT
result: CONFLICT
claim_new: DENY character was_at location (ch14)
claim_canon: AFFIRM character was_at location (ch08)
```

### Continuity reporting in developmental edits

Full-chapter developmental pass load order:

1. Session anchor Section A
2. Chapter PGMs + discourse sidecar
3. Rubric + auditor persona
4. **Chapter verify (readonly)** → attach `event_id` to structural recommendations

Output shape unchanged: verdict → what's working → recommendations — but structural items cite **verify events**, not model memory.

**Apply gate:** Verify flags do not auto-rewrite. Author decides from six-alternative set or named line fix.

### Discourse layer — why it matters

Without discourse metadata, RAG retrieves "character at place A" and "character at place B" and treats them as co-present. **MEMORY** vs **SCENE** framing prevents retrieval-style spatial leaks — a graph fix, not a better embedding.

---

## Comparanda — quarantined craft comparison

**Problem:** Authors need to compare their opening or scene against **successful unrelated** excerpts (hook technique, info-dump anti-patterns) **without**:

- Indexing reference prose into canon
- Letting reference voice become the voice target
- Pasting copyrighted wording into the manuscript

**Solution:** **Comparanda** — exploration-quarantined reference packs + lens-based comparison reports.

### Isolation contract

| Surface | Policy |
|---------|--------|
| Storage | `exploration/comparanda/` only |
| L0 index | Excluded (parent exploration path ignored) |
| Passage FTS | **Never** ingest reference excerpts |
| Promote | Refused for comparanda paths |
| Subject | Manuscript chapters **read-only** |
| Writes | Reports under `comparanda/reports/` only |

### Pack structure

```text
comparanda/
  packs/<pack_id>/
    pack.json          # attribution, excerpt list
    excerpts/*.md      # short fair-use excerpts + metadata
  lenses/              # chapter_hook, scene_drive, custom
  reports/             # generated diagnosis stubs
```

Typical packs:

| Pack | Role |
|------|------|
| `successful-openings` | Technique to contrast **toward** |
| `questionable-openings` | Anti-patterns to **name** — do not imitate |

### Compare workflow

1. `comparanda_list` — confirm packs and lenses
2. `comparanda_compare` — `lens_id`, `pack_id`, subject (`source_file` + line span or `passage_ids`)
3. Agent fills report using **editorial recommendations format** — diagnosis only
4. Prosthetic gate: six alternatives only if author asks; apply only after author decision

### Lens: chapter_hook failure modes

| Mode | Ask |
|------|-----|
| `info_dump` | World/backstory before reason to care? |
| `prior_knowledge` | Names/stakes assumed, not earned? |
| `thin_characterization` | Want/competence/voice from behavior? |
| `stakes_fog` | Present pressure forcing next page? |
| `summary_over_scene` | Told about vs enacted? |
| `setup_over_hook` | Logistics crowding the first question? |

Compare **technique** — what the reference excerpt *does* — not shared plot or voice pastiche.

### Do not

- Load comparanda into continuity verify or co-presence checks
- Treat reference prose as PGM truth
- Commit full copyrighted books to the repo

---

## Other infrastructure patterns

| Technique | Role | Domain |
|-----------|------|--------|
| **Session anchors** | Re-entry state; Section C methodology tuning | 1, cross-cutting |
| **PGMs / lore JSON** | Graph state for characters, world, chapter slices | 3 |
| **Grounding indexes** | Visual anchors, route maps, period facts | 4 |
| **Author inline notes** | `CH## L##` keyed deferrals; promote to PGM | 1–2 |
| **Audit log / `event_id`** | Literal continuity compare trail | 3 |
| **Canon promotion** | EXPLORATORY → CANON explicit register | 3–4 |
| **Methodology check** | Agent behavior vs protocol (optional MCP) | cross-cutting |

---

## Domain map (infrastructure × five domains)

| Domain | Infrastructure you add |
|--------|------------------------|
| **1 Lexical** | Passage resolve at live loci; six-alternatives at `CH## L##` |
| **2 Audit** | Rubric + comparanda reports + verify-attached developmental edits |
| **3 Continuity** | Reanchor/ingest, entities/facts query, verify_run, audit events |
| **4 Grounding** | Geography query + promotion; provenance tags; grounding indexes |
| **5 Production** | Separate PGMs; do not index into prose passage store |

**Collapse failures:**

| Mistake | Consequence |
|---------|-------------|
| Comparanda in passage FTS | Reference voice bleeds retrieval |
| RAG-only for co-presence | False spatial conflicts |
| Verify result → auto-apply | Ghostwrite drift with audit lipstick |
| Skip reanchor after edit | Stale `passage_id` joins |
| L1 + L2 same turn | Double-counted, wrong discourse |

---

## Maturity path

| Stage | Infrastructure |
|-------|----------------|
| **Starter** | PGMs + anchors + manual search |
| **Intermediate** | L1 RAG + structured lore files + verify checklist (manual) |
| **Advanced** | Reanchor/ingest, L2 MCP, verify_run with `event_id`, geography gate |
| **Craft depth** | Comparanda packs + lenses; readonly craft reports |

You do not need the full stack on day one. You **do** need to know which tier answers which question — so you do not treat embed search as continuity truth.

---

## Reference implementation

The maintainer's production stack implements these patterns via **novelist-plugin** (MCP server) and franchise repo Skills:

| Skill / tool | Technique |
|--------------|-----------|
| `fiction-locate` | L2 locators; one per turn |
| `fiction-travel-edit` | Geography gate before travel prose |
| `fiction-craft-compare` | Comparanda workflow |
| `passages_reanchor` / `passages_ingest` | Index maintenance |
| `verify_run` | Continuity reporting |
| `comparanda_compare` | Craft lens comparison |

This repository documents **methodology** — portable patterns. The plugin is one implementation; the tiers and isolation contracts are the portable part.

---

## Next

- [`05-workflow-patterns.md`](05-workflow-patterns.md) — anchors, two-step pipeline
- [`03-five-domains.md`](03-five-domains.md) — domain scope rules
- [`06-failure-modes.md`](06-failure-modes.md) — domain collapse, context amnesia
- [`02-prosthetic-model.md`](02-prosthetic-model.md) — six alternatives, apply gates
