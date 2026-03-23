---
name: critical-thinking
description: Challenge the reasoning, not just the answer. Use when a judgment, plan, or inference chain needs disciplined critique.
---

# Critical Thinking

## Objective
Challenge the reasoning, not just the answer.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- A draft judgment needs stress testing before publication or briefing.
- The analytic path appears too smooth or too certain.
- The task is to expose assumptions, bias, or missing disconfirming evidence.

## Do Not Use When
- The evidence base is still too thin and collection should continue first.
- The task is only formatting or prose cleanup.
- Another challenge method has already fully covered the same ground.

## Required Inputs
- Draft judgment or analytic frame
- Core evidence and assumptions
- Decision context or stakes

## Helpful Inputs
- Prior versions of the assessment
- Known organizational biases or favored explanations
- Named alternatives already considered

## Workflow
1. Identify the current claim, supporting logic, assumptions, and unstated premises.
2. Test for common bias patterns such as confirmation bias, anchoring, and mirror imaging.
3. Ask what evidence would falsify the lead view and whether the workflow looked for it.
4. Compare the argument to at least one serious alternative explanation.
5. Separate fatal issues from caveats that can be managed.
6. Return the strongest critique and the strongest repaired version of the argument.

## Templates To Reuse
- Use the alternative comparison and gap register in [Templates](../../references/shared/templates.md).

## Quality Bar
- The critique should improve the judgment, not only attack it.
- Bias findings should point to concrete evidence or reasoning behavior.
- At least one challenge should focus on missing evidence.
- The repaired argument should be narrower if the evidence does not justify the original scope.

## Common Failure Modes
- Producing generic skepticism.
- Confusing disagreement with rigorous critique.
- Failing to distinguish logic flaws from collection gaps.
- Softening the critique to protect the original conclusion.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md), [Team A / Team B Analysis](../team-a-team-b-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Analytic Techniques Primer](../../references/shared/structured-analytic-techniques-primer.md), [Templates](../../references/shared/templates.md).
