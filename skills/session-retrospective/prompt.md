# Session Retrospective Prompt for Coding Agent

You are not continuing implementation in this task.

Your job is to review the current coding session, reflect on your execution process, summarize what happened, and propose improvements that the human can review before deciding whether to update `AGENTS.md`.

Do not modify source code.
Do not modify `AGENTS.md`.
Do not create commits.
Do not rewrite history.
Do not hide mistakes.

## Goal

Produce a clear retrospective of this session that helps the human understand:

1. What you attempted to do.
2. What you actually changed.
3. What went well.
4. What went wrong or was inefficient.
5. Which instructions, constraints, or project rules were hard to follow.
6. What should be improved in future agent instructions.
7. Whether any changes to `AGENTS.md` are worth considering.

## Required Review Scope

Review the current session using all available evidence, including:

- Git diff
- Git status
- Recent commits, if any
- Files changed
- Tests run
- Test failures or skipped tests
- Build output
- Lint/typecheck output
- Any TODOs, assumptions, or unresolved decisions
- Existing project instructions, especially `AGENTS.md` if present
- Any user instructions given during this session

If evidence is missing, say so explicitly.

## Output Format

# Session Retrospective

## 1. Executive Summary

Summarize the session in 5–10 bullets.

Include:

- Main objective
- Current status
- Whether the task is complete, partially complete, or incomplete
- Biggest implementation outcome
- Biggest risk or uncertainty
- Whether the working tree is clean or dirty
- Whether tests/builds pass

## 2. What I Did

List the concrete actions performed.

Group them by category:

- Planning / investigation
- Code changes
- Test changes
- Documentation changes
- Validation / verification
- Cleanup

For each item, include specific file paths where relevant.

## 3. Evidence

Provide concrete evidence for the claims above.

Include:

- Commands run
- Test results
- Build results
- Important git diff summary
- Any relevant error messages
- Any files that still need review

Do not claim something passed unless it was actually run and passed.

## 4. Timeline of Important Decisions

Reconstruct the main decisions made during this session.

For each decision, include:

- Decision
- Why it was made
- Whether it was correct in hindsight
- Any better alternative

## 5. What Went Well

Identify execution patterns that worked well. Be specific.

## 6. What Went Wrong / Could Be Improved

Be honest and specific.

For each issue, include:

- What happened
- Why it happened
- Impact
- How to prevent it next time

## 7. Instruction Gaps

Identify places where existing project instructions were ambiguous, missing, or easy to misinterpret.

For each gap, include:

- Current ambiguity
- Why it matters
- Suggested clearer instruction
- Whether this belongs in `AGENTS.md`, a task prompt, or a project-specific doc

## 8. Candidate Improvements for `AGENTS.md`

Propose specific changes the human may review.

Rules:

- Do not directly edit `AGENTS.md`.
- Do not propose vague advice.
- Each proposal must be actionable.
- Separate must-have changes from nice-to-have changes.
- Include exact wording you recommend adding or changing.
- Explain why each proposal is useful.

Use this format:

### Proposal A: <short title>

**Priority:** Must-have / Should-have / Nice-to-have

**Problem observed this session:**
...

**Recommended AGENTS.md text:**

```md
...
```

**Why this helps:**
...

**Risk / tradeoff:**
...

## 9. Candidate Session Prompt Improvements

Suggest improvements to the way the human should prompt the agent next time.

Include:

- What the next prompt should make explicit
- What should be forbidden
- What evidence should be required before completion
- What stopping conditions should be defined

## 10. Open Questions for Human Review

List any questions the human should answer before updating `AGENTS.md`.

Do not ask questions that can be answered by inspecting the repo.

## 11. Final Recommendation

Give a clear recommendation:

- Do not update `AGENTS.md`
- Update `AGENTS.md` with small changes
- Update `AGENTS.md` with substantial changes
- Create a separate project workflow doc instead

Explain why.

## Quality Bar

The retrospective should be useful even if the human only reads the executive summary and the AGENTS.md proposals.

Be concrete.
Be honest.
Prefer evidence over opinion.
Do not flatter.
Do not defend mistakes.
Do not invent results.
