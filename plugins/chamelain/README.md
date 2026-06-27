# chamelAIn Cursor Plugin

Thin client for [chamelAIn](https://chamelain.com) — versioned AI personas delivered via hosted MCP.

## Included

- **MCP**: Hosted chamelAIn server (`chamelain` entry in `mcp.json`)
- **Skills**: Browse/activate personas; load active personas with `#<tag>`
- **Commands**: MCP troubleshooting (OAuth + legacy access keys)

Persona content lives on the platform, not in this plugin.

## Install

1. Cursor → Settings → Plugins → Browse Marketplace
2. Search **chamelAIn**
3. Install

## Connect

**OAuth (recommended):** Connect the bundled `chamelain` MCP server in Cursor settings and complete consent at https://chamelain.com/oauth/consent.

**Access key (fallback):** Authorize at https://chamelain.com/mcp/authorize and merge the snippet into `~/.cursor/mcp.json`.

## Use personas

1. `activate_persona` — favorite (if needed) and activate a tag
2. `#<tag>` or `get_persona` — load instructions for the current task

## Support

- Docs: https://chamelain.com
- Email: support@chamelain.com