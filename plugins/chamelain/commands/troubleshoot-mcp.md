---
name: troubleshoot-mcp
description: Diagnose chamelAIn MCP connection failures — OAuth, legacy access keys, URL, and session errors.
---

# Troubleshoot chamelAIn MCP

## First-time connect (OAuth — preferred)

1. Install the chamelAIn plugin (bundles MCP server entry).
2. In Cursor MCP settings, connect **chamelain** — Cursor opens OAuth at https://chamelain.com/oauth/consent.
3. Sign in and approve access for your workspace.
4. Confirm `list_personas` returns data in a new chat.

## Legacy MCP Access Key (fallback)

1. Open https://chamelain.com/mcp/authorize
2. Create or reuse an access key; copy the ready-made `mcp.json` snippet.
3. Merge the `chamelain` entry into `~/.cursor/mcp.json`.
4. Restart Cursor.

## 401 Unauthorized or empty persona list

- Re-authenticate via OAuth or issue a fresh access key.
- Replace the full `chamelain` entry — do not mix stale Bearer tokens with new keys.
- Restart Cursor after config changes.

## Wrong MCP URL

- URL must end with `/mcp` (e.g. `https://mcp.chamelain.com/mcp`).
- Plugin `mcp.json` should point at the hosted server; do not point at localhost unless self-hosting.

## Expired or revoked access key

1. Settings → Security → MCP Access Keys
2. Revoke compromised keys
3. Re-authorize at `/mcp/authorize` or reconnect via OAuth

## Session errors (No valid session ID)

1. Restart Cursor after updating MCP config
2. Ensure only one `chamelain` server entry exists in `mcp.json`

## Persona not loading (#<tag> fails)

1. Call `activate_persona` for that tag, then `get_persona`
2. Plan limits require deactivating another persona at https://chamelain.com/dashboard

## Still stuck?

Email support@chamelain.com with org name and error text (redact tokens).