# History, Hidden AI, and Why This Repository Exists

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** `[glossary.md](glossary.md)`.


| Term                             | Plain language                                                                                                                                   |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **AI (artificial intelligence)** | Software that finds patterns, makes predictions, or generates text, images, or audio — not a thinking person.                                    |
| **LLM (large language model)**   | A text system trained on huge amounts of writing to guess the next word; powers most chat-style writing tools.                                   |
| **Generative AI**                | AI that **creates** new content (words, pictures, sound) from a prompt — not just spell-check or search.                                         |
| **Chat box / chat interface**    | A messaging-style screen (e.g. ChatGPT) where you type prompts and get replies — what made AI visible to the public in 2022.                     |
| **Stochastic**                   | Based on **probability and chance** — the system picks likely outputs, not guaranteed correct ones.                                              |
| **Transformer**                  | The common modern design inside most LLMs; good at keeping track of context across a long passage.                                               |
| **Queueing theory / Erlang**     | Math invented for **telephone networks** to handle random call traffic — early industrial use of probability.                                    |
| **Knowledge engineering**        | Encoding what an expert knows as **explicit rules and files** the computer must follow — not free-form chat.                                     |
| **Theta bias function**          | Research framework for how a system **ranks and chooses** among options when preferences conflict — root of the six-alternative idea.            |
| **Prosthetic model**             | Using AI like **glasses or a thesaurus** — it helps you retrieve or check; **you** still write and choose.                                       |
| **Six-alternative protocol**     | When wording is stuck, the tool offers **exactly six** full options; **you** use them as **inspiration** — pick, blend, reject, or write your own — before anything changes in the manuscript. |
| **Retrieval bias**               | The hidden scoring that pushes a system toward certain words or phrases when it must output something.                                           |
| **Thin solution space**          | Too many rules at once; the system cannot find a good answer and emits vague or "not A, not B, but C" prose.                                     |
| **Governance / apply gate**      | **You** must explicitly approve before any suggested text is pasted into your draft.                                                             |
| **RAG**                          | **Search** over your manuscript or notes to find relevant passages — locates text; does not prove continuity.                                    |
| **Whisper / Chirp**              | Widely used **speech-to-text** foundation models — OpenAI and Google **vendor stacks** (not the chat UI, same transformer-era infrastructure). |
| **Foundation ASR**               | Automatic speech recognition model embedded in captioning, dictation, and meeting tools — e.g. Whisper, Chirp.                                      |


---

Public panic about AI in creative writing often treats the technology as if it arrived fully formed in November 2022. It did not. Nor is today's debate the first time a new capability collided with an established craft.

This document gives skeptics and newcomers three things at once:

1. A **short history** — AI is older than the chat box
2. A **hidden-in-plain-sight map** — you already depend on generative and statistical AI daily, often without naming it
3. **Author authority** — who maintains this repo and why their perspective is grounded in decades of practice, not a weekend prompt experiment

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

#### Where it started (centuries before ChatGPT)


