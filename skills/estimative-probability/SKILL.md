---
name: estimative-probability
description: Express uncertainty with disciplined confidence language and consistent probability bands. Use when an agent must translate evidence strength into estimative terms for an intelligence product.
---

# Estimative Probability

## Objective
Make uncertainty legible, calibrated, and reusable across products.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Working judgment
- Evidence strength and gap summary
- Any required house style for confidence wording

## Workflow
1. Assess how strongly the evidence supports the current judgment versus alternatives.
2. Choose estimative language that matches the actual support level.
3. State the main caveat, disconfirming condition, and what would change the estimate.
4. Avoid false precision when the evidence base is weak or heterogeneous.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Confidence statement; Rationale for the chosen confidence level; Conditions that would change the estimate
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Source Evaluation](../source-evaluation/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)
- Downstream: [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Source Evaluation](../source-evaluation/SKILL.md)

## Shared Doctrine
Read and apply: [Confidence Language](../../references/shared/confidence-language.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
