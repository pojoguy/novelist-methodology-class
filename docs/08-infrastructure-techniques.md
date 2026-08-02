# Infrastructure Techniques — RAG, Continuity, Comparanda

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Infrastructure** | The **files, indexes, and checks** under your workflow — not the chat window itself. |
| **RAG** | **Retrieval-augmented generation** — search your manuscript to find passages; **locates** text, does not prove it is consistent. |
| **L0 / L1 / L2 / L3** | **Kinds of lookup** (see doc): scratch excluded, quick search, tagged passage, continuity check — **one kind per question**. |
| **FTS** | **Full-text search** — keyword-style index of your prose, like a powerful Find across the book. |
| **Passage / passage_id** | A **segment of your chapter** with a stable ID so edits do not break references. |
| **Reanchor** | After you change a chapter, **rebuild** those segments and IDs from the new text. |
| **Ingest** | **Refresh the search index** so lookups match the latest draft. |
| **Canon status** | Label on a passage: official (**CANON**), draft, scratch (**EXPLORATORY**), or rejected. |
| **Discourse layer** | Tag for **how** text works in the story: present scene, memory, dream, etc. — stops false "they can't be in two places" errors. |
| **Continuity check** | Automated **continuity report**: rule name, result, compared quotes — not a rewrite. |
| **Report reference ID** | **Reference number** on one continuity check for your records or editor letters. |
| **Character lookup** | Who someone is and **name changes** across chapters. |
| **Facts lookup** | **Locked story facts** (PGMs) with source tags. |
| **Route lookup** | **Routes and stops** between real places — blocks invented highways if no route exists. |
| **No route on file** | Your project says **no verified route registered** — stop and file facts before writing travel prose. |
| **Comparanda** | **Quarantined short excerpts** from other works to compare **opening technique** — never your canon, never pasted in. |
| **Editorial report corpus** | **Accumulated readonly diagnostics** — trope ledger, tone pass, verify events, etc. — filed outside canon and **reloaded** on later audits. |
| **Lens** | A **checklist of craft questions** (e.g. info dump? thin characterization?) for a comparanda run. |
| **Pack** | A **folder of attributed excerpts** used only for craft comparison. |
| **PGM** | **Formalized author working notes** — canon state in whatever shape you already use (JSON, Cypher, Markdown, plain text). Not a new kind of thinking; a **registered** place for it. |
| **Provenance** | Tag on a fact: **documented**, inferred, invented for story, or **unknown** — blocks blind trust. |
| **Apply gate** | Verify and search **diagnose only**; you still authorize every manuscript change. |
| **Attention / relationship collapse** | The model may hold **pages of text** in context but **lose track of how facts relate** — who knows what, which arc, which lock — especially when multiple story lines resolve on one page. |
| **Conversation context** | What the **chat thread** still "remembers" about **relationships** — unreliable even when raw text fits in the window; not a canon store. |

---

Episodes 0–7 and the prosthetic model cover **governance** — six alternatives, apply gates, domains, failure modes. This document covers the **infrastructure** serious long-form projects add underneath: indexed retrieval, continuity verification, quarantined craft comparison, and structured graph queries.

**Design lock (carry everywhere):**

```text
Search locates.  Structured checks verify.  The tool diagnoses.  You apply.
```

Chat memory is not canon. Indexed state + audit events are.

### Origin — prototyped on frontier chat, hardened in graph + RAG

This methodology was **largely prototyped on frontier LLMs** — long threads in ordinary chat before project files and indexed notes. Prosthetic gates, six-alternative retrieval, developmental audit shape, and apply discipline **emerged in that environment first**.

**What broke:** Not mainly **how much text** fits in the window. Most frontier models today can hold the **word count of several full novels** in a single context. What collapses is **relationship fidelity in attention** — who is bound to whom, what each character knows when, which arc a beat belongs to, which facts are locked. Even on a **single page**, when multiple story arcs resolve together, attention vector space **compresses**: the model sounds confident while merging, dropping, or free-associating relationships. Across months of chat, the same failure looks like **context amnesia** — chapter 4 gear in chapter 12, wrong co-presence, improvised canon from recent tokens. That is not author error; it is asking one live conversation to hold a **relationship graph** it was never built to retain.

