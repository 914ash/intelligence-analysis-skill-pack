---
name: defend-analytic-conclusion
description: Make the reasoning auditable under scrutiny. Use when a judgment must withstand stakeholder challenge, review, or decision pressure.
---

# Defend Analytic Conclusion

## Objective
Make the reasoning auditable under scrutiny.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- A judgment is likely to be challenged by stakeholders or reviewers.
- The analyst needs a concise defense of why the conclusion is the current best view.
- The workflow needs a review-ready argument before delivery.

## Do Not Use When
- The underlying analysis is not mature enough to defend.
- The task is to generate the first judgment rather than defend it.
- The product needs only stylistic editing.

## Required Inputs
- Draft judgment
- Evidence-to-claim map
- Known alternatives or objections

## Helpful Inputs
- Expected stakeholder pushback
- Prior critiques
- Confidence and caveat language already chosen

## Workflow
1. Restate the judgment and why it matters.
2. List the strongest evidence supporting the judgment.
3. List the strongest challenge or rival explanation.
4. Explain why the current judgment still leads despite those challenges.
5. Name what evidence would force revision.
6. Return a concise defense package suitable for review or briefing.

## Templates To Reuse
- Use the long memo template and alternative comparison in [Templates](../../references/shared/templates.md).
- Use the review grid in [Postmortem Analysis](../../references/shared/postmortem-analysis.md) when stress-testing old judgments or forecasts.

## Quality Bar
- The defense should answer the strongest objection, not an easy one.
- The output should not hide weaknesses.
- Reversal conditions should be explicit.
- The argument should remain consistent with the stated confidence.

## Common Failure Modes
- Turning advocacy into overclaiming.
- Ignoring the strongest rival case.
- Repeating the draft verbatim without audit logic.
- Failing to state what would change the conclusion.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)
- Downstream: [Intelligence Writing](../intelligence-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md), [Alternative Analysis](../alternative-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Confidence Language](../../references/shared/confidence-language.md), [Postmortem Analysis](../../references/shared/postmortem-analysis.md), [Templates](../../references/shared/templates.md).