| Period            | Development                                                                                                    | Link to language models                                                                                                                                                                                                                              |
| ----------------- | -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **17th–18th c.**  | Probability theory (Pascal, Fermat, Laplace; later **Bayes**)                                                  | Framework for "how likely, given evidence?" — not "what is absolutely true?"                                                                                                                                                                         |
| **19th c.**       | **Statistical mechanics** (Boltzmann, Gibbs)                                                                   | Macro behavior from huge numbers of random micro-events — order from uncertainty at scale                                                                                                                                                            |
| **Early 1900s**   | **Markov chains** (Andrey Markov)                                                                              | Next state depends only on current state, with **transition probabilities** — memory as a probability table                                                                                                                                          |
| **1909–1920s**    | **Telephone switching and queueing theory** (Agner Krarup **Erlang**, Copenhagen Telephone Co.)                | **First industrial-scale stochastic systems:** model call arrivals, trunk occupancy, and blocking as random processes; **Erlang formulas** still used in capacity planning. The phone network had to work under uncertainty before anyone said "AI." |
| **1948**          | **Information theory** (Claude Shannon, **Bell Labs**)                                                         | Language modeled as a **stochastic process** — symbols with statistical regularity, not fixed rules. Shannon's employer built the telephone infrastructure Erlang's math described.                                                                  |
| **1960s–80s**     | **Hidden Markov Models (HMMs)**                                                                                | Dominant speech-recognition paradigm: guess hidden word sequence from noisy audio via probability — direct descendant of telephone-era statistical signal work                                                                                       |
| **1960s**         | **British electronic telephone switching** (UK Post Office **TXE** family — e.g. **TXE4** 1963, **TXE2** 1966) | Parallel to Bell Labs ESS: stored-program and electronic switching replace Strowger electromechanics; national network engineered for uncertain call load on finite trunks — Erlang's math made operational at scale                                 |
| **1960s**         | **Stochastic computing** (**Brian R. Gaines**, **Standard Telephones and Cables Ltd. / STL**, Britain)         | Inside the same British telecom-industrial world: Gaines characterizes **stochastic computing** while developing processors capable of **learning** — probability-based computation as engineering, not metaphor                                     |
| **1960s–80s**     | **Computerized telephone switching** (e.g. Bell Labs **ESS** — Electronic Switching System)                    | US parallel to TXE: routing and traffic management move to software                                                                                                                                                                                  |
| **1990s–2000s**   | **N-gram language models**                                                                                     | Direct ancestor of LLMs: probability of the next word given previous words, estimated from corpus counts                                                                                                                                             |
| **1980s–present** | **Stochastic gradient descent (SGD)**                                                                          | How neural nets train: update weights from **random batches** of data — learning itself is a stochastic process                                                                                                                                      |
| **2010s**         | Neural language models, word embeddings, RNNs/LSTMs                                                            | Same job as n-grams — predict next token — with learned distributed representations                                                                                                                                                                  |
| **2017–present**  | **Transformers** (attention) at scale                                                                          | Still output a **probability distribution over the vocabulary** for each next token; "generation" is **sampling** from that distribution                                                                                                             |


**Telephone switching — easy to miss, hard to overstate:** Long before chat interfaces, the public telephone network was one of the first infrastructures that **had** to be engineered with stochastic math. Calls arrive at random times. Trunks are finite. A switch must decide how to route traffic when demand is uncertain. Erlang treated that uncertainty formally; Shannon later treated **communication itself** as statistical.

**Britain in the 1960s — where switching and stochastic computing meet:** While Bell Labs deployed ESS in the United States, the UK **General Post Office** (later British Telecom) rolled out its own electronic-exchange family — **TXE** — beginning with transistorised **TXE4** (1963, Leicester) and reed-electronic **TXE2** (from 1966). Same problem class: route unpredictable demand through finite capacity under real-time constraints.

At **Standard Telephones and Cables (STL)** — a major British telecom-equipment firm in that same ecosystem — **Brian R. Gaines** was pioneering **stochastic computing**: using randomness and probability as a **computational primitive** to build processors that could learn. Gaines later published the definitive survey *Stochastic Computing Systems* (1969). The thread is direct: **telephone infrastructure forced stochastic thinking; Gaines turned it into a research program inside British telecom R&D.**

**Where Gaines enters the picture for this repository:**


| Period        | Gaines                                                                                                                                         | Link forward                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **1960s**     | STL, Britain — **stochastic computing**, learning processors                                                                                   | Foundations of probability-as-computation inside telecom industry                                     |
| **1967–1975** | University of **Essex** — electrical engineering / computer engineering                                                                        | Bridges industrial R&D and academic systems research                                                  |
| **1980s**     | University of **Calgary** — **Knowledge Science Institute**; knowledge-based systems with **Mildred Shaw**; Banff knowledge-acquisition school | Expert systems, repertory grids, automated knowledge elicitation — **explicit rules and graph state** |
| **1980s**     | **David Johnson** studies under Gaines, **Joan Vickers**, and Shaw at Calgary                                                                  | First-hand knowledge engineering; early **theta bias functions** research                             |
| **Present**   | Methodology generalized in this repo                                                                                                           | PGMs + session anchors (graph state) + prosthetic gates (governed stochastic sampling)                |


