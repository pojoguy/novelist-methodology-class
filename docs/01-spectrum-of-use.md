# Spectrum of AI Use in Creative Writing

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **LLM** | A large language model — software trained on vast text to predict likely word sequences; used in most AI writing chat tools. |
| **Ghostwriting (level 0)** | Accepting AI-generated prose as your own with little revision — the straw-man use case in most debates. |
| **Prosthetic (levels 2+)** | AI offers options or critique; **you** write, select, and own the final words. |
| **Lexical prosthetic** | Help finding the **right word or phrase** when you know the beat but cannot retrieve the wording. |
| **Developmental audit** | A structured editorial **critique** of your draft — not a rewrite unless you authorize it. |
| **PGM** | A **project file** (often structured data) that records canon facts — character state, timeline, locks — not chat memory. |
| **Canon** | What officially counts as **true in your story** for continuity purposes. |
| **Grounding (Level 5a)** | **Spatial / material verify** — routes, period detail, biology — before facts enter canon. |
| **Scenario simulation (Level 5b)** | **Play-pretend** off-page — run a character or institution through a beat; distill constraints, not manuscript prose. |
| **Agentic workflow** | Multiple automated **steps with rules** (audit, then check, then wait for your pick) — not one "fix my chapter" prompt. |
| **Apply gate** | Nothing changes in your manuscript until **you** explicitly say which option to use. |
| **Sign** | A **craft vocabulary** name for a generic or model-typical pattern in your draft — you decide what to do. See [`04-audit-and-governance.md`](04-audit-and-governance.md). |
| **Session anchor** | An **end-of-session file** you write so the next session can reload continuity — beats, open questions, locks. Template: [`templates/session-close.md`](../templates/session-close.md). |
| **Malformed beat** | A scene or paragraph **structured wrong** — six word options will not fix it; reorder or rewrite the beat. See [`02-prosthetic-model.md`](02-prosthetic-model.md). |

---

Public argument about AI and books often collapses to a single image: someone types *"write me a bestselling YA fantasy"* and publishes the result. That is one point on a spectrum. This document maps the rest.

