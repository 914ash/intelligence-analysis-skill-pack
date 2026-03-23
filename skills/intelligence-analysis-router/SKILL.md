---
name: intelligence-analysis-router
description: Choose the right skill chain when the request is ambiguous. Use when an autonomous agent needs to decide which intelligence-analysis skills to run next.
---

# Intelligence Analysis Router

## Objective
Choose the smallest useful skill chain for the request while preserving the pack analytical contract.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The request is ambiguous or mixed across discovery, collection, analysis, and writing.
- The agent needs to select the next one to three skills autonomously.
- The workflow must preserve shared output fields across several skills.

## Do Not Use When
- The next skill is already obvious and accepted.
- The task is to perform the substantive analysis rather than route it.
- The request is outside the scope of this skill pack.

## Required Inputs
- Task request or mission need
- Any available evidence or draft material
- Current workflow state if known

## Helpful Inputs
- Known deadline
- Consumer type
- Existing partial outputs from previous skills

## Workflow
1. Classify the request as topic discovery, question framing, collection, source evaluation, structured analysis, synthesis, or writing.
2. Identify the highest-risk missing step in the chain.
3. Recommend the smallest useful next skill sequence, usually one to three skills.
4. Carry forward assumptions, missing inputs, and confidence as graph-state fields.
5. Return `blocked` only when the request is unsafe or impossible for the pack to execute.

## Templates To Reuse
- Use the topic triage card, intelligence question brief, and long memo template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Routing should minimize unnecessary hops.
- The chain should preserve the analytical contract.
- The recommendation should name why adjacent options were not chosen.
- The router should favor evidence discipline over speed when the two conflict.

## Common Failure Modes
- Sending a request straight to writing before analysis exists.
- Over-routing into many skills when one would do.
- Ignoring missing source evaluation.
- Using `blocked` instead of recording assumptions.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried forward because the request lacked details.
- `missing_inputs`: the most important context gaps that would improve routing quality.
- `confidence`: a concise confidence statement tied to the quality and completeness of the request.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: `null`
- Downstream: [Find Intelligence Topics](../find-intelligence-topics/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md)
- Companions: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Source Foundations](../../references/shared/source-foundations.md).
