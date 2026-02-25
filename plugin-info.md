# Claude Code Plugin Directory

Popular plugins, MCP servers, skills, and tools for Claude Code — curated from the community.

> Star counts approximate at time of writing (Feb 2026).

---

## Top Ranked Plugins

### 1. [anthropics/skills](https://github.com/anthropics/skills) ⭐ 75,300
**Official skill templates by Anthropic.**
- Copy-paste ready skill folders for common tasks
- Covers creative, technical, and enterprise workflows
- Each skill has a `SKILL.md` with instructions Claude loads dynamically
- Great starting point for building your own custom skills

```bash
gh repo clone anthropics/skills
```

---

### 2. [obra/superpowers](https://github.com/obra/superpowers) ⭐ 60,900
**Auto-planning and autonomous execution.**
- Claude plans and executes tasks without being told step-by-step
- Adds agentic behavior: research → plan → implement → verify
- Useful for large multi-file refactors and feature builds

---

### 3. [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code) ⭐ 51,600
**All-in-one setup: agents + skills + hooks.**
- Single install sets up your entire Claude Code environment
- Bundles popular agents, skills, and hook configurations
- Good for getting fully set up in one command

---

### 4. [upstash/context7](https://github.com/upstash/context7) ⭐ 46,800
**Real-time official documentation injection.**
- Feeds Claude the latest docs for any library (React, Next.js, Prisma, etc.)
- Prevents hallucinated or outdated API usage
- Runs as an MCP server via HTTP

```bash
claude mcp add --transport http context7 https://mcp.context7.com/mcp
```

---

### 5. [@playwright/mcp](https://github.com/microsoft/playwright-mcp) ⭐ ~30,000
**Browser automation and web testing via MCP.**
- Claude can open browsers, click, fill forms, take screenshots
- Great for testing web apps and scraping
- Made by Microsoft

```bash
claude mcp add --transport stdio playwright -- npx @playwright/mcp
```

---

### 6. [@modelcontextprotocol/server-github](https://github.com/modelcontextprotocol/servers) ⭐ ~28,000
**GitHub integration via MCP.**
- Create repos, open issues, make PRs, search code — all from Claude
- Uses your existing GitHub token

```bash
claude mcp add --transport stdio github \
  -e GITHUB_TOKEN=$(gh auth token) \
  -- npx -y @modelcontextprotocol/server-github
```

---

### 7. [@modelcontextprotocol/server-memory](https://github.com/modelcontextprotocol/servers) ⭐ ~28,000
**Persistent memory across Claude sessions.**
- Claude remembers facts, preferences, and context between conversations
- Stored locally as a knowledge graph

```bash
claude mcp add --transport stdio memory -- npx -y @modelcontextprotocol/server-memory
```

---

### 8. [@modelcontextprotocol/server-sequential-thinking](https://github.com/modelcontextprotocol/servers) ⭐ ~28,000
**Structured step-by-step reasoning.**
- Forces Claude to break complex problems into explicit reasoning steps
- Improves accuracy on multi-step coding and planning tasks

```bash
claude mcp add --transport stdio sequential-thinking \
  -- npx -y @modelcontextprotocol/server-sequential-thinking
```

---

### 9. [ryoppippi/ccusage](https://github.com/ryoppippi/ccusage) ⭐ ~12,000
**Token usage and cost tracker.**
- Reads local Claude Code JSONL logs to calculate usage
- Shows daily, monthly, and per-session breakdowns
- No API key needed — fully local

```bash
npx ccusage@latest daily
npx ccusage@latest monthly
npx ccusage@latest blocks    # 5-hour billing windows
```

---

### 10. [Maciek-roboblog/Claude-Code-Usage-Monitor](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor)
**Real-time terminal usage monitor.**
- Live token consumption display
- ML-based usage prediction
- Burn rate and session limit forecasting
- Rich terminal UI

```bash
npm install -g claude-code-usage-monitor
```

---

## MCP Servers — Quick Install All

```bash
# Real-time docs
claude mcp add --transport http context7 https://mcp.context7.com/mcp

# Browser testing
claude mcp add --transport stdio playwright -- npx @playwright/mcp

# GitHub integration
claude mcp add --transport stdio github \
  -e GITHUB_TOKEN=$(gh auth token) \
  -- npx -y @modelcontextprotocol/server-github

# Persistent memory
claude mcp add --transport stdio memory \
  -- npx -y @modelcontextprotocol/server-memory

# Sequential reasoning
claude mcp add --transport stdio sequential-thinking \
  -- npx -y @modelcontextprotocol/server-sequential-thinking
```

---

## Categories

### Skills & Agents
- `anthropics/skills` — Official skill library
- `obra/superpowers` — Autonomous agent behavior
- `affaan-m/everything-claude-code` — All-in-one environment

### Documentation
- `upstash/context7` — Live library docs via MCP

### Testing & Browser
- `@playwright/mcp` — Browser automation

### Version Control
- `@modelcontextprotocol/server-github` — GitHub via MCP

### Memory & Reasoning
- `@modelcontextprotocol/server-memory` — Cross-session memory
- `@modelcontextprotocol/server-sequential-thinking` — Structured reasoning

### Cost Tracking
- `ccusage` — CLI usage reporter
- `Claude-Code-Usage-Monitor` — Real-time terminal monitor

---

*Last updated: February 2026*
