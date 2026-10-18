# Rolewire Agent Skills

[![skills.sh](https://skills.sh/b/har777/rolewire-skills)](https://skills.sh/har777/rolewire-skills)
[![npm version](https://img.shields.io/npm/v/rolewire-mcp.svg?style=flat-square&label=rolewire-mcp)](https://www.npmjs.com/package/rolewire-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

Official Agent Skills for [Rolewire](https://rolewire.app) — verified tech jobs ingested directly from startup and tech company ATS platforms (Ashby, Greenhouse, Lever).

Compatible with **Claude Code**, **Cursor**, **Codex**, **OpenCode**, **Antigravity**, **Zed**, and 75+ coding agents via [skills.sh](https://skills.sh).

---

## Quick Install via skills.sh

```bash
npx skills add har777/rolewire-skills
```

### Run Interactively (without installing):
```bash
npx skills use har777/rolewire-skills --agent claude-code
```

---

## What is Rolewire?

[Rolewire](https://rolewire.app) tracks verified, open technology roles directly from company ATS platforms across 5 sectors:
- **AI**: Machine learning, foundation models, AI agents, tooling
- **DevTools**: Developer tools, infrastructure, databases, cloud, observability
- **Consumer**: Consumer tech, media, audio, social, gaming
- **Crypto**: Blockchains, protocols, cryptography, Web3
- **Fintech**: Modern banking, payments, corporate cards, payroll, ledger infrastructure

---

## Direct Endpoints (No MCP required)

Agents with web or curl access can query Rolewire directly:
- **Feed (Markdown Table)**: `https://rolewire.app/feed.md?q=backend&remote=true`
- **Feed (JSON)**: `https://rolewire.app/feed.json?q=staff&vertical=ai`
- **Job Detail (Markdown)**: `https://rolewire.app/jobs/:slug.md`
- **Job Detail (JSON)**: `https://rolewire.app/jobs/:slug.json`

---

## Related
- **MCP Server**: [`rolewire-mcp`](https://www.npmjs.com/package/rolewire-mcp) on npm

---

## License
MIT © [Rolewire](https://rolewire.app)
