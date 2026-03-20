---
name: bluf-writing
description: Write Bottom Line Up Front openings for intelligence products. Use when an agent needs the lead sentence or opening paragraph to state the key judgment and why it matters.
---

# BLUF Writing

## Objective
Produce a lead that tells the consumer the answer before the details.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Primary judgment
- Why it matters
- Confidence or caveat statement

## Workflow
1. State the answer first, not the background.
2. Include the implication or consequence in the same opening unit if possible.
3. Keep only the caveat needed to prevent overstatement.
4. Trim any setup language that delays the judgment.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: BLUF sentence or opening paragraph; Optional alternate tighter versions
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Writing](../intelligence-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Downstream: [Inverted Pyramid Writing](../inverted-pyramid-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
