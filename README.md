# LLM Methodology in Creative Writing

**Beyond "write me a bestseller."**

**Repository:** https://github.com/pojoguy/novelist-methodology-class

Most public debate about AI and creative writing stops at the worst-case scenario: a novice types a prompt, accepts the output, and calls it a novel. That usage exists. It is also the **smallest** part of what serious authors are building with large language models.

This repository documents a broader, craft-first methodology: how working writers use LLMs as **prosthetic tools** — external working memory, audit engines, continuity graphs, and grounding sandboxes — while keeping creative intent, voice, and final prose mass **human**.

---

## Who this is for

- **Authors skeptical of AI** who have only seen ghostwriting demos and want to understand what serious practitioners actually do
- **Authors already using AI** who want structure, governance, and language to explain their workflow to peers, editors, or readers
- **Editors and beta readers** evaluating how AI-assisted manuscripts are produced

## Who this is not for

- Prompt libraries that promise a finished novel in an afternoon
- "AI wrote my book" marketing
- Replacing craft, revision, or authorial responsibility

---

## Core thesis

| Novice frame | Methodology frame |
|--------------|-------------------|
| LLM as author | LLM as **prosthetic** (retrieval, audit, modeling) |
| Output = manuscript | Output = **diagnostics, alternatives, state** |
| One-shot prompting | **Session anchors**, knowledge graphs, apply gates |
| "The thread remembers my novel" | **Registered notes + lookup** — state outside chat (see [`08`](docs/08-infrastructure-techniques.md) when filing starts to matter) |
| "Make it better" | **Flag → six alternatives → author decides → apply** |
| Trust the model | **Constrain the model**; human authorizes |

Creative intent and final prose remain human. AI assists where human working memory, cross-reference, or statistical pattern-matching would otherwise fail — not where authorship lives.

---

## Repository map

| Path | Contents |
|------|----------|
| [`docs/00-history-and-authority.md`](docs/00-history-and-authority.md) | AI is not new; hidden daily use; maintainer qualification |
| [`docs/01-spectrum-of-use.md`](docs/01-spectrum-of-use.md) | Novice → sophisticated: a honest map of how writers use LLMs |
| [`docs/02-prosthetic-model.md`](docs/02-prosthetic-model.md) | Prosthetic vs ghostwriting; the six-alternative protocol |
| [`docs/03-five-domains.md`](docs/03-five-domains.md) | Five domains of AI use in a long-form project |
| [`docs/04-audit-and-governance.md`](docs/04-audit-and-governance.md) | Rubrics, gates, author locks, apply authorization |
| [`docs/05-workflow-patterns.md`](docs/05-workflow-patterns.md) | Session anchors, two-step pipelines, knowledge state |
| [`docs/06-failure-modes.md`](docs/06-failure-modes.md) | Sparse-edge collapse, ghostwrite drift, structural traps |
| [`docs/07-ethics-and-transparency.md`](docs/07-ethics-and-transparency.md) | Disclosure, authorship, what "AI-assisted" means |
| [`docs/08-infrastructure-techniques.md`](docs/08-infrastructure-techniques.md) | Indexed notes, continuity checks, comparanda, lookup habits |
| [`docs/glossary.md`](docs/glossary.md) | Master glossary (docs also define terms locally at top) |
| [`docs/JARGON-STANDARD.md`](docs/JARGON-STANDARD.md) | Contributor rule: Terms table at start of every doc/script |
| [`scripts/`](scripts/) | YouTube video scripts — one-to-one paired with `docs/`; see [`scripts/production-setup.md`](scripts/production-setup.md) for record/edit workflow |
| [`templates/`](templates/) | Starter templates for sessions and editorial feedback |
| [`examples/`](examples/) | **Start:** [`grounding-pov-blind-case-study.md`](examples/grounding-pov-blind-case-study.md) (POV-blind grounding walkthrough). Also: vocabulary prosthetic workflow, Signs replication protocol, spectrum demo fixtures (**synthetic / demo-only** — not a live manuscript) |

### How this fits together

