# Case study: POV-blind grounding (anonymized)

A **real workflow arc** from a long-form project — not a synthetic demo fixture. Names and manuscript prose are omitted; **line references** and **site** are real to the maintainer corpus.

**Site (illustrative):** Danish Cemetery near Coteau, ND  
**Span:** Chapter 3, lines 62–end — collapse and pickup beside the cemetery on Hwy 15  
**POV:** Boy barely conscious — **no cemetery name in prose** (correct)

---

## Layer 1 — Your notes (author coordinates)

| What you filed | Why |
|----------------|-----|
| [`flaxton-bowbells-coteau.jpg`](grounding-pov-blind-fixtures/flaxton-bowbells-coteau.jpg) — approach, Hwy 15, cemetery label | *Where* and scale |
| [`danish-cemetery-dylan-collapse.jpg`](grounding-pov-blind-fixtures/danish-cemetery-dylan-collapse.jpg) — mowed patch, **no walls**, **no trees**, bald prairie | *What it looks like* — blocks generic Gothic cemetery |
| Chapter header: `ch03 L62–end · collapse pickup · Danish Cemetery (POV-blind)` | Retrospective hook months later |

**Grounding index:** [`grounding-pov-blind-fixtures/README.md`](grounding-pov-blind-fixtures/README.md) — map + Street View rows, constraint table.

**One-line capture (representative):**  
*"Add this map and these Street View images to grounding for chapter 3 — Danish Cemetery near Coteau."*

---

## Layer 2 — Character (on the page)

| Character knows | Character does not know |
|-----------------|-------------------------|
| Collapse, gravel, golden prairie, red Ford pickup | "Cemetery," Bowbells as a named town, formal place labels |

Grounding **counts** even when the narrative withholds the place name.

---

## Layer 3 — Check (documented site vs model pull)

| Generic model pull | Your documented site |
|--------------------|----------------------|
| Walls, iron gate | **No walls** |
| Spooky trees, shade | **No trees** |
| Cemetery as mood set piece | **Mowed patch in grain fields** — easy to miss from the road |

**Your question:** *"Does this roadside beat match what we documented at Coteau — no walls, no trees?"* — not *"Did I type cemetery?"*

A manuscript search for `cemetery` returning **zero hits** does **not** falsify the grounding work.

---

## Failure arc (before anchors)

1. **Weak pull:** Stock cemetery prose — walls, trees, Gothic weather — without filed ground photos.
2. **Misread:** "No place name in chapter → research wasted."
3. **Fix:** Map + Street View filed; load before revising the beat; check against **documented** appearance.

---

## Retrospective (months later)

You open the grounding folder and chapter header — not chat history — and remember: roadside beside Danish Cemetery, POV-blind by design. You can reconcile revised prose against photos without breaking character knowledge.

---

## Cross-links

- [`grounding-pov-blind-fixtures/`](grounding-pov-blind-fixtures/) — map + Street View assets and index
- [`docs/05-workflow-patterns.md`](../docs/05-workflow-patterns.md) — *Grounding capture*, *POV-blind grounding*, *Retrospective meta-analysis*
- [`docs/06-failure-modes.md`](../docs/06-failure-modes.md) — *Generic place hallucination*
- [`docs/03-five-domains.md`](../docs/03-five-domains.md) — Domain 4a
