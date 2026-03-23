# LangGraph Integration Notes

These notes are optional runtime guidance for teams embedding the pack in LangGraph or a similar workflow engine. They are not the primary way to understand the pack; start with the skill docs and shared references first.

## Runtime Assumptions
- Invoke the router skill when the correct skill chain is not already known.
- Pass objective, scope, timeframe, known evidence, and any prior outputs into graph state before calling a skill.
- Keep the tradecraft artifact distinct from the outer workflow envelope.

## Recommended Graph Handling
- Treat `status` as the transition key.
- Use `recommended_next_skill` to select the next node when the current run is not terminal.
- Persist `assumptions_used`, `missing_inputs`, and `confidence` into graph state for later nodes.
- Treat `blocked` as an operator-review or external-collection branch rather than as a normal prompt for more user questions.

## Suggested Branching
- `complete`: move to the recommended next skill or finish the workflow.
- `partial`: persist outputs, queue follow-on collection or analysis, and continue.
- `blocked`: route to an operator-review or external-collection node with `blocker_reason`.

## Implementation Note
If your environment is human-guided rather than unattended, keep the same outer fields but let the skill guidance, templates, and shared references drive the substantive work.
