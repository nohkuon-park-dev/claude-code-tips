# 01 — Setup & Configuration

Everything you need to configure before starting a project.

---

## Checklist

- [ ] VS Code + Anthropic official Claude Code extension installed
- [ ] `claude auth login` — logged in with Claude.ai account (Pro/Max)
- [ ] Global `~/.claude/CLAUDE.md` created with personal rules
- [ ] Project `.claude/CLAUDE.md` created per repo
- [ ] MCP servers installed (see below)
- [ ] Skills configured (see below)

---

## CLAUDE.md — Project Brain

The `CLAUDE.md` file is Claude's compass. Without it, Claude re-learns your preferences every session.

```bash
/init   # Auto-generates CLAUDE.md for your project
```

### Writing Rules

- **Primacy Bias**: Put the most important rules at the top AND bottom — Claude remembers these best
- **Length**: 200–500 words optimal. Longer = ignored. Link to docs, don't paste them inline
- **Modularize**: For large projects, split into `.claude/rules/workflow.md`, `design.md`, etc.

### Global CLAUDE.md Template (`~/.claude/CLAUDE.md`)

```markdown
# My Global Rules

## Code Quality
- No hardcoding or magic numbers
- No duplicate logic
- Separate environment variables
- Add purpose comments to all functions
- Follow SOLID principles

## Workflow
- Always read a file before editing
- Never delete files without asking
- Never force push to main
- Write tests before implementing (TDD)

## Style
- [Your language/framework preferences here]
```

### Project CLAUDE.md Template

```markdown
# Project: [Name]

## Stack
- Frontend: [e.g., Next.js 14, TailwindCSS]
- Backend: [e.g., Node.js, Prisma, PostgreSQL]
- Package manager: [pnpm / npm / bun]

## Rules
- Use TypeScript strictly (no `any`)
- Components go in `src/components/`
- API routes go in `src/app/api/`
- Always run `pnpm lint` after edits

## Do NOT
- Create new files without asking if one already exists
- Change the DB schema without showing me the migration first
```

---

## MCP Servers — Install All

```bash
# Real-time library docs (prevents outdated code)
claude mcp add --transport http context7 https://mcp.context7.com/mcp

# Browser automation & web app testing
claude mcp add --transport stdio playwright -- npx @playwright/mcp

# GitHub repo management
claude mcp add --transport stdio github \
  -e GITHUB_TOKEN=$(gh auth token) \
  -- npx -y @modelcontextprotocol/server-github

# Persistent memory across sessions
claude mcp add --transport stdio memory \
  -- npx -y @modelcontextprotocol/server-memory

# Step-by-step reasoning for complex tasks
claude mcp add --transport stdio sequential-thinking \
  -- npx -y @modelcontextprotocol/server-sequential-thinking
```

---

## Claude Skills

Skills pre-load your work style so Claude always operates your way.

```
my-skill/
├── SKILL.md          ← Entry point (what it does, when to use it)
└── resources/
    ├── CONFIG.md     ← Preferences, constraints
    ├── MAIN.md       ← Core workflow instructions
    ├── NOTES.md      ← Edge cases, examples
    └── TEXTS.txt     ← Templates, tone references
```

**Skill collections:**
- [anthropics/skills](https://github.com/anthropics/skills) — Official library
- [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) — Community collection
