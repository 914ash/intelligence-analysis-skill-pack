---
name: critical-thinking
description: Stress-test assumptions, framing, and reasoning quality in intelligence work. Use when an agent needs to surface hidden assumptions, bias risks, missing comparisons, or weak logic in a draft judgment.
---

# Critical Thinking

## Objective
Challenge the reasoning, not just the answer.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Working judgment or draft
- Evidence summary
- Known assumptions or framing choices

## Workflow
1. List the core claims, assumptions, and inferential jumps in the current reasoning.
2. Look for anchoring, mirror-imaging, confirmation bias, and missing comparators.
3. Ask what evidence would most seriously weaken the current view.
4. Separate strong reasoning problems from low-importance stylistic issues.
5. Return challenge questions or revisions the analyst should address next.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Reasoning risks; Revised assumptions; Priority challenge questions
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Downstream: [Alternative Analysis](../alternative-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
