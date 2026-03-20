---
name: what-so-what-statement
description: Craft analytical statements that pair the factual change with its significance. Use when an agent needs a crisp what happened / why it matters formulation.
---

# What / So What Statement

## Objective
Compress evidence and implication into one disciplined analytic statement.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Observed development
- Analytical implication
- Confidence or caveat if needed

## Workflow
1. State the observable development first.
2. Translate it into an implication, not a generic summary.
3. Cut adjectives and rhetorical flourishes.
4. Add only the caveat needed to prevent misreading.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: One-line or one-paragraph what/so what statement; Optional tighter alternatives
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Analytic Title Writing](../analytic-title-writing/SKILL.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
