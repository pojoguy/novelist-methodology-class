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
| **PGM** | **Organized working notes** — character state, timeline, locks — saved in a file you reload, not chat memory. |
| **Canon** | What officially counts as **true in your story** for continuity purposes. |
| **Grounding (Level 5a)** | **Spatial / material verify** — routes, period detail, biology — before facts enter canon. |
| **Scenario simulation (Level 5b)** | **Play-pretend** off-page — run a character or institution through a beat; distill constraints, not manuscript prose. |
| **Agentic workflow** | Multiple automated **steps with rules** (audit, then check, then wait for your pick) — not one "fix my chapter" prompt. |
| **Apply gate** | Nothing changes in your manuscript until **you** explicitly say which option to use. |
| **Sign** | A **craft vocabulary** name for a generic or model-typical pattern in your draft — you decide what to do. See [`04-audit-and-governance.md`](04-audit-and-governance.md). |
| **Session anchor** | An **end-of-session file** you write so the next session can reload continuity — beats, open questions, locks. Template: [`templates/session-close.md`](../templates/session-close.md). |
| **Malformed beat** | A scene or paragraph **structured wrong** — six word options will not fix it; reorder or rewrite the beat. See [`02-prosthetic-model.md`](02-prosthetic-model.md). |
| **Frontier chat** | A general-purpose LLM in a browser tab (ChatGPT, Claude, Gemini, etc.) — no project plugins or indexed lookup required. |
| **Sycophantic audit** | Flattery-first critique that misses real problems — default frontier-chat habit when you ask for "feedback." See [`06-failure-modes.md`](06-failure-modes.md). |

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

**What it looks like:** **Adversarial** editorial pass on **human-written** draft — readonly, objective, not a cheerleader. Output: verdict, what's working, numbered recommendations (what's wrong / why it matters / what to do). **No manuscript apply** unless you explicitly authorize.

**Typical artifacts:** Rubric Signs (AI textual degradation), POV breaches, pacing, continuity flags.

**Key rule:** "Priority fixes" means **complete the audit and branch alternatives** — not rewrite the chapter. Full governance: [`04-audit-and-governance.md`](04-audit-and-governance.md) — apply gate, Signs, word contracts, *When not to audit*, *Failure shapes — quick recognition*. Named trap when critique becomes rewrite: [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*.

---

## Level 4 — Continuity and knowledge state

**What it looks like:** Character sheets, timeline graphs, location registries, "program guides" (PGMs) loaded before each session. The model cross-references multi-era timelines, gear state, who knows what when.

**Value:** Humans forget; graphs do not. Reduces "wait, didn't she lose that knife in chapter 4?" errors.

**Tooling:** PGM files — usually a **mix of Markdown** (richer narrative notes), **JSON** (precise fact blocks), and **Cypher** (relationship joins: who-knows-what, arc links); structured fact lookup; session anchors with continuity blocks.

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

**How this layer emerged:** Levels 2–3 (prosthetic + audit) work in **any chat tool** with discipline. **Initial PGMs** were also drafted in frontier chat and saved to files. Levels 4–7 deepen when a novel outgrows what you can **reload from paste** each session — canon drifts, line numbers lie, and you need **registered lookup** (passage index, continuity checks) instead of trusting chat memory. Habits: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) and [`05-workflow-patterns.md`](05-workflow-patterns.md).

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

## Frontier chat only (no tooling required)

**Most of this methodology was prototyped in ordinary chat** — ChatGPT, Claude, Gemini, or any frontier LLM in a browser tab. Prosthetic habits, adversarial audit, and the **first PGMs** (character state, timelines, locks) were all built there — then **saved to files you control**. What came later was **registered lookup** (indexed search, continuity checks, MCP) when re-pasting canon every session stopped scaling — and, on long-form work, when **arc density** outgrew what one chat session could hold. You do **not** need novelist-plugin, Cursor, or a separate novel repo to practice the core contract: diagnose, branch, **you** pick, **you** apply — or to **draft** your first PGM sheets in chat and file them yourself.

### What you need

| You have | You do not need (yet) |
|----------|------------------------|
| A frontier chat UI | novelist-plugin or MCP |
| Your manuscript (or a draft passage) | Passage index or RAG |
| Optional: a notes file per session ([`templates/session-close.md`](../templates/session-close.md)) | Cursor rules or agent skills |
| Optional: **adversarial audit discipline** + word contracts in custom instructions | Pre-built PGMs from a vendor |
| A folder on your machine for **PGMs you save** (Markdown, JSON, Cypher — mix by job; drafted in chat, filed by you) | Registered lookup tiers (until re-paste hurts) |

