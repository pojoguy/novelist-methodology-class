# Contributing

Thank you for helping document serious LLM use in creative writing.

## What we want

- **Workflow descriptions** — how you structure sessions, gates, and apply authorization
- **Failure-mode reports** — what went wrong when constraints piled up or the model substituted prose
- **Template improvements** — session anchors, editorial formats, agent instruction starters
- **Video scripts** — revisions to `scripts/` paired with `docs/`; Short and explainer formats
- **Tool comparisons** — honest notes on Cursor, NovelCrafter, Sudowrite, custom MCP, etc. (methodology, not affiliate links)
- **Ethics and disclosure** — how you talk to readers, editors, and peers about AI-assisted work

## What we do not want

- Prompt packs marketed as "write a novel in a day"
- Unattributed ghostwritten sample chapters
- Vendor spam or affiliate funnels
- Claims that AI replaces craft, revision, or authorial responsibility

## Cursor + novelist-plugin (maintainers / optional stack)

This repo documents methodology; **registered lookup** runs through [novelist-plugin](https://github.com/pojoguy/novelist-plugin) against a **franchise repo** (chapters, lore, grounding) — not against `docs/` alone.

1. Install novelist-plugin: `pip install -e ".[dev]"` in your plugin clone.
2. Copy [`.cursor/mcp.json.example`](.cursor/mcp.json.example) → `.cursor/mcp.json` (gitignored) or merge [`mcp-config.example.json`](mcp-config.example.json) into **Cursor Settings → MCP**.
3. Set `NOVELIST_FRANCHISE_ROOT` to your novel repo (maintainer example: `Mark-of-The-Guardian`).
4. **Restart MCP** in Cursor Settings after any plugin update (toggle off → on, or restart Cursor).
5. Skills and commands ship under [`.cursor/`](.cursor/README.md) — `fiction-locate`, `fiction-travel-edit`, `fiction-prosthetic-audit`, `/verify`, `/geography-check`.

When copying grounding into `examples/`, use MCP (`passages_search`, `grounding_check`, `methodology_check`) — not ad hoc filesystem search.

## How to contribute

1. Fork the repository.
2. Add or edit under `docs/`, `scripts/`, `templates/`, or `examples/`.
3. Keep examples **anonymized** — no unpublished manuscript text without explicit permission.
4. **Docs/scripts pairs:** same `00`–`08` numbering and filenames in both directories.
5. **Jargon:** every doc and script must open with a **Terms** table — [`docs/JARGON-STANDARD.md`](docs/JARGON-STANDARD.md).
6. Open a pull request with a short description of what you added and why.

## Style

- Plain language over jargon; **define terms at the top of each doc/script** and in `docs/glossary.md` when reusable
- Prefer **what happened** and **what you changed** over theory alone
- Cite line/chapter conventions if you use them (e.g. `CH07 L63`)

## Code of conduct

Be direct. Debate methodology on merit. Do not harass authors for using or not using AI.
