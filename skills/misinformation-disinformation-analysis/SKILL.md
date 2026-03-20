---
name: misinformation-disinformation-analysis
description: Evaluate whether reporting, narratives, or artifacts show signs of misinformation, disinformation, manipulation, or coordinated influence. Use when deceptive or contaminated information may distort analysis.
---

# Misinformation and Disinformation Analysis

## Objective
Detect distortion risks before they contaminate the analytic picture.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Narrative, claim set, or media artifact
- Source provenance
- Context on likely actors or incentive structures

## Workflow
1. Identify the central claims, emotional triggers, and intended audience.
2. Check provenance, timing, consistency, and signs of coordinated amplification.
3. Compare the narrative to known facts, omissions, and alternative framings.
4. Assess whether the issue is error, rumor, propaganda, or deliberate deception.
5. Explain how contamination should affect downstream analytical confidence.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Manipulation-risk assessment; Claim-level concerns; Impact on source weighting and analytic use
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Source Evaluation](../source-evaluation/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
