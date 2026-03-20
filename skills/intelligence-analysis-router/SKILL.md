---
name: intelligence-analysis-router
description: Route intelligence-analysis requests to the right combination of framing, evidence, analytic, and writing skills. Use when an agent needs to decide which intelligence skill to apply first or how to sequence several skills for a national-security analysis task.
---

# Intelligence Analysis Router

## Objective
Classify the request, pick the next 1-3 skills, and force a traceable end-to-end workflow.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- User request or analytic prompt
- Known audience, timeframe, and decision context if available
- Any existing evidence, draft judgment, or unfinished product

## Workflow
1. Restate the task as an intelligence problem: question, audience, time horizon, and stakes.
2. Choose the entry point: framing, collection, source review, structured method, synthesis, or writing.
3. Recommend an ordered skill chain of 1-3 leaf skills, with one-sentence justification for each hop.
4. Do not ask the user clarifying questions; when context is missing, state assumptions and continue with the safest reversible path.
5. Require the shared analytical contract before allowing a writing skill to be the final step.
6. Escalate to a structured method when ambiguity, stakes, or competing explanations are high.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Ordered skill chain with rationale; Immediate next artifact the agent should produce; Known gaps or blockers before analysis can continue
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: none; this skill is the entry point.
- Downstream: [Find Intelligence Topics](../find-intelligence-topics/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md)

## Shared Doctrine
Read and apply: [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
