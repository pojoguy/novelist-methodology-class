# History, Hidden AI, and Why This Repository Exists

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).


| Term                             | Plain language                                                                                                                                                                                 |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AI (artificial intelligence)** | Software that finds patterns, makes predictions, or generates text, images, or audio — not a thinking person.                                                                                  |
| **LLM (large language model)**   | A text system trained on huge amounts of writing to guess the next word; powers most chat-style writing tools.                                                                                 |
| **Generative AI**                | AI that **creates** new content (words, pictures, sound) from a prompt — not just spell-check or search.                                                                                       |
| **Chat box / chat interface**    | A messaging-style screen (e.g. ChatGPT) where you type prompts and get replies — what made AI visible to the public in 2022.                                                                   |
| **Stochastic**                   | Based on **probability and chance** — the system picks likely outputs, not guaranteed correct ones.                                                                                            |
| **Transformer**                  | The common modern design inside most LLMs; good at keeping track of context across a long passage.                                                                                             |
| **Queueing theory / Erlang**     | Math invented for **telephone networks** to handle random call traffic — early industrial use of probability.                                                                                  |
| **Knowledge engineering**        | Encoding what an expert knows as **explicit rules and files** the computer must follow — not free-form chat.                                                                                   |
| **Theta bias function**          | Research framework for how a system **ranks and chooses** among options when preferences conflict — root of the six-alternative idea.                                                          |
| **Prosthetic model**             | Using AI like **glasses or a thesaurus** — it helps you retrieve or check; **you** still write and choose.                                                                                     |
| **Six-alternative protocol**     | When wording is stuck, the tool offers **exactly six** full options; **you** use them as **inspiration** — pick, blend, reject, or write your own — before anything changes in the manuscript. |
| **Retrieval bias**               | The hidden scoring that pushes a system toward certain words or phrases when it must output something.                                                                                         |
| **Thin solution space**          | Too many rules at once; the system cannot find a good answer and emits vague or "not A, not B, but C" prose.                                                                                   |
| **Governance / apply gate**      | **You** must explicitly approve before any suggested text is pasted into your draft.                                                                                                           |
| **RAG**                          | **Search** over your manuscript or notes to find relevant passages — locates text; does not prove continuity.                                                                                  |
| **Whisper / Chirp**              | Widely used **speech-to-text** foundation models — OpenAI and Google **vendor stacks** (not the chat UI, same transformer-era infrastructure).                                                 |
| **Foundation ASR**               | Automatic speech recognition model embedded in captioning, dictation, and meeting tools — e.g. Whisper, Chirp.                                                                                 |


---

Public panic about AI in creative writing often treats the technology as if it arrived fully formed in November 2022. It did not. Nor is today's debate the first time a new capability collided with an established craft.

This document gives skeptics and newcomers three things at once:

1. A **short history** — AI is older than the chat box
2. A **hidden-in-plain-sight map** — you already depend on generative and statistical AI daily, often without naming it
3. **Author authority** — who maintains this repo and why their perspective is grounded in decades of practice, not a weekend prompt experiment

**Where this doc sits:** **Optional Ep. 0** — history, hidden AI, maintainer context. It does **not** teach the prosthetic protocol, five domains, or audit mechanics — those start at [`01-spectrum-of-use.md`](01-spectrum-of-use.md) → [`02-prosthetic-model.md`](02-prosthetic-model.md). The stochastic argument here **explains why** locked [`04-audit-and-governance.md`](04-audit-and-governance.md) governance (apply gate, word contracts) exists. **Skip to `01`** if you want craft immediately.