Treat the chat thread as **conversation context** — useful for the last few turns, unreliable as canon. See [`glossary.md`](glossary.md) — *Context*.

### Turn off sales mode (keep adversarial discipline)

Frontier chat defaults to **please you** — enthusiastic openers, flattery, eager rewrites. That is [**sycophantic audit**](06-failure-modes.md#sycophantic-audit). The counterweight is not another performance; it is **adversarial discipline** you hold the model to: readonly critique, line-tied notes, no cheerleading, no substitute prose. That stance is how this methodology was **learned on frontier models** before any tooling existed.

**Sales mode** is the gap between the label and the behavior:

| Sounds rigorous | Still sales mode if… |
|-----------------|----------------------|
| *"Brutal but professional adversarial developmental editor"* in custom instructions | No **word contracts** (*priority fixes*, apply gate); model still rewrites or flatters |
| Store-bought "tough love beta reader" GPT | No **letter shape**; poster morals and generic praise slip through |
| Long thread that "remembers" your editor persona | Context noise; flattery momentum; no fresh readonly pass |

**Adversarial discipline that works in frontier chat** pairs stance with structure:

1. **Adversarial, not sycophantic** — objective pass on **your** draft; flag Signs and continuity holes; brief "what's working," then problems. Not *"Beautiful prose!"* then three nits.
2. **Readonly + apply gate** — audit and alternatives; **you** revise. *Priority fixes* = finish the letter and branch options — not chapter substitution.
3. **Letter shape every pass** — [`templates/editorial-recommendations.md`](../templates/editorial-recommendations.md): verdict, numbered line-tied notes, priority order, close stating whether the manuscript was unchanged.
4. **Word contracts in custom instructions** — paste apply-gate and *priority fixes* meanings once; add adversarial / non-cheerleader stance. Starter block: [`templates/agent-instructions-starter.md`](../templates/agent-instructions-starter.md) (trim genre; keep discipline + gates).
5. **Fresh thread for audit work** when you can — long chats soften critique even when the persona says "brutal."
6. **If the model rewrites anyway**, stop and name [**ghostwrite drift**](06-failure-modes.md#ghostwrite-drift) — reset contracts; do not argue in character.

Screen recordings of levels 0–7: [`01b-level-zero-demo.md`](../scripts/01b-level-zero-demo.md), [`01c-spectrum-demos-index.md`](../scripts/01c-spectrum-demos-index.md).

### What works in chat alone

| Level | In frontier chat? | Notes |
|-------|-------------------|--------|
| **1** Brainstorm | Yes | High discard; no rubric policing |
| **2** Lexical prosthetic | Yes | Six alternatives; you pick or write your own → [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| **3** Developmental audit | Yes | Read-only letter; **apply gate** — nothing pasted into the manuscript without your OK → [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| **4** Continuity | Yes to **build**; partial to **hold** | Draft character sheets and who-knows-what in chat; **you** save the file and reload it each session. Chat will not reliably remember joins → [`06-failure-modes.md`](06-failure-modes.md) — *Context amnesia* |
| **5a / 5b** Sandboxes | Partial | Map + Street View in a **folder you control**; chat verifies against what you paste or describe — not against a live index |
| **6** Production | Yes | Blueprinting prompts; no manuscript apply |
| **7** Agentic | No (honestly) | Multi-gate orchestration needs persisted rules and filed state → Level 7 demos use a governed IDE |

**Week 1 honest goal:** Levels **2–3** with discipline — flag → six options or audit letter → you revise. That is already beyond ghostwriting. **Week 2+:** start **PGM files** in chat (distill from scenario work, continuity passes) — save them yourself; indexing can wait until re-paste or arc density hurts (often sooner than you expect on a braided novel).

### How much fits in one frontier session

Maintainer experience on long-form work — not a token-count rule:

**About one chapter per sitting** is the practical ceiling for governed frontier work in a single session — prosthetic passes, adversarial audit, filing what you learned. A single flagged line or a brainstorm list can be much smaller. A full chapter audit with six-alternative branches is already a full session.

**Arc density beats page count.** A **half-page vignette** that resolves **several long-running arcs at once** can bog down sooner than a whole chapter of single-arc material. The model holds words more easily than **joins** — who knows what, which arc owns the beat, which locks apply. That is [**relationship collapse**](glossary.md#relationship-collapse-attention) and [**context amnesia**](06-failure-modes.md#context-amnesia) in practice — not "you ran out of context window."

**Tooling arrives sooner than the week table suggests** if you are writing a braided novel. Frontier chat is enough to **learn** the contract and **draft** your first PGM sheets. It is usually **not** enough to **carry** graph-scale continuity for months without registered files and lookup. For many authors that threshold is **weeks**, not years — especially once multiple arcs start landing on the same page.

### Building PGMs in frontier chat

A **PGM** here means **organized working notes** — who knows what, what gear someone carries, which facts are locked — saved in a file you own, not left in chat. The first ones in this project were **written in frontier chat** and saved by hand. No plugin supplied them.

**Three ways that usually starts:**

- **Character and chapter state** — Ask for a readonly pass on a passage: what is true about this character here? Turn the answer into a short structured note, edit it yourself, save it in your project folder (a `.json` or `.md` file — either is fine).
- **Scenario simulation** — Play a beat off-page (caseworker, institution, "what does she know after three sessions?"). **Distill** what you learned into constraints and knowledge state; file that in your character notes after you review. Do not paste sandbox dialogue into the chapter.
- **Session anchors** — Section A of your end-of-session file (where the story paused, open questions, locks) often holds facts that later move into a PGM when they stabilize.

**Format mix (maintainer practice):** **Markdown** for rich character or scene notes; **JSON** for locks, gear state, and other fields that need to stay exact; **Cypher** when the hard problem is **relationships** — who knows what, which arc owns a beat. One novel may use all three. Start with whatever you will actually reload.

**The habit:** Chat helps you **shape** canon; the **file** is what you reload next month. The common mistake is not "I need novelist-plugin first" — it is never saving canon out of the thread. When copying those files back into every new session gets tedious, that is when registered lookup ([`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)) earns its keep — optional, and **after** you have sheets worth indexing.

### Reading order (chat-only)

1. This doc — spectrum and [*Frontier chat only*](#frontier-chat-only-no-tooling-required) (you are here)
2. [`02-prosthetic-model.md`](02-prosthetic-model.md) — six alternatives, move types, malformed beat
3. [`04-audit-and-governance.md`](04-audit-and-governance.md) — apply gate, word contracts, Signs, *When not to audit*
4. [`06-failure-modes.md`](06-failure-modes.md) — name traps (ghostwrite drift, sycophantic audit, …)
5. **Skim** [`05-workflow-patterns.md`](05-workflow-patterns.md) — session anchors and filing habits; you can use a plain markdown anchor file without any plugin
6. **Defer** [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) until **registered lookup** would save you time — not Week 1

[`03-five-domains.md`](03-five-domains.md) and [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) when you want scope and disclosure language; neither requires tooling to read.

### Habits that transfer without infrastructure

These are the same **gates** and **word contracts** whether you use a browser tab or a governed IDE:

- **Apply gate** — "Priority fixes" means finish the audit and offer options, not rewrite my chapter.
- **Six-alternative protocol** — inspiration set; pick, blend, reject, or own line.
- **Quote gate** — name speaker and situation before dialogue alternatives.
- **Adversarial audit discipline** — readonly, objective, not a cheerleader; pair with letter shape and word contracts ([*Turn off sales mode*](#turn-off-sales-mode-keep-adversarial-discipline) above).
- **Session anchor** — end each session with a short file: where the story paused, open questions, locks. Reload it next time instead of "remember everything."
- **PGM drafting** — shape canon in chat; **you** save the file and own what goes in it. Move facts up from sandbox or session notes when they are settled — never automatic from chat.

Failure when you skip the anchor: [**context amnesia**](06-failure-modes.md#context-amnesia) — the model contradicts earlier chapter state because joins lived in chat attention, not in files you reload.

### When chat stops being enough

**Building** PGMs in chat and saving them to disk is normal frontier practice. **Registered lookup** (indexed search, continuity checks, query without re-paste) is what tooling adds. You are there when **scale** or **arc density** breaks the one-session habit — often before you feel "ready" for infrastructure:

- A governed pass on **more than ~one chapter** per sitting starts to slip — or a **dense half-page** (multiple arcs resolving) fails before a full chapter would
- You re-paste the same PGM chunks every session and edits drift between copies
- Who-knows-what or timeline errors survive correction even when files exist
- You cannot find "where did I say X?" without scrolling old chat threads or hunting through manuscript files one by one
- Travel or grounding beats invent routes you already filed

That is the graduation path to [`05-workflow-patterns.md`](05-workflow-patterns.md) and, when lookup tiers matter, [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md). Optional engine: [novelist-plugin getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md) — not a prerequisite to **draft** PGMs in chat; often worth it **once arc density or re-paste cost** bites, which on long-form work can be early.

**Origin story (short):** Governance, adversarial audit, and **initial PGM drafting** emerged in frontier chat; **registration and indexed lookup** followed when relationship fidelity, **arc density on the page**, and re-paste cost outgrew what one session could hold. Details: [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Why files exist*; [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Origin*.

---

## Video and screen demos

Ep. **01** ([`scripts/01-spectrum-of-use.md`](../scripts/01-spectrum-of-use.md)) is the **author/student explainer** for this doc — framework and habits, not a recording checklist.

| Recording | Script | What it covers |
|-----------|--------|----------------|
| Ep. 01 | [`01-spectrum-of-use.md`](../scripts/01-spectrum-of-use.md) | Spectrum, frontier chat path, adversarial discipline, PGM drafting, scale limits |
| Ep. 01B | [`01b-level-zero-demo.md`](../scripts/01b-level-zero-demo.md) | Level **0** — blank frontier chat contrast (~5 min) |
| Ep. 01C | [`01c-spectrum-demos-index.md`](../scripts/01c-spectrum-demos-index.md) | Levels **1–7** screen demos — env matrix, fixtures, per-level scripts |

**Rule:** Do not use a governed IDE session to demonstrate Level 0 — apply gates are already active. **Disclosure (all demos):** staged on synthetic prose — not a real manuscript workflow.

---

## Where to start (by week)

Same ramp as [`README.md`](../README.md#where-to-start-by-week) — summarized here. **Chat-only path:** see [*Frontier chat only*](#frontier-chat-only-no-tooling-required) for reading order and habits before the week table.

### How this repo relates to tooling

**Three layers, one practice.** Full map: [`README.md`](../README.md#how-this-fits-together) — methodology (this repo), optional [novelist-plugin](https://github.com/pojoguy/novelist-plugin) engine, optional worked example in [`examples/`](../examples/) (manuscript repo not public yet). Summary:

| What | Role for learners |
|------|-------------------|
| **This repo** | Methodology docs, templates, examples — **start here** |
| **[novelist-plugin](https://github.com/pojoguy/novelist-plugin)** | Optional engine — [getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md), registered lookup, continuity checks — **Week 3+** when capture hurts |
| **Worked example** ([`examples/`](../examples/)) | Optional deep dive — [`grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md); full novel repo **not public yet**; **not required** for Week 1 Levels 2–3 |

You do **not** need novelist-plugin or a governed IDE to practice prosthetic + audit in any chat tool.

| Week | Focus |
|------|--------|
| **1** | This spectrum + [`02-prosthetic-model.md`](02-prosthetic-model.md) + session anchor template — **any chat tool** |
| **2** | Map + Street View in a folder; manual route notes before travel beats |
| **3+** | Optional [novelist-plugin getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md) when you want registered lookup |

Levels 2–3 (prosthetic + audit) are achievable in Week 1 on a **passage or chapter** without Cursor or lookup tiers. Levels 4–7 — and registered lookup — tend to arrive **weeks** into a braided novel, not only when a calendar says "Week 3," especially when multiple arcs resolve on the same page.

---

## Next

| Topic | Document |
|-------|----------|
| Prosthetic model, six alternatives, malformed beat | [`02-prosthetic-model.md`](02-prosthetic-model.md) — Levels 2+ |
| Domains maturity checklist | [`03-five-domains.md`](03-five-domains.md) — pairs with [*Levels and domains*](#levels-and-domains) |
| Audit + governance, Signs, apply gate | [`04-audit-and-governance.md`](04-audit-and-governance.md) — Level 3 |
| Session anchors, two-step pipeline, grounding | [`05-workflow-patterns.md`](05-workflow-patterns.md) — Levels 5a, 7 habits |
| Failure catalog (ghostwrite drift, treadmill, …) | [`06-failure-modes.md`](06-failure-modes.md) — Level 0+ traps |
