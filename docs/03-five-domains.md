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
| **PGM** | A structured file holding **official story facts** you register for lookup — not chat memory. |
| **Canon** | Story truth as **registered in your project files** — not whatever the chat said last session. |
| **Exploration / sandbox** | Scratch work marked **not official** until you promote it to canon. |
| **Domain collapse** | Mistake: using a **sandbox fact** or **craft comparison** as if it were story canon. |
| **Prosthetic** | You choose; the tool proposes within rules. |
| **Comparanda** | **Quarantined excerpts** from other books used only to compare **craft technique** — never pasted into your draft. |
| **Verify / continuity report** | An automated **fact-check** with rule names and citations — not a fuzzy search. |
| **POV-blind grounding** | **You** hold place coordinates in files; the **character** may never name the site on the page. |
| **Apply gate** | Nothing changes in your manuscript until **you** explicitly authorize a specific change. |

---

Long-form creative projects rarely use AI in only one way. This framework separates **five domains** so you do not collapse audit into ghostwriting, or simulation into canon.

**Rule:** Creative intent and final prose mass remain human. AI assists retrieval, audit, modeling, simulation, and production blueprinting.

**Where this doc sits:** [`01-spectrum-of-use.md`](01-spectrum-of-use.md) names **levels** (how much structure you add); this doc names **domains** (which craft job you are doing). The prosthetic **contract** (six alternatives, move types, two-step) lives in [`02-prosthetic-model.md`](02-prosthetic-model.md); **Domain 2 governance** (apply gate, Signs, phrase contracts) in [`04-audit-and-governance.md`](04-audit-and-governance.md); **file and reload habits** in [`05-workflow-patterns.md`](05-workflow-patterns.md).

### Domains ↔ levels (do not assume Domain N = Level N)

