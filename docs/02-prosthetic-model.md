# The Prosthetic Model

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Prosthetic model** | AI as a **helper tool** (like glasses) — expands what you can reach; does not replace your voice or decisions. |
| **Ghostwriting** | Letting the model **draft for you** and accepting the output as finished prose. |
| **Six-alternative protocol** | Flag a problem → get **six complete wordings** → **you** pick, blend, or reject → only then apply. |
| **Apply gate / apply authorization** | A hard rule: **no text enters your manuscript** without your explicit instruction. |
| **Priority fixes** | In this methodology, means **finish the audit and offer alternatives** — not "rewrite my chapter for me." |
| **Retrieval bias** | Hidden scoring that pushes the tool toward certain words when it must output something. |
| **Thin solution space** | Too many constraints; the tool cannot choose well and emits vague or "not A, not B, but C" lines. |
| **Theta bias function** | Research term for how systems **rank choices** when preferences conflict — why six options beat one substitution. |
| **Negation triangulation** | Failure pattern: *Not X, not Y. Z.* — sounds deep but means the tool stalled. |
| **Two-step pipeline** | First pass: structure and facts only; second pass: **read-only check**; then you pick; then apply. |
| **Human signal** | Intentional, idiosyncratic prose **you** want to protect — not something for the tool to "smooth away." |
| **Sign** | A checklist flag for **generic or AI-sounding** prose patterns — cite, don't auto-fix. |
| **Session anchor** | A **saved end-of-session file** with continuity notes so you can resume without relying on chat history. |
| **PGM** | Structured **canon state file** for characters, world, or chapter facts. |

---

**Core claim:** A large language model can function as a **prosthetic** — an external aid for specific cognitive or workflow failures — without becoming the author.

This is the same distinction as:

- Glasses vs someone else reading for you
- A thesaurus vs someone else writing your sentences
- A spell-checker vs auto-accepting every suggestion

The prosthetic model only works with **governance**: explicit rules about what the model may output, and what requires human selection before anything touches the manuscript.

---

## Prosthetic vs ghostwriting

| | Prosthetic | Ghostwriting |
|---|-----------|--------------|
| **Goal** | Expand author's retrieval set | Replace author's prose |
| **Default output** | Diagnostics, alternatives, questions | Finished paragraphs |
| **Who chooses** | Author picks, blends, rejects | Model or user accepts |
| **Voice** | Author's; model never "smooths" without flag | Often generic LLM register |
| **Failure mode** | Too many constraints → sparse collapse (see failure-modes doc) | Plausible mediocrity |

---

## The six-alternative protocol

When prose is flagged (weak word, Sign breach, imprecise phrase):

1. **Diagnose** — name what's wrong and why it matters
2. **Offer exactly six alternatives** — full replaceable options for the flagged beat
3. **Wait** — author picks a number, blends, or supplies their own line
4. **Apply** — only then edit the manuscript

**Alternative type must match beat type:**

| Beat type | Six alternatives are… | Not… |
|-----------|----------------------|------|
| Prose phrase | Six wording variants | Six plot reconstructions |
| Scene structure | Six order/cut shapes | Six dialogue lines |
| Dialogue | Six lines **after** speaker + situation are set | Six proverb lines from generic voice |
| Unknown grounding | Six questions or situations | Six fabricated facts |

---

### Why six — and why not one

Six is not a magic number picked for symmetry. It is a **countermeasure** to a documented failure mode of **retrieval bias** under constraint — a problem first characterized in **theta bias function** research (1980s knowledge-representation work; see [`00-history-and-authority.md`](00-history-and-authority.md) Part 4).

#### The underlying failure: thin solution space

A language model (and, in earlier systems, a knowledge-base retrieval layer) does not "search until it finds the right answer." It applies a **bias function** over a vector space of candidates and **must return something** — a single token, a phrase, or a ranked list that gets tokenized into text.

When constraints bind tightly — rubric Signs, PGM locks, implicit "fix it" pressure, missing speaker/situation — the **feasible region narrows**. Candidates that almost fit are rejected; nothing in the remaining space fully satisfies the criteria. The bias function still has to emit output.

At that **thin edge** of the solution space, the system cannot discriminate between near-miss alternatives. Retrieval stalls. What surfaces on the page is not a confident choice — it is **forced emission**:

| Symptom on page | What the bias layer is doing |
|-----------------|------------------------------|
| **Negation triangulation** — *Not A, not B. C.* | Reject near-misses, collapse to a single surviving abstract |
| **Comma-delimited lists** — *not X, not Y, but Z* tokenized as one "answer" | Multiple rejected candidates returned as a bundle |
| **Adjective/adverb triads** — *tired, wary, watchful* | Parallel near-miss descriptors with no decisive selection |
| **Thesis pairs** — *freedom vs duty; land vs law* | Compression when no concrete line earns the highest bias |

