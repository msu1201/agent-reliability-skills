# AGENTS.md Improvement Review Prompt

You are reviewing whether project agent instructions should change.

Do not edit `AGENTS.md`.
Do not modify code.
Produce only reviewable proposals.

## Inputs to inspect

- Current `AGENTS.md`, if present
- Recent session retrospective, if available
- User instructions from the session
- Evidence of repeated or high-impact agent failure
- Current project workflow docs, if relevant

## Output

# AGENTS.md Improvement Review

## 1. Summary Recommendation

Choose one:

- Do not update AGENTS.md
- Update AGENTS.md with small changes
- Update AGENTS.md with substantial changes
- Put this in task prompts instead
- Create a separate workflow doc

Explain why.

## 2. Observed Failure Patterns

For each pattern:

- What happened
- Evidence
- Impact
- Whether it is repeated or one-off

## 3. Proposal List

### Proposal A: <short title>

**Priority:** Must-have / Should-have / Nice-to-have

**Belongs in:** AGENTS.md / task prompt / project doc / not worth preserving

**Problem:**

...

**Recommended wording:**

```md
...
```

**Why this helps:**

...

**Tradeoff:**

...

## 4. Rejected Ideas

List rules that should not be added and why.

## 5. Final Suggested Patch

If updates are recommended, provide a single consolidated Markdown snippet the human can copy.

## Rules

Do not directly edit files.
Do not add vague advice.
Do not turn one-off task context into permanent repo policy.
Prefer fewer, stronger instructions.
