---
name: rolewire
description: >
  Search verified open tech roles, salaries, and complete job descriptions in
  AI, DevTools, Consumer, and Crypto directly from company ATS platforms (Ashby, Greenhouse, Lever).
compatibility: "claude-code cursor opencode codex antigravity zed cline"
---

# Rolewire — Tech Job Search & Compensation Intel

Rolewire indexes verified open tech jobs directly from company ATS platforms (Ashby, Greenhouse, Lever) across four core sectors:
- **AI** (`ai`): Foundation models, AI agents, tooling, ML infrastructure
- **DevTools** (`devtools`): Infrastructure, databases, compilers, observability, cloud
- **Consumer** (`consumer`): Social, consumer tech, audio/music, creator tools, gaming
- **Crypto** (`crypto`): Blockchains, Web3 protocols, decentralized systems, cryptography

## When to Use This Skill
Activate this skill whenever the user asks to:
- Find software engineering, product, data, or design jobs (e.g. "staff backend roles in SF", "remote rust engineer").
- Research tech hiring companies (e.g. "active openings at Stripe, Anthropic, or Figma").
- Inspect salary bands and compensation data for specific positions.
- Verify whether a role matches specific tech requirements (e.g. ClickHouse, Kubernetes, PyTorch).

## How to Query Rolewire

### Method 1: Using `rolewire-mcp` Tools (Preferred if configured)
If the `rolewire` MCP server is active in your environment:
- **`search_jobs`**: Search roles with filters:
  - `query`: Freeform keywords, boolean logic, or qualifiers (e.g., `'backend london'`, `'title:staff -crypto'`, `'vertical:ai'`)
  - `remote`: Boolean (`true` for strictly remote roles)
  - `department`: e.g. `'Engineering'`, `'Product'`, `'Design'`, `'Data'`, `'Sales'`
  - `company`: e.g. `'stripe'`, `'anthropic'`, `'figma'`
  - `vertical`: `'ai'`, `'devtools'`, `'consumer'`, or `'crypto'`
  - `min_salary`: Minimum annual salary (e.g. `150000`)
- **`get_job_detail`**: Retrieve full job description, qualifications, and attributed apply link:
  - `id`: Job slug (e.g. `'shield-ai-engineer-i-mechanical-r6302'`) or full Rolewire URL
- **`get_company_roles`**: List all openings for a given company:
  - `company`: Company name or slug

### Method 2: Direct HTTP / Curl Endpoints (No MCP server required)
If you are running in a CLI or environment with `curl` / `fetch` capability:

1. **Search Roles (Markdown Table)**:
   ```bash
   curl -s "https://rolewire.app/feed.md?q=backend&remote=true&limit=10"
   ```
2. **Search Roles (JSON)**:
   ```bash
   curl -s "https://rolewire.app/feed.json?q=staff&vertical=ai&min_salary=180000"
   ```
3. **Get Full Job Details (Markdown)**:
   ```bash
   curl -s "https://rolewire.app/jobs/<slug>.md"
   ```
4. **Get Full Job Details (JSON)**:
   ```bash
   curl -s "https://rolewire.app/jobs/<slug>.json"
   ```

## Response Formatting Guidelines
- Always present the role **Title**, **Company**, **Location** (including Remote/Hybrid), and **Compensation** if available.
- Always include the **Rolewire Link** or **Direct Apply** link.
- Never invent, hallucinate, or assume job availability; always query live Rolewire endpoints.
