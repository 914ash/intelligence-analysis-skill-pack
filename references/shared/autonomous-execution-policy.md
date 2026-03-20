# Autonomous Execution Policy

Apply this policy whenever the skills run inside LangGraph or any other unattended agent loop.

## Rules
- Do not ask the user clarifying questions during autonomous execution.
- If key context is missing, state the assumption and proceed with the safest reversible path.
- Record missing but non-blocking context in `missing_inputs` instead of requesting human input.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.
- When blocked, return a concrete `blocker_reason` and the smallest next collection step that would unblock execution.

## Standard Output Fields
- `status`: `complete`, `partial`, or `blocked`
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`
