---
name: analysis-of-competing-hypotheses
description: Apply Analysis of Competing Hypotheses to weigh evidence against multiple explanations. Use when there are several plausible hypotheses and the task is to discriminate among them systematically.
---

# Analysis of Competing Hypotheses

## Objective
Use inconsistency analysis to compare hypotheses rather than merely collecting support for a favorite view.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Question with multiple plausible explanations
- Evaluated evidence set
- Candidate hypotheses

## Workflow
1. List mutually distinct hypotheses.
2. Build an evidence-by-hypothesis matrix.
3. Score how inconsistent each item is with each hypothesis, not just how supportive it is.
4. Identify diagnostic evidence and missing disconfirming evidence.
5. Rank the hypotheses and explain the remaining uncertainty.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: ACH matrix summary; Leading and competing hypotheses; Diagnostic evidence and gaps
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Companions: [Alternative Analysis](../alternative-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
