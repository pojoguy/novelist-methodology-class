# Infrastructure — RAG, Continuity, Comparanda

## Metadata

| Field | Value |
|-------|-------|
| **Paired doc** | `docs/08-infrastructure-techniques.md` |
| **Format** | Explainer (3–5 min) or 3-part mini-series |
| **Series** | LLM Methodology — Ep. 08 |
| **Target length** | 4:00 (overview) |
| **Status** | outline |

---

## Terms in this video

| Term | Say this (plain language) | On-screen (optional) |
|------|---------------------------|----------------------|
| **RAG** | **Search** your book — "where did I say that?" | `Manuscript search` |
| **Verify** | **Continuity check** with rule names and quotes. | `Fact-check` |
| **Comparanda** | Other books' excerpts **only for craft compare** — never canon. | `Quarantined refs` |
| **Reanchor** | After edits, **refresh** the index so line refs stay true. | `Re-index chapter` |
| **L1 vs L2** | Fuzzy search vs search **with story tags** — one per question. | `One lookup type` |

---

## Hook (0:00–0:05)

> Six alternatives govern output. RAG indexing, verify reports, and comparanda govern what the agent is allowed to know.

**On-screen:** `RAG locates · Graphs verify · You apply`

---

## Beat 1 — Locator tiers (0:05–1:15)

**Say:**

> Fuzzy search finds mentions — it does not prove continuity. Mature workflow uses tiers: L1 RAG for quick locate, L2 passage search with canon and discourse joins, L3 verify for truth. One locator per question. Never merge fuzzy search and structured query in the same turn.

**On-screen:** L0 → L1 → L2 → L3 ladder

---

## Beat 2 — Reanchor and continuity reports (1:15–2:30)

**Say:**

> When prose changes, reanchor — passage IDs, ingest to search index. Continuity reporting returns event IDs, rule names, literal comparisons — not chat vibes. MEMORY versus SCENE stops flashback spatial false alarms. Verify flags don't auto-rewrite — same apply gate as everything else.

**On-screen:** `reanchor → ingest → verify_run → event_id`

---

## Beat 3 — Comparanda (2:30–3:30)

**Say:**

> Comparanda quarantine unrelated reference excerpts — successful openings and questionable ones — for craft diagnosis. Never indexed into canon, never ingested into passage search, never pasted into your manuscript. Compare technique — info dump, prior knowledge, thin characterization — not voice pastiche.

**On-screen:** `exploration/comparanda` quarantine box

---

## Beat 4 — Geography gate + collapse warnings (3:30–4:00)

**Say:**

> Travel edits query geography first — NO_ROUTE_CLAIM means stop, don't invent highways. Don't load comparanda into verify. Don't treat RAG hits as co-presence proof. Full doc in the repo.

**On-screen:** Repo link

---

## Mini-series spin-offs

| Ep | Topic |
|----|-------|
| 8a | Locator tiers + RAG vs L2 |
| 8b | Verify and continuity reporting |
| 8c | Comparanda craft comparison |
