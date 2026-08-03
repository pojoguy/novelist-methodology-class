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

---

Sophisticated methodology still fails. Naming failures helps skeptics see that practitioners **debug the system** — they do not blindly trust output.

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

**What happens:** Many constraints bind at once (continuity locks + rubric Signs + implicit rewrite pressure). Often the same underlying condition as **thin solution space** (below). Model output collapses to:

- **Negation triangulation:** *Not A, not B. C.*
- Generic recovery abstractions at corners of the solution space
- Thesis taglines and proverb dialogue

**Wrong fix:** Add more rubric Signs. Further constraint shrinks the feasible region and **worsens** token cycling.

**Right fix:**

1. Diagnose which constraints conflict
2. Protect on-page human signal density
3. Offer six alternatives to expand author retrieval set
4. Use prosthetic gates (two-step pipeline) — not more Signs

---

## Ghostwrite drift

**What happens:** You say "priority fixes" or "improve this chapter." The tool substitutes prose.

**Why:** Models default to helpful continuation. Without apply gate, "fix" reads as "rewrite."

**Right fix:** Redefine "fix" in your project expectations: audit + alternatives + stop. Exception only for named line mechanics.

---

## Proverb dialogue

**What happens:** Six alternatives for dialogue are six interchangeable "wise worker" lines — no speaker, no situation, migrant-film dialect bucket.

**Why:** Dialogue alternatives requested before `speaker:` and `situation:` are set.

**Right fix:** Quote gate — Step 1 outputs situation options or AskQuestion; dialogue alternatives only after speaker + situation locked.

---

## Thesis tagline compression

**What happens:** Editor summary reads like a poster: *"Freedom vs duty; the land always punishes the careless."*

**Why:** Chat-summary compression labeled as craft feedback.

**Right fix:** Tagline gate — mark `NON-PROSE — not for manuscript`; rewrite recommendation as concrete *what to do* for author.

---

## Wrong causal merge

**What happens:** Two adjacent PGM concepts collapsed (injury mechanism A merged with injury mechanism B).

**Why:** No enforced graph traversal; model free-associates nearby lore.

**Right fix:** PGM crosswalk table in Step 1; run a continuity check before apply.

---

## Domain collapse

**What happens:** Simulation sandbox output treated as canon; audit uses exploration routing as fact.

**Why:** Domains 2 and 4 run in same turn without promotion gate.

**Right fix:** Explicit NON-CANONICAL labels; promotion workflow; separate session modes.

---

## Grounding vs scenario simulation conflation

**What happens:** A geography verify session is treated like play-pretend (or vice versa). Route query output shapes character interior; sandbox dialogue is filed as spatial canon.

**Why:** Both live in `exploration/` and share a promote-to-PGM gate — but they answer different questions (*where* vs *who under pressure*).

**Right fix:** Label sessions 5a vs 5b (or Domain 4a vs 4b). Promote routes to `lore/routes/`; promote scenario distillates to `lore/characters/`. See [`03-five-domains.md`](03-five-domains.md).

---

## Six-alternative treadmill

**Lead signal:** Six alternatives plus convergence rounds **still** do not land — stop asking for more wordings on the same beat. That pattern usually means a **malformed beat**, not weak vocabulary.

**What happens:** You run six alternatives, then convergence rounds, and **still** nothing lands. You keep asking for more wordings on the same beat.

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

**Right fix:** Pick the kind for the question — quick search for fuzzy mention, tagged search for canon/scene join, continuity check for truth. Start a fresh question if you need a different kind.

---

## Stale passage index

**What happens:** Prose edited; passage IDs and FTS rows outdated. Verify cites wrong spans; `CH## L##` resolve returns stale catalog.

**Why:** Skipped reanchor/ingest after manuscript change.

**Right fix:** Re-index the chapter before continuity checks or structured lookup on edited chapters.

---

## Comparanda bleed

**What happens:** Reference excerpts from craft packs appear in continuity answers or voice drift toward compared authors.

**Why:** Comparanda ingested into passage FTS or loaded into verify/co-presence workflow.

**Right fix:** Keep comparanda under `exploration/` with L0 exclusion; reports only under `comparanda/reports/`; never promote. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Sycophantic audit

**What happens:** "Beautiful prose!" then three minor nits. Misses Sign breaches and continuity holes.

**Why:** Default RLHF helpfulness; no adversarial persona.

**Right fix:** Ask for an adversarial auditor persona; verdict first; what's working is short, not flattery.

---

## Context amnesia

**What happens:** Model contradicts chapter 4 gear state in chapter 12.

**Why:** Relying on **live chat attention** for relationship state instead of PGMs, anchors, and queries. Common on dense pages (multiple arcs resolving) and after months in frontier chat — joins compress or merge; the model still sounds confident while canon detail drifts.

**Right fix:** Section A load every session; fact-query before structural output; promote canon to **registered state** (PGMs, passage index, RAG) — see [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Over-smoothing voice

**What happens:** Model "fixes" autistic tactical interiority or flat affect toward neurotypical emotional exposition.

**Why:** Rubric Sign 4 (show don't tell) applied without human-signal check.

**Right fix:** Author rationale doc; Sign vs human signal collision protocol; six alternatives, not substitution.

---

## Product variance

**What happens:** Workflow perfect on Vendor A; Vendor B ignores gates, applies prose, hallucinates citations.

**Why:** Different system prompts, tool use, context limits.

**Right fix:** Section C meta-analysis per product; adjust load order; consider readonly audit skill as separate step.

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

- [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md)
- [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)
- [`02-prosthetic-model.md`](02-prosthetic-model.md) — governance that prevents drift
