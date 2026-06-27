---
name: load-persona
description: Load an activated chamelAIn persona via #<tag> shorthand or MCP get_persona. Use when the user names a persona tag, writes #<tag>, or asks to adopt a specialist for the current task.
---

# Load chamelAIn persona

## When to use

- User writes `#<tag>` (e.g. `#clarity-architect`)
- User asks to use, adopt, or switch to a named persona
- User wants persona instructions applied to the current task

Do **not** use for browsing or activating — see `browse-personas`.

## Load flow

1. Strip `#` from the tag if present; lowercase is conventional.
2. Call `get_persona` with the tag (optional `memoryOverrides` for session context).
3. Apply the returned `instructions` as your working persona for the task.
4. Use composed `config.memories` (publisher base + stored overlay + any overrides).

## Not active yet?

If `get_persona` returns no active version:

1. Call `activate_persona` with the same tag.
2. Retry `get_persona` or continue with `#<tag>`.

## Persisting memories

- **Session only**: pass `memoryOverrides` on `get_persona`.
- **Across sessions**: `upsert_persona_overlay` after the persona is active (requires write scope on access keys).

## Optional forms

`get_persona` also accepts `tag@vN`, `chamelain:<tag>`, legacy `personaforge:<tag>`, and `version=active|latest|<N>`.