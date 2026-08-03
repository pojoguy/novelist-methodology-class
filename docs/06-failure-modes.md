# Failure Modes

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Failure mode** | A **predictable way the process breaks** — naming it lets you fix the workflow, not blame yourself. |
| **Thin solution space** | Too many rules at once; the tool **cannot pick** and emits vague or "not A, not B, but C" prose. |
| **Retrieval bias stall** | The scoring layer **must return something** but has no good candidate — forced, generic output. |
| **Negation triangulation** | *Not X, not Y. Z.* — sounds decisive but means the tool **collapsed** under constraints. |
| **Sparse-edge collapse** | Same family as thin space — **constraint pile-up** at a corner case; more rules make it worse. |
| **Ghostwrite drift** | You asked for an **audit**; the tool **rewrote prose** anyway. |
| **Proverb dialogue** | Six interchangeable "wise" lines with **no named speaker** — generic filler. |
| **Thesis tagline** | Poster-style moral (*A vs B; nature punishes…*) passed off as craft feedback. |
| **Domain collapse** | Treating **sandbox, reference, or chat** output as official story canon. |
| **PGM** | Your **registered fact files** — when ignored, continuity answers drift. |
| **Sign** | Rubric flag for AI-sounding prose — add more Signs to "fix" thin space and you often **worsen** collapse. |
| **Six-alternative protocol** | Correct response to thin space: **widen options**; you use them as inspiration — pick, blend, reject, or write your own. |
| **Lookup kinds** | **Quick search** vs **tagged passage search** — don't mix in one answer. |
| **Comparanda bleed** | Reference book excerpts **leaking into** continuity or voice — isolation failure. |
| **Human signal** | Voice you protect on the page — do not let generic rubrics flatten it without your choice. |
| **Quote gate** | Dialogue help waits until **speaker + situation** are set. |
| **Tagline gate** | Craft feedback stays specific — not poster morals passed off as direction. |
| **Apply gate** | Nothing touches the manuscript until **you** authorize a specific change. |
| **Malformed beat** | Scene **structure** wrong — six options and convergence still won't land; fix order or situation, not diction. |

---

Sophisticated methodology still fails. Naming failures helps skeptics see that practitioners **debug the system** — they do not blindly trust output.

