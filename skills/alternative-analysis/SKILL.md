---
name: alternative-analysis
description: Generate and evaluate credible alternative explanations for an intelligence problem. Use when the main narrative feels too settled or when the task explicitly requires alternatives.
---

# Alternative Analysis

## Objective
Keep the analysis from collapsing around the first plausible story.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Working explanation
- Evidence summary
- Known assumptions

## Workflow
1. State the current leading explanation.
2. Generate at least two credible alternatives that fit some of the evidence.
3. Identify what each alternative explains well, poorly, and not at all.
4. List the indicators or collection tasks that would discriminate among them.
5. Return the alternative set in a form another skill can use immediately.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Alternative explanation set; Comparison notes; Discriminating indicators
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)
- Downstream: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
