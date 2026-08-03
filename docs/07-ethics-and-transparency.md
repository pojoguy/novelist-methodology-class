# Ethics and Transparency

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **AI-assisted** | You used software help at some stage — **be specific** about which kind (ideas, word options, critique, fact-check). |
| **Human prose mass** | The bulk of **final wording is yours** — selected, revised, and owned by you. |
| **Prosthetic use** | AI expanded **options or audit**; you wrote and chose the lines on the page. |
| **Ghostwriting** | Substantial **drafting by the tool** with little author revision — disclose honestly if true. |
| **Domain (1–5)** | Categories of help — lexical, audit, continuity, **grounding (4a)**, **scenario simulation (4b)**, production. Domain 4 **splits** into 4a and 4b; do not collapse them. See [`03-five-domains.md`](03-five-domains.md). |
| **Disclosure** | Telling readers, editors, or contest organizers **how** you used AI — vague labels help no one. |
| **Authorship** | **You** own creative intent, voice, and responsibility — regardless of tools used. |
| **Sensitivity reader** | A **human expert** on culture or lived experience — not replaceable by unchecked model output. |
| **Lexical prosthetic** | Word-retrieval help; may be **accessibility** for some authors — not the same as outsourcing a chapter. |
| **Apply gate** | Ethical alignment: tools **propose**; you **authorize** changes. |
| **Training memorization** | When a prompt matches a **famous passage**, the model often **continues the canonical text** — frequency in training, not a lookup of your file. |
| **Copyright / safety filter** | Product policy that **blocks or warns** on some famous or sacred text — separate from whether the model "stole" your draft. |
| **Training-material adherence** | How closely prose matches **high-frequency patterns** in model training data — cadence, diction, structure — not whether a human or tool wrote it. |
| **Formula / franchise prose** | Writing to a **tight publisher or genre rubric** where structural and diction conformity is **the product** (e.g. licensed series fiction). |
| **Signs rubric** | **Craft checklist** for generic or model-typical patterns in **your** workflow — flag, cite, branch; not a commercial AI detector. Convergent with [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing). Craft home: [`04-audit-and-governance.md`](04-audit-and-governance.md); detector debate: *Signs rubric vs commercial AI detectors* below. |
| **Commercial AI detector** | Product that scores text as "AI" or "human" — under the hood, typically **statistical + pattern rubric** measuring training-material adherence, **not** verified tool use. |
| **Pick** | Author **selects** one numbered alternative and authorizes apply. |
| **Cluster + author take** | Author names near-miss options, supplies **own draft**, asks for orientation — **not** applying the closest number by default. |

---

Methodology docs mean little without a stance on **authorship**, **disclosure**, and **reader trust**.

**Where this doc sits:** **Ethics and disclosure** — how you describe practice honestly. **Levels** map to labels → [`01-spectrum-of-use.md`](01-spectrum-of-use.md); **domains** → [`03-five-domains.md`](03-five-domains.md); **move types** (pick vs cluster + author take) → [`02-prosthetic-model.md`](02-prosthetic-model.md); **Signs craft** → locked [`04-audit-and-governance.md`](04-audit-and-governance.md); **process artifacts** (anchors, filing) → [`05-workflow-patterns.md`](05-workflow-patterns.md); **named failures** (ghostwrite drift, …) → [`06-failure-modes.md`](06-failure-modes.md). This doc does **not** re-teach audit mechanics — it answers *what you owe readers and peers*.

**Design lock:**

```text
Governance is procedural honesty, not a score.
Signs name pattern adherence for craft inside your workflow; commercial detectors measure a similar signal and mislabel it as authorship — which argues against detector culture, not for treating Signs as a forensic certificate.
```

---

## What "AI-assisted" can mean

Be specific. Vague disclosure helps no one.