**What followed:** State and lookup **outside** the chat window:

| Chat-only limit | Infrastructure response |
|-----------------|-------------------------|
| "Remember" gear / timeline / who knows what | **PGMs**, session anchors, character and fact lookup |
| "Find where I said X" | **Manuscript search** + passage index with story tags |
| Co-presence / route / lock conflicts | **Continuity check reports**, route lookup |
| Multi-step audit without ghostwrite drift | **Two-step pipeline** — structure, then readonly audit |

Frontier models remain the **sampling engine**. Graphs, indexes, PGMs, and gates **unload relationship state from active conversation** while keeping it **queryable on demand** — so attention can focus on the beat in front of you without forgetting the graph behind it.

#### Relationship state vs text in context

| What fits in chat | What does not reliably fit |
|-------------------|----------------------------|
| Raw prose, recent paragraphs, pasted notes | **Stable joins** — identity epochs, who-knows-what, arc membership, lock polarity |
| A character's name appearing in two scenes | Whether those appearances **contradict** under PGM rules |
| "Tell me about this chapter" | "Tell me about Dej **across the book** without merging injuries, timelines, or sandboxes" |

Infrastructure does not exist because authors forgot to paste their bible into the prompt. It exists because **relationship vectors must live outside the rolling attention window** and be **loaded or queried** when a question needs them.

**PGM in one sentence:** A PGM is **organized author's notes** — character sheets, timelines, locks, chapter slices. JSON, Markdown, and plain text are all valid. The requirement is **registered state you can load and cite** — not a specific file format.

---

## Why infrastructure matters

| Without registered files | With registered files |
|--------------------------|------------------------|
| Chat guesses "where did I say that?" | **Passage index** returns cited locations |
| Continuity argued from vibes in the chat window | **Continuity reports** with rule names, quotes, reference IDs |
| Reference novels poison voice or canon | **Comparanda** quarantine — craft diagnosis only |
| Travel edits invent highways | **Route lookup** — no route on file means stop |
| Exploration chat becomes truth | **Promotion workflow** — scratch → canon only when you say so |

Prosthetic gates govern *output shape*. Registered files govern *what your project can answer with evidence*.

---

#### Plain language — what you ask for

You work in **plain language**. You say *"tell me about Dej"*, *"does this contradict chapter 8?"*, *"where did I mention the peel?"* — not protocol names or search tiers.

| You say | Your project should |
|---------|---------------------|
| "Tell me about Dej" | Load character notes + relevant passages |
| "Where did I say X?" | Run a quick text search or tagged passage search — **one kind per question** |
| "Does this break canon?" | Run a **continuity check** — not search alone |
| "What did we lock about the calendar?" | Read locked facts from your PGM files |

**Design intent:** Complexity lives in **how you organize notes once** — not in every writing prompt. You should get **governed answers**, not a checklist of acronyms per question.

#### Artifacts = author's notes; paired visuals

- Infrastructure files = **notes you'd keep anyway**, made queryable.
- **Map alone** fixes *where*; **Street View** fixes *what it looks like*.
- Together they block **generic fictional** setting substitution (e.g. template cemetery).
- **Example:** Danish Cemetery near Coteau, ND — map + Street View filed for **chapter 3** (collapse pickup, lines 62–end); you check prose against what you documented. Site may be **POV-blind** — not named on the page when the character is unaware.

**One-line author capture:**

```text
[map] [street view] → "Add to grounding for chapter 3 — Danish Cemetery near Coteau."
→ place · index · vision extract · update backing structures
```

---

## Kinds of lookup — do not collapse

Most tools offer **one** search mode. Mature long-form work uses **different question types** — each has a job; mixing them in one breath causes false joins.

```text
Scratch folders     — excluded from manuscript search (exploration/, comparanda/)
Quick search        — fast "where mentioned?" — no canon join
Tagged passage      — search with scene/memory tags + PGM links
Continuity check    — truth check — not retrieval
Filed report        — prior audit you reload by reference ID
```

