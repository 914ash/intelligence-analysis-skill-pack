---
name: team-a-team-b-analysis
description: Force the strongest opposing case into the record before finalizing the judgment. Use when high-stakes work needs explicit adversarial challenge.
---

# Team A / Team B Analysis

## Objective
Force the strongest opposing case into the record before finalizing the judgment.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The stakes are high and a single-team draft may be overconfident.
- The organization may be converging too quickly on one story.
- The task benefits from an explicit pro and con analytic structure.

## Do Not Use When
- The question is low stakes and lightweight challenge is enough.
- There is not enough evidence for two serious positions.
- The output needs a single final judgment without an adversarial process.

## Required Inputs
- Shared intelligence question
- Common evidence base
- At least two plausible interpretations

## Helpful Inputs
- Decision deadline
- Rules of engagement for both teams
- Criteria for final adjudication

## Workflow
1. Define the common question, evidence base, and judging rules.
2. Assign one team to the current lead case and another to the strongest rival case.
3. Require both teams to use the same evidence-quality standards.
4. Compare the two cases on evidence quality, assumptions, and explanatory power.
5. Adjudicate the result and record what evidence could reverse the current winner.

## Templates To Reuse
- Use the Team A / Team B scorecard and alternative comparison in [Templates](../../references/shared/templates.md).

## Quality Bar
- Both sides should be argued as strongly as possible.
- The adjudication should rely on evidence quality, not rhetoric.
- Shared assumptions should be exposed, not hidden.
- The final output should name what would change the result.

## Common Failure Modes
- Allowing one side to be weakly staffed or weakly argued.
- Changing evidence standards between sides.
- Mistaking debate performance for analytic strength.
- Failing to produce a final adjudication.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Structured Analytic Techniques Primer](../../references/shared/structured-analytic-techniques-primer.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
