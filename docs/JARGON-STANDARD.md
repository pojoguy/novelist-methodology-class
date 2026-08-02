# Jargon blocks — contributor standard

Every **`docs/*.md`** (except this file and `glossary.md`) and every **`scripts/*.md`** (except `_template.md`) must open with a **Terms** section **before** the main body uses technical vocabulary.

**Audience:** Authors and viewers who are **not** engineers. Define on first use in the document; do not assume prior reading order.

---

## Docs format

Place immediately after the title (and optional one-line subtitle), before the first `---` or first major section:

```markdown
## Terms in this document

**For non-technical readers:** plain-language definitions for jargon used below.  
**Full glossary:** [`glossary.md`](glossary.md).

| Term | Plain language |
|------|----------------|
| **Example term** | One sentence a non-technical writer can understand. |
```

**Rules:**

- Include **only terms that appear in that document** — not the whole glossary.
- One sentence per term; no acronyms without spelling out on first row.
- Link to `glossary.md` for depth, not duplication of every entry.
- When you add new jargon to a doc, add a row to that doc's table in the same PR.

---

## Scripts format

Place after the **Metadata** table, before the hook:

```markdown
## Terms in this video

Define in the **first 30 seconds** or flash **on-screen** when each term first appears.

| Term | Say this (plain language) | On-screen (optional) |
|------|---------------------------|----------------------|
| **Example** | How you would explain it out loud. | 2–4 words for lower third |
```

**Rules:**

- **Say this** = conversational; suitable for teleprompter aside or ad-lib.
- Scripts may have **fewer** terms than the paired doc — only what the speaker uses on camera.
- Ep. 0+ should not assume viewer watched prior episodes; re-define terms that recur.

---

## `glossary.md`

Master reference. Docs and scripts link here; they do not replace per-document tables.

---

## Review checklist

- [ ] New doc/script has Terms section at top
- [ ] No undefined acronym in first section
- [ ] Paired doc ↔ script: script Terms ⊆ doc Terms (or script re-defines for new viewers)
