---
name: key-judgments-writing
description: Draft and refine key judgments for intelligence products. Use when an agent needs short, defensible, high-signal judgments with confidence and caveats.
---

# Key Judgments Writing

## Objective
Produce standalone judgments that can survive extraction from the full product.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Structured findings
- Confidence level
- Audience and product length

## Workflow
1. Write each judgment as a complete proposition, not a topic label.
2. Include confidence when it materially affects how the consumer should use the judgment.
3. Avoid stacking multiple distinct claims into one judgment.
4. Check that each judgment can be defended from the evidence base.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Ranked key judgments; Confidence and caveat notes
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