**Where this doc sits:** **Symptom catalog** — what broke, why, what to do instead. **Recognition layer** for locked [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Failure shapes — quick recognition*. **Fixes** live in peers: level straw man → [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 0; domain scope → [`03-five-domains.md`](03-five-domains.md) — *Scope rules*; prosthetic protocol → [`02-prosthetic-model.md`](02-prosthetic-model.md); authorization → [`04`](04-audit-and-governance.md); filing habits → [`05-workflow-patterns.md`](05-workflow-patterns.md); lookup mechanics → [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

### Quick index (common traps)

| What you notice | Section |
|-----------------|---------|
| *Not A, not B. C.* / comma-list "answers" | [*Thin solution space*](#thin-solution-space-retrieval-bias-stall) · [*Sparse-edge collapse*](#sparse-edge-collapse) |
| Critique became a rewrite | [*Ghostwrite drift*](#ghostwrite-drift) |
| Six "wise" lines, no speaker | [*Proverb dialogue*](#proverb-dialogue) |
| Poster moral as craft note | [*Thesis tagline compression*](#thesis-tagline-compression) |
| Six options still won't land | [*Six-alternative treadmill*](#six-alternative-treadmill) |
| Generic cemetery / wrong place | [*Generic place hallucination*](#generic-place-hallucination) |
| Sandbox or reference text in canon | [*Domain collapse*](#domain-collapse) · [*Comparanda bleed*](#comparanda-bleed) |
| Map session mixed with play-pretend | [*Grounding vs scenario simulation conflation*](#grounding-vs-scenario-simulation-conflation) |
| `CH## L##` wrong after edits | [*Stale passage index*](#stale-passage-index) |
| Lore facts merged | [*Wrong causal merge*](#wrong-causal-merge) |
| Flattery audit, misses Signs | [*Sycophantic audit*](#sycophantic-audit) |
| Contradicts earlier chapter state | [*Context amnesia*](#context-amnesia) |
| Rubric flattens intentional voice | [*Over-smoothing voice*](#over-smoothing-voice) |
| Search + fact-check merged in one answer | [*Mixed lookup collapse*](#mixed-lookup-collapse) |
| Works on Vendor A, breaks on Vendor B | [*Product variance*](#product-variance) |

### Failures by domain (where to look first)

| Domain | Typical failures in this catalog | Scope |
|--------|----------------------------------|-------|
| **1** Lexical / light state | Thin solution space, sparse-edge, six-alternative treadmill | [`03-five-domains.md`](03-five-domains.md) Domain 1 |
| **2** Audit | Ghostwrite drift, sycophantic audit, thesis tagline | Domain 2 · [`04`](04-audit-and-governance.md) |
| **3** Continuity | Context amnesia, wrong causal merge, stale passage index | Domain 3 |
| **4a** Grounding | Generic place hallucination | Domain 4a · [`05`](05-workflow-patterns.md) |
| **4b** Scenario sim | Domain collapse, grounding vs 5b conflation | Domain 4b |
| **5** Production | Production noise during live chapter edit (scope bleed) | Domain 5 · [`03`](03-five-domains.md) — *Scope rules* (trailer blueprints during chapter edit) |
| **Cross-cutting** | Mixed lookup collapse, comparanda bleed, product variance | [`03`](03-five-domains.md) — *Scope rules* |

---

## Thin solution space (retrieval bias stall)

**What happens:** Under tight constraints, the model's **retrieval bias function** cannot discriminate between candidates that almost satisfy the criteria. The feasible region in vector space is too thin. The function **must still return output** — so it emits a forced choice or a bundled rejection list.

**Visible on page (especially devastating for creatives):**

- **Negation triangulation:** *Not A, not B. C.* / *not X, not Y, but Z*
- **Comma-delimited collapse:** multiple rejected near-misses tokenized as one "answer"
- **Adjective/adverb triads:** *tired, wary, watchful* — parallel descriptors with no committed selection
- **Thesis pairs:** abstract oppositions when no concrete line wins the bias

**Why it hurts:** Output looks finished and grammatical but encodes **no real retrieval decision** — the system stalled and emitted anyway.

**Wrong fix:** Add more Signs or constraints (shrinks feasible region further). Accept the single collapsed line.

**Right fix:**

1. Recognize thin-space stall (not "bad style" — structural retrieval failure)
2. Offer **exactly six** full replaceable alternatives — widens solution space deliberately
3. Author applies the final bias (pick, blend, reject, or own line inspired by the set) — human decision is the missing step
4. See [`02-prosthetic-model.md`](02-prosthetic-model.md#why-six--and-why-not-one-theta-bias-rationale) — *Why six — and why not one (theta bias rationale)*

**Research lineage:** Theta bias functions (1980s knowledge-representation work) model how bias and preference select among candidates; thin-solution-space collapse is the LLM-era expression of the same class of failure.

---

## Sparse-edge collapse

**What happens:** Many constraints bind at once (continuity locks + rubric Signs + implicit rewrite pressure). Same family as [**thin solution space**](#thin-solution-space-retrieval-bias-stall) — but the lead signal here is **constraint pile-up** (locks + Signs + rewrite pressure), not a single nexus stall on one line. Model output collapses to:

- **Negation triangulation:** *Not A, not B. C.*
- Generic recovery abstractions at corners of the solution space
- Thesis taglines and proverb dialogue

**Wrong fix:** Add more rubric Signs. Further constraint shrinks the feasible region and **worsens** token cycling.

**Right fix:**

1. Diagnose which constraints conflict
2. Protect on-page human signal density
3. Offer six alternatives to expand author retrieval set
4. Use prosthetic gates — two-step pipeline, quote/tagline/apply gates — not more Signs. See [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Two-step pipeline*; [`04-audit-and-governance.md`](04-audit-and-governance.md).

---

## Ghostwrite drift

**What happens:** You say "priority fixes" or "improve this chapter" — the tool substitutes prose. Same **apply-gate** violation when you said *"here's my take…"* and the tool applied the **nearest numbered option** instead of working on **your** line.

**Why:** Models default to helpful continuation. Without apply gate, "fix" reads as "rewrite"; cluster + author take is misread as "pick the closest number."

**Right fix:** Redefine "fix" in your project — audit + alternatives + stop ([`04-audit-and-governance.md`](04-audit-and-governance.md) — *What your words mean*, *Apply gate in practice*). **Pick ≠ cluster + author take:** [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Pick vs cluster + author take*. Exception only for named line mechanics.

---

## Proverb dialogue

**What happens:** Six alternatives for dialogue are six interchangeable "wise worker" lines — no speaker, no situation, migrant-film dialect bucket.

**Why:** Dialogue alternatives requested before `speaker:` and `situation:` are set.

**Right fix:** **Quote gate** — set speaker and situation in Step 1; dialogue alternatives only after both are locked. See [`02-prosthetic-model.md`](02-prosthetic-model.md) — beat-type table; [`04-audit-and-governance.md`](04-audit-and-governance.md).

---

## Thesis tagline compression

**What happens:** Editor summary reads like a poster: *"Freedom vs duty; the land always punishes the careless."*

**Why:** Chat-summary compression labeled as craft feedback.

**Right fix:** **Tagline gate** — mark summary as *not craft direction*; ask for concrete *what to do* on named lines. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *What good developmental feedback looks like*.

---

## Wrong causal merge

**What happens:** Two adjacent PGM concepts collapsed (injury mechanism A merged with injury mechanism B).

**Why:** No enforced graph traversal; model free-associates nearby lore.

**Right fix:** PGM crosswalk in Step 1; then a **continuity check** — readonly report with rule names, cited lines, and a **reference ID** you can file — not free-association in chat. Developmental letters and continuity compares are different jobs: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Report types*; habits: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Continuity reporting*.

---

## Domain collapse

**What happens:** Simulation sandbox output treated as canon; audit uses exploration routing as fact.

**Why:** Domains 2 and 4 run in same turn without promotion gate.

**Right fix:** Explicit NON-CANONICAL labels; promotion workflow; separate session modes. Habits: [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Exploration vs canon*, *Scenario simulation — what you do*.

---

## Grounding vs scenario simulation conflation

**What happens:** A geography verify session is treated like play-pretend (or vice versa). Route query output shapes character interior; sandbox dialogue is filed as spatial canon.

**Why:** Both live in `exploration/` and share a promote-to-PGM gate — but they answer different questions (*where* vs *who under pressure*).

**Right fix:** Label sessions **5a vs 5b** (or Domain 4a vs 4b). Promote routes to `lore/routes/`; promote scenario distillates to `lore/characters/`. See [`03-five-domains.md`](03-five-domains.md); [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Scenario simulation — what you do*.

---

## Six-alternative treadmill

**Lead signal:** Six alternatives plus convergence rounds **still** do not land — stop asking for more wordings on the same beat. That pattern usually means a **malformed beat**, not weak vocabulary.

**Why:** The beat is **structured wrong** — wrong order, missing situation, POV or grounding mismatch. More line-level options on a broken shape shrinks the solution space further.

**What you do:** Stop the treadmill. Rewrite the paragraph, reorder beats, or reload grounding. See [`02-prosthetic-model.md`](02-prosthetic-model.md) — *When six options fail — the beat is often malformed*.

---

## Generic place hallucination

**What happens:** Stock cemetery / main street / highway — not the site you researched. Often **genre gravity**: the model invents walls, trees, Gothic mood for a cemetery even when your map is roughly right.

**Why:** Map only, or no ground-level photos loaded; or you search the manuscript for a place name the POV never receives.

**Right fix:** File **map + Street View** together; load before you revise the beat; check prose against **what you documented** (no walls, no trees, bald prairie) — not whether the character said the place name. **POV-blind** sites are valid: your notes hold geography the narrative withholds. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture — map + Street View* and *POV-blind grounding*.

---

## Mixed lookup collapse

**What happens:** Quick search and tagged passage search run in the same answer; results merged. Flashback (`MEMORY`) treated as co-present with scene prose; exploration snippet treated as canon.

**Why:** One lookup kind per question rule violated.

**Right fix:** Pick **one lookup kind** per question — quick search for fuzzy mention, tagged passage search for canon/scene join, continuity check for truth. Start a fresh question if you need a different kind. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Kinds of lookup — do not collapse*; [`05-workflow-patterns.md`](05-workflow-patterns.md) — *What you can ask your project*.

---

## Stale passage index

**What happens:** Prose edited; passage IDs and search index rows outdated. Continuity checks cite wrong spans; `CH## L##` resolve to stale text.

**Why:** Skipped **reanchor** after manuscript change.

**Right fix:** Re-index the chapter before continuity checks or structured lookup on edited chapters. [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Passage reanchor*; [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Pointing at lines in revision*.

---

## Comparanda bleed

**What happens:** Reference excerpts from craft packs appear in continuity answers or voice drift toward compared authors.

**Why:** Comparanda mixed into manuscript search or continuity workflow.

**Right fix:** Keep comparanda **quarantined** — craft comparison only; reports under a separate path; never promote to canon. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

---

## Sycophantic audit

**What happens:** "Beautiful prose!" then three minor nits. Misses Sign breaches and continuity holes.

**Why:** Default chat flattery; no readonly audit contract.

**Right fix:** Ask for a **developmental letter** — verdict first, what's working brief, numbered line-tied notes. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *What good developmental feedback looks like*.

---

## Context amnesia

**What happens:** Model contradicts chapter 4 gear state in chapter 12.

**Why:** Relying on **live chat attention** for relationship state instead of PGMs, anchors, and queries. Common on dense pages (multiple arcs resolving) and after months in frontier chat — joins compress or merge; the model still sounds confident while canon detail drifts.

**Right fix:** Load **Section A** every session; query registered facts before structural work; promote canon to **registered files** (PGMs, passage index). [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Session anchors*; [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Over-smoothing voice

**What happens:** Model "fixes" autistic tactical interiority or flat affect toward neurotypical emotional exposition.

**Why:** Generic "show don't tell" rubric applied without **human signal** check.

**Right fix:** Author rationale doc; Sign vs human signal collision — document both, six alternatives, you choose. [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Human Signals vs rubric Signs*.

---

## Product variance

**What happens:** Workflow perfect on Vendor A; Vendor B ignores gates, applies prose, hallucinates citations.

**Why:** Different system prompts, tool use, context limits.

**Right fix:** **Section C** meta-analysis per product ([`05-workflow-patterns.md`](05-workflow-patterns.md)); adjust load order; separate readonly audit step when a vendor ignores gates.

---

## When to stop and ask

**You** should pause — and tell the tool not to invent prose — when:

- Real-world grounding sample is missing
- Speaker or calendar pin is unknown for dialogue prosthetic
- Geography or route claim fails verification
- PGM lock conflict unresolved

Ask for one clear question or six situation options — not fabricated prose.

---

## Next

| Topic | Document |
|-------|----------|
| Failure shapes (recognition only) | [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Failure shapes — quick recognition* |
| Six alternatives, malformed beat, gates | [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| Anchors, grounding, 5a/5b, reanchor | [`05-workflow-patterns.md`](05-workflow-patterns.md) |
| Domains, promotion, comparanda scope | [`03-five-domains.md`](03-five-domains.md) |
| Lookup kinds, comparanda mechanics | [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |
| Disclosure, pick vs cluster | [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) |
| Level 0 straw man → ghostwrite drift | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 0 |
