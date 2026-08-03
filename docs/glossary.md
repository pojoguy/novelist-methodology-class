# Glossary

Terms used across this repository.

**How to use this file:** Each topic document and video script also opens with a **short Terms table** for that piece only. This glossary is the **master list** — use it when a term appears in multiple places or you need more detail.

**Contributor rule:** New jargon in a doc → add to that doc's Terms table **and** here if the term is reusable. See [`JARGON-STANDARD.md`](JARGON-STANDARD.md).

### Quick index by doc

| Doc | Glossary home for… |
|-----|-------------------|
| [`00-history-and-authority.md`](00-history-and-authority.md) | Stochastic lineage (optional depth), hidden AI, Gaines/Calgary, maintainer context |
| [`01-spectrum-of-use.md`](01-spectrum-of-use.md) | Levels 0–7, frontier chat, PGM drafting, lexical prosthetic, spectrum straw man |
| [`02-prosthetic-model.md`](02-prosthetic-model.md) | Prosthetic model, six alternatives, move types, nexus, gates, prosthetic gates |
| [`03-five-domains.md`](03-five-domains.md) | Domains 1–5, 4a/4b, scope rules, canon workflow |
| [`04-audit-and-governance.md`](04-audit-and-governance.md) | Audit, governance, Signs, locks, drift, gates, word contracts, apply gate |
| [`05-workflow-patterns.md`](05-workflow-patterns.md) | Anchors, context, grounding capture, two-step, exploration vs canon |
| [`06-failure-modes.md`](06-failure-modes.md) | Failure modes catalog, drift, context amnesia, thin space, ghostwrite drift |
| [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) | Disclosure, detectors, human prose mass |
| [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) | Context, lookup kinds, RAG, continuity reports, comparanda |

---

## Craft methodology

**Apply authorization**  
Explicit author instruction before any text changes the manuscript — pick alternative #, name line fix, or direct substitute. "Priority fixes" alone is not authorization.