Gaines is the **through-line** from 1960s British stochastic telecom R&D to 1980s knowledge engineering to today's governed LLM workflows. This repository is not namedropping a famous advisor — it is documenting methodology that inherits **both** sides of that arc: **explicit knowledge state** (expert-systems instinct) and **stochastic generation under constraint** (LLM reality).

Speech recognition (HMMs), voice codecs, noise suppression on calls, and modern VoIP routing all sit on the same family tree — which is why Whisper-on-a-video-call and GPT-in-a-doc are less alien to each other than they look.

None of this is a sidebar. It is the **continuous thread** from "what word probably comes next?" to GPT — by way of **what call probably comes next, which trunk is probably free, and which British lab was already building learning machines on probability in the 1960s.**

#### What an LLM does, stripped of mystique

1. **Training:** Ingest vast text. Adjust billions of parameters so the model assigns **high probability** to continuations that match patterns in the training corpus. Training uses SGD — stochastic by construction.
2. **Inference:** Read your prompt. For each next token, output a ranked probability distribution over possible words/subwords.
3. **Generation:** **Sample** from that distribution (temperature, top-*p*, top-*k* control how random). Append token. Repeat.

The model does not "retrieve a fact." It **rolls weighted dice** biased by everything it has seen. Usually the highest-probability token is generic — that is why unprompted LLM prose converges on **statistical average** (the "18 Signs" problem in craft rubrics).

#### Why this matters for writers


| Stochastic property                  | Craft consequence                                                                                                                                    |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Outputs are **likely**, not **true** | Hallucinated citations, dates, geography — plausible wrong                                                                                           |
| Same prompt, different runs          | Non-reproducible "fixes" without locked state and author picks                                                                                       |
| High-probability = **common**        | Cliché syntax, goldilocks words, proverb dialogue — the mode of the training distribution                                                            |
| Constraint pile-up                   | Too many rules shrink the feasible region → **sparse-edge collapse** / **thin solution space** (negation triangulation, triads, comma-list recovery) |


**The prosthetic model exists because the engine is stochastic** — and because **retrieval bias must return something** even when the solution space is too thin to support a good single answer. You do not "trust" the model; you **constrain** it, **audit** its output, **widen** the retrieval set with six alternatives when bias stalls, and **select** from that set — the same posture you already use when autocomplete offers three words and you tap one.

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

| Their claim | Fair? |
|-------------|-------|
| "Night mode **reconstructs** pixels; it doesn't **write**" | **Yes** — different task |
| "Noise suppression **classifies** speech vs clutter" | **Yes** — not composition |
| "Therefore I use **no AI** like ChatGPT" | **No** — category error |

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

