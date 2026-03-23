---
name: bluf-writing
description: Produce a lead that tells the consumer the answer before the details. Use when a product needs a strong bottom-line-up-front opening.
---

# BLUF Writing

## Objective
Produce a lead that tells the consumer the answer before the details.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The product needs a short, decisive lead paragraph.
- The consumer may read only the opening lines.
- The judgment is stable enough to summarize directly.

## Do Not Use When
- The analysis is too uncertain to support a concise lead.
- The task requires a full product structure rather than only the opening.
- The content is still being analytically revised.

## Required Inputs
- Lead judgment
- Why it matters
- Confidence or caveat language

## Helpful Inputs
- Audience context
- Decision deadline
- One or two strongest support points

## Workflow
1. Write the lead judgment in the first sentence.
2. Add the immediate implication for the consumer.
3. Include the most important qualifier or confidence note.
4. Keep the paragraph short enough to scan quickly.
5. Check that the BLUF matches the fuller product exactly.

## Mini Template
```md
[Main judgment in sentence one]. [Immediate implication for the reader]. [Most important confidence note or caveat].
```

## Example
```md
We assess with high confidence that the campaign is shifting from opportunistic probing to deliberate pre-positioning against regional energy infrastructure. If the current pattern continues, operators should expect a higher risk of disruptive action during the next political flashpoint.
```

## Templates To Reuse
- Use the short update template and long memo template in [Templates](../../references/shared/templates.md).

## Quality Bar
- The first sentence should answer the question.
- The implication should be concrete.
- The caveat should not overwhelm the lead but should remain visible.
- The BLUF should not introduce claims missing from the body.

## Common Failure Modes
- Writing a teaser instead of the answer.
- Stuffing too much evidence into the lead.
- Using vague implication language.
- Letting the BLUF overstate confidence.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Writing](../intelligence-writing/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Downstream: [Inverted Pyramid Writing](../inverted-pyramid-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
