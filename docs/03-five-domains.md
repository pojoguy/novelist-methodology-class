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
| **Grounding (Domain 4a)** | **Spatial / material verify** — routes, period detail, biology — before facts enter canon. |
| **Scenario simulation (Domain 4b)** | **Play-pretend** off-page — character or institutional runs; distill constraints, not manuscript prose. |
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

**What you should expect:** Offer alternatives; never substitute unless you pick.

---

## Domain 2 — Manuscript auditing and style alignment

**Intent:** Rigorous, non-sycophantic editorial pass on **human-written** prose; flag statistical tropes, cliché syntax, structural drift.

**Typical tools:** Prose rubric ("Signs"), adversarial editor persona, editorial recommendations format, **comparanda** craft comparison (quarantined references).

**Output shape:** Verdict → what's working → numbered recommendations → priority order. No apply without instruction.

**What you should expect:** Audit and report. Rewrite only when you explicitly request it after selection. Comparanda reports are diagnosis only — never paste reference prose.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

---

## Domain 3 — Systemic continuity modeling

**Intent:** Programmatic cross-reference of timeline, character state, knowledge boundaries (who knows what when), and multi-era arcs.

**Typical tools:** Timeline markdown, world PGMs, character master + chapter slices, passage re-indexing after edits, **continuity check reports**, route and place lookup.

**What you should expect:** Canon lives in your **registered files** — not chat memory. Cite report IDs from continuity checks when you need to prove a finding later.

**Value:** Prevents drift across 80k+ words and months of sessions.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Domain 4 — Sandboxes (grounding and scenario simulation)

Domain 4 splits into two modes humans already keep separate. Both use `exploration/` until promoted; **do not collapse them with each other or with Domain 3 canon reads.**

### Domain 4a — Grounding (spatial / material verify)

**Intent:** Verify place, route, period, biology, and material-culture claims against real-world or registered sources.

**Typical tools:** Grounding indexes, visual anchors, route and place lookup, explicit stop-and-ask when no route or place is on file.

Authors capture **map and Street View together** during research (e.g. Danish Cemetery near Coteau, ND — chapter 3 collapse corridor, lines 62–end). One plain-language instruction to file them; your notes persist for later loads and for **looking back** after drafting. The pair blocks default **generic fictional** places. **POV-blind** sites may never appear in narrative when the character does not know the place — your files still hold the geography. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture — map + Street View* and *POV-blind grounding*.

**Value:** Real-world spatial relations over movie logic.

**What you should expect:** Never invent highways, bearings, or period facts. **No route on file** is a success state — stop and register before you write travel prose.

**Promotes to:** `lore/routes/`, world PGMs, grounding registries.

---

### Domain 4b — Scenario simulation (play-pretend)

**Intent:** Off-page **scenario runs** — what would a character or institution conclude, permit, or refuse in a beat that is not yet drafted?

**Typical tools:** Scratch chat or `exploration/` notes; character constraint files; explicit "distill only — no manuscript apply" prompts.

**Value:** Discovers procedural intelligence, knowledge boundaries, and voice limits before on-page prose.

**What you should expect:** Output **constraints and state registers** — not paste-ready dialogue. Promote to character PGM only after you review.

**Promotes to:** `lore/characters/*.json` (master + chapter slices).

**Do not confuse with:** Domain 4a geography. **Maps answer where; play-pretend answers who under pressure.**

See: [`03b-scenario-simulation.md`](../scripts/03b-scenario-simulation.md) (Ep. 03B).

---

## Domain 5 — Foundational media blueprinting

**Intent:** Post-manuscript production: trailer timing, foley direction, storyboard beats for **human** animators and editors.

**Typical tools:** Production PGMs, frame notes, asset registries.

**Status:** Often future work for prose-only novelists; relevant for transmedia.

**What you should expect:** Out of scope until you open production workflow.

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
               Domain 4a                Domain 5
               Grounding                Production
               (spatial verify)         blueprint
                    │
               Domain 4b
               Scenario sim
               (play-pretend)
```

---

## Scope rules (do not collapse domains)

| Mistake | Why it fails |
|---------|--------------|
| Audit prose using simulation output as canon | Exploration is not manuscript truth |
| Treat geography verify as play-pretend (or vice versa) | Different questions: *where* vs *who under pressure* |
| Paste sandbox dialogue into manuscript | Distill to PGM; author writes scene |
| Generate trailer blueprints during chapter edit | Domain 5 noise pollutes Domain 1–2 |
| Let chat memory substitute for PGMs | Sessions reset; graph state does not |
| Ghostwrite during "priority fixes" | Domain 2 is diagnostic, not generative |

**Operate inside the domain you invoked.** Bridge domains only when you explicitly connect them.

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
| 2 Audit | Ad-hoc "is this AI-sounding?" | Full rubric + editorial format + **report corpus** + comparanda + apply gate |
| 3 Continuity | Character notes | Timeline + structured lookup + re-index + continuity reports |
| 4a Grounding | Ad-hoc fact checks | Registered anchors + promote-to-canon workflow |
| 4b Scenario sim | Off-page character chat | Distilled character PGMs + knowledge-state registers |
| 5 Production | — | Blueprint PGMs tied to manuscript locks |

You do not need all five to be "valid." Most serious projects start at 1–2 and grow.

---

## Next

- [`04-audit-and-governance.md`](04-audit-and-governance.md) — how Domain 2 stays readonly
- [`05-workflow-patterns.md`](05-workflow-patterns.md) — anchors and pipelines
