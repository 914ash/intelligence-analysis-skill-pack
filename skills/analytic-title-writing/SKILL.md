---
name: analytic-title-writing
description: Give the product a title that signals subject, angle, and stakes cleanly. Use when the report needs a strong, informative title.
---

# Analytic Title Writing

## Objective
Give the product a title that signals subject, angle, and stakes cleanly.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The main judgment is stable enough to headline.
- The product will be searched, shared, or briefed widely.
- A generic or descriptive-only title would hide the analytic angle.

## Do Not Use When
- The core judgment is still changing.
- The task is to produce the body, not metadata.
- The house style requires non-analytic titling.

## Required Inputs
- Lead judgment
- Subject or actor
- Angle or implication

## Helpful Inputs
- Audience expectations
- Length limit
- Key term for searchability

## Workflow
1. Identify the subject, analytic angle, and why it matters.
2. Draft short titles that privilege the judgment over generic topic wording.
3. Remove filler words and ambiguous phrasing.
4. Check that the title matches the actual body and confidence level.
5. Pick the version with the best balance of clarity and specificity.

## Mini Template
```md
[Subject]: [Analytic angle or likely development]
```

## Example Options
```md
Weak: Regional Energy Update
Better: Regional Fuel Diversions Signal Preparation for Prolonged Disruption
Better: Militia Reconnaissance Suggests Renewed Cross-Border Attack Planning
```

## Templates To Reuse
- Use the long memo template in [Templates](../../references/shared/templates.md) to check that the title matches the body, not just the topic.

## Quality Bar
- The title should signal subject and angle.
- It should not overclaim beyond the body.
- It should be short enough to scan quickly.
- A reader should know what kind of judgment the report contains.

## Common Failure Modes
- Using generic topic labels.
- Writing a title that promises more certainty than the product supports.
- Making the title so clever it loses clarity.
- Repeating the opening sentence verbatim.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.
The primary artifact should include: Analytic title options; selected title; rationale for the chosen phrasing
If this skill is part of a larger workflow, keep the outer fields `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when the run is truly blocked.

## Cross-Links
- Upstream: [Key Judgments Writing](../key-judgments-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Downstream: [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Templates](../../references/shared/templates.md).
