# Claude Code 200% Utilization — Core Guide

> Solo developer → team-level productivity. The secret: "Project Brain" + "Plan Mode".

---

## 1. CLAUDE.md — Project Brain

The `CLAUDE.md` file at the top of your project is the AI's compass.
With this file, Claude always runs in the right direction without re-explaining context.

**Quick start:**
```bash
/init   # Auto-generates CLAUDE.md for your project
```

Apply your tech stack, code style, and naming rules here.

---

## 2. CLAUDE.md Writing Know-How

### Primacy Bias
AI remembers the **beginning and end** of a document best.
Put the most important rules at the top and bottom.

### Optimal Length: 200–500 words
Too long = content gets ignored.
Reference API docs via links, don't paste them inline.

### Modularize for Large Projects
If rules grow too large, split into separate files:
```
.claude/rules/
  workflow.md
  design.md
  ...
```

---

## 3. Task → Do → Verify Loop

**The #1 cause of AI coding failure = skipping verification.**

If you let Claude keep working without checking results, errors compound into **"Context Rot"** — where the conversation becomes so polluted with bad state that recovery is expensive.

### ✅ Design work
Screenshot results → paste back into Claude → request review and revisions (repeat ~3x)

### ✅ Coding work
Write tests first (TDD) → have Claude iterate until all tests pass

---

## 4. Plan Mode — Most Powerful Feature

Plan Mode makes Claude **design before it codes**.

Claude reads the project structure, asks clarifying questions, and shows you the full implementation plan before touching a single file.

> "1 hour in planning saves 10 hours in building."

Use Plan Mode for any complex task (new features, DB schema, refactors).

---

## 5. Token & Context Management

Tokens and context are like working memory — finite and precious.
Starting a session wrong (bloated system prompts, unnecessary context) can eat 25% before you even begin.

**Useful commands:**
```
/context    # Check current token usage
/compact    # Compress conversation history (great when brainstorming)
```

**Extended Thinking**: For complex tasks, enable this — Claude reasons more carefully and often uses fewer total tokens by getting it right the first time.

---

## 6. Productivity Booster: Multi-Tab & Hooks

### Multi-Tab Workflow
Open 3–4 terminal tabs and run **separate Claude instances in parallel**.
Example: one tab for frontend, one for backend DB setup, one for tests — all running simultaneously.

### Hooks
Set up hooks so Claude **plays a notification sound** when a task finishes.
No need to stare at the screen — go do something else and come back when it's done.

---

## 7. Getting Started Checklist

- [ ] **IDE**: Use VS Code + Anthropic official Claude Code extension
- [ ] **Beginners**: Start with auto-accept mode to build intuition
- [ ] **Advanced**: Use Plan Mode aggressively for non-trivial tasks
- [ ] **Global rules**: Set rules that apply to ALL projects in `~/.claude/CLAUDE.md`
- [ ] **Project rules**: Set project-specific rules in `.claude/CLAUDE.md` at repo root

---

*Source: @aidevsystems on Threads*
