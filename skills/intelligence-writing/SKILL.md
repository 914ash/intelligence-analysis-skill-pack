---
name: intelligence-writing
description: Turn structured findings into clear intelligence prose for decision-makers. Use when analysis is done and the output needs to be readable, concise, and action-oriented.
---

# Intelligence Writing

## Objective
Translate analysis into prose without weakening the logic or caveats.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Structured findings
- Audience and product type
- Required confidence language or style constraints

## Workflow
1. Lead with the key judgment and why it matters.
2. Organize the body so the strongest support appears before background detail.
3. Keep caveats visible but concise.
4. Remove redundant throat-clearing, passive hedging, and unsupported filler.
5. End with the main implication, watch item, or next collection step if relevant.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Decision-ready draft; Visible caveats and confidence; Clean handoff to product-specific writing skills
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Inverted Pyramid Writing](../inverted-pyramid-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [Writing Patterns](../../references/shared/writing-patterns.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
