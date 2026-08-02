# LLM Methodology in Creative Writing

**Beyond "write me a bestseller."**

**Repository:** https://github.com/pojoguy/novelist-methodology-class

Most public debate about AI and creative writing stops at the worst-case scenario: a novice types a prompt, accepts the output, and calls it a novel. That usage exists. It is also the **smallest** part of what serious authors are building with large language models.

This repository documents a broader, craft-first methodology: how working writers use LLMs as **prosthetic tools** — external working memory, audit engines, continuity graphs, and grounding sandboxes — while keeping creative intent, voice, and final prose mass **human**.

---

## Who this is for

- **Authors skeptical of AI** who have only seen ghostwriting demos and want to understand what serious practitioners actually do
- **Authors already using AI** who want structure, governance, and language to explain their workflow to peers, editors, or readers
- **Developers building writing tools** who need a model of author agency that goes deeper than "generate chapter"
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
| "The thread remembers my novel" | **PGMs + RAG** — state outside chat |
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
| [`docs/08-infrastructure-techniques.md`](docs/08-infrastructure-techniques.md) | RAG indexing, continuity reporting, comparanda, locator tiers |
| [`docs/glossary.md`](docs/glossary.md) | Master glossary (docs also define terms locally at top) |
| [`docs/JARGON-STANDARD.md`](docs/JARGON-STANDARD.md) | Contributor rule: Terms table at start of every doc/script |
| [`scripts/`](scripts/) | YouTube video scripts — one-to-one paired with `docs/`; see [`scripts/production-setup.md`](scripts/production-setup.md) for record/edit workflow |
| [`templates/`](templates/) | Starter templates for sessions, editorial feedback, agent rules |
| [`examples/`](examples/) | Walkthroughs of real workflow shapes (anonymized) |

---

## Quick start

0. Skim **[`docs/JARGON-STANDARD.md`](docs/JARGON-STANDARD.md)** — every doc defines jargon at the top for non-technical readers.
1. Read [`docs/00-history-and-authority.md`](docs/00-history-and-authority.md) if you are skeptical that AI is new, novel, or relevant to your existing workflow.
2. Read [`docs/01-spectrum-of-use.md`](docs/01-spectrum-of-use.md) if you want the landscape in ten minutes.
3. Read [`docs/02-prosthetic-model.md`](docs/02-prosthetic-model.md) if you want the central operating model.
4. Read [`docs/08-infrastructure-techniques.md`](docs/08-infrastructure-techniques.md) for RAG, continuity verify, comparanda, and locator tiers.
5. Copy [`templates/agent-instructions-starter.md`](templates/agent-instructions-starter.md) into your own project if you use an agentic editor (Cursor, custom MCP, etc.).

---

## Origin

This methodology grew out of a multi-year novel project where the maintainer is autistic, uses LLMs as vocabulary and continuity prosthetics, and treats agent behavior as **bounded search** under explicit constraints — closer to knowledge engineering than to "chat until it's good."

Research lineage runs to 1980s knowledge-based systems work at the University of Calgary; current practice includes enterprise LLM orchestration (LangGraph). See [`docs/00-history-and-authority.md`](docs/00-history-and-authority.md) for full context.

The patterns here are **generalized** from that practice. They are not tied to one genre, one tool, or one manuscript.

---

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). We welcome workflow descriptions, failure-mode reports, template improvements, and video script revisions from authors who use AI as a tool — not a substitute.

**Docs ↔ scripts:** New doc in `docs/`? Add a matching stub in `scripts/` using [`scripts/_template.md`](scripts/_template.md). Keep numbering and filenames in sync.

---

## License

[MIT License](LICENSE) — use, modify, and distribute with attribution.
