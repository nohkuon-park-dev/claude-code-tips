# Token Saving Tips — Stay on Pro, Skip Max

> A few habits that keep Claude Pro quota sufficient — no need to upgrade to Max.

---

## Tip 1: Save to `memory.md` Before Context Fills Up

Before the conversation hits the context limit and stops:
1. Ask Claude to save all work progress to `memory.md`
2. Remind Claude to reload it at the start of the next session

**Why:** Without this, Claude re-reads the entire codebase from scratch at the next session — burning tokens just to re-understand what it already knew.

```
"Before we continue, save everything we've done so far to memory.md"
```

---

## Tip 2: Stop Claude from Writing Python Scripts for Everything

Claude habitually reaches for Python scripts during bulk tasks.
**Restrain this.** Read/Edit tools are far more token-efficient for most operations.

### Python Script approach — expensive:
1. Write script code → (tokens)
2. Run with Bash → (tokens)
3. Parse output results → (tokens)
4. **If it fails → debugging explodes token usage**

### Read/Edit approach — cheap:
1. Read to confirm → (tokens)
2. Edit to modify → (tokens)

**Done.** No script, no Bash, no debug loop.

> "Simple Read/Edit consumes far fewer tokens. And if a Python script fails or produces unexpected results, token usage explodes during debugging."

---

## Summary

| Habit | Token Impact |
|-------|-------------|
| Save progress to `memory.md` before context limit | Saves re-reading tokens next session |
| Use Read/Edit instead of Python scripts | 3-step process → 2-step process, no debug risk |

---

*Source: @gunny__park on Threads*
