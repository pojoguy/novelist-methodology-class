# Infrastructure — RAG, Continuity, Comparanda

## Metadata

| Field | Value |
|-------|-------|
| **Paired doc** | `docs/08-infrastructure-techniques.md` |
| **Format** | Explainer (3–5 min) or 3-part mini-series |
| **Series** | LLM Methodology — Ep. 08 |
| **Target length** | 4:30 (overview) |
| **Status** | draft |

---

## Terms in this video

| Term | Say this (plain language) | On-screen (optional) |
|------|---------------------------|----------------------|
| **RAG / quick search** | **Search** your book — "where did I say that?" — does not prove continuity. | `Locate · not verify` |
| **Tagged passage** | Search **with** scene/memory tags and PGM links. | `Canon join` |
| **PGM** | Your **working notes**, formalized — any format; tooling queries them. | `Notes → queryable` |
| **Plain-language lookup** | You ask; your project files answer. | `You talk · notes work` |
| **Relationship collapse** | Text fits in context; **joins** don't — who knows what, which arc. | `Joins ≠ tokens` |
| **Continuity check** | **Fact compare** with rule names, quotes, reference ID. | `Verify · not search` |
| **Comparanda** | Other books' excerpts **only for craft compare** — never canon. | `Quarantined refs` |
| **Reanchor** | After edits, **refresh** the index so line refs stay true. | `Re-index chapter` |
| **Grounding pair (4a)** | **Map** + **Street View** — blocks generic fictional places. | `Map + ground view` |
| **Scenario sim (5b)** | Off-page runs → **constraints** filed — not manuscript dialogue in the index. | `Distill · not paste` |

**Note for recording:** Skim: `docs/08-infrastructure-techniques.md` — *Kinds of lookup* skim box + *Design lock*; habits live in `docs/05-workflow-patterns.md` — *This doc vs `08`*.

---

## Hook (0:00–0:10)

**Say:**

> Six alternatives govern output. Registered files govern what your project can cite — and you shouldn't need jargon to get there.

**On-screen:** `Search locates · checks verify · You apply`

---

## Beat 0 — Why files exist (0:10–0:45)

**Say:**

> Text may fit in context — several novels' worth. What collapses is relationship attention: who knows what, which arc, which lock — especially when multiple story lines land on one page. PGMs are your working notes made queryable — JSON, Markdown, whatever you already use. You say "tell me about Dej." Your project loads the right notes underneath.

**On-screen:** `Joins collapse` · `PGM = your notes` · `"Tell me about Dej"`

---

## Beat 1 — Locator tiers (0:45–1:30)

**Say:**

> Quick search finds mentions — it does not prove continuity. Mature workflow uses different question types: quick locate, tagged passage search with canon and scene tags, continuity check for truth. One kind per question. Never merge quick search and tagged search in the same answer. Over months, file typed editorial reports — trope ledger, tone, continuity — and reload them; chat is not your archive. Collapse failure: mixed lookup — see Ep. 06.

**On-screen:** `Quick · tagged · continuity` · `report corpus`

---

## Beat 2 — Reanchor and continuity reports (1:30–2:30)

**Say:**

> When prose changes, re-index — passage IDs, refresh search. Continuity reporting returns reference IDs, rule names, literal comparisons — not chat vibes. Memory versus scene stops flashback spatial false alarms. Continuity flags don't auto-rewrite — same apply gate as everything else.

**On-screen:** `re-index → continuity report → reference ID`

---

## Beat 3 — Comparanda (2:30–3:30)

**Say:**

> Comparanda quarantine unrelated reference excerpts — successful openings and questionable ones — for craft diagnosis. Never indexed into canon, never ingested into passage search, never pasted into your manuscript. Compare technique — info dump, prior knowledge, thin characterization — not voice pastiche.

**On-screen:** `exploration/comparanda` quarantine box

---

## Beat 4 — Geography gate + visual anchors (3:30–4:15)

**Say:**

> Travel edits: look up the route first — no route on file means stop, don't invent highways. Grounding indexes pair map and Street View per place — map alone fixes where; ground view fixes what it looks like. Example: Danish Cemetery near Coteau, ND — chapter three, collapse pickup; POV-blind — your character may not name the site. Scenario simulation is different: off-page runs distill constraints to character files — never index sandbox dialogue as canon. One line: add to grounding. Load the pair before roadside or corridor prose when registered — generic template cemetery means grounding failed. Don't use comparanda for continuity checks. Don't treat search hits as co-presence proof.

**On-screen:** `Map + Street View` · `5a ≠ 5b` · `No generic cemetery`

---

## Close (4:15–4:30)

**Say:**

> Full doc in the repo. Spin-offs: **8a** lookup kinds, **8b** continuity reporting, **8c** comparanda — if you need depth beyond this overview.

**On-screen:** Repo link

---

## Mini-series spin-offs

| Ep | Topic |
|----|-------|
| 8a | Lookup kinds — quick vs tagged search |
| 8b | Continuity reporting |
| 8c | Comparanda craft comparison |
