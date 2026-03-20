---
name: inverted-pyramid-writing
description: Organize intelligence reporting from most important to least important. Use when an agent needs to structure a memo, brief, or note so decision-makers see the judgment first.
---

# Inverted Pyramid Writing

## Objective
Sequence the product so the reader can stop early without missing the core message.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Key judgment
- Supporting points ranked by importance
- Background details

## Workflow
1. Place the key judgment at the top.
2. Order support by decision relevance, not by research chronology.
3. Push background, caveats, and context lower unless they materially change interpretation.
4. Check whether any paragraph can be cut without losing the core answer.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Inverted-pyramid outline or draft; Ordered supporting points
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Writing](../intelligence-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md)
- Downstream: [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [Key Judgments Writing](../key-judgments-writing/SKILL.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
