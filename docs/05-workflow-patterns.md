# Workflow Patterns

## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Session anchor** | A **saved file** at end of session: where the story paused, open fixes, what worked or failed with the tool. |
| **Section A / B / C** | Anchor parts: **A** = resume writing; **B** = revise one chapter; **C** = tune your process across tools. |
| **PGM** | **Formalized working notes** — canon in JSON, Cypher, Markdown, or plain text; registered for load/query. |
| **Author's notes** | Maps, timelines, character sheets, location photos — material authors **already** gather while drafting. |
| **PGM / grounding doc** | Same notes **registered** so tooling can load, query, and cite — not a separate workflow. |
| **Visual anchor pair** | **Map** (where, scale, names) + **ground-level image** (e.g. Street View) for the **same site**. |
| **Grounding capture** | File **map + Street View** (or equivalent) for one site in your project notes — one plain-language instruction per place. |
| **Exploration** | Scratch folder — **not official story truth** until you promote it. |
| **Canon / promote** | Making a scratch fact **official** by moving it into registered lore files. |
| **Two-step pipeline** | Structural pass → read-only audit pass → **you pick** → apply if authorized. |
| **Plain-language lookup** | You ask in ordinary language; your project files answer — search, fact check, route lookup — without you naming technical tiers. |
| **RAG** | **Search** that finds relevant passages in your manuscript — good for "where did I mention this?" |
| **Passage reanchor** | After you edit a chapter, **re-index** it so line numbers and IDs still match the text. |
| **Continuity check** | Readonly compare of prose against **registered** facts — named rules and citations; you decide fixes. Same habit as *verify run* in tooling docs. |
| **Report reference ID** | A **reference number** on a continuity check so you can cite the exact report later. |
| **Retrospective meta-analysis** | Looking back at your registered notes (grounding, routes, anchors) to reconstruct what a span assumed — distinct from Section C session feelings. |
| **Comparanda** | **Isolated reference excerpts** for craft comparison only — never indexed as your story. |
| **Grounding** | Real-world **facts and sources** (maps, period detail) your story must respect. |
| **POV-blind grounding** | **You** hold place coordinates in files; the **character** may never name the site on the page. |
| **Scenario simulation (Level 5b)** | **Off-page play-pretend** — run a character or institution through a beat; distill **constraints and knowledge state**, not manuscript dialogue. |
| **Apply gate** | You authorize every change to the manuscript. |
| **Attention / relationship collapse** | Text may fit in context; **joins** (who knows what, arc, locks) do not reliably survive in attention. |
| **Conversation context** | What the **chat thread** retains about **relationships** — unreliable even when raw text fits; use registered notes and queries instead. |

---

Repeatable infrastructure matters more than clever one-off prompts. These patterns appear across serious long-form AI-assisted projects.

**Where this doc sits:** [`01-spectrum-of-use.md`](01-spectrum-of-use.md) **Levels 4–7** (continuity, **5a** grounding, **5b** scenario simulation, agentic habits) and [`03-five-domains.md`](03-five-domains.md) **Domains 1, 3, 4a, 4b** (notes, continuity modeling, grounding, scenario simulation). The prosthetic **contract** (six alternatives, two-step, apply gate) lives in [`02-prosthetic-model.md`](02-prosthetic-model.md); **authorization language** and filed reports in [`04-audit-and-governance.md`](04-audit-and-governance.md). This doc is **how you file and reload state** across months.

### Why files exist — frontier chat hit a ceiling

Governance (prosthetic model, apply gates, six alternatives) was **developed and tested largely on frontier LLMs** in ordinary long chat sessions. That was enough to prove the **contract** — diagnose, branch, author decides. **Initial PGMs** were also **built in those same sessions** — structured character and continuity notes the author saved to project files.

It was **not** enough to **hold relationship joins in live attention** — even when the raw text of the project (and your saved PGMs) could fit in context. Models carry words more easily than **joins**: who knows what when, which arc owns a beat, which facts are locked. On dense pages where **multiple arcs resolve together**, relationship fidelity collapses in the attention layer before the author runs out of tokens. Across months, that becomes improvised continuity from recent chat.

