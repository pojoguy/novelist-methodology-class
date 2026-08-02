# Five Domains of AI Use

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Domain (1–5)** | A **category of AI use** — lexical help, audit, continuity, grounding, or production planning — kept separate so they do not blur together. |
| **Lexical / continuity assistance (Domain 1)** | Word-finding and **remembering story state** — external memory, not ghostwriting. |
| **Manuscript audit (Domain 2)** | Critical **feedback** on draft prose — flags problems; you revise. |
| **Continuity modeling (Domain 3)** | Cross-checking **timeline, who knows what, and character state** across a long book. |
| **Simulation / grounding (Domain 4)** | Testing beats against **real-world facts** in a sandbox before locking them into the story. |
| **Production blueprinting (Domain 5)** | Planning **trailer, audio, or visual** production — for human crews, not prose generation. |
| **PGM** | A structured file holding **official story facts** the tool must read before answering. |
| **Canon** | Story truth as **registered in your project files** — not whatever the chat said last session. |
| **Exploration / sandbox** | Scratch work marked **not official** until you promote it to canon. |
| **Domain collapse** | Mistake: using a **sandbox fact** or **craft comparison** as if it were story canon. |
| **Prosthetic** | You choose; the tool proposes within rules. |
| **Comparanda** | **Quarantined excerpts** from other books used only to compare **craft technique** — never pasted into your draft. |
| **Verify / continuity report** | An automated **fact-check** with rule names and citations — not a fuzzy search. |

---

Long-form creative projects rarely use AI in only one way. This framework separates **five domains** so you do not collapse audit into ghostwriting, or simulation into canon.

**Rule:** Creative intent and final prose mass remain human. AI assists retrieval, audit, modeling, simulation, and production blueprinting.

---

## Domain 1 — Lexical and continuity assistance

**Intent:** External working memory and vocabulary retrieval; bridge processing gaps **without altering creative intent**.

**Typical tools:** Six-alternative protocol, session anchors, chapter-level character/world state files.

**Status in mature projects:** Often the first domain implemented — small PGMs per chapter, anchor persistence.

**Agent default:** Offer alternatives; never substitute unless author picks.

---

## Domain 2 — Manuscript auditing and style alignment

**Intent:** Rigorous, non-sycophantic editorial pass on **human-written** prose; flag statistical tropes, cliché syntax, structural drift.

**Typical tools:** Prose rubric ("Signs"), adversarial editor persona, editorial recommendations format, **comparanda** craft comparison (quarantined references).

**Output shape:** Verdict → what's working → numbered recommendations → priority order. No apply without instruction.

**Agent default:** Audit and report. Rewrite only on explicit request after author selection. Comparanda reports are diagnosis only — never paste reference prose.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

---

## Domain 3 — Systemic continuity modeling

**Intent:** Programmatic cross-reference of timeline, character state, knowledge boundaries (who knows what when), and multi-era arcs.

**Typical tools:** Timeline markdown, world PGMs, character master + chapter slices, fact-query APIs, **passage reanchor/ingest**, **verify_run** continuity reports, geography query.

**Value:** Prevents drift across 80k+ words and months of sessions.

**Agent default:** Read PGMs as graph state — not soft suggestions. Cite `event_id` from verify — not chat memory.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Domain 4 — Environmental and material simulation

**Intent:** Interactive sandboxes: routing, weather, period medicine, biology, material culture — pressure-tested against real-world constraints.

**Typical tools:** Grounding indexes, visual anchors, exploration folders (non-canonical until promoted), explicit STOP-and-ask when sample is missing.

**Value:** Real-world grounding over movie logic.

**Agent default:** Never treat exploration chat as canon without PGM registration.

---

## Domain 5 — Foundational media blueprinting

**Intent:** Post-manuscript production: trailer timing, foley direction, storyboard beats for **human** animators and editors.

**Typical tools:** Production PGMs, frame notes, asset registries.

**Status:** Often future work for prose-only novelists; relevant for transmedia.

**Agent default:** Out of scope until author opens production workflow.

---

## Domain map

```text
                    ┌─────────────────────────┐
                    │   Human author intent   │
                    │   + final prose mass    │
                    └───────────┬─────────────┘
                                │
        ┌───────────────────────┼───────────────────────┐
        │                       │                       │
   Domain 1              Domain 2                 Domain 3
   Lexical /             Audit /                  Continuity
   continuity            style                    modeling
        │                       │                       │
        └───────────────────────┼───────────────────────┘
                                │
                    ┌───────────┴───────────┐
                    │                       │
               Domain 4                 Domain 5
               Simulation              Production
               / grounding              blueprint
```

---

## Scope rules (do not collapse domains)

| Mistake | Why it fails |
|---------|--------------|
| Audit prose using simulation output as canon | Exploration is not manuscript truth |
| Generate trailer blueprints during chapter edit | Domain 5 noise pollutes Domain 1–2 |
| Let chat memory substitute for PGMs | Sessions reset; graph state does not |
| Ghostwrite during "priority fixes" | Domain 2 is diagnostic, not generative |

**Operate inside the domain the author invokes.** Bridge domains only when author explicitly connects them.

---

## Cross-cutting: methodology tuning

Post-session meta-analysis (Section C of session anchors) tunes **all domains** across LLM products:

1. What worked well this session?
2. What could be improved?
3. What did not work?

This feedback loop updates **operating procedure** — not by adding endless rubric rules, but by adjusting load order, gates, and tool choice.

---

## Maturity checklist

| Domain | Begun | Mature |
|--------|-------|--------|
| 1 Lexical | Six-alternatives on flagged lines | PGMs + anchors per chapter |
| 2 Audit | Ad-hoc "is this AI-sounding?" | Full rubric + editorial format + comparanda + apply gate |
| 3 Continuity | Character notes | Timeline + L2 query + reanchor/ingest + verify_run |
| 4 Grounding | Ad-hoc fact checks | Registered anchors + promote-to-canon workflow |
| 5 Production | — | Blueprint PGMs tied to manuscript locks |

You do not need all five to be "valid." Most serious projects start at 1–2 and grow.

---

## Next

- [`04-audit-and-governance.md`](04-audit-and-governance.md) — how Domain 2 stays readonly
- [`05-workflow-patterns.md`](05-workflow-patterns.md) — anchors and pipelines
