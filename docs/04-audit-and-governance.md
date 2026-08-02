# Audit and Governance

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Audit** | A **diagnostic pass** on existing prose — what works, what fails, what to do — without substituting your voice. |
| **Governance** | The **rules** that stop a helpful tool from rewriting your book by default. |
| **Rubric / Sign** | A numbered **checklist item** for common AI-sounding or weak prose patterns — flag and explain, don't auto-fix. |
| **Editorial recommendations format** | Standard report shape: verdict → what's working → numbered fixes (what's wrong / why / what to do). |
| **Author lock** | A **permanent rule you set** (e.g. naming, calendar, voice) that overrides the tool's generic habits. |
| **Apply gate** | No manuscript change until **you** pick an option or name a specific line fix. |
| **Priority fixes** | Means **complete the audit and branch alternatives** — not permission to rewrite the chapter. |
| **Prosthetic gates** | Mechanical checks on **tool output** (e.g. no dialogue without a named speaker) before anything reaches your draft. |
| **Quote gate** | No full dialogue suggestions until **who is speaking** and **the situation** are defined. |
| **Tagline gate** | Blocks poster-style summaries (*freedom vs duty*) masquerading as craft advice. |
| **PGM lock** | A fact **frozen in your project files** — proposed edits must not contradict it. |
| **`CH## L##`** | Citation form: **chapter number and line number** (e.g. CH07 L63) so fixes target the right text. |
| **Six-alternative protocol** | Six complete options for a flagged phrase; you select before apply. |

---

Methodology without governance becomes ghostwriting with extra steps. This document covers **rubrics**, **gates**, **author locks**, and **apply authorization**.

---

## Why audit-first

LLMs are optimized for **plausible continuation**. Craft often requires **implausible specificity** — your voice, your constraints, your continuity.

Default posture:

1. **Load state** (PGMs, anchors, rubric)
2. **Diagnose** existing human prose
3. **Branch** alternatives or questions
4. **Apply** only after author instruction

---

## Prose rubric (Signs)

A practical rubric flags **AI textual degradation** — patterns that appear in unprompted model output and weak human imitation of it.

Common categories (adapt to your project):

| Category | Examples |
|----------|----------|
| Meta / attribution | "Here is the rewritten scene," tool commentary |
| Sterile cadence | Three+ single-sentence paragraphs in a row |
| Punctuation abuse | Em-dash as structural crutch |
| Emotional telling | "Fear bloomed," "He realized that…" |
| Hedging | "It seemed," "might have been," "could be argued" |
| Pompous diction | utilize, commence, robust |
| Goldilocks words | shimmer, tapestry, luminous, woven, spectral |
| Generic description | Abstract nouns where concrete detail earns the line |
| Probabilistic naming | High-frequency LLM fantasy names |

**Use:** Flag and cite — do not auto-fix. Your project may add voice-specific protocols (POV leaks, gesture format, era-locked vocabulary).

A starter list lives in mature fiction projects as ~18 Signs; fork and trim for your genre.

---

## Editorial recommendations format

Developmental feedback should read like a human editor's letter, not a chat summary.

**Default shape:**

1. **Verdict** — two to four sentences; no sycophantic opener
2. **What's working** — bullets to protect in revision
3. **Recommendations** — numbered; each with:
   - **What's wrong** (quote or cite)
   - **Why it matters** (reader experience)
   - **What to do** (direction for author to draft)
4. **Priority order** — ranked; expand with same three subheads when author needs clarity
5. **Close** — state if no manuscript changes were made; how to proceed

See [`templates/editorial-recommendations.md`](../templates/editorial-recommendations.md).

---

## Author locks

An **author lock** is an explicit, persistent rule that overrides model prior:

- "This character is never trustworthy as a mentor"
- "Accent marks speaker register — not typo"
- "This foreword URL breaks immersion — flag, don't 'fix' by removing without ask"
- "Calendar: peel is green, not red — PGM locked"

**Storage:** Markdown rationale docs, JSON PGMs, inline `author lock YYYY-MM-DD` notes.

**Agent rule:** When lock conflicts with rubric reflex, **document and offer alternatives** — do not collapse silently.

---

## Apply authorization

| Author says | Model does |
|-------------|------------|
| "Review this passage" | Audit only |
| "Priority fixes" | Audit + six-alternatives; no apply |
| "Use option 3" | Apply option 3 to flagged beat only |
| "CH07 L63: add period" | Named mechanical fix only |
| "Apply the edit pass" | **Still** requires per-item pick unless item is mechanical and named |

---

## Prosthetic gates (output-shape)

Some failures are **structural** — not fixed by more rubric Signs:

| Failure | Symptom |
|---------|---------|
| Proverb dialogue | Six "worker wisdom" lines without speaker |
| Thesis tagline | State A vs state B; nature punishes… |
| Negation triangulation | Not X, not Y. Z. |
| Ghostwrite drift | "Priority fixes" → substituted prose |
| Wrong causal merge | Adjacent lore concepts collapsed |

**Response:** Mechanical gates in a two-step pipeline — not more Signs (which shrink the feasible region and worsen collapse).

Gate checklist:

- **Quote gate** — no full dialogue line without speaker + situation
- **Tagline gate** — no poster thesis as editor summary
- **PGM lock** — proposed apply contradicts loaded state
- **Apply gate** — no manuscript edits without author pick
- **Domain collapse** — simulation treated as canon

---

## Line citation convention

When pointing at manuscript text, use stable citations:

- `CH07 L63` — chapter 7, line 63
- `CH04 L39–L40` — range

Avoid bare `L63` or `Ch.7` alone — ambiguity breaks apply gates across sessions.

---

## Priority order of work

When multiple issues are flagged:

1. **Mechanical** — typos, punctuation (if author named lines)
2. **Continuity / PGM** — wrong fact blocks revision
3. **Structural** — scene order, missing bridge beat
4. **Prose / Sign** — line-level craft
5. **Polish** — rhythm, word choice after structure holds

End audits with **suggested order of work** so author does not fix lipstick on a collapsed scene.

---

## Next

- [`05-workflow-patterns.md`](05-workflow-patterns.md) — session anchors, pipelines
- [`06-failure-modes.md`](06-failure-modes.md) — sparse-edge collapse