| Level | Honest label |
|-------|----------------|
| Ideation only | "AI used for brainstorming; all prose human-written" |
| Lexical prosthetic | "AI offered word alternatives; author selected and revised all lines" |
| Developmental audit | "AI used for editorial-style critique; revisions author-written" |
| Continuity tooling | "AI queried project database for fact-checking; prose human-written" |
| Grounding verify (5a / Domain 4a) | "AI checked routes/maps against registered files; prose human-written" |
| POV-blind grounding | "I filed map/ground research for constraint checks; some coordinates never appear on the page — disclose **process**, not every place name in prose" — see [`05-workflow-patterns.md`](05-workflow-patterns.md) — *POV-blind grounding*; walkthrough: [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md) |
| Scenario simulation (5b / Domain 4b) | "Off-page scenario runs distilled to constraints; on-page scene author-written" |
| Production blueprinting (Domain 5) | "AI assisted trailer/storyboard planning; prose human-written" |
| Pick from alternatives | "AI offered six wordings; I selected option N and edited." |
| Blend | "I merged pieces from named options per my specification; I authorized apply." |
| Cluster + author take | "AI offered options; none fit; I drafted my own line with AI used for orientation or audit only." |
| Supersede | "AI options oriented me; final line is mine; optional readonly audit on my line." |
| Ghostwriting | "Substantial prose generated by AI" — if true, say so |

