---
name: what-so-what-statement
description: Compress evidence and implication into one disciplined analytic statement. Use when the product needs a sharp fact-plus-implication sentence pair or paragraph.
---

# What / So What Statement

## Objective
Compress evidence and implication into one disciplined analytic statement.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The analyst needs a short statement linking development to significance.
- A section opening or judgment needs a tighter fact-to-implication connection.
- The consumer benefits from an explicit why-it-matters clause.

## Do Not Use When
- The underlying implication is still speculative.
- The task is to write a full product rather than a compressed statement.
- The fact and implication do not belong together yet.

## Required Inputs
- Observed development or judgment
- Implication for the consumer
- Confidence or caveat if needed

## Helpful Inputs
- Audience role
- Time horizon
- Supporting evidence for the implication

## Workflow
1. State the development or judgment clearly.
2. State why it matters to the consumer, mission, or forecast.
3. Check that the implication actually follows from the stated fact.
4. Trim filler so the linkage is explicit and fast to read.
5. Keep the wording compatible with the wider product.

## Mini Template
```md
**What:** [Observed development or judgment]
**So What:** [Why it matters operationally, strategically, or analytically]
```

## Example
```md
**What:** The ministry moved fuel reserves from commercial depots to military-controlled storage sites over the past two weeks.
**So What:** The shift increases the likelihood that the government expects a period of sustained disruption and is prioritizing regime resilience over civilian market stability.
```

## Templates To Reuse
- Use the short update template and key judgments block in [Templates](../../references/shared/templates.md).

## Quality Bar
- The implication should be concrete.
- The statement should not rely on hidden assumptions.
- The what and so what should be tightly coupled.
- The output should be reusable in a larger report.

## Common Failure Modes
- Writing a fact with no implication.
- Writing an implication that outruns the evidence.
- Using generic significance language.
- Repeating the same idea twice with different words.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
