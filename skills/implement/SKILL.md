---
name: implement
description: Implement an approved vertical slice or explicitly authorized group of slices using the agreed plan, practical TDD, technical review, and user-test handoffs. Use when execution is requested, rather than to create or approve product scope.
---

# Implement approved work

Use this skill in the main agent. Follow the repository's instructions and existing authorization for code, tracking, commits, PRs, deployment, and merge. A skill invocation does not approve new scope or expand permissions.

## Establish the work

Read the approved issue or specification, relevant architecture decisions, domain vocabulary, acceptance criteria, and verification approach. Use `project-planner` to reconcile current readiness and dependencies. Reuse existing approvals; resolve routine implementation choices yourself. Return consequential unresolved product or architecture choices to planning.

Implement the agreed substantial slice. An explicitly authorized group may proceed sequentially under the owner's stated boundaries. Do not treat a supplied backlog as permission to execute all of it. Use existing dependency mapping and reconciliation to identify what may continue; pause affected work when a material decision is needed and continue independent authorized work where repository limits permit.

Record the baseline revision, environment, and observable behavior before changing code, using the planned user test scenario. Work on an appropriate feature branch or isolated checkout; preserve unrelated owner edits and commit only this task's changes. Plan one PR per substantial slice.

## Implement and verify

Read and use the installed `tdd` skill where practical at the testing boundaries agreed during planning. Use one failing behavior test followed by enough implementation to pass, then repeat. Explain meaningful test-first exceptions and record alternative verification; a routine exception is not itself a request for owner approval.

Run type checks and focused tests regularly. Run the full agreed test suite at the end of the slice, plus other required repository checks. Record actual results and unavailable checks. Do not rerun broad checks without new changes or a remaining concern.

Read and use `code-review` before the final commit, including the actual working tree. Resolve defects and material requirement or standards violations, and perform appropriate in-scope refactoring during review. Recheck changed behavior and affected checks after fixes; broaden verification when their impact warrants it.

If a referenced skill is unavailable, disclose that and follow this approved procedure rather than claiming it ran: behavior-focused tests, separate requirements and standards review, resolution of technical findings, and verified user-test evidence. Do not install other workflows or invent replacement requirements automatically.

## Deliver and reconcile

Within repository authorization, commit the verified work and prepare its PR with scope, checks, and limitations. Read and use `user-qa` to provide a usable before/after comparison and short acceptance checklist. Foundational work receives technical evidence and an understandable explanation of what it enables.

Use `project-planner` to reconcile the issue, actual revision and evidence, dependencies, and next eligible work. Technical completion, owner acceptance, provider acceptance, and release readiness remain distinct. Follow the existing owner-review boundary unless continuation is explicitly authorized; presenting a slice does not establish acceptance.

The agent owns technical review and corrections. Escalate only material changes to approved behavior, scope, architecture, cost, or constraints, product-impacting tradeoffs requiring the owner, or genuinely owner-only actions. The owner reviews the user experience and progress, not source code. Specialist assistance requires a bounded concrete benefit and permitted delegation; the main agent retains responsibility.

Adapted from [Matt Pocock's implement skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md); upstream license is included in `LICENSE`.
