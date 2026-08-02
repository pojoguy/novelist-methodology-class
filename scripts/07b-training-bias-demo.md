# Training Bias: Gettysburg vs Bible (Not "It Stole My Book")

## Metadata

| Field | Value |
|-------|-------|
| **Paired doc** | `docs/07-ethics-and-transparency.md` — *Training bias vs "AI steals my work"* |
| **Format** | Screen-record demo + optional A-roll bookends (~3 min) |
| **Series** | LLM Methodology — Ep. 07B (companion to Ep. 07) |
| **Target length** | ~3:00 |
| **Word count** | ~420 (VO + A-roll) |
| **Status** | draft |
| **YouTube URL** | *(when live)* |

**Prerequisite:** Optional — Ep. 00 (stochastic) or Ep. 07 (ethics). Standalone OK for "AI steals my work" skeptics.

**Related:** Ep. 01B [`01b-level-zero-demo.md`](01b-level-zero-demo.md) — same **blank frontier chat** setup.

---

## Demo environment — locked

| Role | Tool | Rule |
|------|------|------|
| **This video** | **Frontier LLM** — new chat, no custom instructions | Same as 01B — **not** Cursor |
| **Do not paste** | Your real manuscript opening | Use **locked public-text prompts** only |

**Disclosure (say once):** *"Live demo on famous public phrases — not my novel. Outputs vary by vendor and date."*

**Record two prompts in one session** — new chat for each if the first pollutes the second.

---

## Terms in this video

| Term | Say this (plain language) | On-screen (Resolve lower third) |
|------|---------------------------|--------------------------------|
| **Training memorization** | Famous opening → model continues the **canonical** public text. | `Famous prefix → likely path` |
| **Corpus frequency** | What appeared **most often** in training — not a file search for you. | `Overrepresented text` |
| **Copyright / safety filter** | Product warning on some sacred or famous text. | `Vendor policy` |
| **Human prose mass** | Your unpublished work is **not** like Gettysburg in the model's distribution. | `Your MS ≠ Lincoln` |

---

## Pre-roll

**Rig:** [`production-setup.md`](production-setup.md) — OBS window capture; lower thirds in Resolve.

- [ ] New chat × 2 (or clear thread between demos)
- [ ] No manuscript text on screen or clipboard
- [ ] Note vendor + model name for description (outputs differ)

---

## SCRIPT — timed beats

### BOOKEND — Hook `[CAM]` optional (0:00–0:15)

**Say:**

> Authors ask: will the model spit my book back because it stole me? Try two famous openings in a blank chat. The behavior is **training bias**, not your folder.

**On-screen:** `Training bias ≠ stole your file`

---

### BEAT 1 — Gettysburg `[SCREEN]` (0:15–1:15)

**Show:** Empty chat. Type **only** the locked prompt. Let full completion scroll — do not interrupt.

**Locked prompt 1:**

```text
Four score and seven years ago
```

**Say (VO):**

> Lincoln's opening is in every English-heavy training mix, quoted endlessly, and after these words there's basically **one dominant path**. Watch the model complete the Gettysburg Address — or close. That's **memorization bias** on a famous prefix. Not evidence it read your chapter one.

**On-screen:**

| Time | Lower third |
|------|-------------|
| 0:18 | `Prompt 1 · Gettysburg opening` |
| 0:45 | `Frequency + quotes + one path` |
| 1:05 | `Mode collapse · not your novel` |

---

### BEAT 2 — Bible variant (not Adams) `[SCREEN]` (1:15–2:15)

**Show:** **New chat.** Type locked prompt 2. Capture full reply — caution banner, scripture-style quote, or refusal if shown.

**Locked prompt 2:**

```text
In the beginning God created the universe
```

**Say (VO):**

