---
name: estimative-probability
description: Make uncertainty legible, calibrated, and reusable across products. Use when a judgment needs explicit probability language.
---

# Estimative Probability

## Objective
Make uncertainty legible, calibrated, and reusable across products.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- A judgment needs explicit probability language.
- The consumer needs calibrated uncertainty rather than binary statements.
- Multiple judgments in the same product need consistent confidence wording.

## Do Not Use When
- The underlying reasoning is still unstable.
- The task is source grading rather than judgment calibration.
- Numeric precision would be misleading or unhelpful.

## Required Inputs
- Draft judgment or key judgment set
- Evidence quality assessment
- Consumer tolerance for probabilistic language

## Helpful Inputs
- Alternative hypotheses and their residual plausibility
- Decision stakes and time horizon
- Trigger events that would move the estimate

## Workflow
1. Identify the proposition that needs a probability statement.
2. Separate the probability of the event from confidence in the assessment.
3. Match evidence strength, disagreement, and volatility to an estimative term.
4. Explain the main drivers of the estimate and what could shift it.
5. Check that wording is consistent across the full product.
6. Return calibrated wording and caveat language for reuse downstream.

## Templates To Reuse
- Use the key judgments block and long memo template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Probability wording should be internally consistent.
- Confidence should not exceed the evidence base.
- The rationale should name what would move the estimate.
- Numeric ranges should be used only when they improve understanding.

## Common Failure Modes
- Treating confidence and probability as the same thing.
- Using near-synonyms inconsistently.
- Choosing a stronger term because it sounds decisive.
- Omitting the reason behind the estimate.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md)
- Downstream: [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md)
- Companions: , [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Confidence Language](../../references/shared/confidence-language.md), [Postmortem Analysis](../../references/shared/postmortem-analysis.md), [Templates](../../references/shared/templates.md).
