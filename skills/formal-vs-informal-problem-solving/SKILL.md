---
name: formal-vs-informal-problem-solving
description: Choose whether a question needs lightweight reasoning or a formal structured analytic technique. Use when an agent must select the right level of rigor before analysis begins.
---

# Formal vs Informal Problem Solving

## Objective
Match the problem shape and stakes to the right level of analytical structure.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Scoped question
- Evidence quality snapshot
- Time pressure and consequence of error

## Workflow
1. Assess stakes, ambiguity, number of plausible explanations, and auditability needs.
2. Decide whether informal synthesis is sufficient or whether a structured method is required.
3. If formal analysis is needed, nominate the best-fit method and explain why.
4. Set trigger conditions for escalating from informal to formal analysis later.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Recommended analysis mode; Selected method or rationale for staying lightweight; Escalation triggers
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Team A / Team B Analysis](../team-a-team-b-analysis/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md), [TRACE Technique](../trace-technique/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
