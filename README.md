# chamelAIn Cursor Plugin

Official [Cursor Marketplace](https://cursor.com/marketplace) plugin for [chamelAIn](https://chamelain.com) — versioned AI personas delivered via MCP.

## Repository layout

```
.cursor-plugin/marketplace.json   # Marketplace manifest
plugins/chamelain/                # chamelAIn plugin
scripts/validate-template.mjs     # Pre-submission validator
```

## Validate

```bash
node scripts/validate-template.mjs
```

## Submission checklist

- Valid `plugin.json` and `marketplace.json`
- Logo committed at `plugins/chamelain/assets/logo.svg`
- Frontmatter on all rules, skills, agents, and commands
- `node scripts/validate-template.mjs` passes
- Production URLs swapped in `mcp.json` and skills before listing
- Submit: [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish) or kniparko@anysphere.com

## Placeholder URLs

Until production domains are live, the plugin uses:

- MCP: `https://mcp.chamelain.com/mcp`
- Web app: `https://app.chamelain.com`

Swap these before marketplace submission.