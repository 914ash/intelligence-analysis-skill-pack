---
name: defend-analytic-conclusion
description: Build a defensible warrant chain for an intelligence judgment. Use when an agent must show how evidence supports the conclusion, answer challenges, or prepare a product for review.
---

# Defend Analytic Conclusion

## Objective
Make the reasoning auditable under scrutiny.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Current judgment
- Evidence-to-claim map
- Known challenges, alternatives, or review comments

## Workflow
1. State the conclusion in its strongest defensible form.
2. Map each major claim to the evidence that supports it and the caveats that limit it.
3. Address the strongest competing explanation directly.
4. Show why the current conclusion is preferred despite uncertainty.
5. Name the evidence that would most likely force revision.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Defensible warrant chain; Response to likely challenges; Revision triggers
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md)
- Downstream: [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
