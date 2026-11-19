# Casebook · Six Gates in the Wild

> All cases come from real project execution records (November 2026 sessions). Each entry marks which gate did the work and where an early judgment would have gone wrong. New cases get appended here. (Chinese full version: `casebook.md`.)

## Case 1: Illustration style → skill (all six gates passed — the positive case)

- **Path**: 7 accepted SVG drafts drawn first (earned by use) → style rules distilled into project docs → then packaged as a user-level skill.
- **Even after that, 4 reworks were needed**: out-of-palette colors, stroke-width violations, an undocumented class variant, zero dark-theme drafts. Plus a routing collision with another illustration skill ("draw an illustration" matched both).
- **Takeaway**: even distilling after 7 drafts still produced rework — the frequency gate only sets direction; **the boundary gate (three-part negative boundary) and validation gate (a self-check script) are what stop the bleeding**. Rework isn't a sign of sealing too early — it's part of sealing. But sealing after draft 1 would have meant 7 drafts' worth of rework.

## Case 2: AGENTS.md created and revoked 10 minutes later (wrong form — the negative case)

- **Path**: rules scattered across README/docs/skill → built an AGENTS.md to consolidate → user judged a single-page blog doesn't need one → revoked.
- **Distilled standard**: AGENTS.md suits projects with "many commands + many prohibitions + multiple collaborators" (like a reasonable 217-line one in a bigger repo); a solo single-page project is context pollution.
- **Takeaway**: the question was never "distill or not" but "distill into WHAT". **The form ladder gets misused more often than the yes/no gate.** The revoked knowledge wasn't lost — it went into the work log first. That is level 1 done right.

## Case 3: Full machine migration → skill (bug-forged)

- **Path**: one real migration run (7 bots / 2 skills) → 6 genuine bugs found in the original approach (nonexistent flags, mapping logic guaranteed to fail, dropped script bundles, hardcoded UUIDs…) → fixed first, then packaged, validated, and round-trip tested.
- **Takeaway**: all 6 bugs **could only surface in real execution**; zero were predictable at design time. Design-first would have shipped all 6 bugs inside the skill. This is the hardest evidence for "earned by use": the case sealed after just 1 execution — because the execution itself was already full of scars, and scars are evidence (hence the high-risk exception clause).

## Case 4: One essay → a prompt-upgrading skill (reading-distilled, gates partially waived)

- **Path**: read a methodology essay → verified a video summary's deviations from the source → packaged as a bilingual skill → published to GitHub → installed into 3 projects.
- **Takeaway**: this one fails the "≥2 executions" rule. Its promotion evidence isn't an execution record but **the user's explicit intent to consume the method repeatedly** (installing it in three projects). The judgment honestly marked it as "reading-distilled: frequency gate replaced by explicit user commitment to reuse."

## Case 5: A user-level skill synced across 3 copies (the maintenance gate's price, on record)

- **Facts**: one illustration skill kept a user-level master plus two project-level copies; any style-rule change required syncing 3 locations via `diff -rq`. Worse, one project's .gitignore distributes the copy while another's doesn't — same label "project-level", different distribution behavior.
- **Takeaway**: this bill was never priced at sealing time; it was paid afterward. The maintenance gate's "count sync points BEFORE sealing" rule comes straight from this case. **Number of skills × copies = the change-cost matrix — put that matrix on the table before sealing anything.**

## Case 6: Data mirror out of sync with the page (the cost of NOT distilling)

- **Facts**: blog page data is inline-first with a mirror data file; the two drifted (an entry existed in the page but not the mirror). Not fixed this time.
- **Verdict a gate would have issued**: this is a "dual source of truth" structural problem. The right landing is **a single-source-of-truth declaration in the docs + a known-drift list** — not a skill. The sync action itself is a discipline problem a level-2 doc already solves.

## Ledger (post-encapsulation rework)

> Per the judgment workflow's step 4: any rework within 30 days of encapsulation gets one line here. Empty = no premature-encapsulation evidence so far.

| Date | Skill | Rework content | Sealed too early? |
|---|---|---|---|
| (none yet) | | | |
