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

**Continuity report / verify_run**  
Structured check producing `event_id`, rule name, literals — proves or disproves claims; does not retrieve prose.

**Domain (1–5)**  
Scope of AI use: lexical, audit, continuity, simulation, production. See [`03-five-domains.md`](03-five-domains.md).

**Domain collapse**  
Treating simulation or exploration output as canon without promotion.

**Ghostwrite drift**  
Model substitutes prose when author requested audit or fixes only.

**Goldilocks words**  
High-probability literary adjectives (shimmer, tapestry, luminous, etc.) common in LLM prose.

**Grounding**  
Real-world constraints (geography, period detail, biology) verified against sources or author samples.

**Human signal**  
Intentional idiosyncratic prose the author protects; may conflict with generic rubric Signs.

**Lexical prosthetic**  
AI expands vocabulary retrieval; author selects. Not voice replacement.

**NEGATION triangulation**  
Collapse pattern: *Not X, not Y. Z.* (or comma-delimited *not X, not Y, but Z*) when retrieval bias stalls at a thin solution space and must emit anyway.

**NON-CANONICAL**  
Exploration or chat content not yet promoted to lore/PGMs.

**PGM (program guide / project graph module)**  
Machine-readable canon slice — character, world, chapter state.

**Priority fixes gate**  
"Fix" means audit + alternatives + stop — not chapter rewrite.

**Prosthetic model**  
AI as external aid for specific failures; human retains intent and final prose.

**Proverb dialogue**  
Generic wisdom lines without speaker/situation — structural failure mode.

**Quote gate**  
No full dialogue alternatives without speaker + situation in Step 1.

**L1 / L2 / L3 locator**  
Tiered retrieval: L1 fuzzy RAG (no metadata join); L2 structured passage/entity/fact/geography query; L3 verify (truth, not search). One locator per question.

**Passage reanchor**  
Re-segment chapter prose into stable `passage_id` rows after edits; prerequisite for accurate L2 search and verify.

**RAG indexing**  
Embed or FTS index of manuscript text for fuzzy locate (L1). Distinct from graph verify and from comparanda (excluded paths).

**Retrieval bias**  
Selection/scoring layer ranking candidates in vector or knowledge space. Under constraint pile-up, may stall when no candidate clearly wins and still must return output.

**Section A / B / C**  
Anchor blocks: continuity entry, revision notes, meta-analysis.

**Sign**  
Rubric flag for AI textual degradation or protocol breach.

**Six-alternative protocol**  
Exactly six full replaceable options for flagged prose. Widens thin solution space when retrieval bias cannot discriminate; author applies final selection. Countermeasure to bias-function stall — see [`02-prosthetic-model.md`](02-prosthetic-model.md).

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
Feasible region too narrow for bias function to choose; forced emission as negation triangulation, comma-lists, or adjective/adverb triads. Six alternatives deliberately widen the space.
