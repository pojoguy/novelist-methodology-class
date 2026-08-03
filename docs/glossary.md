# Glossary

Terms used across this repository.

**How to use this file:** Each topic document and video script also opens with a **short Terms table** for that piece only. This glossary is the **master list** — use it when a term appears in multiple places or you need more detail.

**Contributor rule:** New jargon in a doc → add to that doc's Terms table **and** here if the term is reusable. See [`JARGON-STANDARD.md`](JARGON-STANDARD.md).

---

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

**Apply authorization**  
Explicit author instruction before any text changes the manuscript — pick alternative #, name line fix, or direct substitute. "Priority fixes" alone is not authorization.

**Apply gate**  
Rule blocking manuscript edits until apply authorization is present.

**Anchor (session anchor)**  
Persisted end-of-session file with continuity state (Section A), revision notes (B), methodology meta-analysis (C).

**Author lock**  
Persistent rule overriding model prior; stored in rationale docs or PGMs.

**Comparanda**  
Quarantined unrelated reference excerpts for craft comparison (lens + pack). Never indexed into canon or passage FTS. Reports only — diagnosis, not voice target.

**Continuity report**  
Structured check producing a **reference ID**, rule name, and compared quotes — proves or disproves claims; does not retrieve prose. One report type in the editorial corpus.

**Editorial report corpus**  
Accumulated readonly diagnostics filed outside canon (e.g. `exploration/`) — trope/subversion ledger, tone audit, maturation read, developmental passes, comparanda reports, verify events. **Run, file, reload** on later audits; promote to PGM only on author instruction. See [`04-audit-and-governance.md`](04-audit-and-governance.md).

**Domain (1–5)**  
Scope of AI use: lexical, audit, continuity, sandbox (grounding + scenario sim), production. Domain 4 splits into **4a grounding** and **4b scenario simulation**. See [`03-five-domains.md`](03-five-domains.md).

**Domain collapse**  
Treating simulation or exploration output as canon without promotion.

**Ghostwrite drift**  
Model substitutes prose when author requested audit or fixes only.

**Goldilocks words**  
High-probability literary adjectives (shimmer, tapestry, luminous, etc.) common in LLM prose.

**Grounding (Domain 4a / Level 5a)**  
Spatial and material verify — routes, period detail, biology — against sources or registered lore before prose locks. Distinct from scenario simulation.

**Scenario simulation (Domain 4b / Level 5b)**  
Off-page play-pretend — run a character or institution through a beat; output constraints and knowledge state, not paste-ready manuscript dialogue. Promotes to character PGMs after author review.

**Human signal**  
Intentional idiosyncratic prose the author protects; may conflict with generic rubric Signs.

**Lexical prosthetic**  
AI expands vocabulary retrieval; author selects. Not voice replacement.

**NEGATION triangulation**  
Collapse pattern: *Not X, not Y. Z.* (or comma-delimited *not X, not Y, but Z*) when retrieval bias stalls at a thin solution space and must emit anyway.

**NON-CANONICAL**  
Exploration or chat content not yet promoted to lore/PGMs.

**PGM (program guide / project graph module)**  
Formalized **author working notes** — character, world, chapter state — registered for load/query (JSON, Cypher, Markdown, plain text, etc.). Not a separate species of thinking; organized canon the tooling can cite.

**Relationship collapse (attention)**  
Loss of stable joins (who knows what, arc, locks) in the model's active attention despite sufficient raw text in context; infrastructure unloads relationship state to PGMs, indexes, and verify.

**Priority fixes gate**  
"Fix" means audit + alternatives + stop — not chapter rewrite.

**Prosthetic model**  
AI as external aid for specific failures; human retains intent and final prose.

**Proverb dialogue**  
Generic wisdom lines without speaker/situation — structural failure mode.

**Quote gate**  
No full dialogue alternatives without speaker + situation in Step 1.

**Lookup kinds**  
Quick search (fuzzy, no story tags) vs tagged passage / character / facts / route lookup vs continuity check (truth, not search). **One kind per question.**

**Passage reanchor**  
Re-segment chapter prose into stable passage IDs after edits; prerequisite for accurate tagged search and continuity checks.

**RAG indexing**  
Embed or FTS index of manuscript text for fuzzy locate (L1). Distinct from graph verify and from comparanda (excluded paths).

**Retrieval bias**  
Selection/scoring layer ranking candidates in vector or knowledge space. Under constraint pile-up, may stall when no candidate clearly wins and still must return output.

**Section A / B / C**  
Anchor blocks: continuity entry, revision notes, meta-analysis.

**Retrospective meta-analysis**  
Looking back at your registered notes (grounding, routes, session anchors) to reconstruct what a span assumed — distinct from subjective Section C session notes.

**Sign**  
Internal rubric flag for generic or model-typical prose; cite and branch, don't auto-fix. Independently built for fiction; convergent with [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing). Craft diagnosis, not a detector score.

**Commercial AI detector**  
Third-party product scoring text as "AI" or "human"; typically measures **training-material / pattern adherence**, not verified tool use. Underperformed explicit Signs rubric in maintainer adherence testing on project corpus.

**Training-material adherence**  
Closeness of prose to high-frequency patterns in model training data (cadence, diction, structure). What most detectors approximate; not the same as authorship or tool use.

**Formula / franchise prose**  
Fiction written to tight publisher or series rubric where structural conformity is intentional; can false-positive commercial detectors when work is fully human.

**Pick (prosthetic move)**  
Author selects one numbered alternative for apply; disclose honestly.

**Cluster + author take**  
Author names near-miss options and supplies own draft; AI orients or audits without applying closest number by default.

**POV-blind grounding**  
You file maps and photos for a place the character never names on the page — author coordinates without breaking POV.

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

**Step 1 / Step 2**  
Structural/grounding agent → readonly prosthetic audit agent.

**Tagline gate**  
Block poster-thesis editor summaries masquerading as craft feedback.

**Thesis tagline**  
Compressed moral summary (*A vs B; nature punishes…*) unsuitable as on-page voice.

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
