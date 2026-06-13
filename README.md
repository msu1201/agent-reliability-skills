# Agent Reliability Skills

**Failure patterns and reusable skills for coding agents.**

Coding agents are powerful, but they fail in predictable ways: they drift in scope, reimplement existing work, skip validation, over-edit unrelated files, and produce handoffs that are hard for humans to review.

This repo turns those failure modes into reusable **skills**: structured prompts, checklists, and workflow contracts that help humans prevent, detect, and recover from common coding-agent failures.

> This is not a prompt collection. It is a reliability layer for coding agents.

## Core idea

Every skill follows the same reliability loop:

```text
Failure mode → Prevention → Detection → Recovery → Review evidence
```

A skill is more than a prompt. A skill defines:

- when to use it
- what evidence the agent must inspect
- what the agent must do
- what the agent must not do
- what output format is required
- what the human should review
- what common failure modes it addresses

## Who this is for

This repo is for people using coding agents such as Codex, Claude Code, Cursor agents, Devin-style agents, or custom agent runners on real engineering work.

It is especially useful if you care about:

- smaller review surfaces
- evidence-based completion reports
- safer mutation boundaries
- less scope creep
- fewer false “done” claims
- better AGENTS.md / project instruction maintenance
- repeatable agent handoff workflows

## Initial skills

### Before implementation

| Skill | Purpose |
| --- | --- |
| [`no-reimplementation-check`](skills/no-reimplementation-check/SKILL.md) | Prevent agents from rebuilding functionality that already exists. |
| [`scope-control`](skills/scope-control/SKILL.md) | Keep an agent inside a PR-sized task boundary. |
| [`safe-mutation-gate`](skills/safe-mutation-gate/SKILL.md) | Require explicit safety checks before destructive or broad changes. |

### Before handoff

| Skill | Purpose |
| --- | --- |
| [`evidence-based-closeout`](skills/evidence-based-closeout/SKILL.md) | Make the agent prove what changed and what was validated. |
| [`session-retrospective`](skills/session-retrospective/SKILL.md) | Ask the agent to review its own session and propose instruction improvements. |
| [`agents-md-improvement-review`](skills/agents-md-improvement-review/SKILL.md) | Convert repeated agent failures into reviewable AGENTS.md changes. |

## Recommended workflow

Use these skills as small workflow gates rather than one giant instruction block.

```text
1. Start task
   → scope-control
   → no-reimplementation-check

2. Before risky edits
   → safe-mutation-gate

3. Before handoff
   → evidence-based-closeout

4. After a meaningful session or repeated failure
   → session-retrospective
   → agents-md-improvement-review
```

## Repository structure

```text
skills/
  <skill-name>/
    SKILL.md        # workflow contract
    prompt.md       # copy-paste prompt
    checklist.md    # human/agent review checklist
    examples/       # good and weak outputs

templates/
  AGENTS.md
  TASK_PROMPT.md
  PR_SUMMARY.md
  SESSION_RETRO.md

docs/
  skill-format.md
  failure-taxonomy.md
  philosophy.md
```

## How to use a skill

Copy the `prompt.md` for the skill into your coding agent session.

For stronger results, also keep the `SKILL.md` nearby as a durable workflow contract in your project docs or agent instruction system.

Example:

```text
Use skills/session-retrospective/prompt.md at the end of this coding session.
Do not modify files. Produce only the retrospective.
```

## Design principles

1. **Evidence over vibes** — completion claims require commands, diffs, logs, or explicit missing evidence.
2. **Small review surfaces** — agents should avoid broad rewrites unless explicitly requested.
3. **No hidden uncertainty** — agents should state assumptions, missing evidence, and unresolved risks.
4. **Prevention before recovery** — the best failure mode is the one caught before mutation.
5. **Human keeps final authority** — skills propose changes; humans decide whether to merge or update instructions.

## Contributing

Contributions are welcome, especially:

- real coding-agent failure cases
- reusable prevention skills
- detection checklists
- recovery prompts
- before/after examples
- AGENTS.md instruction patterns that improved reliability

Please start with [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

MIT. See [`LICENSE`](LICENSE).