Session anchors, PGMs, RAG/passage indexing, and structured queries are **external relationship memory** — the same notes you would keep in Scrivener or a wiki, **registered** so tooling can load or query them without stuffing the whole graph into every turn.

**How you work:** Ask in ordinary language (*"tell me about Dej"*). Your registered notes and indexes answer — you do not need to name search tiers or protocols. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Plain language — what you ask for*.

**Why files, not chat:** The maintainer prototyped this methodology in long frontier chat sessions first; when relationship state outgrew what chat could hold, the same author's notes moved into **registered files** you can load and query. See [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Origin*.

**This doc vs `08`:** **`05`** = **habits** — session anchors, file map + Street View, load grounding, run scenario sandboxes, promote to canon, reanchor after edits. **`08`** = **lookup mechanics** — indexing tiers, continuity-check habits, comparanda depth, infrastructure patterns. Start here for workflow; open `08` when you need how indexed search and verify reports work.

---

## Session anchors (continuity re-entry)

**Problem:** You return after days or weeks. You forget calendar pin, gear state, deferred fixes, which LLM product behaved last time.

**Solution:** Close every session with a **persisted anchor file** — not chat-only. Full anchor habits (Section C vs retrospective meta-analysis): [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Session anchors*.

### Typical sections

| Section | Purpose | Load when |
|---------|---------|-----------|
| **A — Entry block** | Timeline, location, physical state, open elements | Next writing session |
| **B — Revision notes** | Minor fixes, prosthetic themes deferred | Revising that chapter |
| **C — Meta-analysis** | What worked / improved / failed (per product) | Tuning methodology |

### Practices

- Write anchor to disk: `anchors/YYYY-MM-DD-chNN-session-close.txt`
- Maintain `_directory.md` index (date, chapter closed, entering chapter, notes)
- Deferred fixes belong in Section A **Open elements** — anchor is canonical deferral record
- Protocol updates follow **only** when author directs after reviewing Section C

See [`templates/session-close.md`](../templates/session-close.md).

---

## Two-step pipeline (structural → audit)

Same contract as [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Two-step pipeline*; phrase contracts and gates in [`04-audit-and-governance.md`](04-audit-and-governance.md).

```text
┌─────────────────────┐
│ Step 1: Structure   │
│ - Load notes/anchor │
│ - Beat sequence     │
│ - Questions if stuck│
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Step 2: Audit       │
│ - Readonly letter   │
│ - Quote/tagline/    │
│   apply gates named │
│ - Six options if    │
│   needed            │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ You pick, cluster + │
│ author take, or     │
│ name a line fix     │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Apply to manuscript │
│ (if you authorized) │
└─────────────────────┘
```

**Waive Step 2** only when you pick a numbered option or name a line fix — that is apply authorization, not blanket rewrite license.

---

## Knowledge state (PGMs)

**PGM** (program guide / project graph module): a **formalized slice of author working notes** — character, world, chapter state — in whatever format you maintain (JSON, Cypher, Markdown, plain text). Examples in this repo often use JSON or graph query shapes; that is **maintainer preference**, not a requirement.

#### Author's notes, formalized

PGMs, grounding indexes, route briefs, and chapter slices are **organized author's notes** — what you would keep in Scrivener, a wiki, or a binder. JSON, Cypher, Markdown, and plain text are storage choices. The requirement is **registered state** the stack can address.

With tooling, you **talk to the project**; the stack writes and indexes the same artifacts you would have kept anyway.

**Practices:**

- Master file + chapter slices (e.g. `character-master.json`, `character-ch07.json`)
- Load relevant slices **before** structural or audit output
- Chat is ephemeral; PGMs persist
- Exploration drafts: mark `NON-CANONICAL until promoted`

**Promotion workflow:** Author reviews exploration → registers in lore → anchor notes promotion date.

#### Grounding capture — map + Street View (example)

**While researching a beat**, authors often gather **two** anchors for one place:

1. **Map snip** — route, scale, place names (e.g. Google Maps).
2. **Street View snip(s)** — ground appearance at the **specific site**.

**Example (illustrative real site):** **Danish Cemetery near Coteau, ND** — map for approach and distances when scale allows; Street View for layout, terrain, markers, access road. Registered for **chapter 3** (`L62`–end): collapse and pickup on Hwy 15 beside the cemetery — see *POV-blind grounding* below.

**Author act (seconds):**

> *[map image] [Street View image(s)]*  
> *"Add this map and these Street View images to the grounding documents for chapter 3 — Danish Cemetery near Coteau."*

**What gets filed when you ask** (you send the images and one sentence; your project handles the rest):

| Step | What happens |
|------|--------|
| Place | Files under grounding / lore path for the chapter; labeled with place name |
| Index | Search index updated so you can find them later |
| Vision — map | Place names; distances **when scale is reliable** |
| Vision — Street View | Layout, structures, sightlines — **documented** appearance, not invented |
| Structure | Grounding registry + provenance (documented source); route links as needed |

**Why pair map + ground view**

| Problem | Effect of pair |
|---------|----------------|
| Model pulls a **generic fictional cemetery** (stock headstones, iron gate, spooky branches, mood weather) | Anchors **overrule** training prior when loaded for the beat |
| Prose drifts from the real site | You can **check your line** against what map and Street View actually show — not whether you typed the place name |

**Documented site vs model prior (Danish Cemetery):**

| Model pull (high-probability cemetery) | Street View / grounding |
|----------------------------------------|-------------------------|
| Dark walls, enclosure | **No walls** |
| Spooky branches, shade trees | **No trees** |
| Gothic mood default | **Bald prairie** |
| Cemetery as set piece | **Mowed patch in grain fields** — easy to miss |

**What you say (plain language):**

- *"Load grounding for chapter 3 before we revise the collapse pickup."*
- *"Does this roadside beat match what we documented at Coteau — no walls, no trees?"*

**Honest limits**

- Street View is **dated** — note capture date if era or site matters.
- Missing angles → **STOP and ask**; do not invent unseen detail.
- Anchors **constrain**; they do not replace voice, drama, or promotion to canon.

Cross-link: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md); [`03-five-domains.md`](03-five-domains.md) Domain 4a.

#### POV-blind grounding

**Your research notes can name a place the character never knows.**

When POV ignorance is intentional, you keep maps and Street View in your grounding files **without** putting the place name in the scene. That is not sloppy research — it is matching **what you know** to **what the character can perceive**.

**Example:** Danish Cemetery near Coteau, ND — chapter 3, lines 62–end. The collapse and pickup happen roadside **beside** the cemetery on Hwy 15. The boy is barely conscious; **no cemetery in the prose** — correct POV. Your grounding photos pin the geography for **you** and stop the model from inventing a generic Gothic cemetery (walls, trees) while the scene stays true to what he feels: prairie, gravel, the red Ford.

| Who | What they know |
|-----|----------------|
| **You (grounding + route notes)** | Danish Cemetery; Bowbells-**area** prairie — not a detour into Bowbells town |
| **The character (on the page)** | Collapse, golden prairie, pickup — not "cemetery" |
| **Your check** | Does the prose match the **documented site** (no walls, no trees, bald prairie)? — not "did I type the place name?" |

**If the character doesn't know where they are, your grounding still does.**

**Looking back later:** Grounding headers and route notes let you reconstruct *where* a span happened months after drafting — even when the prose never names it. See *Retrospective meta-analysis* below.

**Common mistake:** Searching the manuscript for "cemetery," finding nothing, and assuming the grounding work was wasted.

**What you're doing:** Keeping author coordinates in files the character doesn't need to share.

Cross-link: [`06-failure-modes.md`](06-failure-modes.md) — *Generic place hallucination*; [`02-prosthetic-model.md`](02-prosthetic-model.md) — *When six options fail*; [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md).

#### Governance overhead

**Marginal capture** (map + Street View, one instruction per site) can approach **~zero extra hours per 1,000 words** once your filing habit is wired — because capture is part of normal research, not a parallel project.

**Front-loaded cost:** Initial setup, discipline, re-index after edits, discourse tagging, continuity checks, and promotion habits are real labor. Do not confuse low marginal capture with zero total governance.

Full-stack honesty: [novelist-plugin GAPS.md](https://github.com/pojoguy/novelist-plugin/blob/main/docs/GAPS.md) — what the maintainer stack still costs in author time.

---

## Grounding load — what you do

Before you revise a beat that uses real places:

1. Ask to **load grounding** for that chapter and site.
2. Work only from the map and images you filed for that beat.
3. If something is missing → **stop and ask** — do not invent detail.

**Common mistake:** Revising roadside or cemetery prose from memory while generic training prior fills in walls, trees, and mood.

**What you're doing instead:** Checking your line against **documented** anchors before you call the beat done.

---

## Scenario simulation — what you do (Level 5b)

**Question:** *Who would this character or institution be under pressure in a beat that is not on the page yet?*

**What you do:**

1. Run an **off-page** session — play-pretend, institutional logic, "what do they know after three visits?"
2. **Distill** — constraints, refusals, knowledge state — **not** dialogue to paste into the chapter.
3. **File** in `exploration/` (or equivalent scratch) until you review.
4. **Promote** to character PGM / chapter slices when ready — then **you** write the on-page scene.

**Common mistake:** Pasting sandbox chat into the manuscript — that is [**domain collapse**](06-failure-modes.md#domain-collapse), not prosthetic use.

**Do not confuse with 5a:** **Grounding** answers *where* and *what it looks like*; **scenario simulation** answers *who under pressure* and *what they would conclude*. Same promotion gate (`exploration/` → canon); different question. Detail: [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 5b; [`03-five-domains.md`](03-five-domains.md) Domain 4b; explainer: [`scripts/03b-scenario-simulation.md`](../scripts/03b-scenario-simulation.md).

---

## Project expectations

Whether you use a governed editor or a long chat thread, **you** set the contract — adversarial audit, six alternatives, apply only when you say so. Starter checklist: [`templates/agent-instructions-starter.md`](../templates/agent-instructions-starter.md).

---

## What you can ask your project

When your notes and manuscript are registered, ordinary questions work:

- **Locate a beat** — *"Where did I mention the peel?"* / *"Find the naming speech."*
- **Refresh after edits** — re-index the chapter so line references stay true
- **Who / what / when** — character state, locked facts, name changes across chapters
- **Routes and places** — stops between towns; whether a corridor claim is on file
- **Continuity check** — does this passage contradict registered canon? (readonly report with reference ID; you revise — see [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Report types*)
- **Craft compare** — how does my opening compare to **quarantined** reference excerpts? Never promote comparanda into canon — treating reference or sandbox text as story truth is [**domain collapse**](06-failure-modes.md#domain-collapse) or [**comparanda bleed**](06-failure-modes.md#comparanda-bleed). Scope: [`03-five-domains.md`](03-five-domains.md).

**Design lock:** Search **locates**. Structured checks **verify**. **You** apply.

**Hold the line:** No route on file, or a failed continuity check → stop prose changes until resolved. **One kind of lookup per question** — do not mix a quick text search with a canon-sensitive check in the same breath.

Full habits: [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md).

---

## Post-session meta-analysis (Section C)

Three required questions every session close (Section C of your anchor — **how the session felt**, not what place the chapter used):

1. What worked well tonight?
2. What could be improved?
3. What did not work?

**Use:** Switch LLM vendors, adjust load order, add gate — not endless new rubric Signs. Cross-session review of Section C is how methodology **evolves** without bloating constraints. For **looking back at filed notes** months later (grounding, routes, POV-blind sites), see *Retrospective meta-analysis* below.

---

## Retrospective meta-analysis

**Registered notes** let you **reconstruct a span months later** without chat memory: what place you assumed, what photos you filed, what the prose deliberately never says. Distinct from Section C above — retrospective work uses **grounding files, route notes, and anchors**, not session feelings alone.

| Forward (while drafting) | Backward (months later) |
|--------------------------|-------------------------|
| Load map + Street View before revising a beat | Open grounding folder: *"What site was chapter 3, line 62 using?"* |
| File route notes before travel prose | *"Which stops did I register vs name on the page?"* |
| Close with Section C feelings | *"What did I learn — protocol tweak or teaching note?"* |

**What to keep (beyond the manuscript):**

- **Grounding files** — photos, maps, chapter headers (`ch03 L62–end · POV-blind · Danish Cemetery`)
- **Route notes** — stops, rejected paths, line references
- **Session anchors** — Section C across months
- **Continuity check reports** — reference IDs you can cite
- **Promoted lore** — places the narrative may never label

**Example (POV-blind site):** You drafted collapse and pickup with **no cemetery on the page** — correct for POV. Months later you open your grounding folder and remember: roadside beside Danish Cemetery near Coteau, ND. You reconcile revised prose against Street View (no walls, no trees, bald prairie) without breaking character knowledge.

**Common mistake:** "The place name isn't in the manuscript, so the research didn't count."

**What you're doing instead:** Separating **what you know** from **what the character knows** — and keeping files that prove the first without breaking the second.

Full walkthrough: [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md).

Cross-link: [`02-prosthetic-model.md`](02-prosthetic-model.md) — *Session anchors*; [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) — *Looking back at your notes*.

---

## Passage reanchor

**Problem:** You edit a chapter; `CH07 L63` from last month's audit now points at the wrong line.

**What you do:** After substantive chapter edits, **re-index** (reanchor) that chapter so locators and passage IDs match the current text. Until then, cite a **short quoted snippet** with any stale `CH## L##` reference.

**When:** After rewrites, cuts, or merges — not after every typo. Skipping reanchor → stale locators and wrong citations: [`06-failure-modes.md`](06-failure-modes.md) — *Stale passage index*. Line-pointer habits: [`04-audit-and-governance.md`](04-audit-and-governance.md) — *Pointing at lines in revision*.

---

## Multi-edit apply order

When applying several line-keyed changes in one file:

- Process **highest line number first** (bottom → top)
- Prevents line drift after first edit

---

## Exploration vs canon

| Location | Status | Typical content |
|----------|--------|-----------------|
| `exploration/` or scratch chat | Non-canonical sandboxes | **5a:** route/feasibility notes · **5b:** scenario distillates |
| `lore/`, PGMs, promoted grounding | Canon | Routes, character masters, chapter slices |
| Anchor open elements | Deferred human decisions | — |

Never treat exploration as manuscript truth without promotion.

**Do not confuse 5a and 5b:** geography verify and play-pretend share a promotion gate but answer different questions. See [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 5.

---

## Next

| Topic | Document |
|-------|----------|
| Level ladder, Week 2 map + Street View | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) |
| Five domains (1, 3, 4a, 4b) | [`03-five-domains.md`](03-five-domains.md) |
| Level 5b scenario simulation | [`01-spectrum-of-use.md`](01-spectrum-of-use.md) Level 5b · [`scripts/03b-scenario-simulation.md`](../scripts/03b-scenario-simulation.md) |
| Apply gate, filed reports, `CH## L##` | [`04-audit-and-governance.md`](04-audit-and-governance.md) |
| Six alternatives, two-step detail | [`02-prosthetic-model.md`](02-prosthetic-model.md) |
| Failure catalog (place hallucination, …) | [`06-failure-modes.md`](06-failure-modes.md) |
| Lookup tiers, comparanda, infra detail | [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) |
| POV-blind grounding walkthrough | [`examples/grounding-pov-blind-case-study.md`](../examples/grounding-pov-blind-case-study.md) |
| Vocabulary prosthetic example | [`examples/vocabulary-prosthetic-workflow.md`](../examples/vocabulary-prosthetic-workflow.md) |
