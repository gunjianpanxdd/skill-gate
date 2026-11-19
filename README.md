# skill-gate

> A decision gate for one question every agent team eventually faces:
> **"Should this become a skill?"**
> The default answer is **no** — and this skill makes that answer enforceable.

Skills are earned through use, not designed upfront. `skill-gate` turns that
principle into a runnable procedure: a seven-level **distillation ladder** plus
six verifiable **gates** that a process must pass before it gets encapsulated —
and seven concrete landing spots for everything that shouldn't.

## The problem it solves

Without a gate, two failure modes dominate:

1. **Premature encapsulation** — a process gets sealed into a skill after one
   execution, then needs 4 reworks (palette violations, undocumented variants,
   routing collisions with neighboring skills).
2. **Wrong-form encapsulation** — the knowledge gets persisted, but in the wrong
   container: a 217-line AGENTS.md on a single-page blog (created, revoked 10
   minutes later), or a "skill" that is really just relocated instructions with
   zero machine-checkable rules.

## How it decides

**Seven-level ladder** (climb one level at a time, never skip):

```
0 record nothing → 1 note → 2 docs → 3 validation script
→ 4 skill → 5 persistent context (AGENTS.md) → 6 workflow automation
```

**Six gates** (all must pass; stop at the first failure):

| Gate | One-line criterion |
|---|---|
| Frequency | Really executed ≥2 times (or once for high-risk destructive ops), with artifacts as evidence |
| Stability | No step changes between the last two executions |
| Boundary | Description supports "what it does + when to use + what it does NOT cover" |
| Validation | At least one rule machine-checkable by script — otherwise it's instruction relocation, not encapsulation |
| Maintenance | Future sync points counted and justified (skills × copies = change-cost matrix) |
| Triggering | The agent will recall it at the right moment and no other skill fires first |

**Output**: a judgment card (verdict + per-gate evidence + demotion note),
confirmed by the user before any file is created. Rework within 30 days of
encapsulation is logged in the casebook ledger as "sealed too early" evidence,
which automatically raises the frequency bar for future judgments.

## Structure

```
skill-gate/
├── SKILL.md                    # Skill entry (Chinese) — iron rules, ladder, gates, workflow, anti-patterns
├── SKILL.en.md                 # Full English mirror of the skill entry
└── references/
    ├── casebook.md             # Six real post-mortems + rework ledger (Chinese)
    └── casebook-en.md          # English version of the casebook
```

## Install

Copy the `skill-gate/` folder into your agent's skills directory:

- WorkBuddy (user scope): `~/.workbuddy/skills/skill-gate/`
- Claude Code: `~/.claude/skills/skill-gate/`

Then trigger it with things like *"把这个流程做成 skill"*, *"要不要沉淀个 skill"*,
*"should this be a skill?"*, or *"solidify this workflow"*. (`SKILL.md` is the
entry file; `SKILL.en.md` is the English mirror for reference.)

## Closing line

> First time: do it. Second time: note it. Third time: script it.
> Fourth time — with artifacts from all of the above: now talk about a skill.

## License

MIT
