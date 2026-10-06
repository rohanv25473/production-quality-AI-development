---
name: code-review
description: Review a slice, branch, PR, or working tree against its requirements and repository standards, and resolve technical findings during authorized implementation. Use before delivery or when a code review is requested; owner user acceptance remains separate.
---

# Review requirements and standards

Keep two distinct review assessments: whether the implementation delivers the approved behavior, and whether it follows repository standards with maintainable structure. Neither passing assessment substitutes for the other or for owner acceptance.

## Establish the comparison

Read repository instructions, the task's issue or specification, relevant architecture decisions, and documented coding standards. Use existing tracking instructions; do not require Matt's setup skill or a particular issue-tracker file. Discover missing references from the task, PR metadata, and repository before asking the owner. If requirements remain unavailable, report that the requirements assessment cannot be completed; do not invent requirements or claim a complete delivery review.

Respect a supplied baseline. Otherwise determine it from the PR base, recorded slice baseline, or established branch context. Ask only when material ambiguity remains. Validate the reference and record the comparison being reviewed.

For committed branch work, compare the merge base with HEAD. Before committing, also inspect tracked staged and unstaged changes and relevant untracked files. Read enough surrounding code to assess behavior. An empty committed diff is not an empty review if the working tree contains implementation. Separate unrelated pre-existing owner edits from the task; do not alter or stage them.

## Perform both assessments

**Requirements:** check missing or partial acceptance criteria, incorrect behavior, regressions, and additions outside agreed scope. Link findings to the relevant requirement and concrete code or observable evidence. Inspect verification evidence rather than assuming passing tests prove every criterion.

**Standards:** apply documented repository rules and relevant architecture boundaries. Assess naming, duplication, scattered responsibilities, excessive coupling, and speculative abstractions as maintainability heuristics. A heuristic is not automatically a violation and documented project choices override it. Use tooling results rather than duplicating format or lint checks manually.

The main agent normally performs both assessments. Use a specialist only when a bounded independent assessment has a concrete expected benefit and delegation is permitted. Explain the benefit, provide the comparison and governing sources, and assign read-only review ownership. Do not require two parallel agents for every slice. The main agent checks returned evidence and resolves technical disagreements.

## Resolve findings

Within authorized implementation, fix defects, unmet acceptance criteria, and material violations of agreed technical constraints before declaring the slice ready for user review. Add a reproducing test where practical. Make small behavior-preserving refactors within scope, then rerun affected checks. Reassess changed areas after repairs; broaden verification when impact warrants it.

For a review-only request, report findings without changing code unless fixes were authorized. Optional improvements outside the slice are proposals and do not delay delivery. Do not widen the task into a cleanup project.

Escalate only when resolution requires changing approved behavior, scope, consequential architecture, cost, or constraints; an owner decision about a material product limitation; or an action only the owner can perform. Continue eligible independent authorized work where allowed. A technical disagreement between agents is not itself an owner decision.

## Report the outcome

Record separate requirements and standards outcomes, important findings and their resolution, comparison/revision, checks, and limitations in the existing issue or PR. Label self-review accurately; specialist review is not the owner's approval.

Give the owner a concise delivery status and only decisions requiring their involvement. Source-code inspection and adjudicating technical comments are agent responsibilities. Use `user-qa` for the user-test handoff during delivery. Do not mark owner acceptance, close acceptance-dependent issues, or bypass repository merge rules.

Adapted from [Matt Pocock's code-review skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/code-review/SKILL.md); upstream license is included in `LICENSE`.
