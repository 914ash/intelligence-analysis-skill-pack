---
name: research-and-collection
description: Build a disciplined evidence set without collapsing collection and judgment into the same step. Use when an agent needs to gather, log, and structure reporting before analysis.
---

# Research and Collection

## Objective
Build a disciplined evidence set without collapsing collection and judgment into the same step.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The question is clear enough to guide collection but the evidence base is incomplete.
- The next best step is to expand, clean, or structure the reporting set.
- The workflow needs a reproducible evidence ledger before analysis.

## Do Not Use When
- The evidence set is already mature and the task is synthesis.
- The main issue is source grading rather than additional collection.
- The task is only to rewrite or brief existing findings.

## Required Inputs
- Initial intelligence question or mission need
- Scope boundaries or collection constraints
- Known starting sources or leads

## Helpful Inputs
- Named entities, locations, dates, or time horizon
- Collection priorities and stop conditions
- Security, legal, or ethical constraints

## Workflow
1. Restate the question, scope, timeframe, and collection purpose.
2. Translate the question into collection sub-questions or lead types.
3. Log all retrieved material in an evidence ledger before interpretation.
4. Separate raw observations from analyst notes, inferences, and gaps.
5. Prioritize next collection steps by expected analytic value, not convenience.
6. Record collection stop conditions so the workflow does not sprawl.

## Templates To Reuse
- Use the evidence ledger row, source evaluation table, and gap register in [Templates](../../references/shared/templates.md).

## Quality Bar
- Every item should have provenance, date, and a short note on relevance.
- Duplicate reporting should be collapsed or linked, not treated as new evidence.
- Collection priorities should reflect the highest-value unknowns.
- The ledger should make later source evaluation easy.

## Common Failure Modes
- Mixing collection notes with conclusions.
- Gathering more material without improving question coverage.
- Losing provenance or timestamps.
- Treating repeated citations as corroboration.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Find Intelligence Topics](../find-intelligence-topics/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Source Evaluation](../source-evaluation/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md), [Node Link Analysis](../node-link-analysis/SKILL.md), [Delphi Method](../delphi-method/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Templates](../../references/shared/templates.md).