| Kind | Use when | Do not use for |
|------|----------|----------------|
| **Quick search** | Fast locate; brainstorming | "Who was present?" with canon stakes |
| **Tagged passage** | `CH## L##` on screen; flashback vs scene | Proving no spatial conflict |
| **Character / facts / route lookup** | Name changes, locks, stops between towns | Craft hook diagnosis |
| **Continuity check** | Co-presence, calendar, lock conflicts | Finding a quote |
| **Filed report** | Developmental edit attachments | Substituting prose |

**Your rule:** **One kind of lookup per question.** Do not merge a quick text search with a tagged passage search in the same answer — you will double-count and mis-attribute flashback vs scene.

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

**Tagged passage search** joins text to **metadata** — so "Thunder Butte" in a flashback does not co-present with a scene in Kansas.

### Reanchor workflow

When chapter prose changes:

1. **Reanchor** — refresh passage segments and IDs from the new text
2. **Re-index** — update search so lookups match the latest draft
3. **Before a continuity check** — confirm the index is current (stale index = wrong citations)

Do not hand-assign passage IDs in normal workflow — generate them from your real prose when you reanchor.

### Index exclusion (L0)

Paths under `exploration/`, `comparanda/`, scratch sandboxes:

- **Excluded** from manuscript search indexes
- **Never** mixed into passage search as canon
- **Never** promoted to canon without your explicit workflow

This is how comparanda and grounding sandboxes stay out of continuity questions.

### Starting simple

| Capability | Manual approach |
|------------|-----------------|
| Quick locate | Editor Find / project search — accept no story-tag join |
| Stable loci | You maintain `CH## L##` + chapter files |
| Canon state | PGMs + markdown timeline |
| After edits | Re-run line citations; accept drift risk until you re-index |

As your project grows, automated re-index and structured lookup reduce drift — the **habits** (one question type per ask, re-index after edits) matter more than any particular product.

---

## Structured lookup (beyond quick search)

Beyond quick text search, continuity work needs **typed questions**:

| Question type | Answers | Example |
|---------------|---------|---------|
| **Passage at line** | Tags at `CH## L##` — scene vs memory, PGM, arc | "What tags does this line carry?" |
| **Passage search** | Fuzzy prose + filters | "Find the naming speech" |
| **Character lookup** | Identity epochs, aliases, who is whom when | "When does Dylan become Masti?" |
| **Facts lookup** | PGM locks, provenance-tagged claims | "What is locked about peel color?" |
| **Route lookup** | Stops between places, corridor claims | "Where did he stop between A and B?" |

### Geography gate (travel edits)

For Earth-itinerary / corridor rewrites:

1. **Look up the route** before prose changes
2. If **no route on file** — **stop**; file and promote route notes — do not invent from map memory
3. After manuscript change — re-index the affected chapter

**Workflow:** Load grounding and routes first; run readonly audit second.

**Grounding indexes:**

- File **visual anchor sets** (map + ground-level) per place and chapter.
- **Before cemetery/town/corridor prose:** load the pair when registered; generic template description means grounding failed.

### Provenance on facts

| Value | Meaning |
|-------|---------|
| **DOCUMENTED** | Grounding artifact or verified source |
| **DERIVED** | Inferred from documented facts |
| **INVENTED** | Author lock — not real-world fact |
| **UNKNOWN** | Blocks auto-apply — ask first |

Use provenance tags when sandbox work (Domain 4) must not leak into audit (Domain 2).

---

## Continuity reporting

**Search** answers "where is it mentioned?" **Continuity check** answers "does this contradict canon?"

### What a continuity report includes

Per rule evaluated:

| Field | Purpose |
|-------|---------|
| **Reference ID** | Cite this report later in editor letters or audits |
| **Rule** | e.g. co-presence, polarity conflict, calendar |
| **Result** | no conflict \| conflict \| warning \| skipped |
| **Literals** | Compared passage texts — not chat summary |

**Example — no conflict:**

```text
reference_id: ae-2026-07-10-003
rule: spatial_co_presence
result: no_conflict
note: passage_b tagged memory — excluded from co-presence with scene passage_a
```

**Example — conflict:**

