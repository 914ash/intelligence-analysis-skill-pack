---
name: alternative-analysis
description: Keep the analysis from collapsing around the first plausible story. Use when the lead explanation needs explicit alternatives on the record.
---

# Alternative Analysis

## Objective
Keep the analysis from collapsing around the first plausible story.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- A draft has a lead view but weak treatment of alternatives.
- The main risk is confirmation bias or organizational consensus pressure.
- The consumer needs to understand what else could explain the evidence.

## Do Not Use When
- There is no evidence base yet.
- The task requires full ACH rather than a lighter challenge pass.
- The work is purely editorial.

## Required Inputs
- Lead assessment or favored hypothesis
- Current evidence set
- At least one plausible alternative

## Helpful Inputs
- Prior dissent views
- Known institutional preferences
- Indicators that would elevate an alternative

## Workflow
1. List the lead explanation and at least one serious alternative.
2. State what evidence currently favors the lead view.
3. State what evidence could elevate each alternative.
4. Test whether the alternatives are genuinely distinct rather than relabeled versions of the lead view.
5. Return a balanced comparison with watch items and remaining uncertainty.

## Templates To Reuse
- Use the alternative comparison and long memo template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Alternatives should be plausible and consequential.
- The lead view should not get extra detail merely because it is preferred.
- The output should explain what evidence would change the ranking.
- The comparison should strengthen the final judgment.

## Common Failure Modes
- Inventing weak straw-man alternatives.
- Treating alternatives as an afterthought paragraph.
- Ignoring evidence that favors a non-lead view.
- Collapsing distinct alternatives into one vague bucket.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Team A / Team B Analysis](../team-a-team-b-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
