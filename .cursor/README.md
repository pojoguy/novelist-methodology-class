# Cursor — governed stack (optional)

This repo documents methodology; **registered lookup** runs through [novelist-plugin](https://github.com/pojoguy/novelist-plugin) MCP against a franchise repo (maintainer: `Mark-of-The-Guardian`).

## One-time setup

1. Install novelist-plugin: `pip install -e ".[dev]"` in your `novelist-plugin` clone.
2. Copy [`.cursor/mcp.json.example`](mcp.json.example) → `.cursor/mcp.json` (gitignored) and set paths.
   - Or merge [../mcp-config.example.json](../mcp-config.example.json) into **Cursor Settings → MCP**.
3. **Restart MCP** in Cursor Settings after any plugin update (toggle off → on, or restart Cursor).
4. Confirm tools appear: `methodology_check`, `passages_search`, `geography_query`, `grounding_check`.

## Skills (this folder)

| Skill | Use |
|-------|-----|
| `fiction-locate` | Canon-sensitive locate — MCP L2, not `@Codebase` |
| `fiction-travel-edit` | `geography_query` before travel prose edits |
| `fiction-prosthetic-audit` | Readonly Step 2 — quote / tagline / apply gates |
| `fiction-craft-compare` | Comparanda diagnosis (franchise exploration paths) |

## Commands

- `/verify` — continuity check via MCP
- `/geography-check` — travel corridor preflight

## Franchise root

`NOVELIST_FRANCHISE_ROOT` should point at the **novel repo** (chapters, lore, grounding), not this methodology repo. Example work in `examples/` is mirrored from that corpus; use MCP to resolve live paths before copying or citing grounding assets.
