---
name: browse-personas
description: Browse chamelAIn personas via MCP list_personas and activate with activate_persona. Use when the user wants to discover, favorite, or activate personas — not when loading an already-active persona in chat.
---

# Browse chamelAIn personas

## When to use

- User asks what personas are available
- User wants to activate a marketplace or org persona for Cursor
- User hit their active limit and needs guidance

Do **not** use for in-session persona work — use `#<tag>` and `get_persona` (see `load-persona` skill).

## Mental model

| Action | MCP tool | Web only |
|--------|----------|----------|
| Discover tags | `list_personas` | — |
| Favorite + activate | `activate_persona` | — |
| Deactivate / unfavorite | — | https://chamelain.com/dashboard |
| Load instructions in chat | `get_persona` / `#<tag>` | — |

`activate_persona` is idempotent: already-active tags return a no-op. Marketplace personas are favorited automatically when needed.

## Browse flow

1. Call `list_personas` — activated personas plus marketplace catalog entries.
2. Present name, tag, and description when available.
3. Do not assume hardcoded starter tags; use what `list_personas` returns.

## Activate flow

When the user wants to **use** a persona in Cursor:

1. Call `activate_persona` with the tag (optional `version` to pin).
2. On success, call `get_persona` or use `#<tag>` in chat.
3. On plan-limit errors, direct the user to https://chamelain.com/dashboard to deactivate or unfavorite — MCP cannot do that.

## Org-private personas

Private org personas may only appear after activation. `list_personas` focuses on the user's active set and marketplace listings.