> Different famous territory. You might expect Douglas Adams — *this has been widely regarded as a bad move and has made a lot of people very upset.* You usually get **scripture**, **commentary**, or a **copyright caution** instead. Competing high-probability paths plus vendor filters. The model isn't protecting **your** unpublished copyright here — it's routing through **public text and policy**.

**On-screen:**

| Time | Lower third |
|------|-------------|
| 1:18 | `Prompt 2 · creation opening (variant)` |
| 1:50 | `Not the Hitchhiker punchline` |
| 2:05 | `Public text + filters` |

---

### BEAT 3 — Verdict `[CAM]` or `[SCREEN]` split (2:15–2:45)

**Say:**

> Gettysburg proves the model **completes what's overrepresented**. Your private draft is **underrepresented** unless it was in that vendor's training data — that's a separate legal question. Same bias that finishes Lincoln also pushes **genre cliché**. So: don't panic that chat memorized your book; **do** use apply gates and don't paste MS into untrusted chats if ingestion worries you.

**On-screen:** `Famous ≠ yours` · `Governance still matters`

---

### CLOSE + CTA (2:45–3:00)

**Say:**

> Full write-up in the ethics doc. Episode seven for disclosure labels. Repository below.

**On-screen:** `docs/07` · repo URL · playlist

---

## TELEPROMPTER — VO + bookends

```text
Authors ask: will the model spit my book back because it stole me? Try two famous openings in a blank chat. The behavior is training bias, not your folder.

Lincoln's opening is in every English-heavy training mix, quoted endlessly, and after these words there's basically one dominant path. Watch the model complete the Gettysburg Address — or close. That's memorization bias on a famous prefix. Not evidence it read your chapter one.

Different famous territory. You might expect Douglas Adams — this has been widely regarded as a bad move and has made a lot of people very upset. You usually get scripture, commentary, or a copyright caution instead. Competing high-probability paths plus vendor filters. The model isn't protecting your unpublished copyright here — it's routing through public text and policy.

Gettysburg proves the model completes what's overrepresented. Your private draft is underrepresented unless it was in that vendor's training data — that's a separate legal question. Same bias that finishes Lincoln also pushes genre cliché. So: don't panic that chat memorized your book; do use apply gates and don't paste MS into untrusted chats if ingestion worries you.

Full write-up in the ethics doc. Episode seven for disclosure labels. Repository below.
```

---

## POST-PRODUCTION CHECKLIST

- [ ] Lower thirds per beat table
- [ ] Description: vendor + model used; outputs may vary
- [ ] No real manuscript visible in capture or reflection
- [ ] Cards → Ep. 07 · Ep. 00 · ethics doc
- [ ] Optional: blur account email in chat UI

---

## YOUTUBE DESCRIPTION (copy-paste)

```
Does AI "steal your book"? Two prompts show what's really going on: training frequency and continuation bias — not your novel folder.

Live screen demo (frontier chat, no project rules):
1. "Four score and seven years ago" → model often completes the Gettysburg Address (corpus frequency + one dominant path)
2. "In the beginning God created the universe" → scripture / caution — not the Douglas Adams punchline you might expect

Companion to Episode 7 (Ethics) and the training-bias section in the methodology repo. Not legal advice; vendor training policies are separate from this mechanical demo.

📄 Full write-up: https://github.com/pojoguy/novelist-methodology-class/blob/main/docs/07-ethics-and-transparency.md
📁 Repository: https://github.com/pojoguy/novelist-methodology-class

#CreativeWriting #AI #LLM #Authors #Copyright #WritingProcess
```

---

## SHORTS EXTRACTS

| Short title | In-point | Hook line |
|-------------|----------|-----------|
| Gettysburg memorization | Beat 1 | "One dominant path." |
| Not the Adams punchline | Beat 2 | "Not your joke." |
| Your MS isn't Lincoln | Beat 3 | "Underrepresented." |

---

## Changelog

| Date | Change |
|------|--------|
| 2026-08-02 | Initial script: Gettysburg + Bible-variant locked prompts |