**Apply gate**  
Rule blocking manuscript edits until apply authorization is present — the core **authorization gate** in this methodology. Search and continuity checks are **diagnose only** under the same rule. See **gate** (below); [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Apply gate in practice*.

**Audit**  
Diagnostic pass on existing prose — what works, what fails, what to try next — without rewriting your voice. See [`04-audit-and-governance.md`](04-audit-and-governance.md).

**Governance**  
Authorization layer — **gates**, locks, word contracts; nothing touches the manuscript until you say so. Distinct from having a rubric. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Audit vs governance*.

**Blend (prosthetic move)**  
Merge pieces from named numbered alternatives per your specification (e.g. "lead with 3, verb from 5"); apply only when you authorize. See [`02-prosthetic-model.md`](02-prosthetic-model.md).

**CH## L##**  
How you point at a line in revision — chapter and line number (e.g. CH07 L63). Line numbers drift after edits; reanchor or cite a short quoted snippet. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Pointing at lines in revision*.

**Anchor (session anchor)**  
Persisted end-of-session file with continuity state (Section A), revision notes (B), methodology meta-analysis (C). Core **registered context** for re-entry across sessions. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Session anchors*.

**Author lock**  
A **rule you set and keep** (naming, calendar, voice) that outranks generic tool habits — governance that outlasts one session. A kind of **lock** (see below). See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Author locks*.

**Author's notes**  
Maps, timelines, character sheets, location photos — material you **already** gather while drafting. When **registered** for load/query, same habit as PGMs and grounding docs. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Author's notes, formalized*; [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Artifacts = author's notes*.

**Canon**  
Story truth as **registered in your project files** (PGMs, lore, passage index) — not whatever the chat said last session. See [`03-five-domains.md`](03-five-domains.md).

**Comparanda**  
Quarantined unrelated reference excerpts for craft comparison (**lens** + **pack**). Never indexed into canon or passage FTS. Reports only — diagnosis, not voice target. Mechanics: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

**Lens (comparanda)**  
Checklist of craft questions for a comparanda run (e.g. info dump? thin characterization? stakes fog?).

**Pack (comparanda)**  
Folder of attributed short excerpts used only for craft comparison — never canon.

**Comparanda bleed**  
Reference excerpts leaking into continuity answers, passage search, or voice — isolation failure. See [`06-failure-modes.md`](06-failure-modes.md); mechanics: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Comparanda*.

**Continuity check**  
Readonly compare of prose against registered facts — rule names, cited lines, reference ID; you decide fixes. Same habit as continuity report; not a fuzzy search.

**Continuity modeling (Domain 3 / Level 4)**  
Cross-checking timeline, who-knows-what, and character state across a long book — graph-scale continuity, not word-finding alone. See [`03-five-domains.md`](03-five-domains.md).

**Continuity report**  
Structured check producing a **reference ID**, rule name, and compared quotes — proves or disproves claims; does not retrieve prose. One report type in the editorial corpus. **Developmental** reports are letters you act on — different job, same apply gate. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Report types you might accumulate*.

**Context**  
What the model and you are **working from** in a given turn — the central problem this methodology manages by **filing state outside chat** and loading it on demand. Name the layer when you use the word. **Window context:** tokens in the model's **context window** this turn — prose, pasted notes, recent chat. Large windows hold **text** but not reliable **relationship joins** (who knows what, arc, locks) — see **relationship collapse**. **Conversation context:** what the **rolling chat thread** retains about relationships — not a canon store; see **conversation context** (below). **Registered context:** **PGMs**, **session anchors**, passage index, grounding files, continuity reports — **author-owned state** you load or query instead of hoping chat remembers. **Situational context:** speaker + situation before dialogue (**quote gate**); beat/scene framing for retrieval. **Retrieval context:** which **lookup kind** and sources answer this question — one kind per query; comparanda isolated from canon. Failure when registered context is skipped: **context amnesia**. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Origin*; [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Relationship state vs text in context*.

**Context amnesia**  
A **context** failure: model contradicts earlier chapter state because relationship joins lived in chat attention, not registered files. See [`06-failure-modes.md`](06-failure-modes.md); fix: session anchors, PGMs, indexed lookup — [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Conversation context**  
A kind of **context** (unreliable): what the **chat thread** retains about **relationships** — unstable even when raw text fits in the window; use **registered context** (notes and queries) instead. See [`05-workflow-patterns.md`](05-workflow-patterns.md); [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Origin*.

**Exploration / sandbox**  
Scratch folders (`exploration/`, comparanda, scenario sandboxes) — **not official story truth** until you promote. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Exploration vs canon*.

**Failure mode**  
Predictable way the process breaks — naming it lets you fix the workflow, not blame yourself. Catalog: [`06-failure-modes.md`](06-failure-modes.md); quick recognition: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Failure shapes — quick recognition*.

**Editorial report corpus**  
Accumulated readonly diagnostics filed outside canon (e.g. `exploration/`) — trope/subversion ledger, tone audit, maturation read, developmental passes, comparanda reports, verify events. **Run, file, reload** on later audits; promote to PGM only on author instruction. See [`04-audit-and-governance.md`](04-audit-and-governance.md).

**Filed report (lookup kind)**  
Prior readonly diagnostic you **reload** by reference — trope ledger, tone pass, earlier developmental letter. Not a substitute for a **fresh continuity check** when you need truth against canon now.

**Domain (1–5)**  
Scope of AI use: lexical, audit, continuity, sandbox (grounding + scenario sim), production. Domain 4 splits into **4a grounding** and **4b scenario simulation**. See [`03-five-domains.md`](03-five-domains.md).

**Developmental audit (Level 3 / Domain 2)**  
Structured editorial critique of draft prose — flags problems; you revise. Readonly until you authorize a specific change. See [`04-audit-and-governance.md`](04-audit-and-governance.md).

**Design lock**  
Short **doctrine line** carried across docs so behavior stays consistent — e.g. *RAG locates; graphs verify; you apply* ([`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)); *governance is procedural honesty, not a score* ([`07-ethics-and-transparency.md`](07-ethics-and-transparency.md)). **Methodology** lock, not story canon — distinct from **author lock** and **PGM lock**.

**Disclosure**  
Honest description of **how** you used AI — specific domains, move types, process artifacts — not a detector badge. See [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md).

**Discourse layer**  
Tag on a passage for how text works in the story — scene, memory, dream, foreshadow, unreliable — so flashback does not false-trigger co-presence checks. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Domain collapse**  
Treating **sandbox, comparanda, reference, or chat** output as official story canon without promotion. See [`06-failure-modes.md`](06-failure-modes.md); scope: [`03-five-domains.md`](03-five-domains.md) — *Scope rules*.

**Drift**  
Unwanted **movement away from an agreed baseline** — the word means different things by context; name the kind when you use it. **Governance drift:** **ghostwrite drift** — you asked for critique; prose was substituted anyway. **Index drift:** **stale passage index** — passage IDs, search rows, or `CH## L##` pointers no longer match the draft after edits; optional tooling may report **`DRIFT`** on index-hygiene checks ([`08-infrastructure-techniques.md`](08-infrastructure-techniques.md)). **Canon / voice drift (informal):** facts, tone, or reference voice sliding over months without registered state — mitigated by PGMs, anchors, reanchor ([`01-spectrum-of-use.md`](01-spectrum-of-use.md); comparanda bleed in [`06-failure-modes.md`](06-failure-modes.md)). **Retrieval drift:** six-alternatives that leave the **nexus** (off-nexus options on the wrong beat). **Line drift:** line numbers shift after edits — reanchor, or cite a short quoted snippet ([`04-audit-and-governance.md`](04-audit-and-governance.md) — *Pointing at lines in revision*).

**Generic place hallucination**  
Stock cemetery, main street, or highway — not the site you researched; often **genre gravity** (walls, trees, Gothic mood on a bald prairie site). Fix: **map + Street View** filed together; check prose against **what you documented**, not whether the character named the place (**POV-blind** sites are valid). See [`06-failure-modes.md`](06-failure-modes.md); [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture*, *POV-blind grounding*.

**Ghostwrite drift**  
A kind of **drift** (governance): you asked for **audit** or **priority fixes**; the tool **rewrote prose** anyway — apply-gate violation. Same when you said *"here's my take…"* and the tool applied the **nearest numbered option** instead of working on **your** line. Fix: word contracts, apply gate, pick ≠ cluster + author take. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Apply gate in practice*, *What your words mean*; [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*; straw man: [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 0.

**Grounding capture**  
File **map + Street View** (or equivalent ground-level image) for one site — one plain-language instruction per place. See [`05-workflow-patterns.md`](05-workflow-patterns.md); [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Artifacts = author's notes*.

**Sycophantic audit**  
Flattery-first critique that misses Signs and continuity holes — default chat habit; ask for a developmental letter shape instead. See [`06-failure-modes.md`](06-failure-modes.md).

**Goldilocks words**  
High-probability literary adjectives (shimmer, tapestry, luminous, etc.) common in LLM prose.

**Gate**  
A **checkpoint rule** — work stops until a condition is met. In general AI talk, *gate* often means model **guardrails** or safety refusals; here it means **your workflow checkpoints** so the tool does not skip steps or edit the manuscript without authorization. Not a **Sign** (craft diagnosis on existing prose); not a **lock** (registered story law the tool must not contradict). **Authorization gate:** **apply gate** — no manuscript edit without explicit OK. **Precondition gates:** **quote gate** (speaker + situation before dialogue alternatives); **geography gate** — no verified route on file → stop travel prose ([`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Geography gate*). **Output-shape gates:** **tagline gate** (specific critique, not poster morals); **priority fixes gate** (audit + options, not rewrite). **Prosthetic gates** bundles the output-shape set for the two-step pipeline. See [`04-audit-and-governance.md`](04-audit-and-governance.md); [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Two-step pipeline*.

**Grounding (Domain 4a / Level 5a)**  
Spatial and material verify — routes, period detail, biology — against sources or registered lore before prose locks. Distinct from scenario simulation.

**Scenario simulation (Domain 4b / Level 5b)**  
Off-page play-pretend — run a character or institution through a beat; output constraints and knowledge state, not paste-ready manuscript dialogue. Promotes to character PGMs after author review.

**Grounding vs scenario simulation conflation**  
Treating a geography verify session like play-pretend (or vice versa) — both use `exploration/` but answer *where* vs *who under pressure*. See [`06-failure-modes.md`](06-failure-modes.md).

**Human prose mass**  
Bulk of final wording selected, revised, and owned by you — advocated in this methodology; **not** a certifiable percentage metric. See [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md).

**Human signal**  
Intentional idiosyncratic prose the author protects; may conflict with generic rubric Signs.

**Lexical prosthetic**  
AI expands vocabulary retrieval; author selects. Not voice replacement.

**Levels (0–7)**  
Spectrum of how much structure you add. **Level 0** = ghostwriting straw man (substantial model draft, little author revision). **Level 1** = pre-domain ideation / brainstorming — not rubric policing. **Levels 2–3** = lexical prosthetic + developmental audit. **Level 4** = continuity modeling. **5a** = grounding; **5b** = scenario simulation. **6** = production blueprinting. **7** = orchestration across domains. Domains map loosely but not 1:1. See [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — *Levels and domains*.

**Lock**  
Umbrella for **rules and registered facts critique must not override without your OK**. A lock is **story law**, not a Sign. **Author lock** — naming, calendar, voice, era habits you keep across sessions. **PGM lock** — fact frozen in project files; contradicting edits need explicit OK. **Design lock** — methodology doctrine lines (search locates, you apply). Six-alternative sets should respect locks; if none can without breaking canon, say so — malformed beat or reorder. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Author locks*; [`02-prosthetic-model.md`](02-prosthetic-model.md) — PGM locks at the nexus.

**Negation triangulation**  
Collapse pattern: *Not X, not Y. Z.* (or comma-delimited *not X, not Y, but Z*) when retrieval bias stalls at a thin solution space and must emit anyway. Same as **NEGATION triangulation** in some failure-mode tables.

**NON-CANONICAL**  
Label for exploration or chat content not yet promoted to lore/PGMs. See **Exploration / sandbox**; **Promote**.

**Passage / passage_id**  
Segment of a chapter with a stable **passage_id** (UUID join key) so edits do not break references after reanchor. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *RAG indexing and passage reanchoring*.

**Plain-language lookup**  
You ask in ordinary language (*"tell me about Dej"*, *"where did I mention the peel?"*); your registered notes and indexes answer — you do not name search tiers per question. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Plain language — what you ask for*.

**Promote**  
You make a scratch fact **official** by moving it into registered lore files or PGMs — never automatic from chat or sandbox. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Exploration vs canon*; [`03-five-domains.md`](03-five-domains.md).

**PGM (program guide / project graph module)**  
**Organized author working notes** — character, world, chapter state, locks, who-knows-what — saved in files you own (Markdown, JSON, Cypher, plain text, etc.). Often **drafted in frontier chat** first (readonly passes, scenario distill, session-anchor facts), then **saved by hand**; **registration** for load/query (indexed lookup, tooling) comes when re-pasting every session stops scaling. Not a separate species of thinking; becomes **registered context** once filed for reload. See [`01-spectrum-of-use.md`](01-spectrum-of-use.md) — *Building PGMs in frontier chat*; [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Knowledge state (PGMs)*.

**PGM lock**  
A fact **frozen in a PGM or lore file** — prose or critique that contradicts it needs your explicit OK. A kind of **lock**; same apply gate as author locks, with stronger memory at scale. See [`04-audit-and-governance.md`](04-audit-and-governance.md).

**Relationship collapse (attention)**  
Loss of stable joins (who knows what, arc, locks) in the model's active attention despite sufficient raw text in **window context**; infrastructure unloads relationship state to **registered context** — PGMs, indexes, and verify.

**Priority fixes gate**  
An **output-shape gate**: "fix" means audit + alternatives + stop — not chapter rewrite. Kind of **gate**; see **prosthetic gates**.

**Prosthetic gates**  
Bundle of methodology **output-shape gates**: **quote gate** (dialogue waits for speaker + situation), **tagline gate** (critique stays specific, not poster morals), **apply gate**, and **priority-fixes** meaning (critique + options, not paste-in rewrite). Kinds of **gate** (see above). See [`04-audit-and-governance.md`](04-audit-and-governance.md); habits: [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Two-step pipeline*.

**Prosthetic model**  
AI as external aid for specific failures; human retains intent and final prose.

**Proverb dialogue**  
Generic wisdom lines without speaker/situation — structural failure mode.

**Quote gate**  
A **precondition gate**: no full dialogue alternatives without **situational context** — **speaker + situation** — established first. Kind of **gate**; see **prosthetic gates**.

**Lookup kinds**  
Different question types for indexed projects — **one kind per question**. Plain names: **quick search** (fuzzy locate); **tagged passage** (prose + scene/memory tags); **character / facts / route lookup**; **continuity check** (truth, not search); **filed report** (reload prior diagnostics). Optional tooling shorthand: **L0** scratch excluded · **L1** quick search · **L2** tagged passage · **L3** continuity check. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Mixed lookup collapse**  
Quick search and tagged passage search merged in one answer — flashback treated as co-present, exploration as canon. See [`06-failure-modes.md`](06-failure-modes.md).

**No route on file**  
A **geography gate** failure: no verified route registered in your project — stop travel prose; file and promote route notes first. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Geography gate*.

**Over-smoothing voice**  
Generic rubric pressure flattening intentional voice you meant to keep. See [`06-failure-modes.md`](06-failure-modes.md); craft: [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Human Signals vs rubric Signs*.

**Passage reanchor**  
Re-segment chapter prose into stable passage IDs after edits; prerequisite for accurate tagged search and continuity checks.

**Ingest**  
Refresh the search index after prose changes so lookups match the latest draft — paired with reanchor on long projects.

**Production blueprinting (Domain 5 / Level 6)**  
Planning trailer, audio, or visual production for human crews — separate PGMs; do not index blueprint notes into prose passage store during live chapter edit. See [`03-five-domains.md`](03-five-domains.md) Domain 5.

**Provenance**  
Tag on a registered fact — documented, derived, invented for story, or unknown — blocks blind trust in sandbox or audit joins.

**Product variance**  
Workflow that works in one chat product breaks in another — tune anchors and gates in Section C, not endless new rubric rules. See [`06-failure-modes.md`](06-failure-modes.md).

**FTS (full-text search)**  
Keyword-style index of your prose — like a powerful Find across the book; often the engine behind **quick search** / **L1**. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Report reference ID**  
Reference number on a continuity check or verify event — cite in editor letters, anchors, or later audits. Distinct from **passage_id**. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Continuity reporting*; [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Report types you might accumulate*.

**RAG (retrieval-augmented generation)**  
Search that **locates** passages in your manuscript — answers "where mentioned?" not "does this contradict canon?" Often implemented as embed or FTS index (**L1** in tooling shorthand). Distinct from tagged passage search, continuity checks, and comparanda (excluded paths). See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Retrieval bias**  
Selection/scoring layer ranking candidates in vector or knowledge space. Under constraint pile-up, may stall when no candidate clearly wins and still must return output.

**Section A / B / C**  
Anchor blocks: continuity entry, revision notes, meta-analysis.

**Retrospective meta-analysis**  
Looking back at your registered notes (grounding, routes, session anchors) to reconstruct what a span assumed — distinct from subjective Section C session notes.

**Sensitivity reader**  
Human expert on culture or lived experience who vets material — not replaceable by unchecked model output. See [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md).

**Sign / Signs rubric**  
Craft checklist flag for generic or model-typical prose; cite and branch, don't auto-fix. Independently built for fiction; convergent with [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing). Craft diagnosis, not a detector score or authorship proof. Home: [`04-audit-and-governance.md`](04-audit-and-governance.md); ethics: [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md).

**Commercial AI detector**  
Third-party product scoring text as "AI" or "human"; typically measures **training-material / pattern adherence**, not verified tool use. Underperformed explicit Signs rubric in maintainer adherence testing on project corpus.

**Training-material adherence**  
Closeness of prose to high-frequency patterns in model training data (cadence, diction, structure). What most detectors approximate; not the same as authorship or tool use.

**Formula / franchise prose**  
Fiction written to tight publisher or series rubric where structural conformity is intentional; can false-positive commercial detectors when work is fully human.

**Pick (prosthetic move)**  
Author selects one numbered alternative for apply; disclose honestly.

**Own line**  
You write the final wording without picking a number; optional readonly audit on your line; apply only when you authorize.

**Cluster + author take**  
Author names near-miss options and supplies own draft; AI orients or audits without applying closest number by default.

**POV-blind grounding**  
You file maps and photos for a place the character never names on the page — author coordinates without breaking POV.

**Visual anchor pair**  
Map (where, scale, names) plus ground-level image (e.g. Street View) for the **same site** — blocks generic fictional place substitution. See [`05-workflow-patterns.md`](05-workflow-patterns.md) — *Grounding capture*.

**Supersede (prosthetic move)**  
You write a stronger line than any numbered option; the six oriented your thinking.

**Malformed beat**  
Beat order or situation is wrong — **especially when six alternatives fail after convergence rounds**. Exit: rewrite paragraph or reorder; do not run more wordings on the same shape. See [`02-prosthetic-model.md`](02-prosthetic-model.md) — *When six options fail*.

**Six-alternative treadmill**  
Repeated six-option and convergence rounds that still don't land — **lead signal for malformed beat**, not weak vocabulary. Stop; restructure or reload grounding. See [`06-failure-modes.md`](06-failure-modes.md).

**Span counterfactual**  
*"What if X changed between L###–L###?"* — explore ripple effects before you rewrite.

**Six-alternative protocol**  
Exactly six full replaceable options for flagged prose. Widens thin solution space when retrieval bias cannot discriminate; author uses them as **inspiration** — pick, blend, reject, or write your own — before apply. Countermeasure to bias-function stall — see [`02-prosthetic-model.md`](02-prosthetic-model.md).

**Sparse-edge collapse**  
Model output degrades when too many constraints bind; often manifests as thin-solution-space stall. Do not fix with more Signs.

**Two-step pipeline**  
Structural pass (facts, order, grounding) → readonly audit pass → **you** pick → apply if authorized. See [`02-prosthetic-model.md`](02-prosthetic-model.md); habits: [`05-workflow-patterns.md`](05-workflow-patterns.md).

**Wrong causal merge**  
Separate lore facts or timeline epochs merged in one answer — who-knows-what or injury state collapsed. Fix: one lookup kind per question; load PGMs before structural work. See [`06-failure-modes.md`](06-failure-modes.md).

**Stale passage index**  
A kind of **drift** (index): passage IDs or search rows outdated after prose edits — continuity checks cite wrong spans. Fix: reanchor/re-index before verify on edited chapters. See [`06-failure-modes.md`](06-failure-modes.md).

**Tagline gate**  
An **output-shape gate**: block poster-thesis editor summaries masquerading as craft feedback. Kind of **gate**; see **prosthetic gates**.

**Thesis tagline** (also **thesis tagline compression**)  
Compressed moral summary (*A vs B; nature punishes…*) passed off as craft feedback — failure mode, not on-page voice. See [`06-failure-modes.md`](06-failure-modes.md) — *Thesis tagline compression*; gate: **Tagline gate**.

**Word contracts**  
Governance for chat: the same English phrase must not mean "rewrite my chapter" in one session and "letter only" in the next. Fixed meanings for *review*, *priority fixes*, *use option 3*, *here's my take*, span counterfactuals, load grounding, etc. See [`04-audit-and-governance.md`](04-audit-and-governance.md) — *What your words mean*.

**Theta bias function**  
Knowledge-representation framework (1980s research lineage, Calgary) modeling how preference and bias select among candidates. Theoretical root of the six-alternative protocol: when bias stalls at thin edges, human author completes selection.

**Thin solution space (retrieval bias stall)**  
Feasible region too narrow for bias function to choose; forced emission as negation triangulation, comma-lists, or adjective/adverb triads. Six alternatives widen the space locally at the **nexus**. See [`02-prosthetic-model.md`](02-prosthetic-model.md).

**Nexus (retrieval stall)**  
Constraint knot where retrieval stalled — same beat, locks, and near-miss rejections. Six alternatives and convergence rounds branch here, not elsewhere. See [`02-prosthetic-model.md`](02-prosthetic-model.md).

**Convergence round**  
When two or three of six alternatives cluster near the target, offer **three** full options anchored on that sub-region of the nexus — refinement, not a new search. See [`02-prosthetic-model.md`](02-prosthetic-model.md).

**Training memorization (famous-prefix effect)**  
When a prompt matches a highly quoted public passage (e.g. opening of the Gettysburg Address), the model often continues the canonical text — corpus frequency and a single dominant continuation path, not retrieval of your private file. See [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md).

---

## History & ML lineage

**Stochastic system**  
A system that produces outcomes from **probability distributions**, not fixed deterministic rules. LLMs, n-gram models, HMMs, and much of modern ML are stochastic; training often uses stochastic gradient descent.

**N-gram language model**  
Early statistical approach: estimate probability of the next word given the previous *n*−1 words. Direct ancestor of neural LLMs — same prediction task, smaller scale.

**Markov chain**  
Sequence model where the next state depends only on the current state, with transition probabilities. Foundation for HMMs and a conceptual ancestor of "predict next token from context."

**Queueing theory / Erlang**  
Stochastic modeling of arrivals, service times, and blocking in systems with finite capacity. Developed for **telephone switching** (Agner Krarup Erlang, ~1909–1920s) — among the first industrial deployments of formal probability at national infrastructure scale.

**Stochastic computing**  
Using randomness and probability as a computational primitive — pioneered in Britain by **Brian R. Gaines** at Standard Telephones and Cables (STL) in the 1960s, while the UK Post Office deployed electronic exchanges (TXE family). Precursor discipline to modern statistical ML and LLM sampling.

**Brian R. Gaines**  
British scientist; stochastic computing (STL, 1960s); later Knowledge Science Institute, University of Calgary (1980s–). Mentor line for this repository's maintainer — connects British telecom-era stochastic R&D to knowledge-based systems and governed LLM methodology.

**Generative AI**  
Systems that produce new text, images, audio, or code from input. Not synonymous with "transformer" or "LLM."

**Knowledge engineering**  
Encoding expert reasoning as explicit rules, graphs, and constraints — precursor discipline to modern PGM/state workflows.

**LLM (Large Language Model)**  
A language model, usually transformer-based, trained to predict likely continuations; often wrapped in chat interfaces.

**Transformer**  
Neural architecture (2017) for context-aware sequence processing; foundation of most modern writing assistants.
