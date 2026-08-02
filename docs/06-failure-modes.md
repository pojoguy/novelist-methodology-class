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
| **L1 / L2 locator** | **Fuzzy search** (L1) vs **structured search with story metadata** (L2) — don't mix in one answer. |
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
4. See [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Why six — theta bias rationale*

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

**What happens:** Author says "priority fixes" or "improve this chapter." Agent substitutes prose.

**Why:** Models default to helpful continuation. Without apply gate, "fix" reads as "rewrite."

**Right fix:** Redefine "fix" in agent rules: audit + alternatives + stop. Exception only for named line mechanics.

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

**Right fix:** PGM crosswalk table in Step 1; verify_run before apply.

---

## Domain collapse

**What happens:** Simulation sandbox output treated as canon; audit uses exploration routing as fact.

**Why:** Domains 2 and 4 run in same turn without promotion gate.

**Right fix:** Explicit NON-CANONICAL labels; promotion workflow; separate session modes.

---

## L1/L2 locator collapse

**What happens:** Agent runs fuzzy `@Codebase` / RAG and structured passage search in the same turn; merges hits into one answer. Flashback (`MEMORY`) treated as co-present with scene prose; exploration snippet treated as canon.

**Why:** One locator per question rule violated.

**Right fix:** Pick tier for the question — L1 for fuzzy mention, L2 for canon/discourse join, L3 for verify. `session_reset_turn` between locator types if tooling supports it.

---

## Stale passage index

**What happens:** Prose edited; passage IDs and FTS rows outdated. Verify cites wrong spans; `CH## L##` resolve returns stale catalog.

**Why:** Skipped reanchor/ingest after manuscript change.

**Right fix:** `passages_reanchor` + ingest before verify or L2 locate on edited chapters.

---

## Comparanda bleed

**What happens:** Reference excerpts from craft packs appear in continuity answers or voice drift toward compared authors.

**Why:** Comparanda ingested into passage FTS or loaded into verify/co-presence workflow.

**Right fix:** Keep comparanda under `exploration/` with L0 exclusion; reports only under `comparanda/reports/`; never promote. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Sycophantic audit

**What happens:** "Beautiful prose!" then three minor nits. Misses Sign breaches and continuity holes.

**Why:** Default RLHF helpfulness; no adversarial persona.

**Right fix:** Auditor persona in agent rules; verdict first; what's working is short, not flattery.

---

## Context amnesia

**What happens:** Model contradicts chapter 4 gear state in chapter 12.

**Why:** Relying on **conversation context** (chat memory) instead of PGMs and anchors. Common after months in frontier chat — the thread compresses; relationship and canon detail drop out even when the model still sounds confident.

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

STOP (do not generate) when:

- Real-world grounding sample is missing
- Speaker or calendar pin is unknown for dialogue prosthetic
- Geography/route claim fails verification
- PGM lock conflict unresolved

Output: one clear question or six situation options — not fabricated prose.

---

## Next

- [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md)
- [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)
- [`02-prosthetic-model.md`](02-prosthetic-model.md) — governance that prevents drift
