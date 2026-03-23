---
name: key-judgments-writing
description: Produce standalone judgments that can survive extraction from the full product. Use when a report needs a concise judgment list for leaders or briefers.
---

# Key Judgments Writing

## Objective
Produce standalone judgments that can survive extraction from the full product.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The consumer needs a short set of top judgments.
- The report may be excerpted or briefed verbally.
- Each judgment must remain intelligible outside the main body.

## Do Not Use When
- The analysis is still too unsettled to summarize cleanly.
- The task is only a headline or title.
- The material is mostly descriptive background.

## Required Inputs
- Final or near-final judgments
- Confidence language
- Core support points

## Helpful Inputs
- Decision context
- Ordering priority
- Length limit

## Workflow
1. List the few judgments the consumer must remember.
2. Write each as a standalone proposition in plain language.
3. Attach confidence or caveat where it materially matters.
4. Order the judgments by consequence or decision value.
5. Check that each judgment still makes sense if read alone.

## Mini Template
```md

## Key Judgments
- [Most important judgment] ([confidence])
- [Second judgment] ([confidence])
- [Third judgment] ([confidence])
```

## Example
```md

## Key Judgments
- We assess with high confidence that the network is using commercial shipping cover to move dual-use components.
- We assess with moderate confidence that the current surge in procurement activity is tied to expansion rather than stock replacement.
- We assess with low confidence that a parallel financing channel runs through the Gulf, although recent transfers make this more plausible.
```

## Templates To Reuse
- Use the key judgments block and long memo template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Each judgment should be specific and self-contained.
- The ordering should reflect importance.
- Confidence should be visible when needed.
- The list should be short enough to scan quickly.

## Common Failure Modes
- Writing mini paragraphs instead of judgments.
- Making the statements too vague to stand alone.
- Hiding key caveats in the body only.
- Including too many items.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Downstream: [BLUF Writing](../bluf-writing/SKILL.md), [Analytic Title Writing](../analytic-title-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md), [Inverted Pyramid Writing](../inverted-pyramid-writing/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Writing Patterns](../../references/shared/writing-patterns.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
