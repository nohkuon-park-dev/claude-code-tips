# 02 — Workflows

Proven patterns for getting the best output from Claude Code.

---

## The Golden Rule

> **Never write a single line of code before reviewing and approving the plan.**
> Creative work ends at planning. Execution should be boring and mechanical.

---

## Core Loop: Plan → Do → Verify

### Step 1: Research
Claude reads the codebase deeply → saves findings to `research.md`

### Step 2: Plan
Claude writes implementation approach in `plan.md`

### Step 3: Comment Cycle (repeat 1–6x)
You add correction notes directly inside `plan.md`:
```
"This should be PATCH not PUT"
"Reuse the existing auth middleware"
"Don't create a new table — add a column to users"
```
**Always say "don't implement yet" until the plan is exactly right.**

### Step 4: Implement
```
"implement it all"
```
Claude executes mechanically. No surprises.

---

## Plan Mode

Plan Mode forces Claude to design before coding.

- Claude reads project structure, asks questions, shows full plan
- Use for: new features, DB schema changes, refactors, anything 3+ steps
- **"1 hour in planning saves 10 hours in building."**

---

## Task → Do → Verify Loop

The #1 cause of AI coding failure = **skipping verification**.

Unchecked errors compound into **"Context Rot"** — polluted context that's expensive to recover from.

| Task type | Verification method |
|-----------|-------------------|
| Design | Screenshot → paste to Claude → request revisions (×3) |
| Code | Write tests first (TDD) → Claude iterates until all pass |
| Any | Ask: "Would a staff engineer approve this?" |

Never mark a task complete without proving it works.

---

## Task Management Files

```
tasks/
├── todo.md       ← checklist of current work items
├── decisions.md  ← all important decisions (never re-discuss resolved things)
└── lessons.md    ← patterns learned from mistakes
```

**Workflow:**
1. Write plan to `tasks/todo.md` with checkable items
2. Verify plan before implementation starts
3. Mark items complete as you go
4. After any correction: update `tasks/lessons.md`
5. Review `tasks/lessons.md` at every session start

---

## Multi-Agent Team Mode

For large features: run a **Leader + Workers** structure.

### Rules
- **Leader thinks, Workers build** — Leader never writes code itself
- **Leader holds the full plan** in its context window — the only agent that remembers everything
- **Wipe workers between tasks** — fresh context = better output, zero accumulated confusion
- **One task per worker** — focused execution, no context bleed
- **Log all decisions** to `decisions.md` immediately

### Workflow
```
1. Leader kicks off research
2. Leader assigns 4–5 workers to parallel research tasks
3. Workers submit → Leader consolidates → creates 3 proposals
4. You pick one → new workers start implementation in parallel
5. Review worker checks output → final result delivered
```

### Starter prompt
```
"If the leader provides refined context, replace team members automatically
and route tasks through the workflow autonomously."
```

---

## Workflow Principles

| Principle | Rule |
|-----------|------|
| Plan first | Enter plan mode for ANY task with 3+ steps |
| Stop and re-plan | If something goes sideways, stop immediately |
| Self-improvement | After any correction, update `tasks/lessons.md` |
| Verification | Never call done without proof it works |
| Elegance | For non-trivial changes: "is there a more elegant way?" |
| Bug fixing | Given a bug report: just fix it. No hand-holding needed |
| Simplicity | Make every change as simple as possible. Minimal code impact |
