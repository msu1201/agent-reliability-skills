# Skill: Session Retrospective

## Purpose

Ask a coding agent to review its own current session using repository evidence, identify execution issues, and propose instruction improvements for human review.

## Failure modes this skill addresses

- Completion without evidence
- Hidden uncertainty
- Repeated failed commands
- Scope drift
- Unclear handoff
- Unreviewable AGENTS.md changes

## When to use

Use at the end of a coding-agent session, before merging, committing, or updating project instructions. Also use after repeated agent mistakes or when the human wants to decide whether AGENTS.md should change.

## Inputs / evidence required

The agent should inspect, where available:

- `git status`
- `git diff`
- recent commits
- changed files
- tests/builds/lint/typecheck output
- error logs
- project instructions such as `AGENTS.md`
- user instructions from the session

## Agent must do

- State what evidence was inspected.
- Separate facts from opinions.
- Identify what went well and what went wrong.
- Propose AGENTS.md changes only as review candidates.
- Say when evidence is missing.

## Agent must not do

- Do not modify source code.
- Do not modify AGENTS.md.
- Do not create commits.
- Do not claim tests passed unless they actually passed.
- Do not hide mistakes or uncertainty.

## Output format

Use the structure in `prompt.md`: executive summary, what changed, evidence, decisions, what went well, what went wrong, instruction gaps, candidate AGENTS.md improvements, prompt improvements, open questions, and final recommendation.

## Human review checklist

- [ ] Does it identify the task status clearly?
- [ ] Does it cite actual commands or missing evidence?
- [ ] Does it distinguish completed work from incomplete work?
- [ ] Does it include concrete AGENTS.md proposal text?
- [ ] Does it avoid directly editing project instructions?
- [ ] Does it avoid defensive or vague language?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
