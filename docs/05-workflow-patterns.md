# Workflow Patterns

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Session anchor** | A **saved file** at end of session: where the story paused, open fixes, what worked or failed with the tool. |
| **Section A / B / C** | Anchor parts: **A** = resume writing; **B** = revise one chapter; **C** = tune your process across tools. |
| **PGM** | Structured **canon file** (character, world, chapter) the tool loads instead of guessing from chat. |
| **Exploration** | Scratch folder — **not official story truth** until you promote it. |
| **Canon / promote** | Making a scratch fact **official** by moving it into registered lore files. |
| **Two-step pipeline** | Structural pass → read-only audit pass → **you pick** → apply if authorized. |
| **MCP** | A standard way for an editor (e.g. Cursor) to **call tools** on your project — search, verify, compare — without pasting your whole book into chat. |
| **RAG** | **Search** that finds relevant passages in your manuscript — good for "where did I mention this?" |
| **Passage reanchor** | After you edit a chapter, **re-index** it so line numbers and IDs still match the text. |
| **Verify run** | Automated **continuity check** with named rules and citations — not a rewrite. |
| **`event_id`** | A **tracking ID** on a continuity check so you can refer to the exact report later. |
| **Comparanda** | **Isolated reference excerpts** for craft comparison only — never indexed as your story. |
| **Grounding** | Real-world **facts and sources** (maps, period detail) your story must respect. |
| **Apply gate** | You authorize every change to the manuscript. |

---

Repeatable infrastructure matters more than clever one-off prompts. These patterns appear across serious long-form AI-assisted projects.

---

## Session anchors (continuity re-entry)

**Problem:** You return after days or weeks. You forget calendar pin, gear state, deferred fixes, which LLM product behaved last time.

**Solution:** Close every session with a **persisted anchor file** — not chat-only.

### Typical sections

| Section | Purpose | Load when |
|---------|---------|-----------|
| **A — Entry block** | Timeline, location, physical state, open elements | Next writing session |
| **B — Revision notes** | Minor fixes, prosthetic themes deferred | Revising that chapter |
| **C — Meta-analysis** | What worked / improved / failed (per product) | Tuning methodology |

### Practices

- Write anchor to disk: `anchors/YYYY-MM-DD-chNN-session-close.txt`
- Maintain `_directory.md` index (date, chapter closed, entering chapter, notes)
- Deferred fixes belong in Section A **Open elements** — anchor is canonical deferral record
- Protocol updates follow **only** when author directs after reviewing Section C

See [`templates/session-close.md`](../templates/session-close.md).

---

## Two-step prosthetic pipeline

```text
┌─────────────────────┐
│ Step 1: Structural  │
│ - Load PGMs/anchor  │
│ - Beat sequence     │
│ - Questions if stuck│
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Step 2: Audit       │
│ - Readonly          │
│ - Gate checklist    │
│ - PASS / FAIL       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Author pick / line  │
│ fix authorization   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Apply to manuscript │
│ (if authorized)     │
└─────────────────────┘
```

**Waive Step 2** only when author picks a number or names a line fix — that is apply authorization, not blanket rewrite license.

---

## Knowledge state (PGMs)

**PGM** (program guide / project graph module): machine-readable slice of canon — character, world, chapter state.

**Practices:**

- Master file + chapter slices (e.g. `character-master.json`, `character-ch07.json`)
- Load relevant slices **before** structural or audit output
- Chat is ephemeral; PGMs persist
- Exploration drafts: mark `NON-CANONICAL until promoted`

**Promotion workflow:** Author reviews exploration → registers in lore → anchor notes promotion date.

---

## Grounding load protocol

Before visual or geographic grounding:

1. Read grounding directory index
2. Load only images/tags for the beat under audit
3. If sample missing → STOP and ask author

Prevents model from inventing "plausible" geography or period detail.

---

## Agent instruction files

Tools like Cursor use `.cursorrules`, `AGENTS.md`, or project skills. Effective rules:

- Persona: adversarial editor, not cheerleader
- Default: diagnose, six alternatives, no apply
- Cite line format (`CH## L##`)
- Load order: rationale → gates → rubric → chapter PGM
- Explicit domain scope (do not collapse audit + simulation)

See [`templates/agent-instructions-starter.md`](../templates/agent-instructions-starter.md).

---

## MCP and fact-query layers

Advanced setups expose manuscript state via MCP (Model Context Protocol) or equivalent:

- `passages_search` / `passages_resolve` — locate beats (L2)
- `passages_reanchor` / `passages_ingest` — maintain RAG/FTS index after edits
- `facts_query` / `entities_query` — who knows what, when
- `geography_query` — travel corridor validation
- `verify_run` — continuity reporting with `event_id`
- `comparanda_compare` — quarantined craft comparison

**Design lock:** RAG **locates**. Graphs **verify**. Author **applies**.

**Rule:** NO_ROUTE_CLAIM or verify FAIL → stop prose changes until resolved. One locator per question — do not mix L1 fuzzy search and L2 structured query in the same turn.

Full tier model: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Post-session meta-analysis (Section C)

Three required questions every session close:

1. What worked well tonight?
2. What could be improved?
3. What did not work?

**Use:** Switch LLM vendors, adjust load order, add gate — not endless new rubric Signs.

Cross-session review of Section C entries is how methodology **evolves** without bloating constraints.

---

## Multi-edit apply order

When applying several line-keyed changes in one file:

- Process **highest line number first** (bottom → top)
- Prevents line drift after first edit

---

## Exploration vs canon

| Location | Status |
|----------|--------|
| `exploration/` or scratch chat | Non-canonical sandboxes |
| `lore/`, PGMs, promoted grounding | Canon |
| Anchor open elements | Deferred human decisions |

Never treat exploration as manuscript truth without promotion.

---

## Next

- [`06-failure-modes.md`](06-failure-modes.md)
- [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)
- [`examples/vocabulary-prosthetic-workflow.md`](../examples/vocabulary-prosthetic-workflow.md)
