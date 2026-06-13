# Philosophy

Coding agents are becoming capable enough to make large changes quickly. That creates a new problem: humans need better ways to steer, constrain, review, and recover agent work.

This repo treats agent work as an engineering workflow, not a magic prompt.

## The problem

Coding agents often fail in predictable ways:

- They solve a larger problem than requested.
- They reimplement existing code instead of inspecting it.
- They claim success without validation evidence.
- They modify unrelated files.
- They hide uncertainty behind confident summaries.
- They leave the human with a large, unclear diff.

## The approach

We convert failure modes into reusable skills.

A skill should answer:

- What failure mode does this address?
- When should the human invoke it?
- What must the agent inspect?
- What must the agent avoid?
- What evidence must be produced?
- What can the human review quickly?

## Human authority

Skills can recommend actions, but they should not replace human judgment.

The best agent workflow keeps the human in control of:

- scope
- merge decisions
- instruction updates
- risky mutations
- product direction