**Reading path:** Parts 1–2 and 5 are the **main skeptic path**. Deep telephone-switching / Erlang / Gaines-at-STL lineage is **[optional](#appendix-optional-depth--telephone-switching-and-gaines)** — skip if you want straight to workflow docs.

---

## Part 1: AI is not new

### Before the chat box


| Era              | What happened                                                               | Why it matters for writers                                                                                                                                                                            |
| ---------------- | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1950s–60s**    | Turing's imitation game; Dartmouth workshop coins "artificial intelligence" | The question was never only "can a machine write?" — it was whether machine behavior could be **governed** and **useful**                                                                             |
| **1970s–80s**    | Expert systems, knowledge-based systems, rule engines in industry           | Real deployments: medical diagnosis aids, configuration systems, industrial control. **Knowledge engineering** — encoding human expertise as explicit rules and graphs — predates neural-network hype |
| **1990s–2000s**  | Machine learning in production at scale                                     | Spam filters, fraud scoring, search ranking, recommendation — statistical models making millions of decisions per day with no press release                                                           |
| **2010s**        | Deep learning in consumer products                                          | Voice assistants, photo classification, machine translation, predictive text — AI embedded in phones and browsers while most users called it "the algorithm"                                          |
| **2017**         | Transformer architecture ("Attention Is All You Need")                      | Foundation for modern language models: context-aware sequence processing at scale                                                                                                                     |
| **2018–2021**    | Large language models in research and APIs                                  | GPT-2/3, BERT, T5 — capability grows; **public awareness stays low** outside tech and academia                                                                                                        |
| **2022–present** | Chat-style interfaces go mainstream                                         | Same underlying families of models; **new interaction layer** makes capability visible — and frightening — to non-specialists                                                                         |


**Takeaway for authoring circles:** The 2022 moment was a **UI and access** event as much as a capability event. Writers who say "I don't use AI" often mean "I don't use ChatGPT." They may still use AI-mediated tools every hour.

---

### The stochastic lineage — what LLMs are actually built on

LLMs feel like oracles. Under the hood they are **stochastic systems** — machines that reason in **probabilities**, not certainties. Understanding that lineage explains why they sound plausible, why they hallucinate, and why **governance** (human selection, apply gates, six alternatives) is not optional for craft.

**Stochastic** means: given the same input, the system works over a **distribution of possible outputs**, not a single guaranteed answer. Randomness enters at training time, at sampling time, or both.

#### Stochastic lineage — short map

| Step | Idea | Why writers care |
|------|------|------------------|
| **Probability** | Likely, not guaranteed | Hallucination is sampling, not malice |
| **Markov chains** | Next state from current state + odds | "Memory" as statistics |
| **Shannon / language** | Text as stochastic process | Continuation = weighted dice |
| **N-gram models** | Next word from prior words | Direct ancestor of LLMs |
| **Transformers** | Context at scale; still a softmax per token | Chat hides the distribution |
| **Sampling** | Temperature, top-*p* pick the token | Same prompt, different runs |

**Plausible ≠ true** — the posture locked governance assumes. Century-by-century detail (Erlang, HMMs, SGD, telecom): **[appendix](#appendix-optional-depth--telephone-switching-and-gaines)**.

#### What an LLM does, stripped of mystique

1. **Training:** Ingest vast text. Adjust billions of parameters so the model assigns **high probability** to continuations that match patterns in the training corpus. Training uses SGD — stochastic by construction.
2. **Inference:** Read your prompt. For each next token, output a ranked probability distribution over possible words/subwords.
3. **Generation:** **Sample** from that distribution (temperature, top-*p*, top-*k* control how random). Append token. Repeat.

The model does not "retrieve a fact." It **rolls weighted dice** biased by everything it has seen. Usually the highest-probability token is generic — that is why unprompted LLM prose converges on **statistical average** (the [**Signs**](04-audit-and-governance.md) problem in craft rubrics).

#### Why this matters for writers


| Stochastic property                  | Craft consequence                                                                                                                                                           |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Outputs are **likely**, not **true** | Hallucinated citations, dates, geography — plausible wrong                                                                                                                  |
| Same prompt, different runs          | Non-reproducible "fixes" without locked state and author picks                                                                                                              |
| High-probability = **common**        | Cliché syntax, goldilocks words, proverb dialogue — the mode of the training distribution                                                                                   |
| Famous-prefix prompts                | `Four score and seven years ago` → Gettysburg completion — **training frequency**, not your novel stolen (`[07-ethics-and-transparency.md](07-ethics-and-transparency.md)`) |
| Constraint pile-up                   | Too many rules shrink the feasible region → **sparse-edge collapse** / **thin solution space** (negation triangulation, triads, comma-list recovery)                        |


**The prosthetic model exists because the engine is stochastic** — and because **retrieval bias must return something** even when the solution space is too thin to support a good single answer. You do not "trust" the model; you **constrain** it, **audit** its output, **widen** the retrieval set with six alternatives when bias stalls, and **select** from that set — the same posture you already use when autocomplete offers three words and you tap one. Locked governance: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Audit vs governance*, *Apply gate in practice*.

Expert systems (Part 1, 1970s–80s) tried **explicit rules**. Modern LLMs use **implicit statistics** at scale. Serious authoring methodology combines both instincts: **graph state and locks** (knowledge engineering) plus **governed sampling** (stochastic generation under gates).

---

### This is not the first craft panic

Every major writing technology faced resistance:

- **Printing press** — would destroy memory and scholarship
- **Typewriter** — would make prose mechanical
- **Word processor** — would homogenize voice
- **Spell-check** — would erode literacy
- **Google Search** — would end research discipline
- **Grammar tools** — would replace editors

Some fears had merit (homogenization, over-reliance). None eliminated the craft. What changed was **workflow** — and the authors who learned the workflow early had an advantage.

LLMs are the next layer. The relevant question is not "AI yes or no" but **which domain, under what governance, with what human mass remaining**.

---

## Part 2: AI you already use (and don't call AI)

Many people reject "AI" in the abstract while depending on statistical and generative systems constantly. Naming them reduces mystique.

### Language and text (closest to writing)


| Tool                                          | What it does                                                                | AI family                                                  |
| --------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------- |
| **Predictive text / autocomplete**            | Suggests next word or phrase from context                                   | Sequence models (often transformer-based on modern phones) |
| **Spell-check and grammar tools**             | Flags errors, proposes rewrites                                             | Statistical + neural language models                       |
| **Email spam filtering**                      | Classifies inbound mail                                                     | Classic ML → modern classifiers                            |
| **Search engines**                            | Query understanding, ranking, snippet generation                            | Retrieval + ranking models                                 |
| **Subtitle and live-caption systems**         | Speech → text                                                               | Automatic speech recognition (neural)                      |
| **Voice-to-text / dictation / transcription** | Converts speech to editable text in apps, meetings, and accessibility tools | Automatic speech recognition (neural)                      |
| **Translation in browser or app**             | Cross-language rendering                                                    | Neural machine translation                                 |


**Voice-to-text foundations:** Many of the largest transcription and captioning services do not build speech recognition from scratch. They integrate or compete on top of a small set of **foundation ASR models**. Two that dominate the field:

- **Whisper** (OpenAI) — transformer speech-to-text model (separate weights from GPT, **same vendor stack**). Widely deployed via API and embedded in third-party transcription tools, meeting software, and accessibility pipelines
- **Chirp** (Google) — speech model family in the Gemini / Google Cloud Speech stack, used at scale for captioning, dictation, and multilingual recognition

If you have dictated a text message, auto-captioned a video, or received a meeting transcript — you may have already used **OpenAI- or Google-family foundation infrastructure** without ever opening ChatGPT or Gemini for prose.

**Precision matters:** Whisper is not the GPT language model running on audio. It is a different model trained for transcription. The point for skeptics is not "captions wrote your novel" — it is that **vendor and architecture boundaries are thinner** than "I don't use AI" implies.

If you have accepted a autocomplete suggestion, you have **selected** from a generative retrieval set — the same structural move as the six-alternative prosthetic protocol, at phone-keyboard scale.

### Smartphone cameras — computational and generative pipelines

Modern phone cameras are not passive lenses. They are **real-time inference stacks** that make a pocket sensor usable. Most users call this "the camera app," not AI.


| Capability                         | What it does                                                         | AI / generative role                                                                                           |
| ---------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Autofocus and subject tracking** | Locks focus on faces, pets, or moving subjects                       | Detection and tracking models classify subjects and predict motion                                             |
| **Face follow / auto-framing**     | Keeps subjects centered or reframes video as people move             | Tracking + crop/reframe decisions from scene analysis                                                          |
| **Auto white balance**             | Corrects color cast under tungsten, fluorescent, shade, mixed light  | Scene classification estimates illuminant and adjusts color                                                    |
| **HDR / auto dynamic range**       | Merges multiple exposures or lifts shadow without blowing highlights | Multi-frame fusion, tone mapping, often neural denoising in shadows                                            |
| **Low-light and noise reduction**  | Produces a clean image from a dark, noisy sensor read                | Neural denoising and detail recovery — **synthetic** detail where photons were scarce                          |
| **Portrait depth and bokeh**       | Separates subject from background                                    | Segmentation models estimate depth or subject mask                                                             |
| **Computational recomposition**    | Crops, straightens, suggests framing, or reframes after capture      | Scene analysis; some systems **generate** fill pixels when zooming or expanding frame (generative zoom / fill) |


**Why this matters for writers:** Every phone photo you trust is already a **model-mediated reconstruction** of reality — not a neutral recording. You accept or reject the result (delete, retake, edit). That is the same human-in-the-loop posture as governed prose prosthetics: machine proposes, human disposes.

### Audio — noise reduction and cancellation

The same pattern runs in sound: raw input is unusable; models clean it before you hear it.


| Tool                                             | What it does                                       | AI / signal-processing role                                                               |
| ------------------------------------------------ | -------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Hearing aids**                                 | Amplify speech in noisy environments               | Adaptive noise reduction, directional beamforming, classification of speech vs background |
| **Zoom, Teams, Meet, Discord, etc.**             | Make remote conversation intelligible              | Echo cancellation, background noise suppression, often neural noise removal on voice      |
| **Dedicated noise apps (e.g. Krisp, RTX Voice)** | Strip keyboard, fan, and room noise from mic input | Real-time source separation / suppression models                                          |
| **Phone and headset call audio**                 | Clear voice on cellular and VoIP calls             | Wind noise reduction, voice isolation, multi-mic fusion                                   |


If you have taken a video call, worn hearing aids in a restaurant, or shot a night photo you would not have gotten from the bare sensor — you have **depended on generative and statistical AI** without opening a chat box.

### Fair objection — reconstruction, classification, and chat

Skeptics often draw a sharp line:


| Their claim                                                | Fair?                     |
| ---------------------------------------------------------- | ------------------------- |
| "Night mode **reconstructs** pixels; it doesn't **write**" | **Yes** — different task  |
| "Noise suppression **classifies** speech vs clutter"       | **Yes** — not composition |
| "Therefore I use **no AI** like ChatGPT"                   | **No** — category error   |


**Camera and hearing-aid pipelines** are mostly reconstruction and classification. They do not draft your chapter. Grant that.

**Transcription is the wedge:** dictation, live captions, and meeting transcripts often run on **Whisper** (OpenAI stack) or **Chirp** (Gemini stack) — foundation ASR from the same vendors that ship chat products, built on the same transformer-era infrastructure. You may have routed your speech through that stack without naming it AI.

**Why it matters for authors:** Many writers speed first drafts with **speech-to-text** — phone dictation, Word, Dragon, Otter, voice notes pasted into Scrivener — and still say they never touch "generative AI." If the ASR layer is Whisper or Chirp, the distinction is **task and UI**, not vendor zero. You spoke; you revise; you own the file. That is **prosthetic capture** (external input → editable text → human edit mass), not ChatGPT ghostwriting — but it is not "no AI" either. The methodology question is **governance**: what you authorize after capture, not whether probability entered the pipeline.

**The writing-relevant pivot:** The argument is not that every app is ChatGPT. It is that you already **trust or reject probabilistic machine outputs** daily — delete a bad night photo, dismiss a wrong caption, accept an autocomplete tap — and **2022 made the same posture visible for text**. Serious writing methodology asks **governance** questions (who selects, what is canon, what requires authorization), not whether probability entered your workflow.

### Banking — checks, deposits, and fraud

Paper checks feel analog. The pipeline behind them is not.


| Tool                                 | What it does                                     | AI / ML role                                                                                                                                                              |
| ------------------------------------ | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Check processing (clearing)**      | Reads, routes, and settles checks between banks  | MICR recognition, image capture, amount and payee extraction, fraud scoring — **essentially all commercial check processing is automated**; human review is the exception |
| **Mobile check deposit**             | Snap a photo; funds post to your account         | Computer vision validates check image, reads fields, detects duplicates and alterations                                                                                   |
| **Credit card fraud alerts**         | Flags suspicious transactions                    | Anomaly detection on transaction patterns                                                                                                                                 |
| **"Unusual activity" account locks** | Blocks transfers or cards when behavior diverges | Classifiers on spending and access patterns                                                                                                                               |


If you have deposited a check by phone, written a paper check that cleared overnight, or received a fraud alert — you have already depended on **machine reading and classification of documents** in a regulated industry. That is the same class of problem as governed manuscript tooling: high stakes, human override when the model is wrong, and zero press releases announcing "AI banking."

### Daily infrastructure (invisible until it fails)


| Tool                                        | What it does                                        |
| ------------------------------------------- | --------------------------------------------------- |
| **Navigation ETA and traffic routing**      | Prediction on congestion and speed                  |
| **Streaming recommendations**               | Collaborative filtering + content models            |
| **Social and news feeds**                   | Ranking models optimize engagement                  |
| **Voice assistants**                        | ASR + intent classification + response generation   |
| **Medical imaging assist** (where deployed) | Detection aids for radiology — human reads the scan |


None of these require the user to say "I use AI." They require the user to **trust or reject a system output** — which is exactly the governance problem serious writers solve with apply gates and author locks.

### The honesty test

Ask yourself:

1. Have I accepted a autocomplete suggestion this week?
2. Have I used a grammar or spell tool?
3. Have I followed a maps route or a streaming recommendation?
4. Have I relied on a phone camera night mode, portrait depth, or auto-framing — or generative zoom/fill?
5. Have I taken a video call where background noise was stripped without me configuring it?
6. Have I used dictation, live captions, or a meeting transcript?
7. Have I deposited a check by phone or had a paper check clear without a human retyping it?

If yes to any of these, you already practice **human-in-the-loop selection** from machine-generated or machine-reconstructed output. The methodology in this repository scales that instinct to long-form craft — it does not introduce an alien behavior.

---

## Part 3: Generative vs transformer — plain language

Three definitions skeptics ask for — full stochastic timeline in **[appendix](#appendix-optional-depth--telephone-switching-and-gaines)** and [Part 1](#stochastic-lineage--short-map):

| Term | One line |
|------|----------|
| **Generative AI** | Produces new text, images, audio, or code — samples from a distribution; not a lookup table |
| **Transformer** | Common LLM architecture (2017); each step ends in a **probability vector** over the next token |
| **LLM** | Transformer (usually) trained for **likely** continuations; chat wraps sampling in conversation |

**Stochastic system** — behavior defined over probabilities (n-grams, HMMs, LLMs share this). This repo is about **governance** — retrieval vs substitution, audit vs ghostwrite — not model worship. Craft ladder: [`01-spectrum-of-use.md`](01-spectrum-of-use.md).

---

## Part 4: Why the maintainer is qualified to speak on this

This repository is maintained by **David Johnson** — would-be author, knowledge-systems practitioner, and long-form fiction writer. The methodology here is not assembled from influencer threads. It is generalized from **decades of technical practice** and **years of governed LLM use on a real manuscript**.

### Research lineage — Gaines, Calgary, and before

**Brian R. Gaines** is not a footnote in this story. He is the bridge between the [stochastic lineage](#stochastic-lineage--short-map) (and [appendix](#appendix-optional-depth--telephone-switching-and-gaines)) and the methodology in this repository.

- **1960s, Britain:** At **STL** — stochastic computing inside the UK telecom ecosystem. [Optional depth](#appendix-optional-depth--telephone-switching-and-gaines).
- **1970s:** Professorship at the University of **Essex** (electrical / computer engineering) — academic continuation of systems and human-factors research.
- **1980s, Calgary:** **Izaak Walton Killam Chair**, founder of the **Knowledge Science Institute**; with **Mildred Shaw**, developed knowledge-acquisition tools and expert-system methods (repertory grids, KSS tools) that influenced the international **Banff** knowledge-engineering school.

**David Johnson** worked directly under **Gaines**, **Joan Vickers**, and **Shaw** at the University of Calgary in the 1980s:

- **Rule-based and knowledge-based systems** — encoding expert reasoning as explicit state, constraints, and traversal rules (same structural instinct as PGMs, session anchors, and apply gates in this repo)
- **Human factors** — how people actually use knowledge systems under load
- Early research code in what was later known as **theta bias functions** — bias and preference in knowledge representation, not "make text pretty"

That lineage predates ChatGPT by decades and spans **both** poles serious LLM methodology needs: Gaines's **stochastic** foundations (1960s STL) and Calgary's **knowledge-engineering** foundations (1980s). The prosthetic model is not a reaction to hype; it is **bounded search under explicit constraints** — expert-systems discipline updated for transformer-scale sampling.

### Enterprise practice (present)

- Designs **governed LLM systems in production** — explicit state, checkpoints, tool boundaries, **human authorization before side effects** *(implementation uses graph-orchestrated agents; details in [novelist-plugin](https://github.com/pojoguy/novelist-plugin), not required for authors)*
- Uses a governed writing environment professionally — repo-indexed notes and structured lookup in paying work — which informed keeping **methodology in this repo** and **implementation elsewhere**
- Treats creative-writing workflow with the same seriousness: **graph state** (PGMs), **checkpoints** (session anchors), **constraints** (rubric Signs, prosthetic gates), **human authorization** before side effects (apply gate)

Someone who builds governed data systems for a living is not guessing when they say unconstrained "fix my chapter" prompts fail. They have seen **sparse-edge collapse** in other domains.

### Creative practice (multi-year)

- Author of a long-form speculative fiction project using LLMs across **five domains** (lexical prosthetic, developmental audit, continuity modeling, grounding simulation, production blueprinting) — see `[03-five-domains.md](03-five-domains.md)`
- **Prototyped largely on frontier LLMs** in long chat threads — prosthetic and audit patterns **and initial PGMs** (character state, timelines, locks) were drafted there and filed by hand; **indexed lookup and structured query** followed when conversational context could no longer reliably **reload** relationship fidelity across months
- **Planned a custom editor shell**, then adopted a governed IDE when day-job use proved indexed notes beside the manuscript were enough — effort stayed on **gates, PGMs, and continuity habits** rather than a new app
- **Autistic** author using LLM as **vocabulary and continuity prosthetic** — external working memory for lexical retrieval under load, not voice replacement
- Documented **failure modes** (ghostwrite drift, proverb dialogue, negation triangulation) and **countermeasures** (two-step pipeline, six-alternative protocol) from live sessions — see `[06-failure-modes.md](06-failure-modes.md)`

### What this qualification is — and is not


| This repo's authority                                  | Not claimed                      |
| ------------------------------------------------------ | -------------------------------- |
| Knowledge engineering + production LLM orchestration   | "AI will replace all authors"    |
| Governed prosthetic use on a real novel-length project | Prompt-pack bestseller shortcuts |
| Honest failure-mode reporting                          | Vendor marketing                 |
| Methodology you can audit and adapt                    | One true model or one true tool  |


David is qualified to discuss **how to constrain LLMs in creative work** because he has done it in both **enterprise systems** and **personal craft** — and documented where it breaks.

---

## Part 5: What skeptics should do with this

1. **Separate UI from capability** — ChatGPT made models visible; it did not invent statistical assistance
2. **Inventory your own stack** — autocomplete, grammar, search, feeds — before declaring zero AI use
3. **Ask governance questions** — Who selects? What is canon? What requires authorization? Those questions apply to spell-check and to chapter rewrites alike
4. **Judge methodology on structure** — gates, anchors, alternatives, human prose mass — not on whether the author used a chat box

If after reading this you still reject all AI in fiction — that is a valid **values** position. This repository asks only that you argue against **what serious practitioners actually do**, not against a straw-man prompt.

---

## Appendix: Optional depth — telephone switching and Gaines

Skip this section if you are here for **workflow docs** only.

**Telephone switching:** Long before chat interfaces, the public telephone network was engineered with stochastic math — calls arrive at random times, trunks are finite, switches route under uncertainty. **Erlang** formalized that at Copenhagen Telephone Co.; **Shannon** later modeled communication itself as statistical at Bell Labs.

**Britain in the 1960s:** UK **General Post Office** deployed electronic exchanges (**TXE4** 1963, **TXE2** 1966). At **Standard Telephones and Cables (STL)**, **Brian R. Gaines** pioneered **stochastic computing** (*Stochastic Computing Systems*, 1969) — probability as a computational primitive inside the same telecom-industrial world.

#### Century-by-century stochastic lineage (optional)

| Period | Development | Link to language models |
|--------|-------------|-------------------------|
| **17th–18th c.** | Probability theory (Pascal, Fermat, Laplace; Bayes) | "How likely?" not "what is true?" |
| **19th c.** | Statistical mechanics (Boltzmann, Gibbs) | Order from uncertainty at scale |
| **Early 1900s** | Markov chains | Memory as transition probabilities |
| **1909–1920s** | Telephone queueing (Erlang) | Industrial stochastic systems before "AI" |
| **1948** | Information theory (Shannon, Bell Labs) | Language as stochastic process |
| **1960s–80s** | Hidden Markov Models | Speech recognition via probability |
| **1990s–2000s** | N-gram language models | Next-word counts → LLM ancestor |
| **1980s–present** | Stochastic gradient descent | Training is stochastic |
| **2010s** | RNNs, embeddings | Same job as n-grams, learned vectors |
| **2017–present** | Transformers at scale | Still sample from a distribution each token |

**Gaines → Calgary → this repo:** Gaines bridged stochastic telecom R&D and 1980s knowledge engineering at Calgary; David Johnson studied under Gaines, Vickers, and Shaw — **explicit graph state + governed sampling** is the through-line to PGMs, anchors, and prosthetic gates today.

| Period        | Gaines | Link forward |
| ------------- | ------ | ------------ |
| **1960s**     | STL — stochastic computing, learning processors | Probability-as-computation in telecom R&D |
| **1967–1975** | University of **Essex** | Industrial R&D ↔ academic systems |
| **1980s**     | Calgary **Knowledge Science Institute** + **Mildred Shaw** | Expert systems, explicit graph state |
| **1980s**     | **David Johnson** under Gaines, Vickers, Shaw | Theta bias functions; methodology in this repo |
| **Present**   | Generalized here | PGMs + anchors + prosthetic gates |

Speech recognition (HMMs), codecs, and VoIP routing share this family tree with modern LLMs — which is why Whisper-on-a-video-call and GPT-in-a-doc are less alien than they look.

---

## Next

| Topic | Document |
|-------|----------|
| Level ladder — where governed practice sits | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) |
| Prosthetic model — operating detail | [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| Why governance follows stochastic tools | [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Audit vs governance* |
| When plausibility breaks — failure catalog | [`06-failure-modes.md`](06-failure-modes.md) |
| Disclosure, detectors, human prose mass | [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) |
| Optional worked grounding arc (POV-blind) | [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md) |

