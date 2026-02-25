# Claude Code Tips & Tricks

A curated collection of tips, tricks, and best practices for getting the most out of Claude Code.

---

## Table of Contents

- [Getting Started](#getting-started)
- [Core Workflow Tips](#core-workflow-tips)
- [Slash Commands](#slash-commands)
- [CLAUDE.md Tips](#claudemd-tips)
- [MCP Servers](#mcp-servers)
- [Hooks](#hooks)
- [Remote Control](#remote-control)
- [Cost Management](#cost-management)
- [Power User Tips](#power-user-tips)

---

## Getting Started

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# Login with your Claude.ai account (required for Pro/Max plans)
claude auth login

# Start a session
claude
```

---

## Core Workflow Tips

- **Be specific**: The more context you give, the better the output. Instead of "fix the bug", say "fix the null pointer error in auth.ts line 42".
- **Use `/clear`** to reset context when switching tasks — keeps the model focused.
- **Let Claude read first**: Always have Claude read existing files before making edits to avoid overwriting logic.
- **Break big tasks into smaller steps**: Ask for one thing at a time instead of "build an entire app".
- **Use `--continue`** in headless mode to resume a previous conversation.

```bash
claude -p "Add error handling to the login function" --continue
```

---

## Slash Commands

| Command | Description |
|---------|-------------|
| `/help` | Show all available commands |
| `/clear` | Clear conversation history |
| `/compact` | Compress history to save context |
| `/model` | Switch AI model |
| `/mcp` | Manage MCP servers |
| `/config` | Open settings |
| `/remote-control` or `/rc` | Enable Remote Control for mobile access |
| `/rename <name>` | Rename current session |
| `/mobile` | Show QR code to download Claude mobile app |
| `/login` | Login to Claude.ai |
| `/cost` | Show token usage and cost for current session |

---

## CLAUDE.md Tips

`CLAUDE.md` is automatically loaded by Claude Code at startup. Use it to set persistent instructions for your project.

**Global** (`~/.claude/CLAUDE.md`): Applies to all projects.
**Project** (`.claude/CLAUDE.md` in repo root): Applies to that project only.

### Example CLAUDE.md

```markdown
# Project Rules

- Always use TypeScript, never plain JavaScript
- Use pnpm, not npm or yarn
- Write tests for every new function
- Keep components under 200 lines
- Use Korean for comments and commit messages
```

### Tips
- Keep it concise — Claude reads this every session, so long files waste tokens.
- Use it to enforce code style, tech stack choices, and naming conventions.
- Add `# Do NOT` sections for things Claude tends to do wrong in your project.

---

## MCP Servers

MCP (Model Context Protocol) servers extend Claude Code with external tools and data sources.

```bash
# Add an HTTP MCP server
claude mcp add --transport http <name> <url>

# Add a stdio MCP server
claude mcp add --transport stdio <name> -- npx -y <package>

# List installed MCPs
claude mcp list

# Remove an MCP
claude mcp remove <name>
```

### Recommended MCP Servers

| Name | Package | Purpose |
|------|---------|---------|
| context7 | HTTP: `https://mcp.context7.com/mcp` | Real-time library documentation |
| playwright | `@playwright/mcp` | Browser automation & testing |
| github | `@modelcontextprotocol/server-github` | GitHub repo management |
| memory | `@modelcontextprotocol/server-memory` | Persistent memory across sessions |
| sequential-thinking | `@modelcontextprotocol/server-sequential-thinking` | Step-by-step planning |

---

## Hooks

Hooks let you run shell commands automatically in response to Claude Code events.

```json
// ~/.claude/settings.json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          { "type": "command", "command": "npm run lint --fix" }
        ]
      }
    ]
  }
}
```

### Hook Events
- `PreToolUse` — runs before a tool call
- `PostToolUse` — runs after a tool call
- `Notification` — runs when Claude sends a notification
- `Stop` — runs when a session ends

---

## Remote Control

Control your local Claude Code session from your phone or another device.

```bash
# Start Remote Control
claude remote-control

# Or enable inside a session
/rc
```

- Requires **Pro or Max plan**
- Your Mac must stay on and the terminal must stay open
- Reconnects automatically after short network drops
- Scan the QR code with the Claude mobile app to connect

### Keep Your Mac Awake

```bash
# Prevent sleep while Remote Control is running
caffeinate claude remote-control
```

---

## Cost Management

```bash
# Check usage for current session
/cost

# View daily usage report
npx ccusage@latest daily

# View monthly usage report
npx ccusage@latest monthly

# View usage by billing block (5-hour windows)
npx ccusage@latest blocks
```

---

## Power User Tips

### Headless / Automation Mode

```bash
# Run Claude non-interactively (great for CI/CD)
claude -p "Run tests and fix any failures" --allowedTools "Bash,Edit,Read"

# Output as JSON
claude -p "Summarize this codebase" --output-format json

# Stream output in real-time
claude -p "Refactor auth.ts" --output-format stream-json
```

### Useful Aliases

Add to your `~/.zshrc` or `~/.bashrc`:

```bash
alias cc="claude"
alias ccp="claude -p"
alias ccr="caffeinate claude remote-control"
```

### Prevent Accidental Overwrites

In your CLAUDE.md:
```markdown
- Always read a file before editing it
- Never delete files without asking first
- Never force push to main
```

### Multi-file Context

Paste file paths directly in your message — Claude will read them automatically. Or use:
```
Please read src/auth.ts, src/middleware.ts, and tests/auth.test.ts before making changes.
```

---

## Resources

- [Claude Code Official Docs](https://code.claude.com/docs)
- [Anthropic Skills Repository](https://github.com/anthropics/skills)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [ccusage — Token Usage Tracker](https://ccusage.com)
