---
name: analysis-of-competing-hypotheses
description: Apply Analysis of Competing Hypotheses to weigh evidence against multiple explanations. Use when there are several plausible hypotheses and the task is to discriminate among them systematically.
---

# Analysis of Competing Hypotheses

## Objective
Use inconsistency analysis to compare distinct hypotheses rather than collecting support for a favorite explanation.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- Multiple explanations are plausible and the main risk is premature closure.
- The analyst needs a visible, auditable way to show how each observation affects each hypothesis.
- The consumer needs to understand why one explanation currently leads and others do not.

## Do Not Use When
- There is only one serious explanation and the question is already narrow.
- The evidence base is so thin that hypothesis testing would be mostly speculation.
- The hypotheses overlap so heavily that they cannot be independently falsified.

## Required Inputs
- Question with multiple plausible explanations
- Evaluated evidence set
- Candidate hypotheses

## Helpful Inputs
- Evidence ledger with source-quality notes
- Initial list of alternative explanations from a team brainstorm
- Known watch items or indicators that could break a tie

## Workflow
1. List hypotheses that are mutually distinct, non-overlapping, and capable of being proven true or false on their own terms.
2. Remove nested, synonymous, or partially merged hypotheses before building the matrix.
3. Build an observation-by-hypothesis matrix and score each cell for whether the observation supports, undermines, or does not differentiate the hypothesis.
4. Prioritize diagnostic observations. A row that supports every hypothesis equally does not narrow the field.
5. Eliminate or downgrade hypotheses with the strongest contradictory pattern, then explain the residual uncertainty.
6. If two or more hypotheses remain plausible, create an early warning list describing what else would be expected if each remaining hypothesis were true.

## Matrix Output Template
Use this matrix to show the reasoning path. Each row is one observation or piece of intelligence. Each column is one non-overlapping hypothesis.

| Observation / Intelligence | Hypothesis 1 | Hypothesis 2 | Hypothesis 3 | Hypothesis 4 |
| --- | --- | --- | --- | --- |
| Observation 1 |  |  |  |  |
| Observation 2 |  |  |  |  |
| Observation 3 |  |  |  |  |
| Observation 4 |  |  |  |  |

### Matrix Scoring Rules
- Use `+` when the observation is expected if the hypothesis is true.
- Use `-` when the observation undermines or contradicts the hypothesis.
- Use `0` or leave blank when the observation is not diagnostic or not applicable.
- Prefer observations that differentiate hypotheses. A row full of `+` values does not narrow the field.
- Keep hypothesis labels short but specific enough to test independently.

### Hypothesis Design Rule
- Hypotheses must not overlap. Each one should be capable of being proven true or false on its own terms.
- Rewrite nested or partially overlapping hypotheses until they are mutually distinct enough to test.
- If two hypotheses can both be true without contradiction, they are not competing hypotheses yet.

## Templates To Reuse
- Use the ACH matrix and alternative comparison in [Templates](../../references/shared/templates.md).

## Quality Bar
- The hypotheses must compete with one another rather than describe different parts of the same scenario.
- The matrix should highlight disconfirming evidence, not just confirming evidence.
- At least some observations should be diagnostic enough to separate the leading hypotheses.
- The final narrative should explain why surviving hypotheses remain live.

## Common Failure Modes
- Using overlapping hypotheses that can all be true at once.
- Populating the matrix with observations that support every column equally.
- Failing to challenge the initial favorite explanation.
- Treating a blank or non-diagnostic cell as support.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Companions: [Alternative Analysis](../alternative-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md), [Team A / Team B Analysis](../team-a-team-b-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Structured Analytic Techniques Primer](../../references/shared/structured-analytic-techniques-primer.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).

## External References
- [Crayon: Analysis of Competing Hypotheses overview and example](https://www.crayon.co/blog/analysis-of-competing-hypotheses)
