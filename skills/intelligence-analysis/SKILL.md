---
name: intelligence-analysis
description: Synthesize evaluated reporting into structured intelligence judgments. Use when collection is in hand and the task is to integrate evidence, compare explanations, and produce findings.
---

# Intelligence Analysis

## Objective
Produce a traceable judgment from evaluated evidence rather than from intuition alone.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Evaluated evidence set
- Scoped intelligence question
- Known alternatives or competing hypotheses

## Workflow
1. Restate the analytic question and the current state of knowledge.
2. Group the strongest evidence by relevance and reliability.
3. Compare the leading explanation to the strongest alternative.
4. Separate facts, inferences, assumptions, and unresolved gaps.
5. Produce a provisional judgment and state what could overturn it.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Structured judgment; Evidence-to-claim map; Alternatives considered; Key gaps and collection implications
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
