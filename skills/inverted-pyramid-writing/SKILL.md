---
name: inverted-pyramid-writing
description: Sequence the product so the reader can stop early without missing the core message. Use when a report needs high scan value.
---

# Inverted Pyramid Writing

## Objective
Sequence the product so the reader can stop early without missing the core message.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The product must work for time-poor readers.
- The key judgment and implications should appear before background.
- The writer needs a clear ordering discipline.

## Do Not Use When
- The output is only a headline or title.
- The material is still analytically unstable.
- The product format requires a different structure.

## Required Inputs
- Lead judgment
- Supporting evidence
- Background or context material

## Helpful Inputs
- BLUF draft
- Key judgments list
- Audience reading pattern

## Workflow
1. Start with the answer and its significance.
2. Follow with the strongest supporting points in descending importance.
3. Push context, methodology, and lower-priority detail later.
4. Check that the reader can stop at multiple points and still retain the core message.
5. Remove background that delays the answer.

## Mini Template
```md

## BLUF
[Answer and significance]

## Key Support
[Most important support point]
[Second support point]

## Context
[Background, methodology, lower-priority detail]
```

## Example Ordering
```md
1. The militia is likely preparing for cross-border harassment attacks.
2. Recent weapons transfers and reconnaissance activity support that view.
3. The group has used similar staging behavior before.
4. Background on factional politics belongs later in the product.
```

## Templates To Reuse
- Use the long memo template and short update template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Ordering should be driven by decision value.
- The top of the product should stand on its own.
- Lower sections should deepen the answer rather than repeat it.
- Background should never outrank the judgment.

## Common Failure Modes
- Opening with scene-setting instead of the answer.
- Putting methodology ahead of conclusion.
- Treating all sections as equally important.
- Making the reader work to find the point.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.
The primary artifact should include: Inverted-pyramid outline or rewritten draft; descending-importance structure
If this skill is part of a larger workflow, keep the outer fields `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when the run is truly blocked.

## Cross-Links
- Upstream: [Intelligence Writing](../intelligence-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Downstream: [Analytic Title Writing](../analytic-title-writing/SKILL.md), [What / So What Statement](../what-so-what-statement/SKILL.md)
- Companions: [Key Judgments Writing](../key-judgments-writing/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Templates](../../references/shared/templates.md).
