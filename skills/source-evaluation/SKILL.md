---
name: source-evaluation
description: Assess source reliability, information credibility, corroboration, access, and bias. Use when an agent must decide how much weight to place on reporting before using it in analysis.
---

# Source Evaluation

## Objective
Score reporting discipline before any substantive judgment leans on it.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Evidence ledger or source list
- Source provenance
- Any corroborating or contradicting reporting

## Workflow
1. Separate source reliability from information credibility.
2. Assess access, recency, motive, track record, and possible deception incentives.
3. Check whether the claim is first-hand, second-hand, or inferred.
4. Record corroboration level and what would materially upgrade or downgrade confidence.
5. Return source weights the next skill can actually use.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Source-by-source assessment; Weighting guidance; Upgrade or downgrade triggers
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md)

## Shared Doctrine
Read and apply: [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Confidence Language](../../references/shared/confidence-language.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
