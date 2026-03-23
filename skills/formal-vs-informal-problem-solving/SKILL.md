---
name: formal-vs-informal-problem-solving
description: Match the problem shape and stakes to the right level of analytical structure. Use when a workflow needs to choose between lightweight reasoning and a formal method.
---

# Formal vs Informal Problem Solving

## Objective
Match the problem shape and stakes to the right level of analytical structure.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The workflow needs to decide whether lightweight reasoning is sufficient or a formal SAT is warranted.
- Stakes, ambiguity, or competing explanations are high enough to justify method selection.
- A team needs a defensible reason for choosing one analytic path over another.

## Do Not Use When
- The method is already chosen and accepted.
- The task is already deep inside a specific technique.
- The problem is purely editorial.

## Required Inputs
- Intelligence question or problem statement
- Stakes, uncertainty, or ambiguity indicators
- Current evidence maturity

## Helpful Inputs
- Consumer deadline
- Known competing explanations
- Historical failure patterns or bias concerns

## Workflow
1. Restate the problem, stakes, and decision timeline.
2. Evaluate ambiguity, uncertainty, and the number of plausible explanations.
3. Assess whether the dominant risk is speed, complexity, bias, or evidentiary weakness.
4. Decide whether informal reasoning is adequate or a formal SAT is needed.
5. Recommend the specific next technique and why it fits better than the nearest alternative.
6. Return the routing decision with assumptions and caveats.

## Templates To Reuse
- Use the alternative comparison, ACH matrix, and TRACE worksheet in [Templates](../../references/shared/templates.md).

## Quality Bar
- The recommendation should be traceable to problem characteristics.
- The rationale should explain why heavier methods are or are not warranted.
- The nearest rejected option should be named when useful.
- The recommendation should lower analytic risk, not add process for its own sake.

## Common Failure Modes
- Recommending a formal method because it sounds rigorous.
- Under-structuring a high-stakes question because time is short.
- Ignoring the bias risk a challenge technique could reduce.
- Returning a generic method recommendation.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.
The primary artifact should include: Method recommendation; rationale; assumptions; next-skill routing decision
If this skill is part of a larger workflow, keep the outer fields `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when the run is truly blocked.

## Cross-Links
- Upstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md), [TRACE Technique](../trace-technique/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md), [Team A / Team B Analysis](../team-a-team-b-analysis/SKILL.md), [Delphi Method](../delphi-method/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Structured Analytic Techniques Primer](../../references/shared/structured-analytic-techniques-primer.md).
