# The Prosthetic Model

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Prosthetic model** | AI as a **helper tool** (like glasses) — expands what you can reach; does not replace your voice or decisions. |
| **Prosthetic capture** | The **ingestion** phase — machine output lands in your file (dictation, autocomplete, captions) before you revise. |
| **Ghostwriting** | Letting the model **draft for you** and accepting the output as finished prose. |
| **Six-alternative protocol** | Flag a problem → get **six complete wordings** → **you** use them as **inspiration** (pick, blend, reject, or write your own) → only then apply. |
| **Apply gate / apply authorization** | A hard rule: **no text enters your manuscript** without your explicit instruction. |
| **Priority fixes** | In this methodology, means **finish the audit and offer alternatives** — not "rewrite my chapter for me." |
| **Retrieval bias** | Hidden scoring that pushes the tool toward certain words when it must output something. |
| **Thin solution space** | Too many constraints; the tool cannot choose well and emits vague or "not A, not B, but C" lines. |
| **Nexus (retrieval stall)** | The **constraint knot** where the model stalled — same beat, same locks, same near-miss rejections. Six alternatives branch here, not elsewhere. |
| **Theta bias function** | Research term for how systems **rank choices** when preferences conflict — why six options beat one substitution. |
| **Negation triangulation** | Failure pattern: *Not X, not Y. Z.* — sounds deep but means the tool stalled. |
| **Two-step pipeline** | First pass: structure and facts only; second pass: **read-only check**; then you pick; then apply. |
| **Human signal** | Intentional, idiosyncratic prose **you** want to protect — not something for the tool to "smooth away." |
| **Sign** | A checklist flag for **generic or AI-sounding** prose patterns — cite, don't auto-fix. See [`04-audit-and-governance.md`](04-audit-and-governance.md). |
| **Quote gate** | Dialogue help waits until **who is speaking** and **the situation** are clear. |
| **Tagline gate** | Craft feedback stays specific — not a movie-poster moral (*duty vs freedom…*). See [`04-audit-and-governance.md`](04-audit-and-governance.md). |
| **Session anchor** | A **saved end-of-session file** with continuity notes so you can resume without relying on chat history. |
| **PGM** | Structured **canon state file** for characters, world, or chapter facts. |
| **Pick** | Author **selects** one numbered alternative (with or without light edit) and authorizes apply. |
| **Blend** | Merge pieces from named options (e.g. "lead with 3, verb from 5") — you specify the splice; apply only when you authorize. |
| **Own line** | You write the final wording without picking a number — optional readonly audit on **your** line; apply only when you authorize. |
| **Cluster + author take** | Author names near-miss options, supplies **own draft**, asks for **orientation** — not applying the closest number by default. |
| **Convergence round** | Follow-up set (often **three** alternatives) **anchored on a cluster**, still on the nexus. |
| **Supersede** | You write a stronger line than any numbered option; use the six as orientation, then audit **your** line. |
| **Malformed beat** | Beat order or situation is wrong — **especially** when six alternatives fail after multiple passes. Fix structure, not diction. |
| **Span counterfactual** | *"What if X changed between L###–L###?"* — explore ripple effects before you rewrite. |
| **POV-blind grounding** | You know where the scene is; the character doesn't — your notes hold the map, not the prose. |

---

**Core claim:** A large language model can function as a **prosthetic** — an external aid for specific cognitive or workflow failures — without becoming the author.

**Where this doc sits:** [`01-spectrum-of-use.md`](01-spectrum-of-use.md) **Levels 2–3** (lexical prosthetic + developmental audit) run on this contract; **Levels 4–7** add filed state on top. [`03-five-domains.md`](03-five-domains.md) **Domain 1** (lexical) and **Domain 2** (audit) are the domain lens on the same habits. **Governance** — apply gate, phrase contracts, when not to audit — is spelled out in [`04-audit-and-governance.md`](04-audit-and-governance.md); this doc is the **operating model**, not the full audit playbook.

This is the same distinction as:

