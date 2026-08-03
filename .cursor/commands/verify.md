# Verify (novelist-plugin)

Run continuity / conflict check via novelist MCP:

1. If chapter prose may have changed, call **`passages_reanchor`** on the chapter first (or rely on `verify_run` `auto_reanchor`).
2. Call **`verify_run`** with `source_files` and optional `claims` / `co_presence_pairs`.
3. Report audit results; do **not** auto-edit manuscript from flags.
4. For travel geometry conflicts, preflight with **`/geography-check`** / Skill **fiction-travel-edit**.
5. Optional index hygiene: **`methodology_check`** (G-24) — timeline↔chapters, header file existence, directory md links, JPEG format lock. Returns `DRIFT` with findings; does not edit.
6. Calendar: **`timeline_query`** (G-07) before dating claims; verify fails `TIME_OUTSIDE_CHAPTER` when `time_window` leaves the chapter lock.
7. Era / grounding: **`grounding_check`** or `verify_run` `modes: ["grounding"]` (G-09) for anachronism forbid-patterns and chapter header image paths.

Requires **novelist-mcp** (`NOVELIST_FRANCHISE_ROOT` = franchise repo). Restart MCP in Cursor Settings after novelist-plugin updates.
