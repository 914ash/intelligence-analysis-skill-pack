---
name: delphi-method
description: Facilitate a Delphi-style expert consensus workflow with structured rounds, controlled feedback, and convergence checks. Use when an agent needs to synthesize multiple expert views on a complex intelligence question.
---

# Delphi Method

## Objective
Run a repeatable expert-consensus process without losing question discipline or transparency.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Problem statement
- Panel criteria or expert list
- Consensus threshold and round constraints

## Workflow
1. Define the research question, panel criteria, and stopping rule.
2. Draft the first-round prompts and specify the response format.
3. Aggregate round results with controlled anonymous feedback.
4. Track convergence, disagreement, and attrition across rounds.
5. Return the consensus judgment, dissent areas, and residual uncertainties.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Delphi workflow plan; Round summary outputs; Consensus and dissent record
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md)

## Local References
- [Delphi Method Notes](./references/delphi-method-notes.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