Move types (behavior): [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Pick vs cluster + author take*.

This repository advocates **high human prose mass** with **bounded AI assistance** — not hidden ghostwriting.

Level-by-level map: [`01-spectrum-of-use.md`](01-spectrum-of-use.md). Ghostwriting as failure mode: [`06-failure-modes.md`](06-failure-modes.md) — *Ghostwrite drift*; Level 0 straw man: `01` Level 0.

---

## Authorship claim

Under the prosthetic model:

- **Author** = creative intent, voice, selection, final prose, responsibility for canon
- **AI** = retrieval set, audit report, graph query, simulation sandbox

If AI drafts paragraphs you accept without substantial rewrite, your disclosure should reflect that — regardless of what methodology you intended.

#### Human prose mass — and what we cannot measure

This repository advocates **high human prose mass** — creative intent, selection, and responsibility stay with the author. It does **not** claim a **metric**.

| What we can document | What we cannot prove |
|----------------------|----------------------|
| Apply-gate discipline, anchors, audit logs, **move type** (pick vs cluster+take) | Absolute "human %" per line |
| Honest process description | No paste from **another** AI session, vendor, or ghost |
| Signs flagged and addressed in workflow | Detector-grade authorship certificate |

**No tracking system fixes this** — copy/paste from a separate chat tab bypasses any in-repo tooling. Methodology is **craft and governance**, not forensic enforcement.

**Honest disclosure** describes **how you work** (domains, gates, move type), not a certified score. Offer process artifacts if useful (anchors, audits, continuity-check reports) — not a detector badge. Apply gate walkthrough: [`04-audit-and-governance.md`](04-audit-and-governance.md).

---

#### Pick vs cluster + author take — disclosure and ethics

Not the same labor or machine shape:

| Move | Ethical gist |
|------|----------------|
| **Pick** | Model-shaped line; honest to name the option selected and how much you edited. |
| **Cluster + author take** | Author-led; alternatives were **compass**; disclose orientation/audit, not "AI wrote the line." |

**Do not** treat pick and cluster+take as one disclosure bucket. **Do not** claim "AI wrote nothing" if you routinely pick with light edit.

*Move-type behavior is in [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Pick vs cluster + author take*; ethics only requires honest labeling.*

---

#### Signs rubric vs commercial AI detectors

**For video / skim readers:** Detectors ≈ **training-pattern adherence**, not authorship. **Signs** = same signal class, **craft** purpose. Franchise formula can false-positive detectors. **Do not** use Signs or detectors as proof either way. Full argument below; craft checklist in [`04`](04-audit-and-governance.md).

**Primary role:** developmental audit inside governed workflow — flag AI-typical / statistically average patterns; cite; branch; **never** auto-rewrite on Sign hit alone.

**Independent build, Wikipedia convergence:** Signs were **developed independently** for fiction craft. In substance they align with [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) (WikiProject AI Cleanup): a **pattern field guide**, not a detector score. Wikipedia explicitly warns editors **not to solely rely on AI detection tools** — same tool class, different scope (encyclopedia vs fiction voice/POV).

#### What detectors actually measure — adherence, not attribution

Commercial AI detectors are not measuring **who wrote the line** or **which tool was used**. Under the hood they are roughly:

- implicit **pattern rubrics** (cadence, diction, structure), plus
- **statistical analysis** of how closely text resembles high-frequency training-material shapes.

An explicit **Signs** checklist is the same **signal class**, built in the open for **craft** — not sold as forensic attribution. Maintainer experience: a comparable rubric was assembled in a few hours; commercial products wrap similar logic in an "AI score."

**What gets measured:** training-material / formula **adherence** — not AI use.

**What gets mislabeled:** high adherence → "probably AI."

#### Formula fiction vs voice-forward fiction

| Context | High pattern adherence | Detector tendency | Craft question |
|---------|------------------------|-------------------|----------------|
| **Franchise / formula fiction** | Often **desirable** — readers expect the same engine, new names and locations | False positive: **organic** work can score "AI" | Is the piece **on brief**? |
| **Voice-forward / literary / governed prosthetic** | Often **undesirable** when unprompted — mode collapse, generic diction | Mixed; conflates tool use, formula, and weak human prose | Is this **your** committed line? |

**Example:** Prose written to a **formal publisher rubric** — e.g. the **Franklin W. Dixon** franchise (**Simon & Schuster**) with its beat, vocabulary, and resolution specs — can read as "AI-generated" to detectors when it is **purely human**, because **formula adherence is the product**.

**Implication:** Detector culture punishes **genre compliance** and **ghostwriting** with the same score. Signs in this methodology exist to support **your genre's craft goals** — not to certify authorship and not to enforce one global diction standard.

Services that help produce franchise-shaped prose profit in part because **adherence is valuable** in some markets — detectors cannot tell that apart from model substitution.

**Empirical note (maintainer testing):** On this project's corpus, the internal **Signs rubric outperformed every commercial AI detector tried** at separating:

- prose with **high training-material / model-typical pattern density** (including low-revision picks from alternatives), from
- **organically built** governed work (drafted, cluster+author-take, governed pick-and-revise) —

That is **not** a claim that Signs detect "AI use." Both Signs and detectors read **adherence-shaped** signal; Signs do it **explicitly for craft**; detectors **mislabel** it as authorship. On the maintainer corpus, explicit rubric beat implicit product.

Report as **n=1 practitioner evidence**; invite replication via [`examples/signs-replication-protocol.md`](../examples/signs-replication-protocol.md) and [`CONTRIBUTING.md`](../CONTRIBUTING.md).

| Claim | Status |
|-------|--------|
| Detectors measure **tool use** or **authorship** | **No** — they approximate **pattern / training-material adherence** |
| Franchise-formula **organic** prose can false-positive detectors | **Yes** |
| Signs beat commercial detectors in maintainer tests | **Yes** — on **adherence separation**, not attribution |
| Signs certify all-human or no-tool use | **No** |
| High Sign count **proves** ghostwriting | **No** — weak human prose trips same patterns |
| Low Sign / clean detector **proves** honesty | **No** |
| Same adherence signal = same moral category (formula vs ghostwrite) | **No** |
| Commercial detectors are reliable for governed AI-assisted fiction | **Undermined** — worse than craft rubric on same material |

**For advocates:** Use Signs to **improve** prose and catch model-shaped lines in session — not as "undetectable" bragging rights.

**For skeptics:** If Wikipedia's volunteer cleanup trusts **patterns over detectors** for encyclopedia text, the same logic applies to governed fiction — with fiction-specific scope (voice, POV, pick vs cluster+take).

**What we refuse:**

- Using Signs output as pretend all-human proof for contests or peers
- Using commercial detector scores as proof of cheating without asking **how** the manuscript was produced
- Treating Signs like Turnitin — they **invalidate detector culture** by measuring the **same adherence class** honestly for **craft**, while detectors mislabel it as **authorship**

Cross-link: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Signs — craft vocabulary*; optional numbered list: [novelist-plugin `prompts/rubric.md`](https://github.com/pojoguy/novelist-plugin/blob/main/prompts/rubric.md) (separate tooling repo).

---

## Peer and community norms

Writing communities differ:

- Some ban any AI use in contests or workshops
- Some allow audit-only
- Some are still forming policy

**Practice:** Ask before sharing AI-assisted excerpts in critique groups. Methodology does not override venue rules.

---

## Editor and agent conversations

Editors care about **quality and liability**, not tool purity.

Useful framing:

- "I use AI like a continuity spreadsheet and a brutal beta reader — I do not publish model drafts."
- "Detectors score training-material conformity, not whether I used a tool. Franchise formula and ghostwriting can look the same to them. I can show process — gates, move type, anchors — if you care **how** it was made."
- Offer to show anchor files or audit logs if disputed
- Do not oversell ("AI wrote nothing") if alternatives were accepted wholesale without edit

---

## Reader-facing disclosure

Publisher decisions vary:

- Copyright page AI notice
- Author's note
- No on-page notice

**Separation:** *Placement* is publisher/production; *accuracy* is author ethics. This repo does not mandate placement — it mandates **honesty** when asked.

**POV-blind grounding:** Disclose that you filed maps and constraint checks — not that every researched coordinate appears in the narrative. See disclosure table above; [`05-workflow-patterns.md`](05-workflow-patterns.md) — *POV-blind grounding*.

---

## Cultural and indigenous material

Extra care when AI touches:

- Living cultures and languages
- Sacred or restricted knowledge
- Names and protocols community members should vet

Methodology gates do not replace **human cultural review**. STOP and ask living experts — never let the model invent ceremonial detail.

---

## Disability and prosthetic framing

For some authors, lexical prosthetic use is **accessibility** — analogous to assistive tech.

Dismissive takes ("real writers don't need AI") erase neurologically accurate workflows. Advocates can explain prosthetic use without conflating it with Level 0 ghostwriting.

Pressure to **flatten intentional voice** toward generic rubric prose is a craft failure mode, not a moral virtue — [`06-failure-modes.md`](06-failure-modes.md) — *Over-smoothing voice*; [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Human Signals vs rubric Signs*.

---

## Training bias vs "AI steals my work"

Many authors fear: *If I paste my opening, the model will regurgitate my book because it stole me.* Model behavior is easier to understand as **training frequency + continuation bias + product policy** — not a targeted raid on your files.

### What the model actually optimizes

At inference time the model picks **likely next tokens** given everything it saw in training. Famous public text is **overrepresented**. Your unpublished manuscript is **underrepresented** unless it was ingested into that product's training set (a separate legal and policy question — see below).

Three factors drive "it finished a famous thing for me":

| Factor | Meaning |
|--------|---------|
| **Corpus frequency** | Appears in huge swaths of training data |
| **Quotation density** | Repeated on the web, in classrooms, in datasets |
| **Continuation uniqueness** | After the opening phrase, one continuation dominates probability |

### Demo 1 — near-memorization (Gettysburg)

**Prompt:** `Four score and seven years ago`

**Typical behavior:** The model continues with the **Gettysburg Address** — or a close paraphrase — because (a) it is in effectively every English-heavy training mix, (b) it is among the most quoted American texts, and (c) after those words there is **one dominant path** in the model's distribution.

That is **mode collapse on a famous prefix**, not evidence that the model opened your novel folder.

### Demo 2 — famous sacred text + filters (not your joke)

**Prompt:** `In the beginning God created the universe`  
*(variant of the familiar opening; not identical to every translation.)*

**Typical behavior:** A **copyright or usage caution** and/or a **canonical scripture-style quote** — not Douglas Adams's parody from *The Hitchhiker's Guide to the Galaxy* (*"This has been widely regarded as a bad move and has made a lot of people very upset"* — riffing on creation).

**Why the Adams line loses:** Multiple high-probability continuations compete (scripture, commentary, policy blocks). The model is not "respecting your copyright" on an unpublished MS — it is routing through **dominant public text** and **vendor safety rules**. The punchline you might want is **low probability** unless you steer hard toward Adams.

### What this does and does not say

| Claim | Verdict |
|-------|---------|
| "The model completes Gettysburg because that's what training made likely" | **Yes** — useful demo of memorization bias |
| "Therefore my private chapter 1 will be spat back verbatim" | **No** — unless your text was in training data, your opening has **low** memorization pressure |
| "Training never included copyrighted books" | **Unsettled / vendor-specific** — ask the product; distinct from the mechanical demo above |
| "Governed workflow still matters" | **Yes** — prosthetic use assumes **you** authorize what hits the page |

**For skeptics and advocates alike:** The Gettysburg trick shows **why generic LLM prose regresses to the mean** — the same bias that completes Lincoln can complete clichés in your genre. That is an argument for **governance and voice discipline**, not for panic that the chat box has already read your file.

**For craft methodology:** Do not paste unpublished manuscript into untrusted third-party chats if your threat model includes ingestion. Use **local files, PGMs, and apply gates** — see [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

**Screen demo script:** [`../scripts/07b-training-bias-demo.md`](../scripts/07b-training-bias-demo.md) — locked prompts, ~3 min, frontier chat only.

---

## What we refuse to normalize

- Publishing unedited model output as craft
- Hiding AI use when venue or readers require disclosure
- Using AI to imitate marginalized voices without lived expertise
- Replacing paid human editors, sensitivity readers, or translators with unchecked model output
- Treating sandbox, comparanda, or chat output as **canon** without promotion — [`06-failure-modes.md`](06-failure-modes.md) — *Domain collapse* / *Comparanda bleed*; scope: [`03-five-domains.md`](03-five-domains.md) — *Scope rules*

---

## Questions for your own policy

1. What is the minimum disclosure my audience deserves?
2. Which domains do I use (see five-domains doc)?
3. Where is my apply gate documented? → [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Apply gate in practice*, *What your words mean*
4. Who vets cultural or medical grounding?
5. What would I show a skeptical peer to prove I am not ghostwriting?
6. Can I demonstrate **training memorization** (Gettysburg vs Bible prompt) to separate "famous text bias" from "stole my manuscript"? See [Training bias vs "AI steals my work"](#training-bias-vs-ai-steals-my-work).
7. Can I honestly label **pick** vs **cluster+author take** if asked?
8. Am I relying on a **detector score** instead of **process** disclosure?

---

## Next

| Topic | Document |
|-------|----------|
| Level ladder + honest labels | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) |
| Pick vs cluster + author take (behavior) | [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| Five domains + scope rules | [`03-five-domains.md`](03-five-domains.md) |
| Signs craft, apply gate, failure shapes | [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| Anchors, filing habits | [`05-workflow-patterns.md`](05-workflow-patterns.md) |
| Ghostwrite drift, domain collapse | [`06-failure-modes.md`](06-failure-modes.md) |
| Local files, continuity checks | [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |
| Gettysburg / Bible screen demo | [`scripts/07b-training-bias-demo.md`](../scripts/07b-training-bias-demo.md) |
| Signs replication protocol | [`examples/signs-replication-protocol.md`](../examples/signs-replication-protocol.md) |
| Shared vocabulary | [`glossary.md`](glossary.md) |
