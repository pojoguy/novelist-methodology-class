# Example: Signs Replication Protocol

How to **replicate or falsify** the maintainer claim that an explicit **Signs rubric** outperformed commercial AI detectors on **adherence separation** — without turning the rubric into a forensic certificate.

This is a **methodology template**, not published empirical results. Adapt labels and corpus to your project.

---

## What is being tested (and what is not)

| Claim under test | **Yes** | **No** |
|------------------|---------|--------|
| Signs + detectors both read **training-material / pattern adherence** signal | ✓ | |
| Explicit Signs checklist separates **high-adherence** from **governed organic** prose better than detector scores on **your** labeled set | ✓ | |
| Signs prove **no tool use** or **all-human authorship** | | ✓ |
| Wikipedia Signs list **validates** your rubric as science | | ✓ (convergence is descriptive, not citation) |
| n=1 maintainer corpus **generalizes** to all fiction | | ✓ |

**Frame:** Same signal class, different job — **craft diagnosis** vs **mislabeled attribution**.

---

## Corpus design

1. **Stratify** at least three buckets (minimum viable):
   - **A — Governed prosthetic:** passages from sessions with apply gate, anchors, move-type disclosure
   - **B — High-adherence organic:** human prose that follows tight genre/franchise rubric (e.g. formula series voice)
   - **C — Raw model paste:** unedited or lightly prompted model paragraphs (control)

2. **Size:** Small is honest — maintainer report is **n=1**. Label **≥20 passages per bucket** if you want any stable comparison; fewer is exploratory only.

3. **Exclude:** exploration/ drafts, comparanda excerpts, grounding headers — L0/L1 noise.

4. **Document:** chapter, line span, bucket, **how labeled** (session log, author attestation, known paste source).

---

## Signs pass (explicit rubric)

1. Fork project's Signs list (~18 items) or Wikipedia list adapted for fiction POV/voice.
2. **Blind pass:** scorer (human) marks Sign hits per passage with **short cite** — no auto-fix.
3. Record: Sign count, which Signs fired, **human signal override** when intentional voice conflicts.
4. **Score proxy (optional):** weighted Sign density per 500 words — not for ranking authors, only bucket separation.

---

## Detector pass (commercial products)

1. Run **≥2** detector products on the **same passages** (frozen text; same date).
2. Record raw scores and thresholds each product documents.
3. **Do not** treat disagreement between products as ground truth — both approximate adherence.

---

## Comparison metrics (adherence separation)

For each bucket pair (A vs C, B vs C, A vs B):

| Metric | Signs | Detector |
|--------|-------|----------|
| **Separation** | Mean Sign density difference between buckets | Mean score difference |
| **False alarm on B** | Signs flag franchise-organic as "AI" | Detector flags B as AI |
| **Miss on A** | Signs miss known prosthetic lines | Detector scores A as human |

**Success (replication):** Signs achieve **lower false alarm on B** and/or **better A vs C separation** than best single detector — on **your** corpus.

**Failure (falsification):** Detectors match or beat Signs on those metrics — document and narrow Signs scope.

---

## Controls and honesty

- **Franklin W. Dixon / formula fiction control:** Bucket B must include tight franchise prose — detectors often false-positive; Signs should be **tuned** not to punish intentional formula.
- **Paste-from-another-AI control:** Bucket C should include non-session paste — detectors may still miss; Signs should catch **pattern adherence**, not tool provenance.
- **Disclosure:** Publish bucket definitions, Sign list version, detector names/versions, date — not "Signs beat AI" headline.

---

## Reporting template (one page)

```text
Corpus: N passages · buckets A/B/C · project [name] · date
Signs list: [version / source]
Detectors: [product A v…] [product B v…]

Results:
  A vs C separation: Signs […] · Detector […]
  B false-positive rate: Signs […] · Detector […]

Conclusion:
  [Replicated / partial / falsified] on adherence separation — not authorship.

Limits:
  n=… · single project · scorer bias · detector API drift
```

---

## Cross-links

- [`docs/04-audit-and-governance.md`](../docs/04-audit-and-governance.md) — *Prose rubric (Signs)*
- [`docs/07-ethics-and-transparency.md`](../docs/07-ethics-and-transparency.md) — *Signs rubric vs commercial AI detectors*
- [`docs/02-prosthetic-model.md`](../docs/02-prosthetic-model.md) — move types (pick vs cluster+take vs supersede)