```text
reference_id: ae-2026-07-10-004
rule: polarity_conflict
result: conflict
claim_new: denies character was at location (ch14)
claim_canon: affirms character was at location (ch08)
```

### Continuity reporting in developmental edits

Full-chapter developmental pass load order:

1. Session anchor Section A
2. Chapter PGMs + discourse sidecar
3. Rubric + auditor persona
4. **Chapter continuity check (readonly)** → attach reference IDs to structural recommendations

Output shape unchanged: verdict → what's working → recommendations — but structural items cite **continuity reports**, not chat memory.

**Apply gate:** Continuity flags do not auto-rewrite. You decide from six-alternative set or named line fix.

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

1. Confirm packs and lenses are available
2. Run compare — lens, pack, your chapter span
3. Fill report using **editorial recommendations format** — diagnosis only
4. Six alternatives only if you ask; apply only after you decide

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

## Editorial report corpus (Domain 2)

Beyond one-shot chapter audits, mature projects **accumulate typed readonly reports** — trope/subversion ledger, tone pass, maturation read, comparanda diagnosis, verify events — filed under `exploration/` (or typed subfolders), span-labeled, and **reloaded** on later passes.

**Design lock:** Same as comparanda and verify — diagnose only; apply gate on prose; promote to PGM on author instruction.

Full pattern and example report types: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Editorial report corpus*.

---

## Other infrastructure patterns

| Technique | Role | Domain |
|-----------|------|--------|
| **Session anchors** | Re-entry state; Section C methodology tuning | 1, cross-cutting |
| **Retrospective meta-analysis** | Looking back at registered notes to reconstruct what a span assumed | cross-cutting |
| **PGMs / lore JSON** | Graph state for characters, world, chapter slices | 3 |
| **Grounding indexes** | Visual anchor sets (map + ground-level per place), route maps, period facts | 4 |
| **Author inline notes** | `CH## L##` keyed deferrals; promote to PGM | 1–2 |
| **Editorial report corpus** | Typed readonly diagnostics (trope ledger, tone, maturation, etc.) in `exploration/` | 2 |
| **Audit log / reference ID** | Literal continuity compare trail | 3 |
| **Canon promotion** | Scratch → canon only when you promote | 3–4 |
| **Methodology check** | Does tonight's session match your stated contract? | cross-cutting |

---

## Domain map (infrastructure × five domains)

| Domain | Infrastructure you add |
|--------|------------------------|
| **1 Lexical** | Passage resolve at live loci; six-alternatives at `CH## L##` |
| **2 Audit** | Rubric + **editorial report corpus** + comparanda + verify-attached developmental edits |
| **3 Continuity** | Re-index after edits, character/facts lookup, continuity reports |
| **4 Grounding** | Route lookup + promotion; provenance tags; grounding indexes |
| **5 Production** | Separate PGMs; do not index into prose passage store |

**Collapse failures:**

| Mistake | Consequence |
|---------|-------------|
| Comparanda in passage FTS | Reference voice bleeds retrieval |
| RAG-only for co-presence | False spatial conflicts |
| Verify result → auto-apply | Ghostwrite drift with audit lipstick |
| Skip re-index after edit | Stale passage joins |
| Quick search + tagged search same breath | Double-counted, wrong scene vs memory |

---

## Maturity path

| Stage | Infrastructure |
|-------|----------------|
| **Starter** | PGMs + anchors + manual search |
| **Intermediate** | Quick search + structured lore files + **filed editorial reports** + continuity checklist (manual) |
| **Advanced** | Automated re-index, structured lookup, continuity reports with reference IDs, route gate |
| **Craft depth** | Comparanda packs + lenses; readonly craft reports |

You do not need the full habit stack on day one. You **do** need to know which **kind of question** you are asking — so you do not treat a quick search as continuity proof.

---

## Next

- [`05-workflow-patterns.md`](05-workflow-patterns.md) — anchors, two-step pipeline
- [`03-five-domains.md`](03-five-domains.md) — domain scope rules
- [`06-failure-modes.md`](06-failure-modes.md) — domain collapse, context amnesia
- [`02-prosthetic-model.md`](02-prosthetic-model.md) — six alternatives, apply gates