| Layer | Repository | You use it for… |
|-------|------------|-----------------|
| **Methodology** | [This repo](https://github.com/pojoguy/novelist-methodology-class) | Docs, templates, examples — **start here** (Week 1–2, any chat tool) |
| **Optional engine** | [novelist-plugin](https://github.com/pojoguy/novelist-plugin) | Registered lookup, continuity, grounding automation — **Week 3+** when filing hurts |
| **Worked example** | [Mark-of-The-Guardian](https://github.com/pojoguy/Mark-of-The-Guardian) | Optional deep dive — anonymized walkthroughs in [`examples/grounding-pov-blind-case-study.md`](examples/grounding-pov-blind-case-study.md); **not required** to learn Levels 2–3 |

Patterns here are **generalized** from long-form practice; the novel repo shows one author's filing habits — **prose stays there, methodology stays here.** You do **not** need the plugin or novel repo to learn prosthetic + audit in any chat tool.

### Related repository (optional tooling)

**This tree is methodology and templates only** — docs, examples, session templates. It does **not** contain the MCP server, prompt packs, or reference rubric files.

The maintainer's **optional implementation** lives in **[novelist-plugin](https://github.com/pojoguy/novelist-plugin)** — [`prompts/rubric.md`](https://github.com/pojoguy/novelist-plugin/blob/main/prompts/rubric.md) (18 Signs), continuity tooling, and [getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md) for registered lookup.

You do **not** need novelist-plugin to learn Week 1 habits (prosthetic + audit) from these docs alone.

---

## Quick start

0. Skim **[`docs/JARGON-STANDARD.md`](docs/JARGON-STANDARD.md)** — every doc defines jargon at the top for non-technical readers.
1. **Optional:** [`docs/00-history-and-authority.md`](docs/00-history-and-authority.md) — if you are skeptical that AI is new or want the hidden-AI map and maintainer context.
2. Read [`docs/01-spectrum-of-use.md`](docs/01-spectrum-of-use.md) — the landscape in ten minutes.
3. Read [`docs/02-prosthetic-model.md`](docs/02-prosthetic-model.md) — the central operating model.
4. Copy [`templates/session-close.md`](templates/session-close.md) when you close a writing session.
5. When the book outgrows chat, add filing habits — [`docs/05-workflow-patterns.md`](docs/05-workflow-patterns.md) first; [`docs/08-infrastructure-techniques.md`](docs/08-infrastructure-techniques.md) when registered lookup starts to matter (not Week 1).

### Where to start (by week)

You do **not** need a governed IDE on day one. The path is **manual habits first**, optional tooling when capture and lookup start to hurt.

| Week | You do | Tools |
|------|--------|-------|
| **1** | Read spectrum + prosthetic model; close every session with a **session anchor** ([`templates/session-close.md`](templates/session-close.md)) | Any chat tool — ChatGPT, Claude, Gemini, etc. |
| **2** | File **map + Street View** for one real site in a folder; keep **manual route notes** before travel prose | Same chat tool + folders on your machine |
| **3+** | Optional: registered PGMs, search, continuity checks when the book grows | [novelist-plugin getting started](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GETTING-STARTED.md) — only if you want the maintainer's full stack |

**Week 1 goal:** More than *"make me a story"* — diagnose, six alternatives, you pick, you apply. No lookup tiers, no plugin required.

**Reading order (docs):** [`01`](docs/01-spectrum-of-use.md) → [`02`](docs/02-prosthetic-model.md) → [`05`](docs/05-workflow-patterns.md) / [`06`](docs/06-failure-modes.md) for habits and failure modes; [`03`](docs/03-five-domains.md) + [`04`](docs/04-audit-and-governance.md) + [`07`](docs/07-ethics-and-transparency.md) for scope, audit, and ethics; **[`08`](docs/08-infrastructure-techniques.md) when registered lookup starts to matter** — not Week 1. Full three-repo map: [How this fits together](#how-this-fits-together) above; short pointer in [`01`](docs/01-spectrum-of-use.md) — *How this repo relates to tooling*.

---

## Origin

This methodology grew out of a multi-year novel project where the maintainer is autistic, uses LLMs as vocabulary and continuity prosthetics, and treats tool output as **bounded search** under explicit constraints — closer to governed craft than to "chat until it's good."

Research lineage runs to 1980s knowledge-based systems work at the University of Calgary; current practice includes **production knowledge-systems work** — governed LLM systems with explicit state, checkpoints, and human authorization before side effects. See [`docs/00-history-and-authority.md`](docs/00-history-and-authority.md) Part 4 for maintainer context.

The patterns here are **generalized** from that practice. They are not tied to one genre, one tool, or one manuscript.

---

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). We welcome workflow descriptions, failure-mode reports, template improvements, and video script revisions from authors who use AI as a tool — not a substitute.

**Docs ↔ scripts:** New doc in `docs/`? Add a matching stub in `scripts/` using [`scripts/_template.md`](scripts/_template.md). Keep numbering and filenames in sync.

---

## License

[MIT License](LICENSE) — use, modify, and distribute with attribution.
