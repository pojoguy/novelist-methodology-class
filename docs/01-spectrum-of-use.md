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
| **Grounding / simulation sandbox** | A **scratch space** to test real-world facts (routes, period detail) before you promote them to canon. |
| **Agentic workflow** | Multiple automated **steps with rules** (audit, then check, then wait for your pick) — not one "fix my chapter" prompt. |
| **Apply gate** | Nothing changes in your manuscript until **you** explicitly say which option to use. |

---

Public argument about AI and books often collapses to a single image: someone types *"write me a bestselling YA fantasy"* and publishes the result. That is one point on a spectrum. This document maps the rest.

For historical context, hidden daily AI use, and maintainer qualification, see [`00-history-and-authority.md`](00-history-and-authority.md).

---

## Level 0 — Ghostwriting on demand

**What it looks like:** One-shot or few-shot prompts; accept output; minimal revision; authorial credit without authorial labor.

**Typical prompts:** "Write chapter 3," "Make this more emotional," "Give me a plot twist."

**Why critics fixate here:** It is visible, fast, and easy to condemn. It also produces statistically average prose (see any "18 Signs" rubric).

**Methodology stance:** Not what this repository teaches. If you do this, you are not using a prosthetic — you are outsourcing authorship.

---

## Level 1 — Brainstorming and ideation

**What it looks like:** Lists of titles, loglines, character names, "what if" branches. Human selects and discards.

**Value:** Low risk; high discard rate. Good for unsticking a blank page.

**Limit:** Ideas without grounding in your voice, research, or continuity are disposable. Do not confuse volume with craft.

---

## Level 2 — Lexical prosthetic (vocabulary retrieval)

**What it looks like:** You know the beat; you cannot retrieve the word, idiom, or sentence shape under load. The model offers **alternatives** — inspiration, not a menu order; you pick, blend, reject, or write your own.

**Key rule:** Six alternatives, not one substitution. The model expands your retrieval set; it does not choose for you.

**Example:** Flagged line: *"He felt afraid."* → six options that preserve somatic/tactical channel → author inspired by #4, edits into final line.

**Why it matters:** This is how many neurodivergent authors use LLMs — external working memory for lexical access, not for plot or voice.

---

## Level 3 — Developmental audit (read-only critique)

**What it looks like:** Adversarial editorial pass on **human-written** draft. Output: verdict, what's working, numbered recommendations (what's wrong / why it matters / what to do). **No manuscript apply** unless you explicitly authorize.

**Typical artifacts:** Rubric Signs (AI textual degradation), POV breaches, pacing, continuity flags.

**Key rule:** "Do all priority fixes" means **complete the audit and branch alternatives** — not rewrite the chapter.

---

## Level 4 — Continuity and knowledge state

**What it looks like:** Character sheets, timeline graphs, location registries, "program guides" (PGMs) loaded before each session. The model cross-references multi-era timelines, gear state, who knows what when.

**Value:** Humans forget; graphs do not. Reduces "wait, didn't she lose that knife in chapter 4?" errors.

**Tooling:** JSON lore files, MCP fact queries, session anchors with continuity blocks.

**Key rule:** Canon lives in **registered state**, not in chat memory. Chat is ephemeral; PGMs persist.

---

## Level 5 — Grounding and simulation sandboxes

**What it looks like:** Pressure-test beats against real-world constraints: highway routing, period medical practice, weather, biology, material culture. Exploration folders marked **non-canonical** until promoted.

**Value:** Stops "movie logic" from becoming manuscript logic.

**Key rule:** When grounding is unknown, **stop and ask** — do not let the model invent plausible-sounding facts.

---

## Level 6 — Production blueprinting (post-manuscript)

**What it looks like:** Trailer storyboards, foley direction, frame-timing notes for human animators/editors. AI assists pre-production; humans execute.

**Status:** Often future work for novelists; common in transmedia projects.

---

## Level 7 — Agentic methodology (orchestrated workflows)

**What it looks like:** Multi-step pipelines with explicit gates:

1. **Structural / grounding** agent → beat sequence, PGM crosswalk, questions
2. **Prosthetic audit** agent (readonly) → PASS/FAIL on quote gates, tagline gates, apply gates
3. **Author pick** → then apply

Plus: session anchors (continuity re-entry), post-session meta-analysis (what worked / failed per LLM product), `.cursorrules` or equivalent agent constraints, **RAG/passage indexing**, **continuity verify reports**, **comparanda** craft comparison.

**Value:** Repeatable craft infrastructure across months of work and multiple model vendors — with indexed state, not chat memory.

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
| 5 Grounding | High | Simulation / verify | Author promotes canon |
| 6 Production | N/A | Blueprint | Human crew |
| 7 Agentic | High | Bounded agents | Multi-gate |

---

## Talking to skeptics

When someone says "AI can't write real books," you can agree — **if** they mean Level 0.

When someone says "any AI use is cheating," ask which level they mean. Lexical prosthetic and developmental audit are closer to spell-check, continuity spreadsheet, and a brutally honest beta reader than to ghostwriting.

When someone says "AI will replace authors," point to Levels 4–7: the human work is **designing the methodology**, **maintaining state**, and **authorizing every change**. That is not less work — it is different work.

---

## Next

- [`02-prosthetic-model.md`](02-prosthetic-model.md) — the central operating model
- [`03-five-domains.md`](03-five-domains.md) — how domains map to long-form projects
