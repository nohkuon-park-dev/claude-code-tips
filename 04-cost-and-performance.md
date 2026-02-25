# 04 — Cost & Performance

Stay on Pro. Avoid burning tokens unnecessarily.

---

## Token-Saving Habits

### 1. Save to `memory.md` Before Context Fills Up

Before the conversation hits the limit:
```
"Save all progress, decisions, and current state to memory.md"
```
At next session start:
```
"Read memory.md and resume from where we left off"
```
**Why:** Without this, Claude re-reads the entire codebase from scratch — burning tokens just to re-understand what it already knew.

---

### 2. Use Read/Edit Instead of Python Scripts

Claude habitually writes Python scripts for bulk tasks. Stop it.

| Approach | Steps | Risk |
|----------|-------|------|
| Python script | Write (tokens) → Run (tokens) → Parse (tokens) → **Debug if fails (tokens explode)** | High |
| Read/Edit | Read (tokens) → Edit (tokens) | Low |

For most tasks, Read/Edit is faster, cheaper, and safer.

---

### 3. Context Window Commands

```
/context    # Check current token usage %
/compact    # Compress conversation history (use when brainstorming)
```

Starting a session with a bloated system prompt can consume 25% of context before you've typed a word.

---

### 4. Extended Thinking

For complex tasks, enable Extended Thinking.
Claude reasons more carefully → gets it right the first time → fewer total tokens spent on corrections.

---

### 5. Long Sessions > Multiple Short Sessions

Contrary to popular advice (50% context = restart), **long sessions preserve accumulated understanding**.

Research → plan → implement in **one session** = Claude retains full project context.
Restarting mid-task = Claude rebuilds understanding from scratch = wasted tokens.

---

## Usage Tracking

```bash
# Daily usage report
npx ccusage@latest daily

# Monthly usage report
npx ccusage@latest monthly

# 5-hour billing block breakdown
npx ccusage@latest blocks
```

---

## MCP Token Cost

MCP servers add tokens to every message (server descriptions are injected into context).
Only install MCPs you actually use. Unused MCPs = free token tax on every request.

---

## Summary Checklist

- [ ] Save progress to `memory.md` before context limit
- [ ] Use Read/Edit over Python scripts for file operations
- [ ] Run `/compact` when context feels bloated
- [ ] Check `/context` periodically on long sessions
- [ ] Only keep MCPs you actively use
- [ ] Use Extended Thinking for complex architecture decisions
