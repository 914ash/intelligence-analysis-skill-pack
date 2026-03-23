---
name: trace-technique
description: Impose structure on ambiguous cases where evidence is weak but action may still be required. Use when low-evidence reasoning must still be disciplined.
---

# TRACE Technique

## Objective
Impose structure on ambiguous cases where evidence is weak but action may still be required.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- Evidence is sparse or fragmentary.
- The consumer still needs a structured assessment despite the thin record.
- Conditional reasoning matters more than broad narrative synthesis.

## Do Not Use When
- A richer evidence base justifies ACH or a standard analytic flow.
- The question is purely descriptive and low stakes.
- The task is only to write up a completed assessment.

## Required Inputs
- Question or threat frame
- Fragmentary evidence set
- Decision or action context

## Helpful Inputs
- Known thresholds for action
- Alternative explanations
- Indicators that would tighten or relax concern

## Workflow
1. State the threat or problem being assessed and the decision context.
2. Reconcile the sparse facts that are actually known.
3. List the most plausible competing explanations.
4. Evaluate conditional probabilities and threshold implications rather than pretending certainty.
5. Return a bounded judgment, the key assumptions, and the next evidence most likely to sharpen the picture.

## Templates To Reuse
- Use the TRACE worksheet and gap register in [Templates](../../references/shared/templates.md).

## Quality Bar
- The method should acknowledge thin evidence without surrendering discipline.
- Conditional logic should be explicit.
- Assumptions should be visible and testable.
- Recommended next collection should be narrowly focused.

## Common Failure Modes
- Pretending the evidence base is stronger than it is.
- Skipping alternatives because time is short.
- Using vague risk language with no threshold logic.
- Turning a low-evidence case into a sweeping narrative.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
