---
name: intelligence-writing
description: Translate analysis into prose without weakening the logic or caveats. Use when analysis is complete enough to be delivered to a consumer.
---

# Intelligence Writing

## Objective
Translate analysis into prose without weakening the logic, caveats, or consumer utility.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- Analysis is complete enough to deliver.
- The task is to turn judgments into a usable written product.
- The consumer needs concise, decision-useful prose rather than a raw analytic worksheet.

## Do Not Use When
- The judgment is still unstable.
- The task is to pick the analytic method or gather more evidence.
- A narrower writing format skill would be a better fit.

## Required Inputs
- Lead judgment and supporting evidence
- Confidence and caveat language
- Audience or consumer need

## Helpful Inputs
- Key judgments draft
- BLUF draft
- Template or house style

## Workflow
1. Identify the main judgment, why it matters, and the minimum supporting evidence.
2. Sequence the product so the most important takeaway appears first.
3. Preserve caveats, alternatives, and watch items instead of smoothing them away.
4. Use concise sentences and explicit analytic verbs.
5. Check that the final prose remains faithful to the underlying analysis.

## Mini Template
```md
# [Title]

## BLUF
[Main judgment]. [Why it matters]. [Confidence or main caveat].

## Key Judgments
- [Judgment 1 with confidence]
- [Judgment 2 with confidence]

## Analysis
[Lead analytic paragraph]

## Evidence Gaps
[Most important unknowns and why they matter]
```

## Example
```md

## BLUF
We assess with moderate confidence that the supplier disruption is more likely a coordinated sanctions-evasion move than a routine logistics failure. If correct, firms that rely on the corridor should prepare for recurring throughput shocks over the next quarter.
```

## Templates To Reuse
- Use the long memo template, short update template, and key judgments block in [Templates](../../references/shared/templates.md).

## Quality Bar
- The first paragraph should carry the main answer.
- Caveats should remain visible.
- Paragraphs should add analytic value, not repeat headers.
- The prose should support rapid scanning without losing rigor.

## Common Failure Modes
- Writing around uncertainty instead of naming it.
- Turning nuanced analysis into generic business prose.
- Burying the lead.
- Losing the link between evidence and claim.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.
The primary artifact should include: Consumer-ready intelligence prose; preserved caveats; clear lead judgment
If this skill is part of a larger workflow, keep the outer fields `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when the run is truly blocked.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Inverted Pyramid Writing](../inverted-pyramid-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