This doc names **levels** (how much structure you add); [`03-five-domains.md`](03-five-domains.md) names **domains** (which craft job you are doing) — same habits, different lens. See [*Levels and domains*](#levels-and-domains) after the comparison table.

For historical context, hidden daily AI use, and maintainer qualification, see [`00-history-and-authority.md`](00-history-and-authority.md).

---

## Level 0 — Ghostwriting on demand

**What it looks like:** One-shot or few-shot prompts; accept output; minimal revision; authorial credit without authorial labor.

**Typical prompts:** "Write chapter 3," "Make this more emotional," "Give me a plot twist."

**Why critics fixate here:** It is visible, fast, and easy to condemn. It also produces statistically average prose (see any "18 Signs" rubric).

**Methodology stance:** Not what this repository teaches. If you do this, you are not using a prosthetic — you are outsourcing authorship.

The straw-man pattern at Level 0 is pure outsourcing — you may never ask for audit. The same substitution habit has a name once you adopt governed critique: [**ghostwrite drift**](06-failure-modes.md#ghostwrite-drift) — audit or help requested, substitution delivered. See also [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Failure shapes — quick recognition*.

---

## Level 1 — Brainstorming and ideation

**What it looks like:** Lists of titles, loglines, character names, "what if" branches. Human selects and discards.

**Value:** Low risk; high discard rate. Good for unsticking a blank page.

**Limit:** Ideas without grounding in your voice, research, or continuity are disposable. Do not confuse volume with craft.

**Governance boundary:** Level 1 is **discovery** — not a Signs pass or developmental audit. First draft and *what if* brainstorming do not need rubric policing. The **apply gate** still applies: if anything could touch your manuscript, **you** authorize it. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *When not to audit*.

---

## Level 2 — Lexical prosthetic (vocabulary retrieval)

**What it looks like:** You know the beat; you cannot retrieve the word, idiom, or sentence shape under load. The model offers **alternatives** — inspiration, not a menu order; you pick, blend, reject, or write your own.

**Key rule:** Six alternatives, not one substitution. The model expands your retrieval set; it does not choose for you.

**Example:** Flagged line: *"He felt afraid."* → six options that preserve somatic/tactical channel → author inspired by #4, edits into final line.

**Why it matters:** This is how many neurodivergent authors use LLMs — external working memory for lexical access, not for plot or voice.

When six options still will not land, the beat is often **malformed** (structure, not diction) — stop line-shopping. **Pick** vs **cluster + author take** are different move types. See [`02-prosthetic-model.md`](02-prosthetic-model.md#when-six-options-fail--the-beat-is-often-malformed) — *When six options fail*; [`02-prosthetic-model.md`](02-prosthetic-model.md#pick-vs-cluster--author-take--not-the-same-game) — *Pick vs cluster + author take*.

---

## Level 3 — Developmental audit (read-only critique)

**What it looks like:** Adversarial editorial pass on **human-written** draft. Output: verdict, what's working, numbered recommendations (what's wrong / why it matters / what to do). **No manuscript apply** unless you explicitly authorize.

**Typical artifacts:** Rubric Signs (AI textual degradation), POV breaches, pacing, continuity flags.

**Key rule:** "Priority fixes" means **complete the audit and branch alternatives** — not rewrite the chapter. Full governance: [`04-audit-and-governance.md`](04-audit-and-governance.md) — apply gate, Signs, word contracts, *When not to audit*, *Failure shapes — quick recognition*. Named trap when critique becomes rewrite: [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*.

---

## Level 4 — Continuity and knowledge state

**What it looks like:** Character sheets, timeline graphs, location registries, "program guides" (PGMs) loaded before each session. The model cross-references multi-era timelines, gear state, who knows what when.

**Value:** Humans forget; graphs do not. Reduces "wait, didn't she lose that knife in chapter 4?" errors.

**Tooling:** JSON lore files, structured fact lookup, session anchors with continuity blocks.

**Key rule:** Canon lives in **registered state**, not in chat memory. Chat is ephemeral; PGMs persist.

**Why Level 4 is not "Domain 4":** [`03-five-domains.md`](03-five-domains.md) **Domain 1** covers lexical help **and** light chapter state (anchors, small PGMs). **Level 4** is when **graph-scale** continuity — timeline, who-knows-what, multi-era arcs — becomes the main job; that maps to **Domain 3**. You still use the same registered files for word-finding (Domain 1) while continuity modeling deepens (Domain 3).

---

## Level 5 — Sandboxes (two kinds humans keep separate)

Level 5 is **not** one bucket. **Grounding** and **scenario simulation** share a promotion workflow (exploration → canon) but answer different questions.

### Level 5a — Grounding (spatial / material verify)

**Question:** *Is this place, route, period detail, or material claim true or registered?*

**What it looks like:** Highway routing, bearings, weather windows, period medical practice, biology, material culture — checked against sources or registered lore **before** prose locks. File **map and Street View together** during research so later sessions load one place, not a generic movie set.

**POV-blind sites:** Your grounding files may hold coordinates the **character never names** — author knows the cemetery; the boy on the roadside does not. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture*, *POV-blind grounding*; walkthrough: [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md).

**Value:** Stops movie logic from becoming manuscript logic.

**Key rule:** When grounding is unknown, **stop and ask** — do not let the model invent plausible-sounding geography.

**Demo:** [`01c-level-05-grounding.md`](../scripts/01c-level-05-grounding.md) — live `geography_query`.

**Promotes to:** `lore/routes/`, grounding indexes, world PGMs.

---

### Level 5b — Scenario simulation (play-pretend)

**Question:** *What would this character or institution do, say, or conclude in a scene that is not on the page?*

**What it looks like:** Off-screen runs — caseworker probing a journal, institutional triage logic, "what does she know after three sessions?" Output is **constraints and knowledge state**, not chapter dialogue pasted from chat.

**Value:** Discovers voice boundaries, procedural intelligence, and who-knows-what **before** you draft the on-page beat.

**Key rule:** Sandbox dialogue is **not** manuscript prose. Distill → promote to character PGM → **you** write the scene.

**Demo:** [`01c-level-05b-scenario-simulation.md`](../scripts/01c-level-05b-scenario-simulation.md) — synthetic fixture only.

**Promotes to:** `lore/characters/*.json` (master + chapter slices), `what_*_knows_by_end_of_simulation` registers.

**Do not confuse with:** Level 5a geography. Maps answer *where*; play-pretend answers *who under pressure*.

See also: [`03-five-domains.md`](03-five-domains.md) (Domain 4a / 4b), [`03b-scenario-simulation.md`](../scripts/03b-scenario-simulation.md) (Ep. 03B explainer).

---

## Level 6 — Production blueprinting (post-manuscript)

**What it looks like:** Trailer storyboards, foley direction, frame-timing notes for human animators/editors. AI assists pre-production; humans execute.

**Status:** Often future work for novelists; common in transmedia projects.

---

## Level 7 — Agentic methodology (orchestrated workflows)

**What it looks like:** Multi-step pipelines with explicit gates:

1. **Readonly structure + grounding pass** → beat sequence, PGM crosswalk, questions
2. **Readonly prosthetic audit** → quote gates, tagline gates, apply gates
3. **Author pick** → then apply

Plus: **session anchors** (continuity re-entry), post-session meta-analysis (what worked / failed per product), a **project rules file** (e.g. Cursor rules), and indexed habits — passage lookup, continuity checks, comparanda — in [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) and [`05-workflow-patterns.md`](05-workflow-patterns.md).

**Value:** Repeatable craft infrastructure across months of work and multiple model vendors — with indexed state, not chat memory.

**How this layer emerged:** Levels 2–3 (prosthetic + audit) work in **any chat tool** with discipline. Levels 4–7 appear when a novel outgrows what you can hold in one thread — canon drifts, line numbers lie, and you need **filed state** (PGMs, anchors, continuity checks, passage lookup) you reload each session instead of trusting chat memory. Habits: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) and [`05-workflow-patterns.md`](05-workflow-patterns.md).

**This repository:** Primarily documents Levels 2–7.

---

## Comparison table

| Level | Human prose mass | Model role | Apply gate |
|-------|------------------|------------|------------|
| 0 Ghostwrite | Low | Author | None |
| 1 Brainstorm | N/A | Idea fountain | Human discards |
| 2 Lexical prosthetic | High | Retrieval set | Author picks |
| 3 Audit | High | Critic | Author authorizes |
| 4 Continuity | High | Graph traversal | Author authorizes |
| 5a Grounding | High | Spatial / material verify | Author promotes canon |
| 5b Scenario sim | High | Play-pretend off-page | Author promotes PGM; writes scene |
| 6 Production | N/A | Blueprint | Human crew |
| 7 Agentic | High | Multi-step readonly passes | Multi-gate workflow |

---

## Levels and domains

Two maps, one methodology — **do not** assume Level N = Domain N.

| Level | Rough domain map | Note |
|-------|------------------|------|
| **0** | — | Outside methodology (ghostwriting) |
| **1** | — | Discovery / ideation; not rubric or governance policing |
| **2** | Domain 1 (lexical) | Word-finding half of Domain 1 |
| **3** | Domain 2 | Audit + governance → [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| **4** | Domain 3 (+ Domain 1 state) | Graph-scale continuity; lexical work still uses same PGMs |
| **5a / 5b** | Domain 4a / 4b | Grounding vs scenario simulation — same split as [`03-five-domains.md`](03-five-domains.md) |
| **6** | Domain 5 | Post-manuscript production |
| **7** | All + infra | Orchestration across domains — [`05-workflow-patterns.md`](05-workflow-patterns.md), [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |

Level 1 is **pre-domain ideation**: lists and *what if* branches before you are protecting draft prose under audit. Domain detail and maturity checklist: [`03-five-domains.md`](03-five-domains.md).

---

## Talking to skeptics

When someone says "AI can't write real books," you can agree — **if** they mean Level 0.

When someone says "any AI use is cheating," ask which level they mean. Lexical prosthetic and developmental audit are closer to spell-check, continuity spreadsheet, and a brutally honest beta reader than to ghostwriting.

When someone says "AI will replace authors," point to Levels 4–7: the human work is **designing the methodology**, **maintaining state**, and **authorizing every change**. That is not less work — it is different work.

---

## Demonstrating the spectrum (Levels 0–7)

**Do not** use a governed IDE session (e.g. Cursor with project rules loaded) to demonstrate Level 0 — apply gates and prosthetic protocol are already active. That stack documents **Levels 2–7**.

| Level | Demo script | Tool | Notes |
|-------|-------------|------|-------|
| **0** | [`01b-level-zero-demo.md`](../scripts/01b-level-zero-demo.md) | Blank **frontier** chat | ~5 min contrast; synthetic line only |
| **1–7** | [`01c-spectrum-demos-index.md`](../scripts/01c-spectrum-demos-index.md) | Per-level (see index) | Level **5a** + **5b** are separate demos |

**Level 0:** blank frontier chat UI (ChatGPT, Claude, Gemini, etc.) with **no** custom instructions.

**Levels 1–2, 6:** frontier chat acceptable (explicit prompts in each script).

**Levels 3–5, 7:** Cursor + templates / fixtures / rules — same governed stack this series documents.

**Disclosure (all demos):** staged on synthetic prose — not a real manuscript workflow.

---

## Where to start (by week)

Same ramp as [`README.md`](../README.md#where-to-start-by-week) — summarized here:

### How this repo relates to tooling

**Two trees, one practice.** This repository (`novelist-methodology-class`) is **methodology** — how you work. [novelist-plugin](https://github.com/pojoguy/novelist-plugin) is **optional tooling** — MCP server, prompts, rubrics, continuity helpers. They are separate repositories; nothing in this tree is required to run novelist-plugin, and novelist-plugin is not required to learn Week 1 habits here.

| What | Role for learners |
|------|-------------------|
| **This repo** | Methodology docs, templates, examples — **start here** |
| **[novelist-plugin](https://github.com/pojoguy/novelist-plugin)** | Optional engine — [getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md), registered lookup, continuity checks — **Week 3+** when capture hurts |
| **Your manuscript repo** (e.g. maintainer's live novel via MCP) | Where prose and canon live — **not required** to learn Week 1 Levels 2–3 |

You do **not** need novelist-plugin or a governed IDE to practice prosthetic + audit in any chat tool.

| Week | Focus |
|------|--------|
| **1** | This spectrum + [`02-prosthetic-model.md`](02-prosthetic-model.md) + session anchor template — **any chat tool** |
| **2** | Map + Street View in a folder; manual route notes before travel beats |
| **3+** | Optional [novelist-plugin getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md) when you want registered lookup |

Levels 2–3 (prosthetic + audit) are achievable in Week 1 without Cursor or lookup tiers. Levels 4–7 grow as your project needs registered state.

---

## Next

| Topic | Document |
|-------|----------|
| Prosthetic model, six alternatives, malformed beat | [`02-prosthetic-model.md`](02-prosthetic-model.md) — Levels 2+ |
| Domains maturity checklist | [`03-five-domains.md`](03-five-domains.md) — pairs with [*Levels and domains*](#levels-and-domains) |
| Audit + governance, Signs, apply gate | [`04-audit-and-governance.md`](04-audit-and-governance.md) — Level 3 |
| Session anchors, two-step pipeline, grounding | [`05-workflow-patterns.md`](05-workflow-patterns.md) — Levels 5a, 7 habits |
| Failure catalog (ghostwrite drift, treadmill, …) | [`06-failure-modes.md`](06-failure-modes.md) — Level 0+ traps |