This is especially devastating for **creatives** because the failure **looks like prose** — grammatical, plausible, finished — while carrying **no committed retrieval decision**. The author receives something to accept or reject, but not a **breadth of real options**.

#### What six alternatives fix

Offering **exactly six** full replaceable options is a deliberate **widening of the solution space**:

| Mechanism | Effect |
|-----------|--------|
| **Breadth** | Forces the model to populate multiple distinct regions of the retrieval set, not collapse to the highest-probability generic token |
| **Decisiveness** | Each alternative is a **complete candidate**, not a rejected list — the author compares six commitments, not one comma-separated hedge |
| **Human selection** | The author's pick **is** the bias resolution step the automated function could not complete under thin constraints |
| **Working-memory bound** | Fewer than six tends to collapse back to the model's first guess (single-point failure). More than six overwhelms the author under load |

**One substitution** is the failure mode wearing a helpful mask: the model still had to return one element from a thin space — you get *not A, not B, but C* dressed as a rewrite.

**Six alternatives** move the contract: the machine **must not** pretend to have chosen. It **must** branch. The author applies the final bias function — which only a human with creative intent can legitimately apply.

#### Operational rule

When you see negation triangulation, triads, or comma-list recovery in model output:

1. **Do not** add more rubric Signs (shrinks the feasible region further)
2. **Do not** accept the single collapsed line
3. **Do** diagnose the thin-space breach
4. **Do** offer six full alternatives of the correct beat type
5. **Wait** for author pick before apply

See [`06-failure-modes.md`](06-failure-modes.md) — *Thin solution space / retrieval bias stall* and *Sparse-edge collapse*.

---

## Priority fixes gate

Authors often say: "Fix the priority issues" or "Apply the edit pass."

Under the prosthetic model, that means:

1. Complete the audit
2. Branch six-alternative sets where needed
3. **Stop**

It does **not** mean rewrite the chapter. Author authorization to "fix" does not override the apply gate.

**Exception:** Author names a specific line and fix ("line 47: add period") — apply only that named change.

---

## Vocabulary prosthetic (neurological context)

Some authors use LLMs specifically for **lexical retrieval** under load — when phenomenological experience is intact but the word will not surface. In that case:

- Unexpected word choices may be **retrieval failures**, not style choices — flag and offer alternatives
- Do not "smooth" emotional processing toward neurotypical expression unless author directs
- Session re-entry anchors help hippocampal recall boundaries between writing sessions

This is not universal. It is one documented use case that explains why "just write it yourself" is not always neurologically accurate.

---

## Two-step pipeline (structural → audit)

For grounding-heavy beats, dialogue prosthetics, and developmental edits with action items:

```text
Step 1 — Structural / grounding
    → Step 2 — Prosthetic audit (readonly)
        → Author pick or explicit line fix
            → Apply to manuscript (if authorized)
```

**Step 1 may output:** beat sequences, PGM crosswalks, breach diagnostics, situation options, explicit questions.

**Step 1 may not output:** manuscript substitution, dialogue without speaker/situation, thesis taglines as voice.

**Step 2 checks:** quote gate, tagline gate, PGM lock, apply gate, domain collapse (simulation treated as canon).

**Output:** `PASS` or `FAIL` — no rewrite on FAIL.

---

## Human Signals vs rubric Signs

A good rubric flags **AI textual degradation** (sterile cadence, goldilocks words, hedging, etc.).

But dense, asymmetric, idiosyncratic prose on the page may be **human signal** — intentional voice the author protects.

When a Sign conflicts with on-page human signal:

- Document both
- Offer six alternatives
- Do not auto-resolve by substituting

The author chooses whether craft convention or voice wins.

---

## Session anchors

Long projects need **invariant re-entry**: what chapter, what calendar date, what gear, what open fixes were deferred.

Anchors typically have:

- **Section A** — continuity state for next session entry
- **Section B** — revision notes for a specific chapter
- **Section C** — post-session meta-analysis (what worked, what failed, per LLM product)

Section C is methodology infrastructure — how you tune protocol across vendors and months.

See [`templates/session-close.md`](../templates/session-close.md).

---

## What skeptics should take away

The prosthetic model is **not** "AI helped a little." It is a **contract**:

- Model proposes within bounds
- Author disposes
- Manuscript changes require explicit authorization
- Voice and intent stay human

If someone shows you a workflow with gates, anchors, and six-alternative retrieval, they are not doing the novice prompt. Judge that on its merits.

---

## Next

- [`03-five-domains.md`](03-five-domains.md) — five domains in a novel-length project
- [`04-audit-and-governance.md`](04-audit-and-governance.md) — rubrics and locks
- [`06-failure-modes.md`](06-failure-modes.md) — when constraints break the model
