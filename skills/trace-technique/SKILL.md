---
name: trace-technique
description: Apply the TRACE technique to low-evidence or ambiguous cases. Use when an agent must work through threat assessment, fact reconciliation, competing explanations, and conditional evaluation under uncertainty.
---

# TRACE Technique

## Objective
Impose structure on ambiguous cases where evidence is weak but action may still be required.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Ambiguous case summary
- Current evidence
- Operational or decision stakes

## Workflow
1. Assess the threat or analytic consequence if the concern is real.
2. Reconcile what is actually known with the emerging case narrative.
3. List competing explanations and the conditions under which each becomes stronger.
4. Evaluate the case conditionally instead of pretending certainty exists.
5. Return the minimum-defensible judgment and next evidence needs.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: TRACE worksheet summary; Conditional judgment; Next evidence requirements
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