**Level 1** (brainstorming) is **pre-domain** — discovery before you are protecting draft prose under audit. Full table: [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — [*Levels and domains*](01-spectrum-of-use.md#levels-and-domains).

| Domain | Rough level map | Note |
|--------|-----------------|------|
| — | **Level 1** | Ideation; not rubric policing |
| **1** Lexical / light state | **Level 2** (+ light Domain 1 PGMs at higher levels) | Word-finding; anchors and small PGMs |
| **2** Audit | **Level 3** | Readonly critique → [`04`](04-audit-and-governance.md) |
| **3** Continuity modeling | **Level 4** | Graph-scale timeline / who-knows-what |
| **4a / 4b** | **Level 5a / 5b** | Grounding vs scenario simulation |
| **5** Production | **Level 6** | Post-manuscript blueprints |
| Cross-cutting | **Level 7** | Orchestration — [`05`](05-workflow-patterns.md), [`08`](08-infrastructure-techniques.md) |

---

## Domain 1 — Lexical and continuity assistance

**Intent:** External working memory and vocabulary retrieval; bridge processing gaps **without altering creative intent**.

**Domain 1 vs Domain 3:** Domain 1 covers lexical help **and** light chapter state (session anchors, small PGMs). **Domain 3** is when **graph-scale** continuity — timeline, who-knows-what, multi-era arcs — becomes the main job. Same split as [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — Level 4 vs Domain 1. Filing habits: [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Knowledge state (PGMs)*.

**Typical tools:** Six-alternative protocol, session anchors, chapter-level character/world state files.

**Status in mature projects:** Often the first domain implemented — small PGMs per chapter, anchor persistence.

**What you do:** Flag a weak line → ask for six full alternatives → **pick**, **blend**, **cluster + author take**, reject, **supersede** with your own line, or write your own — then authorize apply. When six options still will not land after convergence rounds, the beat is often **malformed** (structure, not diction) — stop line-shopping. Move types and exits: [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Pick vs cluster + author take*, *When six options fail — the beat is often malformed*.

**Common mistake:** Accepting one substituted line because it "sounds fine."

**What you're doing instead:** Expanding your retrieval set; you keep creative intent.

---

## Domain 2 — Manuscript auditing and style alignment

**Intent:** Rigorous, non-sycophantic editorial pass on **human-written** prose; flag statistical tropes, cliché syntax, structural drift.

**Typical tools:** Prose rubric ("Signs"), adversarial editor persona, editorial recommendations format, **comparanda** craft comparison (quarantined references).

**Output shape:** Verdict → what's working → numbered recommendations → priority order. No apply without instruction.

**What you do:** Request a readonly audit — verdict, what's working, numbered fixes. Revise yourself unless you explicitly ask for a named apply.

**Common mistake:** Saying "priority fixes" and getting a rewritten chapter.

**What you're doing instead:** Treating audit as a **letter from an editor**, not a paste buffer.

**Governance (Domain 2 playbook):** Apply gate, Signs, word contracts, *When not to audit*, *Failure shapes — quick recognition* — [`04-audit-and-governance.md`](04-audit-and-governance.md). Named trap when critique becomes rewrite: [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

---

## Domain 3 — Systemic continuity modeling

**Intent:** Programmatic cross-reference of timeline, character state, knowledge boundaries (who knows what when), and multi-era arcs.

**Typical tools:** Timeline markdown, world PGMs, character master + chapter slices, passage re-indexing after edits, **continuity check reports**, route and place lookup.

**What you do:** Keep timeline and character state in **registered files**; load before structural work; cite continuity report IDs when you need proof later.

**Common mistake:** Trusting chat memory for who knows what when.

**What you're doing instead:** External relationship memory — the same notes you'd keep in a bible, made loadable.

**Value:** Prevents drift across 80k+ words and months of sessions.

**Reanchor after edits:** Substantive chapter changes shift `CH## L##` — re-index the chapter or cite a quoted snippet until locators match. [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Passage reanchor*; failure when skipped: [`06-failure-modes.md`](06-failure-modes.md) — *Stale passage index*.

**Continuity check vs developmental audit:** A **continuity check** is a readonly **fact compare** against registered canon (reference ID, you decide fixes). A **developmental pass** is a letter you act on — different job, same apply gate. Report types: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Editorial report corpus*.

See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Domain 4 — Sandboxes (grounding and scenario simulation)

Domain 4 splits into two modes humans already keep separate. Both use `exploration/` until promoted; **do not collapse them with each other or with Domain 3 canon reads.**

### Domain 4a — Grounding (spatial / material verify)

**Intent:** Verify place, route, period, biology, and material-culture claims against real-world or registered sources.

**Typical tools:** Grounding indexes, visual anchors, route and place lookup, explicit stop-and-ask when no route or place is on file.

Authors capture **map and Street View together** during research (e.g. Danish Cemetery near Coteau, ND — chapter 3, lines 62–end). One plain-language instruction to file them; your notes persist for later loads and for **looking back** after drafting. The pair blocks default **generic fictional** places. **POV-blind** sites may never appear in narrative when the character does not know the place — your files still hold the geography. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture* and [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md).

**Value:** Real-world spatial relations over movie logic.

**What you do:** File map + ground photos; load before revising the beat; stop when no route is registered — file route notes first.

**Common mistake:** Searching the manuscript for a place name the POV never receives, then assuming research failed.

**What you're doing instead:** Checking prose against **what you documented** (no walls, no trees, bald prairie) — author coordinates separate from character knowledge.

**Promotes to:** `lore/routes/`, world PGMs, grounding registries.

---

### Domain 4b — Scenario simulation (play-pretend)

**Intent:** Off-page **scenario runs** — what would a character or institution conclude, permit, or refuse in a beat that is not yet drafted?

**Typical tools:** Scratch chat or `exploration/` notes; character constraint files; explicit "distill only — no manuscript apply" prompts.

**Value:** Discovers procedural intelligence, knowledge boundaries, and voice limits before on-page prose.

**What you do:** Run off-page "what would they do?" sessions; distill **constraints and knowledge state**; promote to character files only after you review; **you** write the scene.

**Common mistake:** Pasting sandbox dialogue into the manuscript.

**What you're doing instead:** Play-pretend as research — maps answer *where*; this answers *who under pressure*.

**Promotes to:** `lore/characters/*.json` (master + chapter slices).

**Do not confuse with:** Domain 4a geography. **Maps answer where; play-pretend answers who under pressure.**

**Workflow:** Off-page run → distill → file in `exploration/` → promote to character PGM when ready → **you** write the scene. [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Scenario simulation — what you do (Level 5b)*. Explainer: [`03b-scenario-simulation.md`](../scripts/03b-scenario-simulation.md) (Ep. 03B).

---

## Domain 5 — Foundational media blueprinting

**Intent:** Post-manuscript production: trailer timing, foley direction, storyboard beats for **human** animators and editors.

**Typical tools:** Production PGMs, frame notes, asset registries.

**Status:** Often future work for prose-only novelists; relevant for transmedia.

**What you do:** Open production workflow only when the manuscript is far enough along; keep trailer/storyboard notes separate from chapter edits.

**Common mistake:** Mixing production blueprints into live drafting sessions.

**What you're doing instead:** Planning for human crews — not generating prose.

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
| Treat **comparanda** (craft reference excerpts) as canon | [**Comparanda bleed**](06-failure-modes.md#comparanda-bleed) / [**domain collapse**](06-failure-modes.md#domain-collapse) — quarantine references; never paste into manuscript |

**Operate inside the domain you invoked.** Bridge domains only when you explicitly connect them.

---

## Cross-cutting: methodology tuning

**Section C** of your session anchor (post-session meta-analysis) tunes **all domains** across LLM products — **how the session felt**, not what place a chapter used:

1. What worked well this session?
2. What could be improved?
3. What did not work?

This feedback loop updates **operating procedure** — not by adding endless rubric rules, but by adjusting load order, gates, and tool choice. For **looking back months later** at grounding files, route notes, and POV-blind sites (reconstructing what a span assumed), see [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Retrospective meta-analysis* — distinct from Section C.

---

## Maturity checklist

| Domain | Begun | Mature |
|--------|-------|--------|
| 1 Lexical | Six-alternatives on flagged lines | PGMs + anchors per chapter |
| 2 Audit | Ad-hoc "is this AI-sounding?" | Full rubric + editorial format + **report corpus** + comparanda + apply gate + **when not to audit** discipline ([`04`](04-audit-and-governance.md)) |
| 3 Continuity | Character notes | Timeline + structured lookup + re-index + continuity reports |
| 4a Grounding | Ad-hoc fact checks | Registered anchors + promote-to-canon workflow |
| 4b Scenario sim | Off-page character chat | Distilled character PGMs + knowledge-state registers |
| 5 Production | — | Blueprint PGMs tied to manuscript locks |

You do not need all five to be "valid." Most serious projects start at 1–2 and grow.

---

## Next

| Topic | Document |
|-------|----------|
| Level ladder, Levels ↔ domains | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — [*Levels and domains*](01-spectrum-of-use.md#levels-and-domains) |
| Prosthetic contract, Domains 1–2 moves | [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| Domain 2 governance, Signs, reports | [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| Anchors, grounding, 5b workflow, reanchor | [`05-workflow-patterns.md`](05-workflow-patterns.md) |
| Domain collapse, comparanda bleed, … | [`06-failure-modes.md`](06-failure-modes.md) |
| Comparanda, lookup tiers, infra detail | [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |
| POV-blind grounding walkthrough | [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md) |
