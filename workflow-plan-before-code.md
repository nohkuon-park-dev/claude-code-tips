# Plan Before Code — 9-Month Claude Code Workflow

> Core principle: **Never write a single line of code before reviewing and approving the plan.**
> Creative work ends at the planning stage. Execution should be boring and mechanical.

---

## The 4-Step Workflow

### Step 1: Research
Claude reads the codebase deeply and organizes findings in `research.md`.

### Step 2: Plan
Claude writes the implementation approach in `plan.md`.

### Step 3: Add Comments (repeat 1–6x)
You personally add correction notes directly inside `plan.md`.

Examples of notes to add:
```
"This should be PATCH, not PUT"
"Use the existing auth middleware here"
"Don't create a new table — add a column to users"
```

Repeat until the plan fits your project exactly.

### Step 4: Implement
Run one command: **"implement it all"**

Claude executes mechanically against the approved plan.

---

## The "Comment Cycle" — Most Important Part

1. Claude writes the plan
2. You open the plan and write correction memos directly in the document
3. Return the modified plan to Claude and ask it to reflect the changes
4. Repeat until the plan is exactly right

**Critical:** Always say **"아직 구현하지 마" (don't implement yet)** at each cycle.
Without this, Claude will start writing code the moment it thinks it understands the task.

---

## On Context Window Length

Some say performance drops past 50% context window.
This author **prefers long sessions** — research through implementation in one session.

The AI's accumulated understanding of your codebase is preserved, leading to better output than starting fresh mid-task.

---

## Key Insight

> "Implementation should be boring."

All creative and architectural decisions happen during planning.
By the time you say "implement it all", there should be no surprises.

---

## Reference

- Original article: [How I Use Claude Code — Boris Tane](https://boristane.com/blog) (Feb 10, 2026)

---

*Source: @ai_jobdori on Threads*
