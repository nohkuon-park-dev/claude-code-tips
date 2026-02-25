# Claude Skills — Make AI Think Like You

> Top AI users don't just chat. They build Skills that pre-load their work style,
> thinking patterns, and domain knowledge so Claude always operates their way.

---

## Why Skills Beat Chatting

Every time you start a new chat, you re-explain your context, preferences, and standards.
With Skills, Claude already knows:
- How you work
- How you think
- What you need from each type of request

The output quality difference is incomparable.

> "Even non-developers are using Claude Code — because of Claude Skills."

---

## Skill File Structure

```
my-skill/
├── SKILL.md          ← Entry point: tells Claude what this skill does and when to use it
└── resources/
    ├── CONFIG.md     ← Settings, preferences, constraints
    ├── MAIN.md       ← Core instructions and workflow
    ├── NOTES.md      ← Edge cases, gotchas, examples
    └── TEXTS.txt     ← Reference material, templates, tone examples
```

**SKILL.md** is the most important file — Claude reads it first to understand the skill's purpose and activation conditions.

---

## How to Create a Skill

1. Create a folder under `.claude/skills/` or `~/.claude/skills/`
2. Add a `SKILL.md` with:
   - What this skill does
   - When Claude should use it
   - Any required inputs
3. Add supporting files in `resources/` as needed

### Minimal SKILL.md example

```markdown
# My Writing Style

## When to use
Apply this skill whenever writing emails, posts, or documents.

## Style rules
- Tone: direct, confident, no fluff
- Structure: conclusion first, then reasoning
- Length: as short as possible without losing meaning

## Reference
See resources/TEXTS.txt for examples of my past writing.
```

---

## Skill Collections (Reference)

| Repo | Description |
|------|-------------|
| [anthropics/skills](https://github.com/anthropics/skills) | Official Anthropic skill library — marketing, technical, enterprise |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | Community collection for real-world usage, subagents, and Claude Code commands |

---

## Good Domains for Custom Skills

- **Marketing**: tone of voice, campaign brief templates, copy review criteria
- **Business**: decision frameworks, meeting summary format, proposal structure
- **Design**: design system rules, review checklist, feedback style
- **Planning**: project breakdown format, risk assessment criteria
- **Code review**: standards checklist, comment style, naming conventions

---

## Key Insight

> Pre-load your thinking into Claude once → get on-brand, on-style output every time,
> without re-explaining yourself in every conversation.

---

*Source: @superb.sup on Threads*
