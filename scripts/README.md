# YouTube Scripts

Short-form video scripts paired **one-to-one** with [`docs/`](../docs/). Same numbering, same filenames — open the doc for depth, open the matching script for camera-ready beats.

---

## Directory map

| Script | Paired doc | Suggested format |
|--------|------------|------------------|
| [`00-history-and-authority.md`](00-history-and-authority.md) | `docs/00-history-and-authority.md` | Series opener — **ready to record** (~5:15) |
| [`01-spectrum-of-use.md`](01-spectrum-of-use.md) | `docs/01-spectrum-of-use.md` | 60–90s Short or 3–5 min explainer |
| [`01b-level-zero-demo.md`](01b-level-zero-demo.md) | `docs/01-spectrum-of-use.md` (Level 0) | **~5 min screen demo** — frontier chat only, not Cursor |
| [`01c-spectrum-demos-index.md`](01c-spectrum-demos-index.md) | `docs/01-spectrum-of-use.md` (Levels 1–7) | **Index** — suite map, env matrix, shared fixtures |
| [`01c-level-01-brainstorm.md`](01c-level-01-brainstorm.md) … [`01c-level-07-agentic.md`](01c-level-07-agentic.md) | `docs/01-spectrum-of-use.md` | **~2:30–3:30 each** — per-level screen demos |
| [`02-prosthetic-model.md`](02-prosthetic-model.md) | `docs/02-prosthetic-model.md` | 3–5 min — core thesis video |
| [`03-five-domains.md`](03-five-domains.md) | `docs/03-five-domains.md` | 3–5 min or 5× Short series |
| [`03b-scenario-simulation.md`](03b-scenario-simulation.md) | `docs/03-five-domains.md` (Domain 4b / L5b) | **~3:30** — grounding vs play-pretend |
| [`04-audit-and-governance.md`](04-audit-and-governance.md) | `docs/04-audit-and-governance.md` | 3–5 min |
| [`05-workflow-patterns.md`](05-workflow-patterns.md) | `docs/05-workflow-patterns.md` | 3–5 min |
| [`06-failure-modes.md`](06-failure-modes.md) | `docs/06-failure-modes.md` | 60–90s Short (high share potential) |
| [`07-ethics-and-transparency.md`](07-ethics-and-transparency.md) | `docs/07-ethics-and-transparency.md` | 3–5 min |
| [`07b-training-bias-demo.md`](07b-training-bias-demo.md) | `docs/07-ethics-and-transparency.md` (training bias) | **~3 min screen demo** — Gettysburg vs Bible prompts |
| [`08-infrastructure-techniques.md`](08-infrastructure-techniques.md) | `docs/08-infrastructure-techniques.md` | 3–5 min or 3-part mini-series |
| [`glossary.md`](glossary.md) | `docs/glossary.md` | Overlay cards / end-screen term stack |
| [`production-setup.md`](production-setup.md) | — | **HF G20 · DeckLink · OBS · G733 · Resolve** workflow |

---

## Script format

Copy [`_template.md`](_template.md) when starting a new script. Every script opens with **Terms in this video** — plain language for non-technical viewers. See [`../docs/JARGON-STANDARD.md`](../docs/JARGON-STANDARD.md).

Each script includes:

- **Metadata** — title, length target, paired doc, series tag
- **Hook** — first 3–5 seconds (pattern interrupt)
- **Beats** — spoken lines with optional timestamps
- **On-screen** — lower thirds, titles, bullet cards
- **B-roll / visual** — what the viewer sees
- **CTA** — subscribe, repo link, next video in series

---

## Production notes

- **Shorts (≤60s):** One idea per video; hook in frame 1; text on screen for silent viewers
- **Explainers (3–5 min):** Hook → problem → framework → one example → CTA
- **Series order:** `00` → `01` → `01b` (L0) → `01c` (L1–L7 demos; **5a+5b** separate) → `02` → `03` → `03b` (maps vs pretend); `06` and `02` work as standalone hooks
- **Repo link for description:** https://github.com/pojoguy/novelist-methodology-class — point to the paired `docs/` file for depth

---

## Contributing

New doc in `docs/`? Add a matching stub in `scripts/` using `_template.md`. Keep numbering in sync.
