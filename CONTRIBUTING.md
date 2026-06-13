# Contributing

Thank you for helping improve coding-agent reliability.

This repo is not a general prompt dump. Contributions should be based on real or plausible agent failure modes and should help humans prevent, detect, or recover from those failures.

## Good contributions

A good contribution usually includes:

- a clear failure mode
- when the skill should be used
- what evidence the agent must inspect
- what actions are allowed or forbidden
- a copy-paste prompt
- a checklist
- at least one example of good output or a common bad output

## Skill acceptance criteria

Before opening a PR, check that the skill:

- has a narrow purpose
- has a clear trigger condition
- defines `Must do` and `Must not do`
- avoids vague advice
- requires evidence for completion claims
- preserves human review authority
- avoids encouraging broad, unsafe mutation

## Suggested skill folder format

```text
skills/<skill-name>/
  SKILL.md
  prompt.md
  checklist.md
  examples/
    good-output.md
    weak-output.md
```

## Style guide

Use direct, practical language.

Prefer:

```text
Do not claim tests passed unless you actually ran them and they passed.
```

Avoid:

```text
Try to be careful with testing.
```

## Pull request title format

```text
Add <skill-name> skill
Improve <skill-name> checklist
Document <failure-mode> pattern
```
