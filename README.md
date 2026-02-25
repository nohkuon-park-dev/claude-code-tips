# Claude Code Tips & Tricks

A curated knowledge base for getting the most out of Claude Code.

---

## Files

| File | Contents |
|------|---------|
| [01-setup.md](./01-setup.md) | CLAUDE.md templates, MCP install, Skills setup |
| [02-workflows.md](./02-workflows.md) | Plan→Do→Verify, Plan Mode, multi-agent team mode |
| [03-prompts.md](./03-prompts.md) | Anti-sycophancy, ISO architect, quick prompt templates |
| [04-cost-and-performance.md](./04-cost-and-performance.md) | Token saving, context management, usage tracking |
| [05-tools.md](./05-tools.md) | MCP servers, skill collections, scraping tools |

---

## How to Use This Repo

### New project → `01-setup.md`
Copy the CLAUDE.md templates and run the MCP install commands.

### Starting a feature → `02-workflows.md`
Follow the Plan→Do→Verify loop. Use Plan Mode. Never implement without an approved plan.

### Important decision → `03-prompts.md`
Use the Anti-Sycophancy prompt before committing to anything significant.

### Bill too high → `04-cost-and-performance.md`
Apply the token-saving habits. Check usage with `npx ccusage@latest daily`.

### Need a new tool → `05-tools.md`
Browse verified MCPs and install what you need.

---

## Quick Start

```bash
# 1. Login
claude auth login

# 2. Install MCPs
claude mcp add --transport http context7 https://mcp.context7.com/mcp
claude mcp add --transport stdio playwright -- npx @playwright/mcp
claude mcp add --transport stdio github -e GITHUB_TOKEN=$(gh auth token) -- npx -y @modelcontextprotocol/server-github
claude mcp add --transport stdio memory -- npx -y @modelcontextprotocol/server-memory
claude mcp add --transport stdio sequential-thinking -- npx -y @modelcontextprotocol/server-sequential-thinking

# 3. Create global CLAUDE.md
touch ~/.claude/CLAUDE.md   # Add your global rules

# 4. In each project
claude   # then run /init to generate project CLAUDE.md
```