See also **[The stochastic lineage](#the-stochastic-lineage--what-llms-are-actually-built-on)** in Part 1 — LLMs are stochastic systems before they are chat products.

**Generative AI** — systems that **produce** new text, images, audio, or code from input. Not all generators are transformers. At inference time, most **sample** from a probability distribution — they do not look up a single correct answer.

**Transformer** — a specific neural architecture (2017) excelling at **context over long sequences**. GPT, Claude, Llama, and most modern writing assistants are transformer-based language models. Each forward pass still ends in a **softmax over the vocabulary** — a probability vector for the next token.

**Large Language Model (LLM)** — a transformer (usually) trained on vast text to predict **likely** continuations. "Chat" wraps an LLM in conversation and often hides the sampling step.

**Stochastic system** — any system whose behavior is defined over probability distributions. LLMs inherit this from n-gram language models, HMMs, and statistical mechanics — not from the 2022 product launch.

**Why distinguish:** Critics often argue against "generative AI" as if it were one monolith. Practitioners argue about **governance** — retrieval vs substitution, audit vs ghostwrite — regardless of architecture. This repo is about **methodology**, not model worship. Methodology starts with accepting **plausible ≠ true**.

---



## Part 4: Why the maintainer is qualified to speak on this

This repository is maintained by **David Johnson** — would-be author, knowledge-systems practitioner, and long-form fiction writer. The methodology here is not assembled from influencer threads. It is generalized from **decades of technical practice** and **years of governed LLM use on a real manuscript**.

### Research lineage — Gaines, Calgary, and before

**Brian R. Gaines** is not a footnote in this story. He is the bridge between the [stochastic lineage](#the-stochastic-lineage--what-llms-are-actually-built-on) above and the methodology in this repository.

- **1960s, Britain:** At **Standard Telephones and Cables (STL)** — inside the UK telecom-equipment world that was simultaneously deploying electronic exchanges (**TXE**) — Gaines pioneered **stochastic computing**: processors that learn using probability as a computational primitive. His survey *Stochastic Computing Systems* (1969) codified the field.
- **1970s:** Professorship at the University of **Essex** (electrical / computer engineering) — academic continuation of systems and human-factors research.
- **1980s, Calgary:** **Izaak Walton Killam Chair**, founder of the **Knowledge Science Institute**; with **Mildred Shaw**, developed knowledge-acquisition tools and expert-system methods (repertory grids, KSS tools) that influenced the international **Banff** knowledge-engineering school.

**David Johnson** worked directly with **Gaines**, **Joan Vickers**, and **Shaw** at the University of Calgary in the 1980s:

- **Rule-based and knowledge-based systems** — encoding expert reasoning as explicit state, constraints, and traversal rules (same structural instinct as PGMs, session anchors, and apply gates in this repo)
- **Human factors** — how people actually use knowledge systems under load
- Early research code in what was later known as **theta bias functions** — bias and preference in knowledge representation, not "make text pretty"

That lineage predates ChatGPT by decades and spans **both** poles serious LLM methodology needs: Gaines's **stochastic** foundations (1960s STL) and Calgary's **knowledge-engineering** foundations (1980s). The prosthetic model is not a reaction to hype; it is **bounded search under explicit constraints** — expert-systems discipline updated for transformer-scale sampling.

### Enterprise practice (present)

- Designs and integrates enterprise scaled **LLM-backed systems** in production using **LangGraph** and **LangGraph4j** — graph-orchestrated agents with state, checkpoints, and tool boundaries
- Uses **Cursor** professionally — repo index, MCP, and agent editing in paying work — which informed the decision **not** to build a separate RAG + LLM editor shell for fiction; custom work went into **methodology and MCP tooling** (e.g. novelist-plugin) instead
- Treats creative-writing workflow with the same seriousness: **graph state** (PGMs), **checkpoints** (session anchors), **constraints** (rubric Signs, prosthetic gates), **human authorization** before side effects (apply gate)

Someone who builds agent graphs for data management is not guessing when they say unconstrained "fix my chapter" prompts fail. They have seen **sparse-edge collapse** in other domains.

### Creative practice (multi-year)

- Author of a long-form speculative fiction project using LLMs across **five domains** (lexical prosthetic, developmental audit, continuity modeling, grounding simulation, production blueprinting) — see `[03-five-domains.md](03-five-domains.md)`
- **Prototyped largely on frontier LLMs** in long chat threads before IDE rules and MCP tooling — prosthetic and audit patterns came first; **PGMs, RAG, and graph-backed queries** followed when conversational context overwhelmed relationship and canon fidelity
- **Planned a custom RAG + LLM-backed editor**, then adopted **Cursor** as host after day-job use proved the plumbing (index, MCP, rules, diff-aware edit) was already there — effort shifted to gates, PGMs, and passage/verify tooling rather than a new IDE
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



## Next

- `[01-spectrum-of-use.md](01-spectrum-of-use.md)` — where governed practice sits on the novice-to-sophisticated map
- `[02-prosthetic-model.md](02-prosthetic-model.md)` — the operating model in detail
- `[07-ethics-and-transparency.md](07-ethics-and-transparency.md)` — disclosure and authorship