- Glasses vs someone else reading for you
- A thesaurus vs someone else writing your sentences
- A spell-checker vs auto-accepting every suggestion

The prosthetic model only works with **governance**: explicit rules about what may touch your manuscript and what requires your selection first. Walkthrough: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Apply gate in practice*, *What your words mean*.

---

## Prosthetic vs ghostwriting

| | Prosthetic | Ghostwriting |
|---|-----------|--------------|
| **Goal** | Expand author's retrieval set | Replace author's prose |
| **Default output** | Diagnostics, alternatives, questions | Finished paragraphs |
| **Who chooses** | Author picks, blends, rejects | Model or user accepts |
| **Voice** | Author's; model never "smooths" without flag | Often generic LLM register |
| **Failure mode** | Too many constraints → sparse collapse ([`06-failure-modes.md`](06-failure-modes.md) — *Thin solution space*) | Plausible mediocrity; [**ghostwrite drift**](06-failure-modes.md#ghostwrite-drift) once you expected critique |

---

## The six-alternative protocol

When prose is flagged (weak word, Sign breach, imprecise phrase):

1. **Diagnose** — name what's wrong and why it matters
2. **Offer exactly six alternatives** — full replaceable options for the flagged beat
3. **Wait** — you choose a **move type** (pick, blend, cluster+author take, reject, own line); the tool should not assume "pick a number" is the default
4. **Apply** — only then edit the manuscript

**Alternative type must match beat type:**

| Beat type | Six alternatives are… | Not… |
|-----------|----------------------|------|
| Prose phrase | Six wording variants | Six plot reconstructions |
| Scene structure | Six order/cut shapes | Six dialogue lines |
| Dialogue | Six lines **after** speaker + situation are set (**quote gate**) | Six proverb lines from generic voice — [**proverb dialogue**](06-failure-modes.md#proverb-dialogue) when the gate is skipped |
| Unknown grounding | Six questions or situations | Six fabricated facts |

---

### Why six — and why not one (theta bias rationale)

Six is not a magic number picked for symmetry. It is a **pragmatic default**: expand the answer space enough to break single-line collapse, without leaving the **nexus** where retrieval stalled. The failure mode — retrieval bias under constraint — was first characterized in **theta bias function** research (1980s knowledge-representation work; see [`00-history-and-authority.md`](00-history-and-authority.md) Part 4). Six is the countermeasure that survived contact with real sessions: repeatable, local, and bounded.

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

When retrieval stalls, the model is not stuck nowhere. It is stuck at a **nexus** — a tight knot of constraints, near-miss rejections, and forced emission. The collapsed line (*not A, not B. C.*) still sits on that nexus. It marks **where** bias failed, not a random bad phrase. Any prosthetic response must branch from that knot, not wander to unrelated high-probability prose.

#### What six alternatives fix — local expansion, not global drift

Offering **exactly six** full replaceable options widens the solution space **locally** — around the nexus — not globally across the manuscript.

| Mechanism | Effect |
|-----------|--------|
| **Local expansion** | Forces multiple distinct escape paths from the same constraint knot — same beat type, speaker, situation, PGM locks |
| **Nexus tether** | Six is enough to branch without the bias function drifting to genre-default or unrelated completions (leaving the nexus) |
| **Decisiveness** | Each alternative is a **complete candidate**, not a rejected list — the author compares six commitments, not one comma-separated hedge |
| **Human selection** | The author's pick **is** the bias-resolution step the automated function could not complete under thin constraints |
| **Working-memory bound** | Fewer than six tends to collapse back to the model's first guess. More than six overwhelms the author and invites off-nexus drift |

**One substitution** stays inside the collapse — same nexus, no branches.

**Many more than six** often leave the nexus: alternatives solve a different problem, reconstruct plot when you needed a phrase, or revert to statistical-average diction. Same failure, wider menu.

**Six alternatives** move the contract: the machine **must not** pretend to have chosen. It **must** branch on the nexus. The author applies the final bias function — which only a human with creative intent can legitimately apply.

**Design intent (one line):** Six is the smallest branch count that breaks single-line collapse while keeping every alternative tethered to the constraint knot that caused the stall.

**For video / skim readers:** Retrieval stalls at a **nexus** (constraint knot) → **six alternatives branch locally** on that knot → **you** apply the final choice (pick, blend, cluster + author take, reject, or own line). The subsections below are the full theory; Ep. 02 can teach from this box plus the pick/cluster and malformed-beat sections.

#### Convergence rounds (when no single option wins)

Round one is not always enough. When two or three options cluster near the target but none is final — e.g. "#3 and #4 are closest" — run a **convergence round**:

1. **Name the cluster** (which numbers, what they share)
2. **Offer three** (not six) full alternatives anchored on that sub-region of the nexus
3. **Repeat** until the author picks, blends, or supplies an own line — then apply

This is **refinement inside the nexus**, not a new search. Shrinking to three reduces noise at the edges without leaving the stall point. Stop when you have a line; do not iterate indefinitely.

**Hold the line:** Convergence rounds stay on the same beat type, speaker, situation, and loaded locks. A partial match is not permission to rewrite the beat or blur domains.

#### Pick vs cluster + author take — not the same game

The six-alternative set supports **different moves**. Treat them as distinct — and hold the session to the same contracts ([`04-audit-and-governance.md`](04-audit-and-governance.md) — *What your words mean*).

| Move | You say (examples) | What should happen |
|------|------------------------|--------------|
| **Pick** | "Use 3." / "Apply option 3 with minor edit." | Named alternative → apply gate → manuscript |
| **Blend** | "Lead with 3, steal the verb from 5." | You specify merge; tool drafts **only** the named splice |
| **Cluster + author take** | "3 and 4 are closest. Here's my take: … Get me on the right track." | You supply **draft direction**; tool diagnoses, asks questions, or runs a **convergence round** — **does not** apply model option 3 or 4 |
| **Reject** | "None of these." / "All off-nexus." | Re-diagnose or new six on the same nexus |
| **Own line** | You write final line without picking a number | Audit only if requested |

**Hold the line:** *"Here's my take"* is **not** permission to apply the closest numbered option. It is permission to **work on your line** — readonly audit, constraint check, or convergence from your draft — until you explicitly authorize apply.

**Disclosure:** Pick and cluster+take are both honest prosthetic use; they are not the same labor or machine shape. See [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) — *Pick vs cluster + author take*.

#### When six options fail — the beat is often malformed

**Lead signal:** If six alternatives **still** do not land after one or more **convergence rounds**, the problem is usually **structure** — wrong order, missing situation, POV or grounding mismatch — not vocabulary. Another pass of wordings on the same beat shape makes thin solution space worse.

Six alternatives are the **default line-level** tool. In practice you rarely end on "pick option 3." More often you **supersede** the set with your own stronger line, or you discover the problem was never diction.

| What you notice | What you do |
|-----------------|------------|
| Six options orient you; **your line is stronger** | Write your line; ask for a **readonly audit** on it — don't default to the nearest numbered option |
| **Two or more rounds** of six + convergence, still none land | **Malformed beat** — rewrite the paragraph or reorder before more line shopping |
| You need to see ripple effects | Ask a **span counterfactual**: *"What would changing X do between CH## L###–L###?"* — readonly ripple discussion; see [`04-audit-and-governance.md`](04-audit-and-governance.md) — *What your words mean* |
| Geography, period, or material fact was wrong | **Reload grounding** (map + Street View, route notes); keep alternate drafts until checks pass |

**Typical flow:**

```text
Weak line → six options (often superseded, rarely picked)
        ↓
Still failing after convergence? → malformed beat → rewrite paragraph(s) or reorder
        ↓
If place/tech was wrong → reload grounding; span counterfactual if needed
        ↓
You authorize apply when the beat earns the line
```

Cross-link: [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Two-step pipeline*; [`06-failure-modes.md`](06-failure-modes.md) — *Six-alternative treadmill* and *Generic place hallucination*.

Irreducible tool-contract rules (convergence, pick vs cluster+take): [`templates/agent-instructions-starter.md`](../templates/agent-instructions-starter.md).

#### When output collapses (negation triangulation)

When you see *Not A, not B. C.*, triads, or comma-list recovery:

1. **Do not** add more rubric Signs — that shrinks the feasible region
2. **Do not** accept the single collapsed line
3. **Do** ask for six full alternatives of the correct beat type — or step back if you've already run the **six-alternative treadmill**
4. **You** pick, blend, reject, or supply your own line before apply

See [`06-failure-modes.md`](06-failure-modes.md) — *Thin solution space* and *Sparse-edge collapse*.

---

## Priority fixes gate

Authors often say: "Fix the priority issues" or "Apply the edit pass."

Under the prosthetic model, that means:

1. Complete the audit
2. Branch six-alternative sets where needed
3. **Stop**

It does **not** mean rewrite the chapter. Author authorization to "fix" does not override the apply gate. Phrase contracts: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *What your words mean*; failure shape: [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*.

**Exception:** Author names a specific line and fix ("line 47: add period") — apply only that named change.

---

## Vocabulary prosthetic (neurological context)

Some authors use LLMs specifically for **lexical retrieval** under load — when the felt experience is clear but the word will not surface. In that case:

- Unexpected word choices may be **retrieval failures**, not style choices — flag and offer alternatives
- Do not "smooth" emotional processing toward neurotypical expression unless author directs
- Session re-entry anchors help **memory boundaries between writing sessions** — what you were doing when you stopped

This is not universal. It is one documented use case that explains why "just write it yourself" is not always neurologically accurate.

---

## Two-step pipeline (structural → audit)

For grounding-heavy beats, dialogue prosthetics, and developmental edits with action items:

```text
Step 1 — Structure + grounding (readonly)
    → Step 2 — Prosthetic audit (readonly)
        → You pick, cluster + author take, or name a line fix
            → Apply to manuscript (only if you authorized)
```

**Step 1 produces:** beat sequences, fact crosswalks, breach notes, situation options, explicit questions — not manuscript substitution.

**Step 2 produces:** developmental letter; names **quote gate** failures (dialogue before speaker/situation), **tagline gate** failures (poster morals instead of craft direction), and **apply gate** violations (rewrite when you asked for critique); six options where needed — not a paste-in rewrite on "priority fixes." Gate vocabulary: [`04-audit-and-governance.md`](04-audit-and-governance.md).

Tool-contract detail for governed editors: [`templates/agent-instructions-starter.md`](../templates/agent-instructions-starter.md).

---

## Human Signals vs rubric Signs

A good rubric flags **AI textual degradation** (sterile cadence, goldilocks words, hedging, etc.). Starter categories and governance: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Signs*. **Optional** maintainer catalog (BYO Signs policy same as `04`): [novelist-plugin `prompts/rubric.md`](https://github.com/pojoguy/novelist-plugin/blob/main/prompts/rubric.md) §1 and §3 — not required to practice the prosthetic model.

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

**Distinct from retrospective meta-analysis:** Section C is **what you felt** about the session. Your **registered notes** (grounding files, route maps, chapter anchors) support **looking back later** — see [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Retrospective meta-analysis*.

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

| Topic | Document |
|-------|----------|
| Level ladder, Levels ↔ domains | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — Levels 2–3 |
| Five domains maturity | [`03-five-domains.md`](03-five-domains.md) — Domains 1–2 |
| Audit, apply gate, Signs, phrase contracts | [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| Two-step pipeline, grounding, session anchors | [`05-workflow-patterns.md`](05-workflow-patterns.md) |
| Thin solution space, treadmill, ghostwrite drift | [`06-failure-modes.md`](06-failure-modes.md) |
| Pick vs cluster disclosure | [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) |
| Indexed lookup, continuity checks | [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |
