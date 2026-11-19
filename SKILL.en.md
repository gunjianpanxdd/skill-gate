---
name: skill-gate
description: A decision gate for judging whether a recurring process should be distilled into a skill, and which form it should take. When a project hits repeated workflows, hard-won fixes, or a "should we codify this?" moment, run the six gates before building anything — the default answer is NO; promotion requires evidence; prefer demotion over premature encapsulation. This skill should be used when the user asks to turn a process into a skill, asks to persist or solidify a workflow, or when the same operation is observed being executed for the second time or more (trigger phrases: "做成skill", "沉淀skill", "封装skill", "固化流程", "should this be a skill"). Do NOT trigger when a skill already exists and only needs to be followed, when auditing or editing an existing skill (that is expert-manager's job), or for clearly one-off tasks.
agent_created: true
---

# skill-gate · The Distillation Gate

## Iron Rules (read these first)

1. **Skills are earned through use, not designed upfront.** A process that has never been executed for real at least twice does not deserve encapsulation. Every "this should become a skill" impulse during a first execution gets demoted to a single note.
2. **The default answer is "don't distill."** The six gates are a valve, not a factory. Failing any single gate means landing on a lower form — not patching the argument and climbing anyway.
3. **Choosing the wrong form ≈ not distilling at all.** A 217-line AGENTS.md on a single-page blog, two skills whose trigger conditions overlap, a skill that merely relocates instructions with zero validation — all negative assets. Better a note than a premature skill.

## The Distillation Ladder (seven landing spots, low to high)

| Level | Form | Promotion evidence (all required) | Real case |
|---|---|---|---|
| 0 | Record nothing | One-off; context is sufficient | — |
| 1 | Project note / log | Possibly needed a second time | Log the color-token sync risk first |
| 2 | Docs file | Team/cross-session readers; rules have stabilized | An illustration style guide doc |
| 3 | Validation script | Machine-checkable hard rules (palette / stroke / format / exit codes) | An SVG style self-check script |
| 4 | **Skill** | Levels 2+3 stable + all six gates passed | An illustration skill distilled only after 7 accepted drafts |
| 5 | Persistent context (AGENTS.md) | Many commands + many prohibitions + multiple collaborators — all three, no exceptions | A single-page blog's AGENTS.md, revoked 10 minutes after creation |
| 6 | Workflow automation | Steps fully fixed, order immutable, scheduled/unattended runs | — |

**Ladder discipline**: capabilities only climb one level at a time, never skip. Before proposing a skill, check "have levels 2 and 3 been done?"

## The Six Gates (all must pass before building a skill)

| # | Gate | Criterion (verifiable, not vibes) | Demotion if failed |
|---|---|---|---|
| 1 | **Frequency** | Really executed ≥2 times; or once for a high-risk destructive operation. Evidence: execution records, logs, artifacts | Stay at level 1 notes |
| 2 | **Stability** | No step changes between the last two executions. Codifying a drifting rule = instant obsolescence | Level 1; wait for stability |
| 3 | **Boundary** | The description supports a three-part statement: "what it does + when to use (with real trigger words) + what it does NOT cover". **No negative boundary = routing collision with existing skills**; check the existing skill list first | Level 2 doc, or merge into an existing skill |
| 4 | **Validation** | At least one rule is machine-checkable via script/code (format, counts, palette, exit codes). **Zero checkable rules = instruction relocation, not capability encapsulation** | Level 2 doc (instructions in a doc work just as well) |
| 5 | **Maintenance** | Count future sync points: user-level master + N project-level copies, plus each project's gitignore distribution behavior. ≥3 sync points needs a strong justification | Narrow to a single project-level copy |
| 6 | **Triggering** | The agent will recall it at the right moment: the description contains words real users actually say; no other skill fires first in the same scenario | Rename / reword, then re-judge |

## Judgment Workflow

```text
1. Gather evidence: how many times has this been done? Any artifacts/logs?
   Did the steps change since last time?
2. Run the six gates (in order 1→6; stop at the first failure — no wishful
   thinking down the line)
3. Output the judgment card (below); build nothing until the user confirms
4. If any rework happens within 30 days of encapsulation (spec edits /
   validation fixes), log it in the casebook ledger — it is evidence of
   "sealed too early"; raise the frequency gate next time
```

**Judgment card format** (output for user confirmation; do not create files directly):

```text
Verdict: <level X, form name>
Evidence: frequency=...; stability=...; boundary=...; validation=...; maintenance=...; trigger=...
Demotion note: weakest gate is ...; if the user insists on promotion, the risk is ...
```

## Anti-Patterns (block on sight)

| Anti-pattern | Signal | Countermeasure |
|---|---|---|
| **Design a pile upfront** | Imagining the skill directory structure before the task is done | Finish the task first; artifacts go to level 1 |
| **Instruction relocation** | Content is all natural-language "do this, then that" — no scripts, no validation | Demote to level 2 doc |
| **Routing collision** | Two skills' "when to use" overlap | Block at the boundary gate; draw negative boundaries first |
| **Context pollution** | Creating persistent AGENTS.md for a solo small project | Ladder level 5's "all three or none" rule |
| **Sealed too early** | Spec changed twice within a week of encapsulation | Log in the rework ledger; demote to level 1/2 |

## Resources

- `references/casebook.md` — Real case library: six post-mortems from actual projects (all gates passed / wrong form / bug-forged / reading-distilled / sync cost / the cost of NOT distilling) + the post-encapsulation rework ledger. Read this first when a judgment is uncertain; append one entry after each completed judgment or discovered premature-encapsulation rework.

## Closing Line

> First time: do it. Second time: note it. Third time: script it. Fourth time — with artifacts from all of the above: now talk about a skill.
> **An encapsulation's benefit must be priced in change cost — any encapsulation that cannot answer "how many files does the next change touch" is debt owed to your future self.**
