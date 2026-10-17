---
name: rolewire-mcp
description: >
  Model Context Protocol (MCP) tool integration for Rolewire. Connects agents to live tech job search,
  verified ATS openings, salary data, and full job descriptions.
compatibility: "claude-code cursor opencode codex antigravity zed cline"
---

# Rolewire MCP Integration

This skill configures and instructs the agent on using the official Rolewire Model Context Protocol (MCP) server.

## Installation & Setup

If `rolewire-mcp` is not yet running in your agent harness, configure it using `npx`:

### Claude Desktop / Claude Code
Add to `claude_desktop_config.json` (or `.claude.json`):
```json
{
  "mcpServers": {
    "rolewire": {
      "command": "npx",
      "args": ["-y", "rolewire-mcp@latest"]
    }
  }
}
```

### Cursor IDE
In Settings -> Features -> MCP -> Add New MCP Server:
- **Name**: `rolewire`
- **Type**: `command`
- **Command**: `npx -y rolewire-mcp@latest`

### Antigravity / Windsurf
Add to your `mcp_config.json`:
```json
{
  "mcpServers": {
    "rolewire": {
      "command": "npx",
      "args": ["-y", "rolewire-mcp@latest"]
    }
  }
}
```

### Zed Editor
Add to `settings.json`:
```json
{
  "context_servers": {
    "rolewire": {
      "command": {
        "path": "npx",
        "args": ["-y", "rolewire-mcp@latest"]
      }
    }
  }
}
```

## Available MCP Tools

- **`search_jobs`**: Search verified tech roles with query syntax (`query`, `remote`, `department`, `company`, `vertical`, `min_salary`, `limit`).
- **`get_job_detail`**: Fetch complete description, tech stack requirements, and direct ATS application link via `id` (role slug or URL).
- **`get_company_roles`**: Fetch active openings for a specific company (`company`, `limit`).
- **`get_sectors`**: List industry sectors (`ai`, `crypto`, `consumer`, `devtools`).
- **`get_departments`**: List standardized functional departments.

## Fallback (Direct Endpoints)
If MCP tool execution is unavailable, fetch data via HTTP:
- Feed: `https://rolewire.app/feed.md?q=<query>`
- Detail: `https://rolewire.app/jobs/<slug>.md`
