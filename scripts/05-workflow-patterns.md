# Session Anchors and Pipelines

## Metadata

| Field | Value |
|-------|-------|
| **Paired doc** | `docs/05-workflow-patterns.md` |
| **Format** | Explainer (3–5 min) |
| **Series** | LLM Methodology — Ep. 05 |
| **Target length** | 4:30 |
| **Status** | draft |

---

## Terms in this video

| Term | Say this (plain language) | On-screen (optional) |
|------|---------------------------|----------------------|
| **Session anchor** | Saved **end-of-session notes** — where you paused, what's open. | `Saved resume file` |
| **PGM** | **Working notes** formalized — character, world, locks; any format. | `Your notes · queryable` |
| **Visual anchor pair** | **Map** + **Street View** for the same site. | `Map + ground view` |
| **Grounding capture** | One plain-language line; tooling files and indexes. | `Talk · stack writes` |
| **Relationship collapse** | Words fit in chat; **joins** don't — who knows what, which arc. | `Joins ≠ tokens` |
| **RAG** | **Search** your manuscript — finds mentions, doesn't prove consistency. | `Search, not truth` |
| **Verify** | **Fact-check** with citations — separate from search. | `Continuity check` |

---

## Hook (0:00–0:10)

**Say:**

> Chat resets relationships before it runs out of words. That's why you need anchors — and registered notes, not a bigger paste buffer.

**On-screen:** `Joins ≠ token count`

---

## Beat 1 — Session anchors (0:10–1:30)

**Say:**

> Close every session with a persisted anchor file — not chat only. Section A: continuity state for next entry — calendar, gear, open fixes. Section B: revision notes for that chapter. Section C: what worked, what failed, per LLM product. Section C is how you tune methodology across vendors and months.

**On-screen:** A / B / C diagram

---

## Beat 2 — PGMs and author's notes (1:30–2:15)

**Say:**

> A PGM is your working notes made formal — character sheets, timelines, locks — JSON, Markdown, plain text, whatever you already use. Not a separate knowledge-engineering workflow. Exploration stays non-canonical until you promote. Ask in plain language: "tell me about Dej." Your registered files answer. Chat is ephemeral. Registered notes persist.

**On-screen:** `PGM = your notes` · `exploration/` · `"Tell me about Dej"`

---

## Beat 3 — Grounding capture: map + Street View (2:15–3:00)

**Say:**

> Researching a beat, you already grab a map snip and Street View at the site. Example: Danish Cemetery near Coteau, North Dakota — map for approach, Street View for layout. Registered for **chapter three**, collapse pickup — lines sixty-two to end. Dylan doesn't know he's beside a cemetery; grounding still pins the geography for you. One sentence: add these to grounding for chapter three. Tooling places files, indexes them, extracts what it can see. Map fixes where; Street View fixes what it looks like. Together they block a generic fictional cemetery — walls, spooky branches, Gothic mood — when the real site is bald prairie and a mowed patch in grain fields. Load grounding before you revise; check prose against **constraints**, not whether the MC said "cemetery." Street View is dated — note capture date. Missing angles? Stop and ask.

**On-screen:** `Map + Street View` · `Ch3 · POV-blind` · `Documented · not invented`

---

## Beat 4 — Two-step pipeline (3:00–3:30)

**Say:**

> Step one: structure and grounding — beats, questions, speaker and situation set. Step two: readonly audit — quote gate, tagline gate, apply gate; developmental letter, not a paste-in rewrite. You pick, cluster plus author take, or name a line fix — then apply only if you authorized. Bottom-up line edits when applying several fixes — highest line number first. Grounding capture is low marginal cost once the habit is wired; setup is front-loaded.

**On-screen:** Pipeline flowchart · `Readonly audit` · `You authorize apply`

**Note for recording:** See `docs/05-workflow-patterns.md` — *Two-step pipeline (structural → audit)*; `docs/02-prosthetic-model.md` — gates and move types.

---

## Close + CTA (3:30–4:30)

**Say:**

> Section C of your session anchor is subjective — what worked tonight. Your **grounding files, route notes, and anchors** are how you **look back** months later: what place a span used, what the prose never said. Chat forgets; registered notes don't. When constraints break the model — failure modes. Episode six.

**On-screen:** `Section C = how it felt` · `Your files = what happened` · Ep. 06 card
