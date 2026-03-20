---
name: analytic-title-writing
description: Write precise, informative titles for intelligence products. Use when a memo, brief, or note needs a title that states the subject and angle without hype.
---

# Analytic Title Writing

## Objective
Give the product a title that signals subject, angle, and stakes cleanly.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Topic
- Main judgment or angle
- Audience and formality level

## Workflow
1. Name the actor, issue, or event directly.
2. Signal the analytic angle rather than a generic topic area.
3. Avoid vague labels, clickbait phrasing, and overclaiming.
4. Offer a few title variants when the angle could be framed differently.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Recommended title; Optional alternates by tone or specificity
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [BLUF Writing](../bluf-writing/SKILL.md)
- Downstream: none; this skill is usually the last step.
- Companions: [What / So What Statement](../what-so-what-statement/SKILL.md)

## Shared Doctrine
Read and apply: [Writing Patterns](../../references/shared/writing-patterns.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
