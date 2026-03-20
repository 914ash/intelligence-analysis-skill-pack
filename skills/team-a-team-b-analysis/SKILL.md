---
name: team-a-team-b-analysis
description: Use adversarial red-team analysis to compare a baseline judgment with the strongest competing case. Use when a high-stakes conclusion needs a structured challenge before publication.
---

# Team A / Team B Analysis

## Objective
Force the strongest opposing case into the record before finalizing the judgment.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Baseline judgment
- Evidence summary
- Key assumptions and stakes

## Workflow
1. State the baseline view as Team A.
2. Construct the strongest credible rival view as Team B.
3. List which evidence, assumptions, and indicators each side relies on.
4. Compare which side better explains the current evidence and what future indicators would decide the issue.
5. Return a synthesis instead of declaring a theatrical winner.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Team A vs Team B comparison; Indicator watchlist; Synthesis judgment
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Alternative Analysis](../alternative-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
