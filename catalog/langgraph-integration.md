# LangGraph Integration Notes

## Runtime Assumptions
- Invoke the router skill when the correct skill chain is not already known.
- Pass objective, scope, time horizon, and any known evidence into graph state before calling a skill.
- Do not expose a normal human-input branch inside the default automated path.

## Required Graph Handling
- Treat `status` as the transition key.
- Use `recommended_next_skill` to select the next node when the current run is not terminal.
- Persist `assumptions_used`, `missing_inputs`, and `confidence` into graph state for later nodes.
- Treat `blocked` as a machine-handled escalation branch, not as permission to ask the user a question.

## Suggested Branching
- `complete`: move to the recommended next skill or finish the workflow.
- `partial`: persist outputs, queue follow-on collection or analysis, and continue.
- `blocked`: route to an operator-review or external-collection node with `blocker_reason`.
