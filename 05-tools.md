# 05 — Tools & Plugins

Verified tools that extend Claude Code's capabilities.

---

## MCP Servers

| Name | Purpose | Install |
|------|---------|---------|
| **context7** | Real-time library docs — prevents outdated/hallucinated APIs | `claude mcp add --transport http context7 https://mcp.context7.com/mcp` |
| **playwright** | Browser automation, web app testing | `claude mcp add --transport stdio playwright -- npx @playwright/mcp` |
| **github** | Repo management, PRs, issues | `claude mcp add --transport stdio github -e GITHUB_TOKEN=$(gh auth token) -- npx -y @modelcontextprotocol/server-github` |
| **memory** | Persistent knowledge graph across sessions | `claude mcp add --transport stdio memory -- npx -y @modelcontextprotocol/server-memory` |
| **sequential-thinking** | Structured step-by-step reasoning | `claude mcp add --transport stdio sequential-thinking -- npx -y @modelcontextprotocol/server-sequential-thinking` |

---

## Skill Collections

| Repo | Stars | Description |
|------|-------|-------------|
| [anthropics/skills](https://github.com/anthropics/skills) | ⭐ 75k | Official Anthropic skill templates |
| [obra/superpowers](https://github.com/obra/superpowers) | ⭐ 61k | Autonomous planning and execution |
| [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code) | ⭐ 52k | All-in-one: agents + skills + hooks |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | ⭐ 2k | Community skills for real-world use |

---

## Web Scraping

### Firecrawl CLI
Convert any URL into a structured markdown/JSON file.

```bash
npx skills add firecrawl/cli
```

**Use cases:**
- Save competitor pricing pages on a schedule
- Scrape entire documentation sites in one command
- Pull research data as markdown → summarize automatically

### Scrapi AI
Free alternative: [scrapi.ai](https://scrapi.ai) — scrapes sites others can't.

---

## Token Usage Tracking

### ccusage
```bash
npx ccusage@latest daily      # Daily report
npx ccusage@latest monthly    # Monthly report
npx ccusage@latest blocks     # 5-hour billing windows
```

### Claude-Code-Usage-Monitor
Real-time terminal monitor with ML-based usage prediction.
```bash
npm install -g claude-code-usage-monitor
```

---

## Keep Mac Awake (for Remote Control)

```bash
# Prevent sleep while Claude Code is running
caffeinate claude remote-control

# Or in background
caffeinate -d &
```

---

## Remote Control

Control your local Claude Code session from your phone.

```bash
claude remote-control   # Start session
# or inside a session:
/rc
```

- Requires Pro or Max plan
- Mac must stay on and terminal must stay open
- Scan QR code with Claude mobile app to connect
