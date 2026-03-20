---
name: evidence-gap-analysis
description: Identify known unknowns, collection gaps, and missing disconfirming evidence. Use when evidence is incomplete, contradictory, or too thin for a confident judgment.
---

# Evidence Gap Analysis

## Objective
Make uncertainty explicit and convert it into collection priorities.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Question and current evidence set
- Working judgment if one exists
- Known constraints on collection

## Workflow
1. Identify what must be known to answer the question credibly.
2. Compare those requirements to the evidence currently in hand.
3. Distinguish critical gaps from nice-to-have context.
4. Call out missing disconfirming evidence, not just missing supporting evidence.
5. Prioritize next collection or analytic actions by expected value.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Prioritized gap list; Collection priorities; Impact of each gap on confidence
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Downstream: [Research and Collection](../research-and-collection/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Source Evaluation](../source-evaluation/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
