# Claude Code Team Mode — Multi-Agent Workflow

> Run 5 Claude instances simultaneously. Senior developer feel, 24/7 availability.
> The secret: an optimized team structure where a Leader directs and workers execute.

---

## Tip 1: Never Let the Director Write Code

The team has one **Leader** whose only job is thinking and planning.

- The Leader holds the **entire battle plan in its main context window**
- It is the only agent that remembers the full picture across the session
- All code/file context flows through the Leader first
- **The Leader assigns tasks to team members one by one** — it never codes itself

> "What have I done so far?" — only the Leader knows the answer.

---

## Tip 2: Write Important Decisions to a File

**Never trust Claude's memory alone.**

- Claude auto-compresses old content as context grows long
- Important decisions get silently summarized away with each compression
- Record all critical decisions in a dedicated file immediately

```
decisions.md   ← always write important choices here
```

> "Don't repeat the same discussion 3 times. You'll regret it."

---

## Tip 3: Wipe Team Members and Start Fresh (Repeat)

Team members finish their task → wipe their context → start fresh.

- After completing a task, **create a new clean team member instance**
- Fresh context = faster, more accurate, no accumulated confusion
- Always start the next task with a clean slate

**The result:** features completed with zero bugs, fully automated.

---

## Simple Workflow Example

```
1. I start as team leader
2. Leader kicks off initial research
3. Leader spawns 4 team members → each runs 5–8 parallel research tasks per topic
4. After research, leader compiles ~30 data points simultaneously
5. Leader aggregates research into real-time reference data
6. Team members submit results → leader synthesizes 3 proposals → I pick one
7. 4 new team members start implementation in parallel
8. ~30 sub-tasks run concurrently → done in ~5 minutes
9. A review agent checks the output
10. 30 minutes later: consolidation + final review → final result delivered to me
```

---

## Starter Prompt

Use this to kick off the automated workflow:

```
"If the leader provides refined context, replace team members automatically with AI
and route tasks through the workflow autonomously."
```

---

## Key Principles

| Rule | Why |
|------|-----|
| Leader thinks, workers build | Clean separation of reasoning and execution |
| Log decisions to `decisions.md` | Prevents re-discussing resolved choices |
| Wipe workers between tasks | Fresh context = better output, fewer errors |
| One task per worker | Focused execution, no context bleed |

---

*Source: @ddg.kang on Threads*
